Product: [[What is Console]]
Detailed notes are in [[WI01027739 - CCC - Frontend is Hot Reloadable]]

Old system:
- To use, access frontend at 7170 and all requests to frontend

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
Also, test `npm run start:all` and `npm run start-and-cy-test`

## Update

```
Please read through all the documentation to make sure it is accurate. In getting started for developers we want one method, the easiest, to recommend to new devs. I think npm run dev for FE and double clicking exe in the BE. I think this is already there but check. Somewhere else in the docs we need to explain there are 3 methods to running the frontend and backend and ideally they can all be run in parallel (this excludes service tasks and is only for testing the web api), please put this in the appropriate place and make sure there is no duplicate docs.
```