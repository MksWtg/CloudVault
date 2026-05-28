Prerequisites: [[What is WiseCloud Accessor]], [[RDP vs Web]]

When a user double clicks a logo in the WCA client what happens in between this and the user being able to use cargowise?

It depends if they are using RDP or web.

# RDP

#### WiseCloudClientLegacy / WiseCloudTokenClient (your PC)

1. Double-click captured `ApplicationItemViewBehavior.AssociatedObject_MouseLeftButtonDown` fires, calls `applicationItem.AsyncRunCommand.Execute(null)`
2. RDS upgrade- before anything else progresses a check happens to make sure the latest RDS is installed. At the lowest level this happens in `TryInstallLatestPerUserRds`. It doesn't run if there is a flag saying install per machine (not per user), or if it cant find the installer, or if per RDS is up to date.
3. Get thumbprint (cached) `accessProvider.GetThumbprint()` sends a post request to the WCA frontend at `/WiseCloudAccessProviderService.svc/GetThumbprint`. This is received by `WiseCloudUnauthenticatedAccessProviderService.GetThumbprint()` then it calls `RdpSign.GetCertificateThumbprint()` which opens the certificate store on the frontend server and returns the sha of the certificate.
4. Get RDP file accessProvider.GetRdpFile(applicationType, applicationId, username, password, countryCode) another network call to the frontend.
5. Both calls go through WebWiseCloudAccessProvider which sits inside WebFailover — it injects the WCACFE sticky session cookie and retries fallback URLs if the primary fails.

#### WiseCloudAccessorServer (frontend IIS server the first server your request hits)

5. Receive GetRdpFile
WiseCloudAccessProviderController.GetRdpFile receives the POST

6. Validate and delegate
WiseCloudAccessProviderService.GetRdpFile validates credentials are not blank, confirms applicationType == "CW", then calls WiseCloudAccessorProviderServiceHelper.GetCWRdpFile

7. Find the instance
Calls SystemServices.Instance.CargoWiseOneInstanceClass.FindInstance(id, username, password) — but CargoWiseOneInstanceClass here is actually a BackendSystemServicesWrapper, which makes an HTTP call to the backend server (POST /BackendServices/FindCargoWiseInstance)

8. Resolve data centre
DataCenterMapping.GetDataCenterElement(domain, serverIp) — looks up the instance's domain and IP in the config to find which data centre it belongs to

9. Get CargoWise version
CargoWiseDatabaseInfoCache.GetApplicationVersionAndFeatureControl — calls backend (GET /BackendServices/GetCWApplicationVersionAndCWNextFeatureControlFlag) to find the CW version on that SQL server

10. Route to terminal server
TerminalServerRoutingService.ResolveTargetServerAsync — may call backend (GET /BackendServices/GetStatus) to check terminal server health, then picks one via TerminalServersLoadBalancer.GetTargetServer which calls (GET /BackendServices/FindAllComputers) to find servers in the AD OU, and (GET /BackendServices/GetStatusAndRDP) to check each one is healthy

11. Get parameter signature (if required)
Calls backend (POST /BackendServices/PostSignatureForInstance) — the backend signs the session parameters using a key from AD or Azure Key Vault

12. Build and return the RDP file
Frontend assembles the .rdp file content with: username, targetServer, RD Gateway hostname, databaseName, signature, workspace ID. Logs the connection details via NLog. Returns the file as a string.

-------------------------------------------------------------------------------------------------

📦 WiseCloudBackendServer (backend IIS server — never talked to directly by the client)

The backend handles all the calls the frontend delegates to it:

13. FindCargoWiseInstance
BackendServicesController.FindCargoWiseInstance → BackendServices.FindCargoWiseInstance → CargoWiseOneInstanceClass.FindInstance — queries Active Directory using System.DirectoryServices to find the CargoWise instance by name, authenticating with the user's credentials

14. GetCWApplicationVersionAndFeatureControlFlag
BackendServices.GetCWApplicationVersionAndCWNextFeatureControlFlag → DatabaseInfo.GetCWApplicationVersionAndCWNextFeatureControlFlag — connects to the SQL Server where CargoWise is installed and queries its version

15. GetStatusAndRDP / FindAllComputers
TerminalServerStatusProvider.GetStatusAndRDPAsync — queries each terminal server via WMI/RPC to check it's healthy and accepting connections. DirectorySearcher.FindAllComputers queries AD for all machines in the terminal servers OU

16. PostSignatureForInstance
BackendServices.PostSignatureForInstance → ParameterSignatureRetriever.PostSignatureForInstance — retrieves a signing key from AD (or Azure Key Vault in production), uses it to sign the session parameters so the terminal server can verify them

-------------------------------------------------------------------------------------------------

Back on your PC

17. Cache the RDP file
FileCache writes the .rdp file to %APPDATA%\<StartMenuGroup>\RDP\<appId>.rdp

18. Launch the RDP session
Tries MsRdpClientShell.StartWorkspaceEx(...) (Windows RemoteApp COM object) first — CargoWise appears as a seamless window. Falls back to mstsc.exe if that fails, after storing credentials with cmdkey.exe.

-------------------------------------------------------------------------------------------------

🌐 Windows RDP stack (no Accessor code from here)

19. Connect through RD Gateway
mstsc.exe / MsRdpClientShell opens an HTTPS connection to the RD Gateway on port 443. The gateway unwraps it and forwards RDP to the target terminal server on port 3389.

20. Authenticate on terminal server
The terminal server validates your credentials against Active Directory. Your Windows session starts, CargoWise launches as a RemoteApp.

21. You see CargoWise
# Web
