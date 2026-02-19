
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

DONE: WI links are updated