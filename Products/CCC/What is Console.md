
CargoWise Cloud Console (CCC) is a web app. The SAND version is accessible [here](https://cwc-console.sand.wtg.zone/).

## Why CCC?

Every solution in WiseCloud exists to solve a problem.

### The Problem

The process of creating new customer systems  (customer system, customer instance, instance, test rig, test system all refer to instances of CW with slight differences used for various purposes, but are fundamentally the same thing) for wtg customers has multiple steps. Some of these steps include:
- Restoring the main Odyssey DB
- Registering the instance
- Putting the instance in a particular OU which decides whether or not it should be orchestrated by PCO
- Assigning AWS resources such as buckets and credentials
- Many more

So far, this is being managed by GPS (Global Product Support) headed by Denny. This is a non technical team that historically has completed all these steps painstakingly for every new customer system.

### The Solution

A central webapp that operators can use to spin up new CW systems, that completes these steps automatically. This webapp is the CargoWise Cloud Console (CCC). It is accessible [here](https://cwc-console.sand.wtg.zone/).

It looks like this:
![[Pasted image 20260203144146.png]]

As can be seen in the SS above, Console does more than just manage customer systems, it also manages SQL servers, IIS servers, Customers, etc.

We have two versions, or ccc "products"- SAND and PROD. They are essentially the same product. PROD is actively used by Denny's team to create new customer systems. While some of their work has been automated, some has not. You can see a list of ongoing projects within console here:
[CargoWise Cloud Console Projects](https://ediprod.cw.wisetechglobal.com/link/ShowEditForm/NetworkDiagram/1238d975-2801-4b77-acdb-62c292966c56?lang=en-gb)
- Some of these goals are part of automating the work of GPS and some are just general enhancements

SAND is used by us, the CWC team to functionally test changes we make to PROD before we roll out to GPS.