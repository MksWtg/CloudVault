AD Explorer is a RO tool that lets you inspect [[Active Directory]] (AD) without using PS or LDAP queries. The main use case is querying and navigating the AD in an intuitive way, like file explorer. It looks like this:
![[Pasted image 20260203145611.png]]

At WTG we have 4 main ADs for the 3 main environments: SAND (for testrigs), CORP (for wtg employees) and PROD/TEST (for customers). AD Explorer can be used for all of these.

### CORP AD

You can access CORP AD through the domain `wtg.zone` and then using your wtg credentials to authenticate. If you type nothing in the box, AD will default to this as work laptops are AD joined.

![[Pasted image 20260203151305.png]]

You can search by filtering only relevant results, by class or attribute. For example, looking for the user entry corresponding to me:

![[Pasted image 20260203151125.png]]

The result:
![[Pasted image 20260203151155.png]]

Note: every query you make is visible to the sys admins, so don't go stalking other people.

### SAND AD
- Domain is `sand.wtg.zone`
- Username and pword are blank

### PROD AD/TEST AD
- Domain for PROD is `wisecloud.zone`
- Domain for TEST is `test.wisecloud.zone`
- TODO: Figure out username and pword, and if I need to be on jump host to access 

### Some Interesting Records

Orchestrated Test Rigs: `OU=OrchestratedSH0,OU=ASPAC,OU=Applications,OU=root,DC===sand==,DC=wtg,DC=zone,==sand==.wtg.zone`

SQL Servers:`OU=SQL,OU=AU2,OU=ASPAC,OU=Servers,OU=Computers,OU=root,DC===sand==,DC=wtg,DC=zone,==sand==.wtg.zone`

