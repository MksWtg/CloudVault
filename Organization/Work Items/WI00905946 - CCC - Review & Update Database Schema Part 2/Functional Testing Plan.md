
```
 How migrations are applied to production

  Yes, migrations run automatically on startup. DatabaseInitializer.UpgradeDatabase() calls 
  dbContext.Database.MigrateAsync() and is invoked in both WebApi/Program.cs and ScheduledTasks/Program.cs before the
  app starts serving requests. So when you deploy, the schema changes + seed data (HasData inserts) are applied
  automatically. No manual dotnet ef database update needed in production.

  ⚠️ Risk note: The migration does a UPDATE to backfill LicenseTypeId on existing rows. If the production DB is large,
  this could briefly lock tables. Worth testing timing on a staging copy first.
```



```
  Functional Testing Plan

  1. API — License Types dropdown

   - GET /lookup/license-types → returns all 5 types with {id, name, domainName}
   - GET /lookup/domains → returns all 5 domains

  2. Frontend — Dropdowns populate

   - Create Customer System form → LicenseType dropdown shows all 5 options
   - Search Customer Systems → LicenseType filter dropdown works
   - Same for IIS Servers and SQL Servers create/search forms

  3. Create Customer System end-to-end

   - Create with LicenseType = "Sand", verify it saves and displays correctly
   - Create with invalid LicenseType → should get validation error

  4. Environment endpoint

   - GET /environment/is-production → returns {isProduction: true} on prod domain, false on sand

  5. Database Server CRUD

   - POST (Add) a new database server → 200 OK
   - POST same server again → 409 Conflict
   - PUT (Update) an existing server → 200 OK
   - PUT a non-existent server → 404
   - GET /search with LicenseType filter → correct results

  6. Existing data integrity

   - After migration, existing CustomerSystem records still have correct LicenseType (old enum 0→1 ID mapping)
   - Existing DatabaseServer, IISServer records likewise correct

  7. Validation

   - On a "wisecloud.zone" domain, only "Production" and "Test" license types are accepted for create
   - On "sand.wtg.zone", only "Sand" is accepted
```