
Consider the product WCA ([[What is WiseCloud Accessor]]). It is a product used to access CargoWise. When our customers open the app, they are using their own computing power to run the logic of WCA (or the client portion at least).

WiseTech itself is self hosted and therefore a user of WCA. But 
1) We want slightly different configurations when we give our customers. For example, we have our own AD, where to get RDP sign certificates, defaults for legacy/token authentication, etc.
2) On top of this we would like to get to functionally test WCA with real customers before rolling out changes to customers.

To solve both these problems, we create "deployment environments" known 