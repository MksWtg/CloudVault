# Intermittent Test Error Analysis
## Method: `LoginWithCorruptedCacheDisplaysErrorMessageInConnectionLogs`

---

## Error 1 — Failed to initialize BackendPassword

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: Failed to initialize BackendPassword at https://A2DAT031-DAT27:60051/` |
| **Throwing line** | `WiseCloudClientServerTestBase.cs:605` — `Assert.Fail($"Failed to initialize {serviceType} at {baseUrl}")` |
| **Root cause** | `WaitForInitialization` polled `wtg/status` with at most **10 retries × 1 s sleep = ~10 s total wait**. On a loaded CI machine, the freshly-installed IIS-hosted BackendPassword service takes longer than 10 s to finish its ASP.NET startup sequence and begin returning a non-"initializing" status response. |
| **Fix** | **Already fixed in this session.** Retries increased from 10 → 60 (≈60 s total), `HttpClient.Timeout` set to 10 s per request, and `TaskCanceledException` caught so a slow/hung HTTP call doesn't unwind the retry loop. |
| **Explanation of fix** | CI machines are slower and busier. 60 s gives the server a realistic window to finish its startup. The explicit per-request timeout prevents the default 100-second `HttpClient` timeout from consuming multiple retries on a single stalled connection. |
| **How it happened on CI** | The CI agent was under load (e.g. concurrent test suites, background Windows Installer activity, or a slow disk). The BackendPassword service wasn't ready within the previous ~10 s budget. |
| **Reproducible locally?** | Unlikely under normal conditions. To force it: lower the retry count back to 2 and run the test on a machine with high CPU load, or insert a breakpoint between MSI install and the polling loop to simulate a startup delay. |

---

## Error 2 — Installed Site UTBackend… was not started

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: Installed Site UTBackendb0492845-… was not started. Assert.That(isStarted, Is.True)` |
| **Throwing line** | `WiseCloudClientServerTestBase.cs:597` — `Assert.That(isStarted, Is.True, ...)` |
| **Root cause** | After a successful MSI install (exit code 0), the code polls `serverManager.Sites` for up to **11 iterations × 5 s sleep = ~55 s** to see `ObjectState.Started`. On a busy CI machine IIS may be slow to start the application pool / site — or the site may be stuck in `Stopped`/`Unknown` because the app pool failed to start (e.g. credential error, missing dependency, or an IIS reset in-flight). |
| **Fix** | No code change made. The 55 s budget is reasonable. The deeper cause is likely transient CI load or an intermittent app pool startup failure. Adding diagnostics (logging the site `ObjectState` and app pool state on each iteration) would improve future investigation but won't prevent the failure. If this recurs frequently, increasing the iteration count or polling interval would help. |
| **How it happened on CI** | IIS was under load (another test suite installing/starting its own sites simultaneously), causing the Windows Process Activation Service (WAS) to take longer than 55 s to spin up the application pool. |
| **Reproducible locally?** | Hard to reproduce reliably. You could try starting several IIS-based installs simultaneously, or deliberately misconfigure the app pool identity to cause a startup failure and observe the same assertion. |

---

## Error 3 — MSI exit code 1618 (Another installation in progress)

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: Failed to install BackendPassword server MSI. Exit code: 1618 … MainEngineThread is returning 1618` |
| **Throwing line** | `WiseCloudClientServerTestBase.cs:577` — `Assert.Fail(BuildMsiInstallFailureMessage(...))` |
| **Root cause** | Windows Installer error 1618 = `ERROR_INSTALL_ALREADY_RUNNING`. The test waits up to **1 minute** for the `Global\_MSIExecute` mutex via `WaitForMsiExecutionMutexAvailable`, then launches `msiexec.exe`. There is a classic **TOCTOU race**: the mutex appears free when polled (using `mutex.WaitOne(0)` in the test process), but another `msiexec` invocation — from a parallel test fixture or a system process (Windows Update, antivirus, etc.) — acquires the mutex in the ~0 ms gap before our `msiexec` gets a chance to. The MSI log confirms this: msiexec started at `18:04:32:739` and returned 1618 at `18:04:32:757` (18 ms) — it entered the engine but immediately found the mutex held. |
| **Fix** | Retry the MSI install when `exitCode == 1618`. `RunMsiInstallAttempt` currently runs once. Adding a retry loop (e.g. up to 3 attempts, each waiting for the mutex again) eliminates the TOCTOU window. Alternatively, increase `MsiExecutionMutexWaitTimeout` from 1 minute to 3–5 minutes to reduce the probability of a timeout-induced gap, but this doesn't eliminate the race. A retry is the proper fix. |
| **Explanation of fix** | 1618 is a well-known transient condition. Microsoft documentation explicitly recommends retrying on 1618. The existing `WaitForMsiExecutionMutexAvailable` logic already demonstrates intent to handle concurrent installs; the retry closes the TOCTOU window. |
| **How it happened on CI** | A parallel job on the same CI agent (a different test fixture, a Windows Installer scheduled task, or CI tooling itself) was holding the `_MSIExecute` mutex when our install was launched. |
| **Reproducible locally?** | Yes. Run two test fixtures that each call `SetupAWiseCloudServer` at the same time (e.g. start two test runs in parallel). One will likely get 1618 on the first install. Alternatively, manually hold the mutex in a small program while running the test. |

