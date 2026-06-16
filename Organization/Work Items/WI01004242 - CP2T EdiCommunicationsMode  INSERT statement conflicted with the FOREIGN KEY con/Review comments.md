Summary of changes?
1) `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/CopyProductionToTest/DataToPreserve/EDICommunicationModeToPreserveForTesting.cs` was removed
2) `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/CopyProductionToTest/DataToPreserve/EDICommunicationModeToPreserveTest.cs` was removed
3) In the SQL file `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/TestFiles/testProdCopy.sql` a ton of changes were made including to the encoding (most likely), impossible to see the diff without pulling locally [TODO]
4) In the file `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/TestFiles/testProdDbCopyWithInterchangeAndMessage.sql` we made some changes: this sql query is used to set up a db to perform the cp2t operation when we have messaging data that needs to be treated specially. The schema has been modified to include a foreign key reference to itself, not sure why
	1) see if EM_EM_RequestMessage is used anywhere else in the logic
	2) `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/DbRestoreManagerTest.cs` is a TEST file and is not very important. In one test: `TestCopyProductionToTest`, there is an assertion that all the tables we want to clean up (and strip prod data from) are empty. This is because the requirement from product is that all PROD data is wiped. BUT all test data should be copied back into this table. We should leave a comment suggesting to have data in the aux pre CP2T that we can assert is still there post operation, although this only works if we have a mechanism to have a "pre" db and that the CP2T isnt done onto an empty/non existent test.


```
I am trying to understand the order of operations in the class CopyProductionToTestScriptManager during a copy production to test (CP2T). My understanding is (please confirm or refute) first we take a backup of existing test into an aux/temp db. Then we copy prod over the existing test. Then we clear data using GetClearDataToBeOverwrittenByTestDataScript, this iterates through GetClearDataScripts() list in forwards order. This should be children first then parents to prevent orphans. But then why do we iterate through 'CopyProductionToTestScriptsCollection.Reverse()' afterwards and append `GetClearDataToBeOverwrittenByTestDataScript` for each script to the list, isnt this backwards because we would be clearing parents first? Then to copy test data back in after clearing prod data we iterate throgh CopyProductionToTestScriptsCollection in forwards order which also seems backwards, because we should be copying parents first not children first. but the comment below says the list has children first. What am I missing?
```


```
Does the test "TestCopyProductionToTest" perform the CP2T operation on top of an existing test db with existing data (does the test setup create this db before doing the CP2T) or does it do the CP2T fresh and create the DB as part of CP2T?
```
