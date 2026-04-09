DBBR is a software application to back up customer databases (?)

It is a module in cargowise (?)

It looks like this:
![[Pasted image 20260311140657.png]]

There is also a command line version.

It is used to do a few basic database operations on the odyssey database:
- backing up the database into a series of .bak files
- restoring the .bak into a database
- turning a production backup into a test database, usually on another server (this process is typically called CP2T or copy production to test)

It is a wrapper around the T-SQL `BACKUP` and `RESTORE` commands. It coordinates the backup for all the cw dbs, such as odyssey, userrepository, audit, etc.