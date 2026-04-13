PR: [https://github.com/WiseTechGlobal/CargoWise/pull/46286/changes#r3055083627](https://github.com/WiseTechGlobal/CargoWise/pull/46286/changes#r3055083627)

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
	1) Create 3 VMs- two SQL server hosts and 1 domain controller and network share
	2) Create cluster
	3) Have backup on local first VM, try the restore, expect a failure mid way (ask patrick for logs, look for logs in the old system)
2) For the fix
	1) Try running the dbbr tool with the fix code, there should be an error

```csharp
if (inaccessible.Count > 0)
			{
				throw new DbBackupAndRestoreException(
					string.Format(CultureInfo.InvariantCulture,
						"The following secondary replicas cannot access the backup file:\r\n{0}\r\nEnsure the backup file is on a network share accessible by all secondary SQL Server service accounts.",
						string.Join("\r\n", inaccessible)));
			}
```

What should this error do?

We want this to cascade up the call stack until it hits some sort of dialog box.


## Prompt

I want to do the following test.

Context:
- Defect: my backup tool (wrapper around sql server backup and restore) does not check if database backups are reachable by all servers in the AG cluster.
- I have made the fix, I need to functionally test it.

Setup
- make three VMs, two of them sql server hosts and one of them as a network file share

Reproducing defect
- put a .bak onto one of the SQL server hosts but not the other (so the backup is only accessible from one)
- try use the tool, expect a crash/error logs mid run after restoring the first DB

Testing fix:
- try again with the new tool, this time an error dialog pops up before restore starts (no partial restore)

Functional regression testing
- put the .bak on the network share
- restore should work properly

Is this functional testing plan ok?