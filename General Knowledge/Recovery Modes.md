
Prerequisites: [[Log Files]]
In sql sever, every data changing query starts a transaction even if you dont explicitly write one

E.g.

`UPDATE Users SET Name = 'Alice' WHERE Id = 1;`

becomes

```SQL
BEGIN TRANSACTION;
UPDATE Users SET Name = 'Alice' WHERE Id = 1;
COMMIT;
```

this is called implicit transaction, or auto commit transaction

Now with all these transaction logs, we can restore the db in the case of a crash

Recovery modes tell you how many of these logs are kept and what options we have for restoring after crash.

## Checkpoint

A checkpoint in Microsoft SQL Server is a process that writes all dirty (modified but not yet saved) data pages from memory to disk so the database stays consistent with the transaction log.
SQL Server keeps data changes in memory (buffer cache) for speed
A checkpoint forces those changed pages to be written to the data files (.mdf/.ndf)
It also records a point in the transaction log so recovery knows where to start
## Models

1) FULL- simplest, it keeps everything
2) SIMPLE- after a checkpoint happens, we write the new database rows/data to disk from buffer, and we truncate the logs (so that part of the ldf can be overwritten later)
3) BULK- In Bulk-Logged recovery mode, normal transactions are fully logged like in Full recovery, but during bulk operations (such as bulk inserts or index rebuilds), SQL Server uses minimal logging, meaning it records only the allocation of data pages rather than every row change