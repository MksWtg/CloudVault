
### Notes from a few weeks ago

- From what i remember Cart saying, it has something to do with a prod database and a test database during a cp2t operation, and removing the edicommunication configs during a copy production to test so that we are not making connections using prod settings with test dbs. how this translates to foreign key constraint error i am not sure.

### Root cause analysis (using WI notes)

- start with the error
	- `The INSERT statement conflicted with the FOREIGN KEY constraint "EDICommunicationsMode_EK_ECC_CommunicationPartyConfig_FK2_EDICommunicationPartyConfig_RRR_120N". The conflict occurred in database "OdysseyHPLTRN", table "dbo.EDICommunicationPartyConfig", column 'ECC_PK'. The statement has been terminated.`
		- `OdysseyHPLTRN` is one db corresponding to the customer `HPLTRN`
		- `EDICommunicationPartyConfig` is the parent table
		- `EDICommunicationsMode` is the child table
		- `ECC_PK` is the column that the fk column is connected to
		- `EDICommunicationsMode_EK_ECC_CommunicationPartyConfig_FK2_EDICommunicationPartyConfig_RRR_120N` is the constraint
		- What happened: we tried to insert a row into the "[EDICommunicationsMode]" table and it errored in the "[EDICommunicationsMode]" table because the FK column didn't correspond to a PK in the "[EDICommunicationPartyConfig]" table
		- Other info: the fk column in the child is nullable- so it doesnt have to be linked to a parent
		- This leads us to the first note that yash made in dec 11 last year: `EDICommunicationsMode.EK_ECC_CommunicationPartyConfig must be either **NULL** or reference an existing EDICommunicationPartyConfig.ECC_PK row.` This was the error and we understand how this happened at the lowest level- because we inserted a bad row into the child. The question remains: why did we try inserting a bad row into the mode table?
	- Let us trace a copy production to test operation
		- Common high level DBBR method `RestoreDatabasesUnsafe` is called
		- Performs collection of generic step methods: 
			```cs
				try
				{
					// Save test specific data before restoring production backup over it
					PerformCopyProductionToTestPreRestoreSteps(connection, dbRestoreSettings, vaultAuxDbName, isNewDb);
					DoRestore(connection, mainServerConfig, auditServerConfig, edwServerConfig, dbRestoreSettings);
			#if DEBUG
					ApplyChangeAfterRestoreDatabase(connection, dbRestoreSettings.TargetDbName);
			#endif
					// Re-apply test specific data (from vault DB) and make other test system related adjustments
					PerformCopyProductionToTestPostRestoreSteps(connection, dbRestoreSettings, vaultAuxDbName, isNewDb);
				}
			```
		- Call `PerformCopyProductionToTestPostRestoreSteps` after the restore
		- Call `ClearProductionInfoFromTestSystem` as part of the post restore steps
		- Call static method `CopyProductionToTestScriptManager.GetClearDataToBeOverwrittenByTestDataScript`
		- Call `GetClearDataScripts` which returns a hardcoded list of class instances
		- foreach of those, call `BuildScript`. One of these is `ClearEDICommunicationMode.BuildScript`
		- When this last line of code runs, it empties this table (presumably). This is a safe option since this table is the child. This aligns with the second note that yash made in dec 11 last year: `_ClearEDICommunicationMode.cs_ - CP2T clear scripts run 'DELETE FROM EDICommunicationsMode' (table is cleared, no FK violations)`
	- Separately
		- `PerformCopyProductionToTestPostRestoreSteps` (see above)
		- `CopyAuxiliaryDataToTestDatabase` is called as the final step
		- Static method `CopyProductionToTestScriptManager.GetCopyTempDbDataToTestDbScript` is called
		- Iterate through `CopyProductionToTestScriptsCollection` which is a collection of scripts, for each script we call `GetCopyTempDbDataToTestDbScript`. So at some point we call `EDICommunicationModeToPreserve.GetCopyTempDbDataToTestDbScript`. This runs a fat copy data into test db query:
			```SQL
			-- OVERWRITE PROD DATA WITH TEST DATA IF DUPLICATE PKS --
			DECLARE @OverwriteProdEdiCommsWithTestIfDuplicatePK NVARCHAR(MAX) = N'
			UPDATE [{1}].[dbo].[EDICommunicationsMode] SET '
			
			SELECT @OverwriteProdEdiCommsWithTestIfDuplicatePK = @OverwriteProdEdiCommsWithTestIfDuplicatePK + c.COLUMN_NAME + ' = b.' + c.COLUMN_NAME + ','
			FROM [{1}].INFORMATION_SCHEMA.COLUMNS as c
			WHERE TABLE_NAME = 'EDICommunicationsMode'
			
			SET @OverwriteProdEdiCommsWithTestIfDuplicatePK = SUBSTRING(@OverwriteProdEdiCommsWithTestIfDuplicatePK, 1, LEN(@OverwriteProdEdiCommsWithTestIfDuplicatePK) - 1)
			
			SET @OverwriteProdEdiCommsWithTestIfDuplicatePK = @OverwriteProdEdiCommsWithTestIfDuplicatePK + ' FROM [{0}]..[TempEDICommunicationsMode] b '
			SET @OverwriteProdEdiCommsWithTestIfDuplicatePK = @OverwriteProdEdiCommsWithTestIfDuplicatePK + 'JOIN [{1}]..[EDICommunicationsMode] a '
			SET @OverwriteProdEdiCommsWithTestIfDuplicatePK = @OverwriteProdEdiCommsWithTestIfDuplicatePK + 'ON a.EK_PK = b.EK_PK'
			
			EXEC sp_executesql @OverwriteProdEdiCommsWithTestIfDuplicatePK
			
			-- COPY TEST SPECIFIC DATA INTO TEST DB --
			DECLARE @CopyOldTestEdiCommsIntoNewTestDatabase NVARCHAR(MAX) = N'
			INSERT [{1}]..EDICommunicationsMode
			SELECT *
			FROM [{0}]..TempEDICommunicationsMode
			WHERE EK_PK NOT IN (SELECT EK_PK FROM [{1}]..EDICommunicationsMode)'
			
			EXEC sp_executesql @CopyOldTestEdiCommsIntoNewTestDatabase
			```
		- This aligns with the third note yash made in dec 11 last year
	- Importantly, both of the points regarding dropping rows and copying in test data are for `EDICommunicationsMode`. The config table `EDICommunicationPartyConfig` only has PROD rows, it has not been touched. This aligns (mostly) with the fourth note yash made in dec 11 last year. I say mostly because he included the assertion `TEST-only EDICommunicationPartyConfig rows no longer exist.` which is not technically true because there were never test only config rows.
	- The constraint `EDICommunicationsMode_EK_ECC_CommunicationPartyConfig_FK2_EDICommunicationPartyConfig_RRR_120N` from way back is still valid during the insert operation- which means inserting test rows may fail because there are no test configs in the configs table. This aligns with the fifth note yash made in dec 11 last year. `However, the preserved TEST EDICommunicationsMode rows still reference **TEST-only** EK_ECC_CommunicationPartyConfig values. When these rows are re-inserted, the FK constraint rejects them because the referenced ECC_PK values are not present in the PROD-restored EDICommunicationPartyConfig table. This results in the FK violation during the restore.` He summarizes the above 5 notes with the following 6th note: `Preserved **TEST** EDICommunicationsMode **incompatible** with the PROD-restored EDICommunicationPartyConfig data, causing FK violations during CP2T restore.`
- Quick question: where does the new data in the mode table come from?
- Ok, great. We know what is failing. We even know enough to reproduce it/the exact situation which would cause this to appear in PROD. That being: after the CP2T operation if the config table is missing a PK and we try blindly inserting into the mode table we get an FK error. We have an old and a new proposed fix
	- OLD: only insert data into mode table that has a pk that is in the config table. drop remaining rows
	- NE