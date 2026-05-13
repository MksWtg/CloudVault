
Prerequisites: [[What is Process Controller Orchestrator]]

Fundamentally, Process Controller Orchestrator is a c sharp program that runs a loop. You can find the source code [here](https://github.com/WiseTechGlobal/CargoWiseCloud.ProcessControllerOrchestrator).

Every round (which occurs once every 5 minutes) the `EnvironmentNormalizationTask` runs.

There are PC host servers (physical servers/VM servers) in a data centre that run PC services. Maybe 10-20 host computers. Each of these needs to have cargowise start on it (see [[How Does Process Controller Orchestrator Work#CargoWise as a Prerequisite for PCO]]).

Customer database instances are segregates one per instance. There might be 30 instances for 30 customers, which is 30 dbs, but all running off one host.

1) Discovery:
	- What are all the hosts that can have PCO?
	- What are all the instances that need a corresponding orchestrator?
2) Create a plan:
	- If a service has no matching customer record, it is an orphan, remove the service
	- If a customer has more than the required number of services for some reason, remove excess
	- If service is in a bad state, remove it and get a new one
	- If customer has fewer services than required get a new one.
	- Each of these goes in the plan
3) Actions are grouped by hosts and run in parallel across hosts. Actions on the same host run sequentially. `sc.exe` is used to start and stop services.
4) 










## CargoWise as a Prerequisite for PCO

First, the host that the PC will be installed on needs to have cargowise preinstalled- or more specifically: the orchestrator checks an `EnvironmentValid` flag on each PC host, which is true if CargoWise.Start.exe (the bootstrapper) already exists at 

`C:\Program Files\WiseTech Global\CargoWise\CargoWise.Start.exe`

## How Does Installation happen

The actual installation happens via `WinRM` (TODO: what is this?) and powershell remoting.

The orchestrator calls `Invoke-RemoteScript` over an encrypted WinRM connection to the target PC host. No SSH or RDP or VNC. PS over 5986 (SSL).

TODO where is the code that does this.

