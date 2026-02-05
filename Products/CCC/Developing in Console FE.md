
For some silly reason, the ordinary build process of npm run dev (exposing FE at 5173) and running dotnet build (exposing BE at 7170) does not work. Requests are not proxied correctly. The QGL build method serves the FE and exposes BE at 7170- FE are served as static files from /Bin/WebApi/wwwroot.

Problem:
- Whenever we make a frontend change, we cannot run npm run dev as it will not connect to backend, requests don't go through
	- See `Comparison of Methods of Running CCC` for why

Solution:
- Since actual builds are very short, just do what QGL does (instructions below)

## How QGL Builds Console FE (Not a .NET Project)
- Runs the following commands after a build

1) `cmd /c "cd /d ..\ConsoleFrontend\  && npm install  && npm run format && npm run build"`
2) `cmd /c "robocopy ..\ConsoleFrontend\dist ..\Bin\WebApi\wwwroot /MIR & IF %ERRORLEVEL% LSS 8 (exit 0) ELSE (exit %ERRORLEVEL%)"`

Or

1) `cd C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/ConsoleFrontend && npm run build`
2) `robocopy C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/ConsoleFrontend/dist C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/bin/WebApi/wwwroot /MIR`

## Comparison of Methods of Running CCC

### QGL

1) Checkout main and QGL full build
2) Navigate to `Source\bin\WebApi` and then run `CargoWiseCloudConsole.WebApi.exe`
3) Visit `localhost:7170`

- `7170` is the port the backend is accessible from, you can hit any API endpoints from this port and access swagger at `http://localhost:7170/swagger/index.html`
- The reason the frontend is also served at `7170` is because of ASPNET settings
	- We run the exe from `Source\bin\WebApi`
	- Content root becomes `Bin/WebApi`
	- Web root (where static files are served from) becomes `Bin/WebApi/wwwroot`
	- In program config we have:  `webApplication.UseStaticFiles();` and `webApplication.UseDefaultFiles();`
	- That directory contains the FE build because the robocopy task put it there
### Debug

1) Build backend through VS debugger at `7170`
2) Run frontend through `npm run dev` at `5173`
3) Access the application at `7170` (backend), all requests that are NOT to controllers are proxied to FE

For development, we want hot reload. Since the QGL method precompiles and serves static files it is impossible to reconcile that method with a live server. So we must go for option 'B'
### Authentication Differences

Problem:
- Requests made at `7170` to authorized API endpoints are returning HTML, chat GPT reckons this is because there is no NTLM so it falls back to serving XTML
1) Frontend sends `GET http://localhost:7170/security/authorized-apis`
2) The browser does not include `Authorization` header
3) ASPNET sees  unauthenticated request to  protected endpoint
	1) Controller requires `[Authorize(Policy = RequireViewerOrHigher)]`
4) ASPNET returns 401
5) Chrome does not consider the origin trusted for Windows Auth, it sees failed network request
6) In error interceptor we aren't handling 401, so Axios does rejects the 401, error handler navigates back to "/" which causes the SPA to reload and the dev server (Vite) serves index.html
7) How does the QGL method handle NTLM? frontend files are also being served from ASPNET, so the browser considers this same origin

Solution:
- Send authentication