Also known as always on availability group

Sometimes databases fail- the host of the sql server instance crashes, it can't connect to the network etc. In these cases, we need another copy of the database to take over that has the exact same data, just on a different machine. This is an availability group.

AG: logical container, group of databases that need to be replicated together e.g. Orders, Customers (if they are different DBs). the AG also knows which servers are part of the AG and whether the data is synced across them sync or async

Replica: A server participating in the AG that has copies of all DBs

Listener: The common endpoint that you connect to- it makes a connection to the current primary, so if a db goes down when you try to make a connection it will point you to the right primary.
- a listener is a virtual network name (DNS)

Windows Server Failover Clustering (WSFC) is the underlying system that makes Availability Groups work- it tracks replicas (each replica in an AG is a cluster node in WSFC) and WSFC monitors their health. 

A cluster is basically a group of servers that work together as a single system to provide high availability and fault tolerance.

A virtual network name (VNN) is a DNS name (a word that resolves to an IP). The VNN is tied to a virtual IP inside the cluster. The VIP can be any node (server) in the cluster. WSFC updates teh network stack on the old servers

If the pimary fails, WSFC detects htis and promotes a secondary to primary, it moves the listener IP to the new primary.