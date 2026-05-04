
#### How will the migration be applied to PROD? or to any running instance of console in general.

```
  Migrations run automatically on startup. DatabaseInitializer.UpgradeDatabase() calls 
  dbContext.Database.MigrateAsync() and is invoked in both WebApi/Program.cs and ScheduledTasks/Program.cs before the
  app starts serving requests. So when you deploy, the schema changes + seed data (HasData inserts) are applied
  automatically. No manual dotnet ef database update needed in production.

  Risk note: The migration does a UPDATE to backfill LicenseTypeId on existing rows. If the production DB is large,
  this could briefly lock tables. Worth testing timing on a staging copy first.
```

#### Functional Testing Setup
```
it's essentially build and run. Here's the process:

To functional test locally:

 1. Build the WebApi project — open in Visual Studio or dotnet build Source\WebApi\WebApi.csproj
 2. Run it — use the "CargoWise Cloud Console" launch profile in Visual Studio, or dotnet run --project 
Source\WebApi\WebApi.csproj
 3. On startup, Program.cs line 20 calls DatabaseInitializer.UpgradeDatabase() → MigrateAsync() which automatically 
applies any pending migrations (including AddLicenceTypeAndDomainTables). This:
  - Creates the Domain and LicenseType tables
  - Seeds the 5 domains and 5 license types
  - Renames FK columns and backfills existing rows
 4. Open the frontend (started automatically if using the Frontend .sln) and test the dropdowns
 5. If you need auth setup, see Documentation/WebAPI/Authorization/AuthorizationDetails.md

Summary

 - No manual migration step needed — just build → run → it migrates automatically → test the UI
 - The connection string in your local appsettings.json/appsettings.Development.json determines which DB gets 
migrated
 - If you want a clean slate, you could drop and recreate the local DB — the migration will rebuild everything from 
scratch
```

#### Functional Tests That Must Run in Parallel
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

  1. Validation ---???? todo what is this

   - On a "wisecloud.zone" domain, only "Production" and "Test" license types are accepted for create
   - On "sand.wtg.zone", only "Sand" is accepted
```