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
	- this was the cause of the initial incident, you can do more robust testing with path exists but permission denied, path exists but network unreachable timeout, path accessible from primary but not secondary and vice versa
- try use the tool, expect a crash/error logs mid run after restoring the first DB

Testing fix:
- try again with the new tool, this time an error dialog pops up before restore starts (no partial restore)
	- we can make this condition more explicit and verifiable with "no db created on any node", can check `sys.databases`

Functional regression testing
- put the .bak on the network share
- restore should work properly

What I have done:
- created an sql server hyper V VM with sql server
- created a fileshare hyper V VM with a fileshare folder
- I have the .bak on my host laptop that the VMs are on
- What do i need to do the first test
---

Is this functional testing plan ok?

Edit: have added edits

## Creds

unam: `Administrator`
pwod: `DBBRtest123`

Sql server admin: `SqlServerAdmin` (username is `sa`)
Creating cert: `YourStrongPassword1!`

![[Pasted image 20260413143726.png]]
![[Pasted image 20260413144710.png]]

`WIN-82Q6UCMNIK0`

## Node 1

hostname: `sqlnode1`
![[Pasted image 20260414103323.png]]

![[Pasted image 20260414103408.png]]

## Node 2

![[Pasted image 20260414105120.png]]
![[Pasted image 20260414105312.png]]

## FileshareVM

hostname: `Fileshare`
Settings

![[Pasted image 20260414110558.png]]

remember the hostname for sqlnode1 is `sqlnode1` and for sqlnode2 it is `SqlNode2`

## Helpful commands

to move the certs:

run this on node 1

**push the cert**
```
copy C:\Certs\NODE1_Cert.cer \\Fileshare\fileshare\NODE1_Cert.cer
```

**pull the cert**
```
copy \\Fileshare\fileshare\NODE2_Cert.cer C:\Certs\NODE2_Cert.cer
```

run this on node 2

**push the cert**
```
copy C:\Certs\NODE2_Cert.cer \\Fileshare\fileshare\NODE2_Cert.cer
```

**pull the cert**
```
copy \\Fileshare\fileshare\NODE1_Cert.cer C:\Certs\NODE1_Cert.cer
```

## Query Catalogue

To create certs:

on node 1
```SQL
-- Create master key
USE master;
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'YourStrongPassword1!';

-- Create certificate
CREATE CERTIFICATE NODE1_Cert
WITH SUBJECT = 'NODE1 AG Certificate',
EXPIRY_DATE = '2030-01-01';

-- Create the hadr endpoint using the cert
CREATE ENDPOINT Hadr_endpoint
STATE = STARTED
AS TCP (LISTENER_PORT = 5022)
FOR DATABASE_MIRRORING (
    AUTHENTICATION = CERTIFICATE NODE1_Cert,
    ROLE = ALL
);

-- Back up the cert so Node2 can trust it
BACKUP CERTIFICATE NODE1_Cert
TO FILE = 'C:\NODE1_Cert.cer';
```

on node 2
```SQL
USE master;
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'YourStrongPassword2!';

CREATE CERTIFICATE NODE2_Cert
WITH SUBJECT = 'NODE2 AG Certificate',
EXPIRY_DATE = '2030-01-01';

CREATE ENDPOINT Hadr_endpoint
STATE = STARTED
AS TCP (LISTENER_PORT = 5022)
FOR DATABASE_MIRRORING (
    AUTHENTICATION = CERTIFICATE NODE2_Cert,
    ROLE = ALL
);

BACKUP CERTIFICATE NODE2_Cert
TO FILE = 'C:\NODE2_Cert.cer';
```

#### Trusting

```SQL
USE master;

CREATE LOGIN NODE2_Login WITH PASSWORD = 'YourStrongPassword2!';
CREATE USER NODE2_User FOR LOGIN NODE2_Login;

CREATE CERTIFICATE NODE2_Cert
AUTHORIZATION NODE2_User
FROM FILE = 'C:\Certs\NODE2_Cert.cer';

GRANT CONNECT ON ENDPOINT::Hadr_endpoint TO NODE2_Login;
```

```SQL
USE master;

CREATE LOGIN NODE1_Login WITH PASSWORD = 'YourStrongPassword1!';
CREATE USER NODE1_User FOR LOGIN NODE1_Login;

CREATE CERTIFICATE NODE1_Cert
AUTHORIZATION NODE1_User
FROM FILE = 'C:\Certs\NODE1_Cert.cer';

GRANT CONNECT ON ENDPOINT::Hadr_endpoint TO NODE1_Login;
```

#### Firewall down:

allowing AG to run
```bash
netsh advfirewall firewall add rule name="AG Endpoint" dir=in action=allow protocol=TCP localport=5022
```

