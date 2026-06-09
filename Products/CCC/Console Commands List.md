Building the frontend:
```cmd
cd C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/ConsoleFrontend && npm run build && robocopy dist C:/git/GitHub/WiseTechGlobal/CargoWiseCloud.Console.git/Source/bin/WebApi/wwwroot /MIR
```

Recreating DB:
```cmd
cd C:\git\GitHub\WiseTechGlobal\CargoWiseCloud.Console.git\Source && dotnet ef database drop --context CloudConsoleAuditingDbContext --project Core\Core.csproj --force && dotnet ef database update --context CloudConsoleAuditingDbContext --project Core\Core.csproj
```

SQL Server insert admin role:
```SQL
INSERT INTO	WiseCloudDeploymentService.dbo.UserSecurityGroup (Name, Domain) VALUES ('Cargowise Cloud', 'wtg.zone');
INSERT INTO WiseCloudDeploymentService.dbo.ApplicationRole (Name, Comment) VALUES ('Administrator', 'Administrator');

/* This line of code create a mapping between UserSecurityGroup Cargowise Cloud and ApplicationRole Administrator */
INSERT INTO WiseCloudDeploymentService.dbo.UserSecurityGroupApplicationRole (ApplicationRoleId, UserSecurityGroupId)
VALUES (
	(SELECT Id FROM WiseCloudDeploymentService.dbo.ApplicationRole WHERE Name = 'Administrator'),
	(SELECT Id FROM WiseCloudDeploymentService.dbo.UserSecurityGroup WHERE Name = 'Cargowise Cloud')
);
```