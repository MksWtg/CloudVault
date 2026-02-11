Detailed notes are in [[WI01027739 - CCC - Frontend is Hot Reloadable]]

Just thinking out loud here

OLD:
7170 -> serves frontend static
7171 -> N/A

NEW
7170 -> proxies to 5173
7171 -> serves frontend

TODO:
03:25:57.5638|The WebRootPath was not found: C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Console.git\Source\WebApi\wwwroot. Static files may be unavailable.

TODO:

extract 5173 url to a common place DONE

TODO:
fix warning
logger.LogInformation($"Frontend is running live, SPA requests proxied to {viteUri}"); DONE

checklist of things that need to work:
- running backend wtih debugger and frontend running vs not vs cypress
- running exe with frontend running vs not vs cypress
- installing after build as a service with frontend running vs not vs cypress

## Functional Testing
Need to test these scenarios:

|                   | Frontend: npm run dev | Frontend: static | Frontend: cypress |
| ----------------- | --------------------- | ---------------- | ----------------- |
| Backend: Debugger |                       |                  |                   |
| Backend: Exe      |                       |                  |                   |
| Backend: Service  |                       |                  |                   |
Also, test npm:startall