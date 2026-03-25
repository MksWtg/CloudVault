Also known as always on availability group

Sometimes databases fail- the host of the sql server instance crashes, it can't connect to the network etc. In these cases, we need another copy of the database to take over that has the exact same data, just on a different machine. This is an availability group.

AG: logical container, group of databases that need to be replicated together e.g. Orders, Customers (if they are different DBs). the AG also knows which servers are part of the AG and whether the data is synced across them sync or async

Replica: A server participating in the AG that has copies of all DBs

Listener: The common endpoint that you connect to- it makes a connection to the current primary