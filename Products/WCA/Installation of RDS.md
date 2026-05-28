
> This process says RDS- it does not refer to microsoft's RDS but WTG's special RDS. It comes from https://github.com/WiseTechGlobal/CargoWise.RemoteDesktopServices/tree/master


RDS needs to be installed on the client to enable a user to connect to the session host/RD session host/cargowise host via RDP.

Installation/upgrade is checked when you double click an RDP icon to open cargowise via RDP.

#### There are 2 WCA Installers

If you use the old WiseCloudClient.Installer, it installs RDS per machine
- this is at `%ProgramFiles(x86)%\WiseTech Global\...` and requires admin

If you use the new CargoWiseCloudAccessor.Client.Installer, it installs RDS per user
- this is at `%LocalAppData%\WiseTech Global\...` 