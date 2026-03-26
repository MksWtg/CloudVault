
What do we have to do?

Existing notes:

```
YR 15-Jan-26 11:00 GMT+11:00:

  

CP2T restores UserRepository db and preserves schema ownership (user mapped to login); however, it should reassign schema owners otherwise we end up with schemas owned by non-existent/out-of-scope users.

  

EnsureDbLoginsCorrectlyMappedToAllDatabases() (outside of this repo, in cargowise) currently helps create/match logins/users but it does not alter schema ownership.

  

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
- Insert a Production License to {DatabaseNameYouPrefer}.dbo.StmData [DONE]
- Backup it with DBBR [DONE]
- Restore with CP2T to another database name, [DONE] you can see the corresponding login related to the database you just restore does not exist [???]
```

Run this command to run cargowise connecting to `Odyssey` DB:
`C:\git\GitHub\WiseTechGlobal\CargoWise\Bin\CargoWiseOneAnyCpu.exe . Odyssey2`


## Reframing

CP2T (copy production to test, a subset of the DbBackupAndRestore tool) restores the UserRepository database and preserves schema ownership (user mapped to login); however, it should reassign schema owners otherwise we end up with schemas owned by non-existent/out-of-scope users.

EnsureDbLoginsCorrectlyMappedToAllDatabases() (a method in cargowise, outside of this repo) currently helps create/match logins/users but it does not alter schema ownership.


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

I don't understand this. Can you explain 1) what the problem is, 2) how I can verify this for the production and test database with an SQL query?

## Technical Terms

**Principal**: A security identity (user, role, or application) in SQL Server that can be granted permissions to access database objects.

**Login**: A server-level account used to authenticate and allow access to a SQL Server instance.

**Users**: Database level

**Schema Owner**: The principal that owns a schema and has full control over all objects within that schema.

**Database owner**: server level login that owns the database. In the database this appears as the dbo user.

**dbo**: in sql server, this stands for database owner and is a special built in user account. it is also the default schema for all new objects in a database.


Few loose work items:
- fixed failing tests and resubmit
- compilign information for louise for 

