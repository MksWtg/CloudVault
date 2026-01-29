For some silly reason, the ordinary build process of npm run dev (exposing FE at 5173) and running dotnet build (exposing BE at 7170) does not work. Requests are not proxied correctly. The QGL build method serves the FE and exposes BE at 7170- FE are served as static files from /Bin/WebApi/wwwroot.

Problem:
- Whenever we make a frontend change, we cannot run npm run dev as it will not connect to backend, requests don't go through
	- TODO: investigate why

Solution:
- Since actual builds are very short, just do what QGL does (instructions below)

# How QGL Builds Console FE (Not a .NET Project)
- Runs the following commands after a build

1) `cmd /c "cd /d ..\ConsoleFrontend\  && npm install  && npm run format  && npm run build"`
2) `cmd /c "robocopy ..\ConsoleFrontend\dist ..\Bin\WebApi\wwwroot /MIR & IF %ERRORLEVEL% LSS 8 (exit 0) ELSE (exit %ERRORLEVEL%)"`

Or 

1) `cd C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/ConsoleFrontend && npm run build`
2) `robocopy C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/ConsoleFrontend/dist C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/bin/WebApi/wwwroot /MIR & IF %ERRORLEVEL% LSS 8 (exit 0) ELSE (exit %ERRORLEVEL%)`
