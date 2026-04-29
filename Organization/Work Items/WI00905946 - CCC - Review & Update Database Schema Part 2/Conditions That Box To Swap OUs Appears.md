
```
Backend (always enforced):

 - [Authorize(Policy = Policies.RequireOperatorOrHigher)] — user must have Operator or Admin role

Frontend (UI-level):

 - Checkbox only appears in non-production environments (the serviceTaskEnabled column is only added when 
environment.isProduction() returns false)
 - Checkbox is disabled if user lacks permission for 
PUT-CustomerSystemController.CustomerSystemUpdateServiceTaskAsync
 - Checkbox is disabled if the system is not Active (e.g. Activating, Deactivating, Removing)
 - Checkbox is disabled if an update is already in flight for that row
```