```
CP2T is a tool within database backup and restore (DBBR) to copy a production database and change some things to make a test database.

CP2T restores UserRepository db and preserves schema ownership (user mapped to login); however, it should reassign schema owners otherwise we end up with schemas owned by non-existent/out-of-scope users.

  

EnsureDbLoginsCorrectlyMappedToAllDatabases() (outside of this repo, in cargowise) currently helps create/match logins/users but it does not alter schema ownership.


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

# Solutions

### Goals:
For new testing customer system
    - delete logins not matched for each database
    - create `EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName}` logins on SQL server level and set corresponding permission with random password
    - add `EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName}` logins on database level and set corresponding permission
- For existing testing customer system
    - only create `EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName}` logins that not exist on SQL server and set corresponding permission with random password
    - only add `EnterpriseDbUser_{TestCustomerSystemMainDatabaseName}_{UserName}` logins logins that not exist on database level and set corresponding permission

## Yash's OG PR

https://github.com/WiseTechGlobal/CargoWise/pull/33986

### Changes:

Add the following methods

```
void FixSchemaOwnershipForUserRepositoryDatabase(AdminConnection mainDbConnection, DbRestoreSettings dbRestoreSettings)
		{
			if (!dbRestoreSettings.RestoreUserRepositoryDatabase)
			{
				return;
			}

			var userRepoDbNames = dbRestoreSettings.RestoreDbFiles
				.Cast<DbFileInfo>()
				.Where(f => f.Visible)
				.Where(f => f.DbType == DbFileInfo.DbTypeUserRepository)
				.Select(f => GetActualDatabaseName(dbRestoreSettings.TargetDbName, f))
				.Distinct(StringComparer.OrdinalIgnoreCase)
				.ToList();

			foreach (var dbName in userRepoDbNames)
			{
				FixSchemaOwnershipForUserRepositoryDb(mainDbConnection.ServerName, dbName);
			}
		}

		void FixSchemaOwnershipForUserRepositoryDb(string serverName, string userRepositoryDbName)
		{
			try
			{
				using (Db.DisableSchemaVersionCheck())
				using (var connection = Db.NewAdminConnection(serverName, userRepositoryDbName))
				{
					if (!connection.DatabaseExists(userRepositoryDbName))
					{
						FireOnShowInfoMessage($"Skipping schema ownership fix. Database does not exist: {userRepositoryDbName}");
						return;
					}

					var targetAppPrincipal = ResolveTargetApplicationDbPrincipal(connection, userRepositoryDbName);
					if (string.IsNullOrWhiteSpace(targetAppPrincipal))
					{
						FireOnShowInfoMessage($"Schema ownership: skip (target app principal not found) for {userRepositoryDbName}");
						return;
					}

					FireOnSubtaskStarted($"Normalising UserRepository schemas to '{targetAppPrincipal}' in {userRepositoryDbName}", 0);
					NormaliseEnterpriseDbUserSchemaOwners(connection, targetAppPrincipal);
				}
			}
			catch (Exception ex) when (!ex.IsCriticalException())
			{
				LogDetailedError(ex, $"Schema ownership: failed for {userRepositoryDbName}");
			}
		}

		static string ResolveTargetApplicationDbPrincipal(AdminConnection conn, string userRepositoryDbName)
		{
			// TEMPORARY - ideally, the target principal should be determined based on the actual application pool identity used to connect to the User Repository database in the test environment, but for now, we resolve it based on the existing principals in the database.
			// Need to look into CargoWise.Data code to find a more reliable way to determine the target principal that should own the schemas in the User Repository database in test environments.

			const string sql = @"
SELECT TOP (1) dp.name
FROM sys.database_principals dp
JOIN sys.server_principals sp ON sp.sid = dp.sid
WHERE dp.type IN ('S','U')
  AND dp.name LIKE 'EnterpriseDbUser[_]%' ESCAPE '\'
ORDER BY dp.name;";

			return conn.ExecuteScalar<string>(sql);
		}

		static void NormaliseEnterpriseDbUserSchemaOwners(AdminConnection conn, string targetAppPrincipal)
		{
			const string sql = @"
DECLARE @Target sysname = @TargetUser;
DECLARE @Sql nvarchar(max) = N'';

;WITH SchemasToFix AS
(
	SELECT s.name AS SchemaName, dp.name AS OwnerName
	FROM sys.schemas s
	JOIN sys.database_principals dp ON dp.principal_id = s.principal_id
	WHERE s.name NOT IN ('dbo','guest','INFORMATION_SCHEMA','sys','cdc')Expand commentComment on line R1118Resolved
	  AND s.schema_id < 16384
)
SELECT @Sql = @Sql + N'
ALTER AUTHORIZATION ON SCHEMA::' + QUOTENAME(SchemaName) + N' TO ' + QUOTENAME(@Target) + N';'
FROM SchemasToFix
WHERE OwnerName LIKE 'EnterpriseDbUser[_]%' ESCAPE '\'
  AND OwnerName <> @Target;

IF (@Sql <> N'')
BEGIN
	EXEC sp_executesql @Sql;
END
";
			conn.ExecuteNonQuery(sql, cmd => cmd.AddParameter("@TargetUser", SqlDbType.NVarChar, 128, targetAppPrincipal));
		}
```

Methods added:
- `FixSchemaOwnershipForUserRepositoryDatabase`
- `FixSchemaOwnershipForUserRepositoryDb`
- `ResolveTargetApplicationDbPrincipal`
- `NormaliseEnterpriseDbUserSchemaOwners`

This method was augmented to add the new funvtion call:

```
rotected virtual void PerformCopyProductionToTestPostRestoreSteps(AdminConnection connection, DbRestoreSettings dbRestoreSettings, string vaultAuxDbName, bool isNewTestDb)
		{
			if (dbRestoreSettings.RestoreOption != DbRestoreOption.CopyProdToTest)
			{
				return;
			}

			var licence = new LicenceBuilder();
			try
			{
				HandleS3AccessKeySetup(connection, dbRestoreSettings, vaultAuxDbName, isNewTestDb, licence);
			}
			finally
			{
				ClearProductionInfoFromTestSystem(connection, dbRestoreSettings, vaultAuxDbName);
				AdjustCompanyLicensesForTestSystem(connection, dbRestoreSettings, vaultAuxDbName, isNewTestDb, licence);
				CopyAuxiliaryDataToTestDatabase(connection, dbRestoreSettings, vaultAuxDbName, isNewTestDb);
				FixSchemaOwnershipForUserRepositoryDatabase(connection, dbRestoreSettings);
			}
		}
