
Indexing in SQL is a database optimization technique used to speed up data retrieval operations (like `SELECT` queries) by creating a special data structure that allows the database engine to quickly locate specific rows, much like a book's index helps you find information without reading every page.

Without an index, the database must perform a full table scan, checking every single row to find data that matches the query's criteria, which can be slow, especially in large tables.

When you create an index on a column (or multiple columns), the database engine creates a sorted copy of that data, usually in a B-tree structure, which allows for efficient searching (logarithmic time). This index contains pointers to the physical location of the complete data rows in the main table. The query optimizer can then use this sorted index to quickly find the relevant rows and retrieve the full data.

## Clustered

Clustered Index: This determines the physical order in which the data rows are stored in the table. Because the data itself is physically sorted, a table can only have one clustered index. In many database systems (like SQL Server and MySQL/InnoDB), a table's primary key automatically creates a clustered index.

## Non Clustered

Non-Clustered Index: This is a separate structure from the data rows, containing the indexed columns' values in a sorted order and pointers to the actual data's physical location. You can have multiple non-clustered indexes on a single table, serving different query needs, similar to having multiple subject indexes in a library catalog.