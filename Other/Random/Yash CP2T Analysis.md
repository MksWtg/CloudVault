
1) in the method that does the main CP2T operation, add the following command

```
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