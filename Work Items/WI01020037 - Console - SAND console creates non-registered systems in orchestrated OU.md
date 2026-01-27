

SAND CCC is used for functionally testing Console changes. New customer systems are orchestrated by default- you can see this by the fact (they have service tasks running). Systems are orchestrated by placing them in a specific OU in the AD. Then separately, PCO (Process Controller Orchestrator)



In addition, these instances are not registered with a product license.

  

When PRC Orchestrator see's these, it triggers a SCOM alert, because in it's eyes something has gone wrong if a non-registered system is asking to be orchestrated

  

Either:

1. Make SAND console create these systems in the non-orchestrated OU

or

2. Make SAND Console register customer systems on creation

  

M22 22-Jan-26 11:46 GMT+11:00:

  

some random questions:

- why has this not been an issue until now (ans: garland was cancelling the SCOM alert)

- where is the portal that can be used to see all the alerts? (ans: operations manager, need to request access from SRE) or are we simply noticing them because they are turned into incidents and pushed onto the board (ans: YES, there is a mapping between SCOM source and the target capability, all the ones that matter come onto the board anyway)

  

M22 23-Jan-26 14:46 GMT+11:00: solutions

  

sol #1: disallow sand instances being orchestrated. service tasks are not part of console, the system connecting PRC/ORC and CW is loosely coupled via the DB anyway. So console functional tests shouldn't be heavily affected by disallowing service tasks, only for SAND (TODO: confirm with victor). if you need to use service tasks, e.g. for functional testing winzor, for the very basic logging in the identity provider needs certain service tasks. So depending on how thorouhg the console functional testers are, when they make winzor instances they might want service tasks.

  

pros:

- alerts go away

  

cons:

- sand instances can't have service tasks

  

**sol #2: functional testing procedure change: if you ever create a sand instance with service tasks, you must register it manually (no code change just procedure) :D**

  

**pros:**

**- alerts go away**

**- get to choose service tasks**

  

**cons:**

**- bit more work when functionally testing**

  

since sol #2 just requires less work overall I would rather do that. Even if there is a tiny additional ongoing cost.

  

TODO: communicate the functional testing procedure change to the product team, through documentation I guess

  

M22 28-Jan-26 10:37 GMT+11:00:

The policy change does come with a small code change, show an alert when a user creates a new customer system if they select service tasks, which is created by default. Then remember that once auto registration is complete, remove this feature.