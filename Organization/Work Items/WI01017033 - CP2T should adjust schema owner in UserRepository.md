
What do we have to do?

Existing notes:

```
YR 15-Jan-26 11:00 GMT+11:00:

  

CP2T restores UserRepository db and preserves schema ownership (user mapped to login); however, it should reassign schema owners otherwise we end up with schemas owned by non-existent/out-of-scope users.

  

EnsureDbLoginsCorrectlyMappedToAllDatabases() currently helps create/match logins/users but it does not alter schema ownership.

  

CW9 04-Mar-26 13:48 GMT+11:00:

Investigation

- It's CargoWise created those user logins
- CP2T restore those logins settings directly from User Repository backup but didn't create and adjust to corresponding restored database name to EnterpriseDbUser logins.
- SQL Server logins for EnterpriseDbUser of new test Customer System is not exists after we copy production to the test customer system

Reproduce and Manual test

- Use CWTool to download the latest version of CargoWise
- Open a powershell and Change dir to C:\git\GitHub\WiseTechGlobal\CargoWise\Bin\net8.0\
- Run .\Generator.exe . {DatabaseNameYouPrefer} -restoredb
- Open CargoWise with the database you just create, wait for upgrade, this will take a while
- Create a new staff with IsDatabaseDevelpoer ticked
- Close CargoWise
- Insert a Production License to {DatabaseNameYouPrefer}.dbo.StmData
- Backup it with DBBR
- Restore with CP2T to another database name, you can see the corresponding login related to the database you just restore does not exist

Solution

- For new testing customer system
    - delete logins not matched for each database
    - create EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName} logins on sql server level and set corresponding permission with random password
    - add EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName} logins on database level and set corresponding permission
- For existing testing customer system
    - only create EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName} logins that not exist on sql server and set corresponding permission with random password
    - only add EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName} logins logins that not exist on database level and set corresponding permission
```

- CP2T restores UserRepository db and preserves schema ownership (the database principle that owned the production DB schema also owns the test DB schema). Instead it should reassign schemas to the relevant one.


## Questions
Is DBBR just a wrapper around SQL Server backup??


## Manual Test

```
Reproduce and Manual test

- Use CWTool to download the latest version of CargoWise [DONE]
- Open a powershell and Change dir to C:\git\GitHub\WiseTechGlobal\CargoWise\Bin\net8.0\ [DONE]
- Run .\Generator.exe . {DatabaseNameYouPrefer} -restoredb [DONE]
- Open CargoWise with the database you just create, wait for upgrade, this will take a while [DONE]
- Create a new staff with IsDatabaseDevelpoer ticked [DONE]
- Close CargoWise [DONE]
- Insert a Production License to {DatabaseNameYouPrefer}.dbo.StmData
- Backup it with DBBR
- Restore with CP2T to another database name, you can see the corresponding login related to the database you just restore does not exist
```

Run this command to run cargowise connecting to `Odyssey` DB:
`C:\git\GitHub\WiseTechGlobal\CargoWise\Bin\CargoWiseOneAnyCpu.exe . Odyssey2`