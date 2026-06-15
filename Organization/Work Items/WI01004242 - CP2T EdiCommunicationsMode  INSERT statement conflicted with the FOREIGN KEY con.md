
### Notes from a few weeks ago

- From what i remember Cart saying, it has something to do with a prod database and a test database during a cp2t operation, and removing the edicommunication configs during a copy production to test so that we are not making connections using prod settings with test dbs. how this translates to foreign key constraint error i am not sure.

### Root cause analysis (using WI notes)

- start with the error
	- `The INSERT statement conflicted with the FOREIGN KEY constraint "EDICommunicationsMode_EK_ECC_CommunicationPartyConfig_FK2_EDICommunicationPartyConfig_RRR_120N". The conflict occurred in database "OdysseyHPLTRN", table "dbo.EDICommunicationPartyConfig", column 'ECC_PK'. The statement has been terminated.`
		- `OdysseyHPLTRN` is one db corresponding to the customer `HPLTRN`
		- `EDICommunicationPartyConfig` is the table
		- `ECC_PK` is the column
		- `EDICommunicationsMode_EK_ECC_CommunicationPartyConfig_FK2_EDICommunicationPartyConfig_RRR_120N` is the constraint