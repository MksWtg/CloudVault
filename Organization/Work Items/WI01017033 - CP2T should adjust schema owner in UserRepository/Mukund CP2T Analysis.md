Prerequisites: [[WI01017033 - CP2T should adjust schema owner in UserRepository]], [[What is Copy Production to Test]]

https://github.com/WiseTechGlobal/CargoWise/pull/43392

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

What does this change do? After restoring all dbs without recovery, restoring all dbs with recovery, giving rights to all dbs, altering db authorization, **it invokes doing the reassigning.**

How does the remapping actually work?

```csharp
internal virtual void ReassignSchemaOwnersForUserRepositoryDatabase(List<DatabaseDetails> dbDetailsList, DbRestoreSettings dbRestoreSettings)
{
	var targetMainDbName = dbRestoreSettings.TargetDbName; // O2_Restore, this comes directly from the DBBR user facing settings
	var sourceMainDbName = GetSourceDatabaseNameFromBackup(dbRestoreSettings); //Odyssey2, this comes from the main file from the main database inside the .bak
	if (string.IsNullOrEmpty(sourceMainDbName) || sourceMainDbName.Equals(targetMainDbName, StringComparison.OrdinalIgnoreCase))
	{
		return;
	}

	var sourceLoginPrefix = DbUserRepository.GetStaffDbLoginFullPrefix(sourceMainDbName); //EnterpriseDbUser_{sourceMainDbName}_ string
	var targetLoginPrefix = DbUserRepository.GetStaffDbLoginFullPrefix(targetMainDbName); //EnterpriseDbUser_{targetMainDbName}_ -> note this is the prefix, the real login would have the user after this 

	foreach (var dbDetail in dbDetailsList) //this must be a list of database files e.g. odyssey, edocs, user repository (unsure)
	{
		try
		{
			FireOnSubtaskStarted(
				$"Reassigning schema owners in {{{nameof(dbDetail.DatabaseName)}}}",
				1,
				(nameof(dbDetail.DatabaseName), dbDetail.DatabaseName));

			using (var connection = Db.NewAdminConnection(dbDetail.ServerConfig.ServerName, Db.SqlMasterDb))
			{
				// reassigns the schema owner for each database, we might be able to reduce this to purely the user repository database
				ReassignSchemaOwnersInDatabase(connection, dbDetail.DatabaseName, sourceLoginPrefix, targetLoginPrefix);
			}
		}
		catch (Exception ex) when (!ex.IsCriticalException())
		{
			FireOnShowInfoMessage(
				$"Warning: Failed to reassign schema owners in {{{nameof(dbDetail.DatabaseName)}}}: {{{nameof(ex)}}}",
				(nameof(dbDetail.DatabaseName), dbDetail.DatabaseName), (nameof(ex), ex.Message));
		}
	}
}
```

```csharp
// generic method to do this in a database i am sure we can reduce this to only work for user repository
void ReassignSchemaOwnersInDatabase(AdminConnection connection, string databaseName, string sourceLoginPrefix, string targetLoginPrefix)
{
	var schemasOwnedBySourceUsers = GetSchemasOwnedByEnterpriseDbUsers(connection, databaseName, sourceLoginPrefix);
	if (schemasOwnedBySourceUsers.Count == 0)
	{
		return;
	}

	foreach (var (schemaName, sourceUserName) in schemasOwnedBySourceUsers)
	{
		var staffSuffix = sourceUserName.Substring(sourceLoginPrefix.Length); //just the staffname e.g. mukund1234 from EnterpriseDbUser_Odyssey2_mukund1234
		var targetLoginFullName = targetLoginPrefix + staffSuffix; //new staff name EnterpriseDbUser_{targetdbname}_mukund1234
		var targetLoginName = targetLoginFullName.Length > 128 ? targetLoginFullName.Substring(0, 128) : targetLoginFullName; //take first 128 chars, not sure why

		EnsureServerLoginExists(connection, targetLoginName); // want to make sure there is a server principal with the name EnterpriseDbUser_{targetdbname}_mukund1234
		EnsureDatabaseUserExists(connection, databaseName, targetLoginName);
		AlterSchemaAuthorization(connection, databaseName, schemaName, targetLoginName);
	}
}
```

This method returns for example "Schema1, EnterpriseDbUser_Odyssey2_mukund1234", "schema2, otheruser" etc.
```csharp
static List<(string SchemaName, string OwnerName)> GetSchemasOwnedByEnterpriseDbUsers(AdminConnection connection, string databaseName, string sourceLoginPrefix)
{
	var result = new List<(string SchemaName, string OwnerName)>();
	var quotedDbName = databaseName.QuoteName();
	var sql = Invariant($@"
SELECT s.name AS SchemaName, dp.name AS OwnerName
FROM {quotedDbName}.sys.schemas s
JOIN {quotedDbName}.sys.database_principals dp ON s.principal_id = dp.principal_id
WHERE dp.name LIKE @sourceLoginPrefix + N'%'
AND s.name <> dp.name");

	var command = connection.Command(sql);
	command.AddParameter("@sourceLoginPrefix", SqlDbType.NVarChar, 128, DataUtils.ReplaceSqlLikeWildcard(sourceLoginPrefix));
	using (var reader = command.ExecuteReader())
	{
		while (reader.Read())
		{
			result.Add(((string)reader["SchemaName"], (string)reader["OwnerName"]));
		}
	}

	return result;
}
```


```csharp
static void EnsureServerLoginExists(AdminConnection connection, string loginName) // param EnterpriseDbUser_{targetdbname}_mukund1234
{
	var checkSql = "SELECT COUNT(*) FROM sys.server_principals WHERE name = @loginName"; //there may be multiple 
	var checkCommand = connection.Command(checkSql);
	checkCommand.AddParameter("@loginName", SqlDbType.NVarChar, 128, loginName);
	var exists = (int)checkCommand.ExecuteScalar() > 0; // maybe a user with the name EnterpriseDbUser_{targetdbname}_mukund1234 already exists

	if (!exists)
	{
		var password = GenerateRandomPassword();
		var createSql = Invariant($"CREATE LOGIN {loginName.QuoteName()} WITH PASSWORD = N'{password}', DEFAULT_DATABASE = [master], CHECK_POLICY = OFF, CHECK_EXPIRATION = OFF");
		connection.ExecuteNonQuery(createSql);
		// TODOs- why is check policy off, why is check expiration off, why is default database master
		// TODO: how does the user login if their password is random
	}
}
```

This part of the code does not make sense
```csharp
static void EnsureDatabaseUserExists(AdminConnection connection, string databaseName, string loginName) //we kn
{
	var quotedDbName = databaseName.QuoteName();
	var quotedLoginName = loginName.QuoteName();
	var checkSql = Invariant($"SELECT CASE WHEN EXISTS (SELECT 1 FROM {quotedDbName}.sys.database_principals WHERE name = @loginName) THEN 1 ELSE 0 END");
	var checkCommand = connection.Command(checkSql);
	checkCommand.AddParameter("@loginName", SqlDbType.NVarChar, 128, loginName);
	var exists = (int)checkCommand.ExecuteScalar() == 1;

	if (!exists)
	{
		var createSql = Invariant($"USE {quotedDbName}; CREATE USER {quotedLoginName} FOR LOGIN {quotedLoginName}");
		connection.ExecuteNonQuery(createSql);
	}
}
```