
```
please confirm that (at the ui level) the following: if we wanted to change this to prod only, or both, that it is a
   simple fix and that the method in the backend is flexible enough to swap to the OUs given by the prod license      

● Yes, confirmed on both points.

  Frontend: The column visibility is controlled by a single check in isProductionEnv() (line ~520):

   if (!(await environment.isProduction())) {
       this.columns.splice(..., { key: 'serviceTaskEnabled', ... });
   }

  To show it in prod too, just remove the if wrapper. To show only in prod, flip to if (await
  environment.isProduction()).

  Backend: GetTargetOUPath already handles all license types — including Production:

   LicenseType.Production => $"/root/Applications/{region}/{dataCentre}"          // orchestrated
   LicenseType.Production => $"/root/Applications-Other/NonOrchestrated/{region}/{dataCentre}"  // non-orchestrated

  The endpoint doesn't care about environment — it takes the DataCentre and LicenseType from the customer system
  entity and resolves the correct OU. No backend changes needed.
```