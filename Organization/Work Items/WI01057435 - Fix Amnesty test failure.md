Prerequisites: [[BuildDeployers]]

If `EnsureChocolateyInstalled` cannot get the chocolatey version, it assumes it needs to be installed. In the installation retry loop, it tries to install choco as a separate process with `powershell.exe "$tempDir\tools\chocolateyInstall.ps1"`. If this fails e.g. due to the MSI being occupied, the script does not report a failure. Then in `GetInstalledChocolateyVersion` after the install, we don't catch a relevant exception so the retry loop fails, making it pointless.

### Before the change?

Transient install failure crashes retry loop.

### After the change?

Transient install failure does not crash retry loop, retry loop can proceed.

### Note

Another way of solving this issue would be checking `LASTEXITCODE` in the powershell script. This would be a bigger change, and this is a very niche edge case anyway, so I decided not to make it.