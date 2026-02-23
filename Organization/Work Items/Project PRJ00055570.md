We are trying to find out what went wrong with doc util, then we fix it and be happy.

Error: migration_status column does not exist fuck why do they have incorrect schemas

error:
```
**ESN 16-Feb-26 16:28 GMT+11:00:**

  

When trying to download documents for CLEMEL the CargoWiseDocumentUtility tool is throwing and error:

  
  

2026-02-16 05:27:47.4179|CLEMEL|CargoWiseDocumentUtility.Program|INFO|12268590 documents to process

2026-02-16 05:27:47.5339|CLEMEL|CargoWiseDocumentUtility.Program|INFO|Processing StorageDocs record with primary key '2153541f-cea7-45ae-b7df-9144a92bca12'

2026-02-16 05:27:47.5339|CLEMEL|CargoWiseDocumentUtility.Program|INFO|Processing StorageDocs record with primary key '4b210bba-75bc-401e-92f1-d9624eb80a75'

2026-02-16 05:27:47.5339|CLEMEL|CargoWiseDocumentUtility.Program|INFO|Processing StorageDocs record with primary key '148935c5-4ba8-459b-9ee2-53576d3c204f'

2026-02-16 05:27:47.5339|CLEMEL|CargoWiseDocumentUtility.Program|INFO|Processing StorageDocs record with primary key '4fa6ead1-35c3-43f9-aca2-f39176f7064f'

2026-02-16 05:27:48.1691|CLEMEL|CargoWiseDocumentUtility.Program|WARN|eDoc with pk "2153541f-cea7-45ae-b7df-9144a92bca12" not found in S3 bucket

2026-02-16 05:27:48.2004|CLEMEL|CargoWiseDocumentUtility.Program|INFO|Customer has a RptDt_S3MigrationReconciliation table for recording missing eDocs.

2026-02-16 05:27:48.2925|CLEMEL|CargoWiseDocumentUtility.Program|ERROR|Invalid column name 'migration_status'.

  
  
Please advice how to proceed.
```