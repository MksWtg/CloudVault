Instructions

```
RL5 23-Jul-25 10:32 GMT+10:00:

We postponed this as part of testrig setup. The creation of OU is complete, but move between OU may only be needed by testrig spin up and some code work in CargoWise.ActiveDirectory.DirectoryEntryWrapper

Please re-investigate and design.

  

  

RL5 21-Oct-24 16:34 GMT+11:00:

Create instance into environmental-specific OU via gMSA account has been done.

  

RL5 16-Aug-24 11:07 GMT+10:00:

The design is [Cloud - CCC - WI00782542 Detailed Design](https://wisetechglobal-my.sharepoint.com/:w:/p/ronan_liu/EdxpYJl7D9tPtvAlcv8YGcwB0Vzr6tEKR825MIwjhXc2Lg?e=rW3Mw5)

  

  

GRH 08-Aug-24 10:12 GMT+10:00:

  

New requirement for CW1 Spin up:

  

When creating a testrig, Dev's can specify if they need Service Tasks activated or not (since maybe their new feature doesn't need service tasks, and not enabling them saves CPU on our pool)

On the backend, this is handled by which OU the CW1 AD entry is placed in.

  

If CN=SH0,CN=WiseTech Global,CN=Program Data,DC=sand,DC=wtg,DC=zone, then no Service Tasks

If OU=OrchestratedSH0,OU=ASPAC,OU=Applications,OU=root,DC=sand,DC=wtg,DC=zone, then it has service tasks

  

Technically, we have the same requirement in PROD, but 'Non-Orchestrated' doesn't mean no Service Tasks, rather it means we want to manually install Service tasks for it, ask GRh to fetch the OU for PROD and TEST

  

We'll need a new field in Customer System 'Has Service tasks'. In SAND, default it to false, in PROD, default it to true, then depending on this field, put the CW1 AD entry in the right OU

  

We'll also need a webAPI endpoint that DAT can call to modify this field, and the Console should move the CW1 AD entry accordingly
```

What did we do (changes made):

```
 Add a PUT /CustomerSystem/updateServiceTask WebAPI endpoint that moves a CW1 Active Directory entry
  between the orchestrated and non-orchestrated OUs, controlling whether CargoWise runs service tasks for that
  instance. Updates the stored ADPath in the database to reflect the new OU. Includes unit tests covering move, no-op
  (already in correct OU), and not-found scenarios.
```

PR:

https://github.com/WiseTechGlobal/CargoWiseCloud.Console/pull/209/changes

Detailed summary:
Files changes: 10

