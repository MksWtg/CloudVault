Description:

```
M22 09-Apr-26 11:18 GMT+10:00:

  

In this incident [CS02292376 - AHARTRHAM - Enterprise DB Backup and Restore exe - Failure without Error Message](https://ediprod.cw.wisetechglobal.com/link/ShowEditForm/SupportIncident/4102a3a6-20b0-4ac9-a3d0-c7be98274fd1?lang=en-gb) the customer had previously accidentally tried to initiate a DBBR to an AG with the .bak stored locally on the same machine as the primary replica, rather than a network share.

The secondary replica was unable to access the file since it was local and not on a network share, and so DBBR worked for the primary replica but failed mid run for the secondary.

Add a check using SQL server xp_fileexist, or one of the existing CS methods that wraps xp_fileexist in DBBR before commencing with the restore.

  

---

Some more info

---

  

A check to see if the resource exists seems like a pretty fundamental thing. Why has noone done this so far?

  

I suspect initially back in '07 DBBR did not support AGs (AGs as they exist now were released in 2012). Back then, you would be able to select a local file to restore from. And so if you were able to select the file locally, it obviously existed and was reachable, so there was no problem. This local file system selection remains today, you can only select local files not network share ones.

  

After adding support for AGs we never updated this. The way to use DBBR for AG (or any kind of backup/restore across multiple machines, like in CP2T) is to paste the location to the network share .bak into the tool rather than navigating to it in a file explorer, which is pretty jank.

  

Maybe the recommended approach was to have the network share on the primary replica machine, i'm not sure. (optional: do some investigation into DBBR history to confirm this, although this may be a waste of time since the commits go back 20 years so use your discretion).
```

How to functional test?

1) Reproduce defect
	1) Create 3 VMs- two SQL server hosts and 1 domain contro