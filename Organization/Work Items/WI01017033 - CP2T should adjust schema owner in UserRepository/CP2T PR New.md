Top level function call: change happens EARLIER than it used to:

```csharp
protected virtual void RestorePrimaryReplica(List<DatabaseDetails> dbDetailsList, DbRestoreSettings dbRestoreSettings)
{
	foreach (var dbDetails in dbDetailsList)
	{
		ExecuteRestoreWithNoRecovery(dbDetails, dbRestoreSettings);
	}

	if (dbRestoreSettings.RestoreOption != DbRestoreOption.RestoreWithNoRecovery)
	{
		foreach (var dbDetails in dbDetailsList)
		{
			ExecuteRestoreWithRecovery(dbDetails, dbRestoreSettings);
		}
		foreach (var dbDetails in dbDetailsList)
		{
			GrantDatabaseRights(dbDetails, dbRestoreSettings);
		}
	}

	if (dbRestoreSettings.RestoreOption == DbRestoreOption.CopyProdToTest)
	{
		foreach (var dbDetail in dbDetailsList)
		{
			AlterDbAuthorisation(dbDetail);
		}
		
		ReassignSchemaOwnersForUserRepositoryDatabase(dbDetailsList, dbRestoreSettings);
	}

	if (dbDetailsList.FirstOrDefault(db => db.DatabaseName.Equals(dbRestoreSettings.TargetDbName, StringComparison.OrdinalIgnoreCase) && IsTargetDatabaseMainDb(dbRestoreSettings.TargetDbName)) is { ServerConfig.ServerName: var mainServer })
	{
		SynchroniseSynonyms(mainServer, dbRestoreSettings.TargetDbName);
		ConfigureServerForDatabase(mainServer, dbRestoreSettings.TargetDbName);
	}
}
```