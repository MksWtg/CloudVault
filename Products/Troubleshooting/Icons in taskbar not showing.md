
In the taskbar sometimes on startup and restart some of the apps don't have logos. You can get these logos by clearing the cache with the command:

```cmd
taskkill /IM explorer.exe /F
del /F /Q "%localappdata%\IconCache.db"
del /F /Q "%localappdata%\Microsoft\Windows\Explorer\iconcache*"
start explorer.exe
```