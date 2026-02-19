
Source: https://github.com/WiseTechGlobal/CargoWiseCloud.Content/blob/main/Home%2FProjects%2FCargoWise-Web-Version-Server-Management%2FFAQ.md

CargoWise Web Version is an update to CargoWise. The old version, which at the time of writing most customers are still using, is referred to as the "RDP" version as it is served over [[RDP]]. The new version is served over the browser, over HTTPS, using a WebView to embed it into a C# desktop client. It is called the cargowise web version, or CWWV.

![[Pasted image 20260219111415.png]]

Unfortunately, we cannot access the web version via the web as we need access to the windows registry. So it is accessed via a thin desktop client.