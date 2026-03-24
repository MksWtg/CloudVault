
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

If someone CP2T restores to the same name, the method returns early (by design). But orphaned schemas still 
exist

- Schema owned by a user with the same name as the schema
- Source/target DB names are identical