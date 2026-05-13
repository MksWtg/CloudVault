 CargoWise Cloud hosts CargoWise as a SaaS. Each customer's system runs background jobs via a Process Controller which is a Windows service (TODO what is a windows service) that must be co-located with the customer's database. In a multi-tenant cloud, PC services are
  packed onto shared Process Controller Host servers, each hosting services for many customers.

  The orchestrator's job is to continuously ensure every customer has exactly the right number of healthy Process
  Controller services installed on the right servers. No more, no less.