Every solution in WiseCloud exists to solve a problem.

### The Problem

The process of creating new customer systems for wisetech customers has multiple steps. Some of these steps include:
- restoring the DB
- registering the instance
- putting the instance in a particular OU which decides whether or not it should be orchestrated by PCO
- assigning AWS resources such as buckets and credentials
- many more

So far, this is being managed by GPS (Global Product Support) headed by Denny. This is a non technical team that historically has completed all these steps painstakingly for every new customer system.
### The Solution

A central webapp that operators can use to spin up new CW systems, that completes these steps automatically. This webapp is the CargoWise Cloud Console (CCC). It is accessible [here](https://cwc-console.sand.wtg.zone/).

It looks like this:
![[Pasted image 20260203144146.png]]


We have two versions, or ccc "products"- SAND and PROD. They are essentially the same product. PROD is actively used 