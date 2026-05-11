
## Description:

#### RELATED INCIDENTS:

CS02323076 — SCOM:SAND-WTG ORC WebEndPoint Status Monitor: Failure (WISGLOSYD, 2026-04-29, Working)
#### BACKGROUND/CONTEXT:

PRC Orc currently treats any SQL exception raised while checking the database upgrade applock as a Cw1DatabaseUpgradeLockException `(note: we confirmed this is true, located at file "C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.ProcessControllerOrchestrator.git\Source\Common\DataLayer\DataAccess.cs")`. 

As a result, databases that do not exist, or databases that exist but are temporarily unavailable, can be surfaced as database lock errors in logs, customer resolution, and SCOM / Orc status monitoring.

*Sample Logs*

```

## Alert Title :
SAND-WTG ORC WebEndPoint Status Monitor: Failure

## Object Name
au2sp-torc-401.sand.wtg.zone//InternalSand.Orc//InternalSand.Orc

## Time Raised
[0] 30/04/2026 05:59:16 AUS Eastern Standard Time

## Alert Description
{
  "Category": "Error",
  "Details": [
    {
      "Category": "Error",
      "Name": "WiseCloudOrchestrator.Common.Exceptions.Cw1DatabaseUpgradeLockException", <-- here
      "Desc": "Application could not query database upgrade lock for au2sp-tsql-403.sand.wtg.zone\\INSTANCE1 SH0WI00957791",
      "DetailDescription": "au2sp-tsql-403.sand.wtg.zone\\INSTANCE1 SH0WI00957791"
    },
    {
      "Category": "Error",
      "Name": "WiseCloudOrchestrator.Common.Exceptions.Cw1DatabaseUpgradeLockException",
      "Desc": "Application could not query database upgrade lock for au2sp-tsql-408.sand.wtg.zone\\INSTANCE1 SH0WI00956082",
      "DetailDescription": "au2sp-tsql-408.sand.wtg.zone\\INSTANCE1 SH0WI00956082"
    },
    
    ...
    
```

This was observed in CS02323076 (`see above`), where multiple databases that could not be queried were reported through the ORC WebEndPoint status monitor as upgrade lock exceptions, even though the underlying problem was not necessarily a real database upgrade lock (`TOOD: what was it? Note that this doesn't really matter.`).

The expected behaviour is to reserve the upgrade lock path for genuine applock conflicts only. When the target database does not exist, ORC should surface a clear "does not exist" message. When the target database exists but is not accessible, for example OFFLINE, RECOVERING, or RESTORING, ORC should surface a clear "database is unavailable" message that includes the current database state.

This change improves diagnostic accuracy, reduces false positive DB lock alerts, and makes triage easier for Cloud / IS teams by exposing the actual failure reason instead of a misleading lock error.

#### DONE STATEMENTS:

1. ORC no longer reports a missing database as a Cw1DatabaseUpgradeLockException or generic database lock error.

2. ORC returns an explicit application instance error when the target database does not exist.

3. ORC returns a Cw1ApplicationDatabaseUnavailableException when the target database exists but is not in ONLINE state, including the current database state in the message.

4. ORC continues to treat a real APPLOCK_TEST conflict as a genuine database upgrade lock.

5. Resolver continues to add upgrade-related database unavailability to the environment error cache, while preserving a specific unavailable-state message for non-lock scenarios.

6. Tests have been added or updated to cover missing database behaviour, unavailable database behaviour, the new exception path, and resolver cache handling.
