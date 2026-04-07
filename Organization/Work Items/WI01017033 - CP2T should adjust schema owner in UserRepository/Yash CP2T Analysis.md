
Prerequisites: [[WI01017033 - CP2T should adjust schema owner in UserRepository]]
https://github.com/WiseTechGlobal/CargoWise/pull/33986
1) in the method that does the main CP2T operation (post restoration), add the following command

```csharp
		protected virtual void PerformCopyProductionToTestPostRestoreSteps(AdminConnection connection, DbRestoreSettings dbRestoreSettings, string vaultAuxDbName, bool isNewTestDb)
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
				
				// New
				FixSchemaOwnershipForUserRepositoryDatabase(connection, dbRestoreSettings);
			}
		}
```

What occurs in `FixSchemaOwnershipForUserRepositoryDatabase`?
- we need to be restoring the user repository database

```csharp
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
```

Then that calls this for each db file in user repository, again not sure what a db file is but i presume .mdf and .ndf and .ldf:

```csharp
void FixSchemaOwnershipForUserRepositoryDb(string serverName, string userRepositoryDbName)
		{
			try
			{
				using (Db.DisableSchemaVersionCheck()) //After the object is disposed it enables the schema version check
				using (var connection = Db.NewAdminConnection(serverName, userRepositoryDbName))
				{
					if (!connection.DatabaseExists(userRepositoryDbName))
					{
					// If user repository does not exist
						FireOnShowInfoMessage($"Skipping schema ownership fix. Database does not exist: {userRepositoryDbName}");
						return;
					}

					// target principal is the old database user
					var targetAppPrincipal = ResolveTargetApplicationDbPrincipal(connection, userRepositoryDbName);
					if (string.IsNullOrWhiteSpace(targetAppPrincipal))
					{
						FireOnShowInfoMessage($"Schema ownership: skip (target app principal not found) for {userRepositoryDbName}");
						return;
					}

					FireOnSubtaskStarted($"Normalising UserRepository schemas to '{targetAppPrincipal}' in {userRepositoryDbName}", 0);
					
					// then we call this function which im guessing makes the new login
					NormaliseEnterpriseDbUserSchemaOwners(connection, targetAppPrincipal);
				}
			}
			catch (Exception ex) when (!ex.IsCriticalException())
			{
				LogDetailedError(ex, $"Schema ownership: failed for {userRepositoryDbName}");
			}
		}
```

What does resolve target application db principal do?

FOR CONTEXT: in the original sql server we had a login, and in the original user repository we had a user with the same name (`EnterpriseDbUser_Odyssey2_mukund1234`). This was created by us through cargowise.
```csharp
static string ResolveTargetApplicationDbPrincipal(AdminConnection conn, string userRepositoryDbName)
		{
			// TEMPORARY - ideally, the target principal should be determined based on the actual application pool identity used to connect to the User Repository database in the test environment, but for now, we resolve it based on the existing principals in the database.
			// Need to look into CargoWise.Data code to find a more reliable way to determine the target principal that should own the schemas in the User Repository database in test environments.

// two tables: database_principals has the users and server_principals has the logins. We select the name from the database principals where they have the same SID. S is an SQL user, U is a windows user. S
			const string sql = @"
SELECT TOP (1) dp.name
FROM sys.database_principals dp
JOIN sys.server_principals sp ON sp.sid = dp.sid
WHERE dp.type IN ('S','U')
  AND dp.name LIKE 'EnterpriseDbUser[_]%' ESCAPE '\'
ORDER BY dp.name;";

// what does it do? It returns the alphabetically first database user whose name starts with `EnterpriseDbUser_` and is correctly mapped to an existing server login (via matching SID).

			return conn.ExecuteScalar<string>(sql);
		}
```

Finally, the method that actually creates the database principal

```csharp
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
	WHERE s.name NOT IN ('dbo','guest','INFORMATION_SCHEMA','sys','cdc')
	  AND s.schema_id < 16384
)
^ all schemas and owners that are not the default ones

SELECT @Sql = @Sql + N'
ALTER AUTHORIZATION ON SCHEMA::' + QUOTENAME(SchemaName) + N' TO ' + QUOTENAME(@Target) + N';'

**^ set owner to targetAppPrincipal if the schema owner starts with 'EnterpriseDbUser'**
The thing is, the target app principal is just the first enterprise db user haha, so all we have done is set all the owner of all schemas owned by enterprise db user to the first enterprise db user

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