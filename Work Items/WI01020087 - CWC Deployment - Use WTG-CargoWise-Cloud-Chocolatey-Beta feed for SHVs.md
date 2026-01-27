Context:
- proget is a binaries/packages repository
- It is a computer that hosts a bunch of packages such as npm, nuget, binaries, etc.
- It is accessible on the wisetech network at https://proget.wtg.zone/ and a SAND version at https://proget.sand.wtg.zone/

Previous System
- We would use proget to host all binaries for PROD and proget sand for SAND environments
- When we deployed a product via DAT, we could pick from one of several deployment "targets". These targets are specified in the build.xml file and includes information such as build type (DEBUG, RELEASE) and deployment config (SAND, PROD).
- Our deployment targets are connected to a build deployer, after clicking deploy DAT hands control to our build deployer which has logic that reads the information provided by our build.xml and chooses what to do to deploy the product
- Typically this is just pushing the binaries to the right remote feed e.g. https://proget.wtg.zone/nuget/WTG-Chocolatey/
- Our projects consume them by pulling from a repo on demand