
An SQL server database is stored on disk as two files:
- `mdf` stores the tables, structure and data inside those tables
- `ldf` stores transactions, records of what changes were made and when (sort of akin to a git history)

Database backups taken in `.bak` files contain these files inside