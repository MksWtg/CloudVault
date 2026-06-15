
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
		- Common high level DBBR method `RestoreDatabasesUnsafe` runs
		- 