---

## Error 4 — Installed Site UTFrontend… was not started

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: Installed Site UTFrontenda3fc7b97-… was not started. Assert.That(isStarted, Is.True)` |
| **Throwing line** | `WiseCloudClientServerTestBase.cs:597` (via `SetupAWcaServer` → `SetupAWiseCloudServer`) |
| **Root cause** | Identical to Error 2 but for the Frontend (WiseCloudAccessorServer) site. |
| **Fix** | Same as Error 2. No code change made. |
| **How it happened on CI** | Same as Error 2. Backend and Frontend sites are installed sequentially in `OneTimeSetUp`; by the time the Frontend install runs, IIS may be under additional load from the already-running Backend and BackendPassword sites. |
| **Reproducible locally?** | Same as Error 2. |

---

## Error 5 — SSL certificate expired during test run

| Field | Detail |
|---|---|
| **Error** | `Assert.That(cacheFileExists, Is.True) … Connection info: Certificate error … NotBefore=2026-05-18 20:44:43Z; NotAfter=2026-05-18 22:49:43Z; ChainStatus=[NotTimeValid]` |
| **Throwing line** | `WiseCloudClientServerTest.cs:97` — `Assert.That(cacheFileExists, Is.True, ...)` |
| **Root cause** | `TestCertificate` creates self-signed certs with only a **2-hour validity window** (`DateTimeOffset.UtcNow.AddHours(2)` at `TestCertificate.cs:70`). The cert is created during `OneTimeSetUp` and its thumbprint is bound to the IIS site. If the total test suite run time from `OneTimeSetUp` through to this specific test exceeds **~105 minutes** (2 h minus the 15-minute `MinimumReusableLifetime` buffer), the cert bound in IIS has expired. `GetCert()` would issue a new cert, but the IIS binding still points to the old expired thumbprint — the server keeps serving the stale cert and the client gets `NotTimeValid`. |
| **Fix** | Increase the certificate validity period in `TestCertificate.cs` from `AddHours(2)` to a longer duration such as `AddHours(24)`. This gives a full day's buffer, making expiry during a CI run essentially impossible. The 15-minute `MinimumReusableLifetime` threshold ensures slightly-stale certs are still regenerated well before expiry. |
| **Explanation of fix** | The 2-hour window was probably chosen to limit how long a leaked test cert stays valid. 24 hours is still short enough to avoid long-lived test certificate concerns while eliminating the race between cert expiry and test execution time. |
| **How it happened on CI** | The CI agent was slow, queued, or had a long test suite ahead of this fixture. By the time the seed login ran (line 87), the cert installed during `OneTimeSetUp` had been valid for >2 hours and the SSL handshake failed. |
| **Reproducible locally?** | Yes. Change `AddHours(2)` to `AddMinutes(3)` temporarily, run the full fixture, wait 3 minutes, then run the `LoginWithCorruptedCacheDisplaysErrorMessageInConnectionLogs` test specifically. The seed login will fail with the same SSL error. |

---

## Error 6 — Batch timeout (5 minutes)

| Field | Detail |
|---|---|
| **Error** | `The tests in the batch did not complete within the total batch timeout period of 00:05:00 … Process msiexec Not a .NET process` |
| **Throwing line** | Imposed by the CI batch runner, not by test code. |
| **Root cause** | A consequence of errors 2, 3, or 4. The `OneTimeSetUp` installs three MSIs sequentially; if any single install is slow (e.g. waiting 60 s for the `_MSIExecute` mutex + up to 180 s for msiexec itself + 55 s site-start polling) the total can exceed 5 minutes before a single test has run. The `msiexec` process visible in the dump confirms the batch timed out while an MSI was still running. |
| **Fix** | No direct fix. Fixing errors 3 (MSI 1618 retry) and ensuring servers start reliably (errors 2/4) reduces the average `OneTimeSetUp` time. If errors 2/4/3 are rare after those fixes, the 5-minute batch timeout should not be hit. If CI still times out, the batch timeout itself may need to be raised. |
| **How it happened on CI** | The combination of slow CI agent + mutex contention on Windows Installer pushed `OneTimeSetUp` past the 5-minute mark. |
| **Reproducible locally?** | Difficult to reproduce the exact timeout boundary, but triggering error 3 (run concurrent MSI installs) will cause similar delays. |

---

## Error 7 — Failed to download MSI from Chocolatey: 503 Service Unavailable

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: System.IO.FileNotFoundException : Failed to download MSI from Chocolatey: WiseCloudClient v6.5.18482 … Status: 503 Service Unavailable` |
| **Throwing line** | Thrown in `VersionedArtifactManager.GetHistoricalInstallerMsiPath` (wraps the `FileNotFoundException`). The underlying 503 comes from `DownloadPackageFromFeed` after exhausting retries. |
| **Root cause** | The internal ProGet server (`proget.wtg.zone`) returned 503 (Service Unavailable). `DownloadPackageFromFeed` uses `ExecuteWithRetry` (7 attempts, 503 is in `transientStatusCodes`), so it already retried. ProGet was unavailable for longer than the retry window. This is an **external infrastructure failure** — entirely outside the test code's control. |
| **Fix** | No code change warranted for this specific failure. The retry logic is already correct. If this recurs frequently, consider increasing `DefaultMaxRetryAttempts` or the retry delay, or adding an alert/skip mechanism to mark tests as inconclusive rather than failed when ProGet is down. |
| **How it happened on CI** | ProGet was in a brief maintenance window, overloaded, or experiencing a transient outage at the time the CI run tried to download the historical MSI. |
| **Reproducible locally?** | Only if ProGet is genuinely unavailable. You can simulate it by pointing `ChocolateySourceUrl` at a local server that returns 503. |

