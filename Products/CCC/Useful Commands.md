
```sql
INSERT INTO	WiseCloudDeploymentService.dbo.UserSecurityGroup (Name, Domain) VALUES ('Cargowise Cloud', 'wtg.zone');
INSERT INTO WiseCloudDeploymentService.dbo.ApplicationRole (Name, Comment) VALUES ('Administrator', 'Administrator');

    /* This line of code create a mapping between UserSecurityGroup Cargowise Cloud and ApplicationRole Administrator */
INSERT INTO WiseCloudDeploymentService.dbo.UserSecurityGroupApplicationRole (ApplicationRoleId, UserSecurityGroupId)
VALUES (
	(SELECT Id FROM WiseCloudDeploymentService.dbo.ApplicationRole WHERE Name = 'Administrator'),
	(SELECT Id FROM WiseCloudDeploymentService.dbo.UserSecurityGroup WHERE Name = 'Cargowise Cloud')
);
```
