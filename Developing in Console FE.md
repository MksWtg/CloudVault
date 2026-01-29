For some silly reason, the ordinary build process of npm run dev (exposing FE at 5173) and running dotnet build (exposing BE at 7170) does not work. Requests are not proxied correctly. The QGL build method serves the FE and exposes BE at 7170- FE are served as static files from /Bin/WebApi/wwwroot.

Problem:
- Whenever we make a frontend change, we cannot run npm run dev as it will not connect to backend, requests don't go through
	- TODO: investigate why

Solution:
- Since actual builds are very short, just do what QGL does (instructions below)

# How QGL Builds Console FE (Not a .NET Project)
- Runs the following commands
<Exec Command="cmd /c &quot;cd /d ..\ConsoleFrontend\  &amp;&amp; npm ci  &amp;&amp; npm run check-format  &amp;&amp; npm run build&quot;" Condition="$(ConfigurationName) == RELEASE" />
<Exec Command="cmd /c &quot;cd /d ..\ConsoleFrontend\  &amp;&amp; npm install  &amp;&amp; npm run format  &amp;&amp; npm run build&quot;" Condition="$(ConfigurationName) == DEBUG" />
<Exec Command="cmd /c &quot;robocopy ..\ConsoleFrontend\dist ..\Bin\WebApi\wwwroot /MIR &amp; IF %ERRORLEVEL% LSS 8 (exit 0) ELSE (exit %ERRORLEVEL%)&quot;" />