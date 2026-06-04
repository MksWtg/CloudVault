
Can you please verify the following for me:
- SAND gmsa SAND\s_gMSA_CWCCNSLR$ does not have create and delete perms in SAND orc OU
	- OU=OrchestratedSH0,OU=ASPAC,OU=Applications,OU=root,DC=sand,DC=wtg,DC=zone
- SAND gmsa SAND\s_gMSA_CWCCNSLR$ does not have create and delete perms in SAND non orc OU 
	- OU=Non-Orchestrated,OU=ASPAC,OU=Applications,OU=root,DC=sand,DC=wtg,DC=zone
- PROD gmsa PROD\s_gMSA_CWCCNSLR$ does not have create and delete perms in PROD orc OU
	- OU=Applications,OU=root,DC=wisecloud,DC=zone
- PROD gmsa PROD\s_gMSA_CWCCNSLR$ does not have create and delete perms in PROD non orc OU
	- OU=NonOrchestrated,OU=Applications-Other,OU=root,DC=wisecloud,DC=zone

If any of the above is not the case please let me know.

If it is the case, can you please grant those perms WITH INHERITANCE as the actual records are in OUs corresponding to data centers within the larger OU
- SAND gmsa SAND\s_gMSA_CWCCNSLR$ can create and delete records in SAND orc OU
	- OU=OrchestratedSH0,OU=ASPAC,OU=Applications,OU=root,DC=sand,DC=wtg,DC=zone
- SAND gmsa SAND\s_gMSA_CWCCNSLR$ can create and delete records in SAND non orc OU
	- OU=Non-Orchestrated,OU=ASPAC,OU=Applications,OU=root,DC=sand,DC=wtg,DC=zone
- PROD gmsa PROD\s_gMSA_CWCCNSLR$ can create and delete records in PROD orc OU
	- OU=Applications,OU=root,DC=wisecloud,DC=zone
- PROD gmsa PROD\s_gMSA_CWCCNSLR$ can create and delete records in PROD non orc OU
	- OU=NonOrchestrated,OU=Applications-Other,OU=root,DC=wisecloud,DC=zone