```
## New PR



# Important Note

In SQL Server, schemas are owned by USERS, this is a per database thing (not per server).

Here is query to find all users for a db:

```
SELECT 
    name AS user_name,
    type_desc AS user_type,
    authentication_type_desc,
    create_date,
    modify_date
FROM sys.database_principals
WHERE type IN ('S', 'U', 'G', 'E', 'X')  -- SQL user, Windows user, group, external user/group
ORDER BY name;
```

For: `Odyssey2` we have: `EnterpriseDbUser_Odyssey2_mukund1234` (corresponds to created db person staff in CW)

For `Odyssey2_UserRepository` we have: `EnterpriseDbUser_Odyssey2_mukund1234` (same)

For: `O2_RestoredDb` we have: `EnterpriseDbUser_Odyssey2_mukund1234` (same)

For: `O2_RestoredDb_UserRepository` we have: `EnterpriseDbUser_Odyssey2_mukund1234` (same)

---

But we don't want this, we want (for example) `EnterpriseDbUser_O2_RestoredDb_mukund1234`.

**Question**: Is this just a naming error or does it actually prevent anything?

```
In SQL Server, a **principal** is any security identity—such as a login, database user, or role—that can own objects or be granted permissions.
```

To see PR comparison, look at [[CP2T PR Comparison]]

Yash:
https://github.com/WiseTechGlobal/CargoWise/pull/33986

Mks:
https://github.com/WiseTechGlobal/CargoWise/pull/43392

```
-- EXEC xp_cmdshell 'dir \\uat-backups.wtg.zone\SQL_Backup\CargoWiseCloud\DBBR\WI01017033';
-- EXEC xp_cmdshell 'ipconfig';
-- EXEC xp_cmdshell 'ping uat-backups.wtg.zone';
-- EXEC xp_cmdshell 'mkdir C:\temp\WI01017033';

-- EXEC xp_cmdshell 'copy /Y \\uat-backups.wtg.zone\SQL_Backup\CargoWiseCloud\DBBR\WI01017033\* C:\temp\WI01017033\';
-- EXEC xp_cmdshell 'dir C:\temp\WI01017033\'
```

If i take an SQL server database backup with the DB schema owned by a user, and the user corresponding to a login in that server, and then i restore the db to another server that is missing the login, what will happen to the login, user and schema?


```SQL
-- declare a variable named @Target and set the data type to sysname and initialize it with the value of @TargetUser
DECLARE @Target sysname = @TargetUser;

-- declare a variable named @Sql and set the data type to nvarchar(max) and initialize it with the value of N'' (empty unicode string)
DECLARE @Sql nvarchar(max) = N'';

;WITH SchemasToFix AS -- named result set, selects all the schemas (from sys schemas) and owners (from database principles) where the schema owner matches database principle, excluing the default schemas

-- in english: the schemas we want to modify are all those that are not default
(
	SELECT s.name AS SchemaName, dp.name AS OwnerName
	FROM sys.schemas s
	JOIN sys.database_principals dp ON dp.principal_id = s.principal_id
	WHERE s.name NOT IN ('dbo','guest','INFORMATION_SCHEMA','sys','cdc')
		AND s.schema_id < 16384
)

-- this part modifies the sql we actually want to execute
SELECT @Sql = @Sql + N'
ALTER AUTHORIZATION ON SCHEMA::' + QUOTENAME(SchemaName) + N' TO ' + QUOTENAME(@Target) + N';'
FROM SchemasToFix
WHERE OwnerName LIKE 'EnterpriseDbUser[_]%' ESCAPE '\'
	AND OwnerName <> @Target;

IF (@Sql <> N'')
BEGIN
	EXEC sp_executesql @Sql;
END
```