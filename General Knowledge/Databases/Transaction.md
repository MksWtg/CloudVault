Prerequisites: [[ACID]]

A transaction in databases is a sequence of operations treated as a single unit of work. Either all changes succeed or none do (this is part of the ACID properties, especially atomicity and consistency).

Stages of a transaction
Active
The transaction is running and executing its SQL statements (e.g., INSERT, UPDATE, DELETE).
Partially Committed
All statements have executed, and the system is preparing to make the changes permanent (e.g., waiting for final checks or logging).
Committed
The transaction completes successfully, and all changes are permanently saved to the database.
Failed
An error occurs (e.g., constraint violation, system crash), preventing completion.
Aborted (Rolled Back)
The transaction is undone, and the database is returned to its previous consistent state.
Simple flow

Active → Partially Committed → Committed
or
Active → Failed → Aborted