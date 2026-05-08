ACID are principles for doing db operations and queries.

A: Atomicity
A transaction is all-or-nothing. Either every operation succeeds or the whole transaction is rolled back.

C: Consistency
A transaction must leave the database in a valid state and obey all constraints, rules, and relationships.

I: Isolation
Concurrent transactions should not interfere with each other. One transaction should behave as if it is running alone.

D: Durability
Once a transaction is committed, the data is permanently saved, even after crashes or power loss.

Example:

If transferring $100 from Account A to Account B:

1. Deduct $100 from A
2. Add $100 to B

ACID guarantees:

* both happen or neither happens
* balances remain valid
* concurrent transfers do not corrupt data
* committed transfer survives system failure
