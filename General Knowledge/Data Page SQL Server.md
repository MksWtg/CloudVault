
In Microsoft SQL Server, a data page is the smallest unit of storage used to store actual table or index data on disk, typically fixed at 8 KB in size, and it contains multiple rows of data along with metadata that describes how those rows are stored within the page.

In simple terms: a table in SQL Server is not stored row-by-row on disk, but as a collection of pages, and each page holds several rows (depending on row size), so when SQL Server reads or writes data, it works with these pages rather than individual rows.