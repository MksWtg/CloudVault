Prerequisites: [[What is WiseCloud Accessor]]

When a user double clicks a logo in the WCA client what happens in between this and the user being able to use cargowise?

1) User double clicks an icon on the client page `ApplicationItemViewBehavior.AssociatedObject_MouseLeftButtonDown`. This checks the registry to confirm whether single or double click is configured, then it calls `applicationItem.AsyncRunCommand.Execute(null)`.
2) This calls `ApplicationItemBaseViewModel.RunCommand` which checks teh target type of the application and branches into one of three paths
	1) RDP
	2) WEB
	3) Winzor