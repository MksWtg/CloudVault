
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