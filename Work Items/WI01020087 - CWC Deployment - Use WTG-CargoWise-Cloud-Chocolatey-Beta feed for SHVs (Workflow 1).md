Context:
- proget is a binaries/packages repository
- It is a computer that hosts a bunch of packages such as npm, nuget, binaries, etc.
- It is accessible on the WiseTech network at https://proget.wtg.zone/ and a SAND version at https://proget.sand.wtg.zone/
![[Pasted image 20260128105031.png]]

Previous System
- We would use proget to host all binaries for PROD and proget sand for SAND environments
- When we deployed a product via DAT, we could pick from one of several deployment "targets". These targets are specified in the build.xml file and includes information such as build type (DEBUG, RELEASE) and deployment config (SAND, PROD).
- Our deployment targets are connected to a build deployer, after clicking deploy DAT hands control to our build deployer which has logic that reads the information provided by our build.xml and chooses what to do to deploy the product
- Typically this is just pushing the binaries to the right remote feed e.g. https://proget.wtg.zone/nuget/WTG-Chocolatey/
- Our projects consume them by pulling from a repo on demand [TODO: confirm if project is configured to pull from repo on demand or if we manually install it onto the server by going onto the server and fetching the file or what]

New System
- We are stopping using sand proget for deploying our sand projects. Sand proget is now for the proget team to test proget itself, which means it cannot reliably host binaries and packages for us
- The standard WiseCloud BuildDeployer now needs to push to ordinary proget as well
- To keep PROD and SAND binaries segregated, we will use separate feeds


More Detailed Info:
- Before we had targets for SAND and SAND ALPHA targets, copying the system of PROD and PROD ALPHA system for prod. However, we have decided to remove that feed.