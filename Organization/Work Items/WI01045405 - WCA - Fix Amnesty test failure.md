amnesty

# Fix: Intermittent SSL Certificate Hash Mismatch in TestInstallIsSuccessful

## Symptoms

`WebInstallerTestBase.TestInstallIsSuccessful` fails intermittently on CI with:

```
Assert.That(httpsBinding.CertificateHash, Is.EqualTo(certificateWithLongestExpiry!.GetCertHash()))

Expected and actual are both <System.Byte[20]>
  Values differ at index [0]
  Expected: 105
  But was:  98
```

The test expects IIS to have one certificate bound, but IIS has a different one.

## Underlying Problem

The **installer** and the **test** used different certificate matching strategies:

| | Installer (`PatchIISWebSiteAndScomRegistry.ps1`) | Test (`FindCertifiateWithLongestExpiry`) |
|---|---|---|
| **Match type** | Exact: `$_.Subject -eq "CN=$SslCertificateName"` | Substring: `X509FindType.FindBySubjectName` |
| **Effect** | Only matches certs whose full Subject is exactly `CN=hostname` | Matches any cert whose Subject *contains* the hostname |

When a CI machine's certificate store contains a multi-CN certificate (e.g. a self-signed
test cert) whose Subject includes the hostname as a substring, the test's broader match
picks it up while the installer's exact match does not.

If that extra certificate happens to have a later expiry, the test selects it as the
"longest expiry" cert and expects IIS to have it bound — but IIS correctly has the real
machine cert (selected by the installer's exact match).

## Proof

Diagnostic logging on the failing CI server (`A2DAT058-DAT23`) revealed two matching
certificates:

```
Subject='CN=A2DAT058-DAT23.sand.wtg.zone'
  NotAfter=2027-03-02  Hash=BAB19A5C...  ExactCNMatch=True   ← installer picks this

Subject='CN=WTG Tests Self-Signed, CN=localhost, CN=A2DAT058-DAT23, CN=A2DAT058-DAT23.sand.wtg.zone'
  NotAfter=2027-03-09  Hash=A9C8F2BA...  ExactCNMatch=False  ← test picked this (longer expiry)
```

The self-signed test certificate has a later expiry (March 9 vs March 2) and its Subject
contains the hostname as a substring. `FindBySubjectName` matched it, the test selected
it as "longest expiry", but the installer never considered it because its full Subject
doesn't equal `CN=A2DAT058-DAT23.sand.wtg.zone`.

The failure is **intermittent** because this self-signed certificate is only present on
some CI machines in the pool.

## Fix

Updated `FindCertifiateWithLongestExpiry` in `WebInstallerTestBase.cs` to use exact
Subject matching, mirroring the installer's PowerShell logic:

**Before** (substring match via `FindBySubjectName`):
```csharp
var validCertificates = certificateStore.Certificates
    .Find(X509FindType.FindBySubjectName, certificateName, validOnly: false)
    .Find(X509FindType.FindByApplicationPolicy, "1.3.6.1.5.5.7.3.1", validOnly: false);
```

**After** (exact match on `CN=hostname`):
```csharp
var exactSubject = $"CN={certificateName}";
foreach (var cert in certificateStore.Certificates)
{
    if (!string.Equals(cert.Subject, exactSubject, StringComparison.OrdinalIgnoreCase))
        continue;
    if (!cert.EnhancedKeyUsageList.Any(eku => eku.Value == "1.3.6.1.5.5.7.3.1"))
        continue;
    // ... pick longest expiry
}
```

Also removed:
- Diagnostic `Assert.Fail` and `StringBuilder` logging from `AssertSSLCertification`
- Redundant duplicate call to `FindCertifiateWithLongestExpiry`
