
Ok... what is going on in this defect?

1) Murray reports that a customer is experiencing weird issues and getting kicked off cargowise. [Murray Grant: Assistance Request: CargoWise "crash" for customer | Product-Development (all staff) > General | Microsoft Teams](https://teams.microsoft.com/l/message/19:9ebf2b2fa75e4a728d27674ca62554b8@thread.skype/1769746297192?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=c9fbec07-f470-451e-a107-255c9b777d30&parentMessageId=1769746297192&teamName=Product-Development%20\(all%20staff\)&channelName=General&createdTime=1769746297192 "https://teams.microsoft.com/l/message/19:9ebf2b2fa75e4a728d27674ca62554b8@thread.skype/1769746297192?tenantId=8b493985-e1b4-4b95-ade6-98acafdbdb01&groupId=c9fbec07-f470-451e-a107-255c9b777d30&parentMessageId=1769746297192&teamName=Product-Development%20(all%20staff)&channelName=General&createdTime=1769746297192")
	1) Yaakov offers to raise a CR6 and asks for information such as username, time, name of machine they were on (session host)
	2) Murray says, how can I find the RDP machine they are connected to?
	3) Yaakov says check the WCA logs for where the user got routed to on their last login before $timestamp
	4) Zeynep suggests exactly which logs to look for: https://kibana.apac-prod-1.wtg.zone/s/cargowisecloud/app/r/s/Ue25v