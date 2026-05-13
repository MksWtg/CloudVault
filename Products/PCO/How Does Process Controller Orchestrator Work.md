
Prerequisites: [[What is Process Controller Orchestrator]]

Fundamentally, Process Controller Orchestrator is a c sharp program that runs a loop. You can find the source code [here](https://github.com/WiseTechGlobal/CargoWiseCloud.ProcessControllerOrchestrator).

Every round (which occurs once every 5 minutes) the `EnvironmentNormalizationTask` runs.

There are PC host servers (physical servers/VM servers) in a data centre that run PC services. Maybe 10-20 host computers. Each of these needs to have cargowise on it.
1) Discovery:
	- What PC host servers exist in my data centre?
	- What customer instances exist in my domain










## CargoWise as a Prerequisite for PCO

First, the host that the PC will be installed on needs to have cargowise preinstalled. the orchestrator checks an `EnvironmentValid` flag on each PC host, which is true if CargoWise.Start.exe (the bootstrapper) already exists at 

`C:\Program Files\WiseTech Global\CargoWise\CargoWise.Start.exe`

The actual installation happens via `WinRM` (TODO: what is this?) and powershell remoting.

The orchestrator calles `Invoke-RemoteScript` over an encrypted WinRM connection to the target PC host. No SSH or RDP or VNC. PS over 5986 (SSL).

