

SAND CCC is used for functionally testing Console changes. New customer systems are orchestrated by default- you can see this by the fact (they have service tasks running). Systems are orchestrated by placing them in a specific OU in the AD. Then separately, PCO (Process Controller Orchestrator) will look for all the instances listed in this OU and create process controllers that run service tasks for those instances.

The issue:
- When PCO does this, it performs a check to see if the instance it is creating a PC for is "registered" with a product license. This is determined by running a simple TSQL stored procedure. (You can see this here: https://github.com/WiseTechGlobal/CargoWiseCloud.ProcessControllerOrchestrator/blob/93b69b7d5b4a096c9eb9a6023a61ffa7eeb18967/Source/Common/DataLayer/DataAccess.cs#L83).
- TODO: figure out what registration is for. As of right now it is just an arbitrary action, mandated for policy.
- When Denny's team create PROD systems they perform this registration manually (The process is detailed here: [Mukund Srinivasan: What is "Registering" a customer system? | CargoWise Cloud > CargoWise Cloud Console | Microsoft Teams](https://teams.microsoft.com/l/message/19:J_86s9F8V8fw-qtEJ6XkiTRBLQDTwAFtfOQmy4wjKZk1@thread.tacv2/1769125776064?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=ced3190c-f7ff-408f-a149-760a9449c556&parentMessageId=1769125776064&teamName=CargoWise%20Cloud&channelName=CargoWise%20Cloud%20Console&createdTime=1769125776064&ngc=true&allowXTenantAccess=true "https://teams.microsoft.com/l/message/19:J_86s9F8V8fw-qtEJ6XkiTRBLQDTwAFtfOQmy4wjKZk1@thread.tacv2/1769125776064?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=ced3190c-f7ff-408f-a149-760a9449c556&parentMessageId=1769125776064&teamName=CargoWise%20Cloud&channelName=CargoWise%20Cloud%20Console&createdTime=1769125776064&ngc=true&allowXTenantAccess=true")). When test rigs create customer systems they register them programmatically. However, console instances are not registered with a product license.
- We want to try doing this programmatically but we are blocked by the CW Installer project. This is to reduce effort/code duplication + separate business logic (i.e., Console shouldn't be making CargoWise changes, CargoWise should).
- When PRC Orchestrator sees the console instances, it triggers a SCOM alert, because in its eyes something has gone wrong if a non-registered system is asking to be orchestrated



In addition, 

  



  

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