AD Explorer is a RO tool that lets you inspect [[Active Directory]] (AD) without using PS or LDAP queries. The main use case is querying and navigating the AD in an intuitive way. It looks like this:
![[Pasted image 20260203145611.png]]

At wtg we have 3 main ADs for the 3 main environments: SAND (for testrigs), CORP (for wtg employees) and PROD (for customers). AD Explorer can be used for all 3 of these.

### CORP AD

You can access CORP AD through the domain `wtg.zone` and then using your wtg credentials to authenticate. If you type nothing in the box, AD will default to this as work laptops are AD joined.

![[Pasted image 20260203151305.png]]

You can search by filtering only relevant results, by class or attribute. For example, looking for the user entry corresponding to me:

![[Pasted image 20260203151125.png]]

The result:
![[Pasted image 20260203151155.png]]

Note: every query you make is visible to the sys admins, so don't go stalking other people.

### SAND AD

