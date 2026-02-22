
Ok... what is going on in this defect?

1) Murray reports that a customer is experiencing weird issues and getting kicked off cargowise. [Murray Grant: Assistance Request: CargoWise "crash" for customer | Product-Development (all staff) > General | Microsoft Teams](https://teams.microsoft.com/l/message/19:9ebf2b2fa75e4a728d27674ca62554b8@thread.skype/1769746297192?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=c9fbec07-f470-451e-a107-255c9b777d30&parentMessageId=1769746297192&teamName=Product-Development%20\(all%20staff\)&channelName=General&createdTime=1769746297192 "https://teams.microsoft.com/l/message/19:9ebf2b2fa75e4a728d27674ca62554b8@thread.skype/1769746297192?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=c9fbec07-f470-451e-a107-255c9b777d30&parentMessageId=1769746297192&teamName=Product-Development%20(all%20staff)&channelName=General&createdTime=1769746297192")
	1) Yaakov offers to raise a CR6 and asks for information such as username, time, name of machine they were on (session host)
	2) Murray says, how can I find the RDP machine they are connected to?
	3) Yaakov says check the WCA logs for where the user got routed to on their last login before $timestamp
	4) Zeynep suggests exactly which logs to look for: https://kibana.apac-prod-1.wtg.zone/s/cargowisecloud/app/r/s/Ue25v. Searching by WCA username (mfi.eric.fernandez@wisecloud.zone) TODO: how did they find the correct username?
2) Murray accesses link to view logs
	1) Murray does not have permission: ![[Pasted image 20260219171501.png]]
	2) Murray finds the right cloud access package (presumably with Zeynep's help) and requests access
3) Zeynep sends link for CWC PROD readonly: https://myaccess.microsoft.com/@WiseTechGlobal.onmicrosoft.com#/access-packages/146ffef3-1b62-4d82-968b-cceceabf3c75
4) Zeynep resolves to update documentation to make the access package link clearer, as it currently points to [this link](https://myaccess.microsoft.com/@WiseTechGlobal.onmicrosoft.com#/access-packages/active/c4ed3e49-64b2-4a47-b12d-1802f7602254), which is empty: ![[Pasted image 20260219171746.png]]. Presumably murray had issues as he tried to use this link which is out of date
5) Zeynep creates WI with the above instructions

### Done Statement

DONE: WCA out of date links are updated

### Steps

1) Query for all md files
2) Visit all links in all md files
3) Update all broken links

#### 1)
`PS C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git> Get-ChildItem -Path "." -Recurse -Filter *.md -File`
(roughly 40 files)

```
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\README.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\.github\pull_request_template.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\CLI Commands.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\DeploymentGuide.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\NewServerSetup.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\README.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\Server List.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\New Deployment\Architecture.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Deployment\New Deployment\Server List.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\BackwardsCompatibilityTesting.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\ClientInstallerDelivery.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\GetClientIpAddress.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\InternationalFailover.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\README.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\Parameter Signing\CW1 Parameter Signing.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\Parameter Signing\Updating WCA parameter signing keys.md
[DONE]C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\WorkInProgress\AppManagerRemoval.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\WorkInProgress\BackwardsCompatibilityTesting.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\WorkInProgress\DeploymentProcessUplift.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Design\WorkInProgress\ServerMSIPackaging.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\Automated Integration Testing.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\Dev Dependencies to Install.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\Functional Testing.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\Load Testing.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\Local Testing.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Development\README.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\README.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\Logging\README.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\BackEndPasswordScomResolution.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\BackEndScomResolution.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\Discovery.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\FrontEndScomResolution.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\Resolution.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Monitoring\SCOM\TerminalServerScomResolution.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Documentation\Requirements\README.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Source\Deployment.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Source\README.md
C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Accessor.git\Source\bin\all\Deployment\CargoWiseCloudDeployment.1.0.0.362\README.md
```