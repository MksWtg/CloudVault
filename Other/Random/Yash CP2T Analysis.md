
1) in the method that does the main CP2T operation, add the following command

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

					// target principal is the new login/user we want to make?
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
```

What does resolve target application db principal do?

FOR CONTEXT: in the original sql server we had a login, and in the original user repository we had a user with the same name (`EnterpriseDbUser_Odyssey2_mukund1234`). This was created by us through cargowise.
```csharp
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
```