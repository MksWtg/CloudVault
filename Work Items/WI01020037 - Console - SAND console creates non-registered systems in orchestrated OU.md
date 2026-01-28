

SAND CCC is used for functionally testing Console changes. New customer systems are orchestrated by default (they have service tasks running). You can see this in the customer creation modal. 

![[Pasted image 20260128111524.png]]

Systems are orchestrated by placing them in a specific OU in the AD. Then separately, PCO (Process Controller Orchestrator) will look for all the instances listed in this OU and create process controllers that run service tasks for those instances.

The issue:
- When Denny's team create PROD systems (with or without console) they register customer systems with a product license manually (The process is detailed here: [Mukund Srinivasan: What is "Registering" a customer system? | CargoWise Cloud > CargoWise Cloud Console | Microsoft Teams](https://teams.microsoft.com/l/message/19:J_86s9F8V8fw-qtEJ6XkiTRBLQDTwAFtfOQmy4wjKZk1@thread.tacv2/1769125776064?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=ced3190c-f7ff-408f-a149-760a9449c556&parentMessageId=1769125776064&teamName=CargoWise%20Cloud&channelName=CargoWise%20Cloud%20Console&createdTime=1769125776064&ngc=true&allowXTenantAccess=true "https://teams.microsoft.com/l/message/19:J_86s9F8V8fw-qtEJ6XkiTRBLQDTwAFtfOQmy4wjKZk1@thread.tacv2/1769125776064?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=ced3190c-f7ff-408f-a149-760a9449c556&parentMessageId=1769125776064&teamName=CargoWise%20Cloud&channelName=CargoWise%20Cloud%20Console&createdTime=1769125776064&ngc=true&allowXTenantAccess=true")). When test rigs create customer systems they register them programmatically. However, when we create console instances they are not registered with a product license.
	- TODO: figure out what registration is for. As of right now it is just an arbitrary action, mandated for policy.
	- TODO: confirm test rigs register programmatically
- When PCO tries to spin up a PC, it performs a check to see if the instance it is creating a PC for is registered. This is determined by running a simple TSQL stored procedure. (You can see this here: https://github.com/WiseTechGlobal/CargoWiseCloud.ProcessControllerOrchestrator/blob/93b69b7d5b4a096c9eb9a6023a61ffa7eeb18967/Source/Common/DataLayer/DataAccess.cs#L83).
- Since the console instance is not registered, it triggers a SCOM alert, because in its eyes something has gone wrong if a non-registered system is asking to be orchestrated.

Solutions:
1. Make console create SAND systems in the non-orchestrated OU (no service tasks, so no registration required). For PROD systems, keep doing what we are doing now- which is Denny's team manually registering them. This solution is not great because we need service tasks for functionally testing Winzor test rigs.
2. Make console register customer systems on creation (register programmatically like the test rigs). But we are blocked by the CW Installer project. This is to reduce effort/code duplication + separate business logic (i.e., Console shouldn't be making CargoWise changes, CargoWise should).
3. Just a policy change, have a little popup that asks users to register the instance when they create one.

  


Other Info:
- why has this not been an issue until now?
	- Garland was cancelling the SCOM alert

- where is the portal that can be used to see all the alerts?
	- SCOM operations console, need to request access from SRE. However, this is not critical. All SCOM incidents relevant to our products show up on our board as incidents. There is a mapping between SCOM source and the target capability.

  

Chosen Solution: 3
- The policy change does come with a small code change, show an alert when a user creates a new customer system if they select service tasks, which is created by default. 
- TODO: Once auto registration is complete, remove this feature


Prompts used:

- When users click teh "Create Customer System" button in the create customer system modal, if the "Service Tasks Enabled" is toggled on, open a dialog box that says "Make sure to register customer system or otherwise disable service tasks" and teh user can eitehr go back or confirm, which closes both the dialog box and the modal. if service tasks are toggled off, just do nothing- the create customer system button does what it does now