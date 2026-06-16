Summary of changes?
1) `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/CopyProductionToTest/DataToPreserve/EDICommunicationModeToPreserveForTesting.cs` was removed
2) `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/CopyProductionToTest/DataToPreserve/EDICommunicationModeToPreserveTest.cs` was removed
3) In the SQL file `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/TestFiles/testProdCopy.sql` a ton of changes were made including to the encoding (most likely), impossible to see the diff without pulling locally [TODO]
4) In the file `Enterprise/Product/Core/DataTools/DbBackupAndRestore/DbBackupAndRestore.Business.Test/Restore/TestFiles/testProdDbCopyWithInterchangeAndMessage.sql` we made some changes: this file is used to set up a db to perform the cp2t operation when we have messaging data that needs to be treated specially


```
I am trying to understand the order of operations in the class CopyProductionToTestScriptManager during a copy production to test (CP2T). My understanding is (please confirm or refute) first we take a backup of existing test into an aux/temp db. Then we copy prod over the existing test. Then we clear data using GetClearDataToBeOverwrittenByTestDataScript, this iterates through GetClearDataScripts() list in forwards order. This should be children first
```