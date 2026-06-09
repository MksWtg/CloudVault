
1) Create unorchestrated instance. Verify:
	1) checkbox is disabled on get customer page
	2) AD path is unorchestrated in DB:  `/root/Applications/ASPAC/OrchestratedSH0/code/instancename`
	3) record exists in AD (go to AD and look for record)
2) Toggle using checkbox. Verify:
	1) checkbox is checked in but greyed out (cannot click)
	2) While greyed out, database pending service task change is set to true
	3) while greyed out you cannot click it
	4) while greyed out, clock icon appears and on hover a tooltip