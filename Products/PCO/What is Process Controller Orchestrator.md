 CargoWise Cloud hosts CargoWise as a SaaS. Each customer's system runs background jobs via a Process Controller which is a [[Windows Service]] that must be co-located with the customer's database (the process controller must run on a server that is physically in the same data centre as the customer's database- both in DE1, Germany).
 
In a multi-tenant cloud, PC services are packed onto shared Process Controller Host servers, each hosting services for many customers.

The orchestrator's job is to continuously ensure every customer has exactly the right number of healthy Process Controller services installed on the right servers. No more, no less.