---

## Error 8 — Failed to retrieve version list for cargowisecloudclient-prod: 503

| Field | Detail |
|---|---|
| **Error** | `OneTimeSetUp: System.Web.HttpException : Failed to retrieve version list for cargowisecloudclient-prod … Status: 503 Service Unavailable` |
| **Throwing line** | Thrown inside `VersionedArtifactManager.FetchAvailableClientVersions` after `ExecuteWithRetry` exhausts its 7 attempts. |
| **Root cause** | Same as Error 7 — ProGet returned 503 for the version index endpoint (`/v3/flatcontainer/cargowisecloudclient-prod/index.json`). `FetchAvailableClientVersions` is wrapped in `ExecuteWithRetry` and 503 is a recognised transient status code, so retries happened and all failed. **External infrastructure failure.** |
| **Fix** | Same as Error 7. No code change warranted. |
| **How it happened on CI** | Same as Error 7. |
| **Reproducible locally?** | Same as Error 7. |

---

## Summary of Actions

| Error                                   | Action                                                                                                  | Status                  |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------- |
| Error 1 — BackendPassword init timeout  | Increase `WaitForInitialization` retries 10→60, add `HttpClient.Timeout`, catch `TaskCanceledException` | ✅ Fixed in this session |
| Error 2 — Backend site not started      | No code change; 55 s poll budget is reasonable. Better diagnostics would help triage recurrence         | ⚠️ Needs monitoring     |
| Error 3 — MSI exit code 1618            | Retry MSI install when exit code is 1618                                                                | 🔧 Fix needed           |
| Error 4 — Frontend site not started     | Same as Error 2                                                                                         | ⚠️ Needs monitoring     |
| Error 5 — SSL cert expired during test  | Increase cert validity from 2 h to 24 h in `TestCertificate.cs:70`                                      | 🔧 Fix needed           |
| Error 6 — Batch timeout                 | Consequence of other errors; resolving errors 3/2/4 reduces risk                                        | ⚠️ Dependent on above   |
| Error 7 — Chocolatey 503 (download)     | Transient ProGet outage; retry logic already in place                                                   | ✅ Already handled       |
| Error 8 — Chocolatey 503 (version list) | Transient ProGet outage; retry logic already in place                                                   | ✅ Already handled       |
