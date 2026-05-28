RDS is a group of related microsoft technologies for doing RDP.

It includes 
- RD session host (the software that enables a machine to be a terminal server)
- RD gateway
- RD broker (the load balancer)
- RD licensing and remoteapp (idk what these are)

The full RDP hosting stack

When someone says they want to install RDS on a server, they mean install RD session host.

```powershell
Install-WindowsFeature RDS-RD-Server -IncludeManagementTools

Restart-Computer
```