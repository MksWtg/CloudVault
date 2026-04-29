
# Functional Testing Plan: Service Task Toggle (AD OU Move)

## Feature Summary

Operators can toggle whether a CW1 customer system has service tasks enabled/disabled via a checkbox in the Console UI. This moves the system's AD entry between orchestrated and non-orchestrated OUs. The feature is only available in non-production (SAND) environments.

---

## Setup / Prerequisites

### Environment
- **SAND environment** (non-production) — the toggle is only visible in non-production
- Console WebAPI running and accessible
- Active Directory accessible from the WebAPI host (the AD move is a real `MoveTo` call)
- User account with **Operator** or higher role (viewers cannot toggle)

### Test Data
- At least one customer system in **Active** state (e.g. `ATCTST`)
- At least one customer system in a **non-Active** state (e.g. Activating, Deactivated) for negative testing
- Know the current ADPath of each test system before testing (query the DB or inspect the details panel)

### Tools
- Console UI (browser)
- SQL Server Management Studio or equivalent (to verify DB state)
- AD Users and Computers or `Get-ADObject` PowerShell (to verify AD OU placement)
- Swagger/curl for direct API testing

---

## Test Cases

### 1. UI Visibility

| # | Test | Steps | Expected Result |
|---|------|-------|-----------------|
| 1.1 | Column visible in SAND | Navigate to Customer Systems page in SAND | "Service Tasks?" column is visible in the table |
| 1.2 | Column hidden in PROD | Navigate to Customer Systems page in PROD | "Service Tasks?" column does not appear |

### 2. Checkbox State & Permissions

| # | Test | Steps | Expected Result |
|---|------|-------|-----------------|
| 2.1 | Enabled for Active system (Operator) | Log in as Operator, find an Active customer system | Checkbox is interactive (not disabled) |
| 2.2 | Disabled for non-Active system | Find a system in Activating/Deactivated state | Checkbox is visible but disabled (greyed out) |
| 2.3 | Disabled for Viewer role | Log in as Viewer, find an Active customer system | Checkbox is visible but disabled |

### 3. Toggle: Enable Service Tasks (non-orchestrated → orchestrated)

| # | Step | Action | Verification |
|---|------|--------|-------------|
| 3.1 | Pre-condition | Identify a system with service tasks **disabled** (checkbox unchecked). Record its current ADPath from DB. | ADPath contains non-orchestrated OU (e.g. `/root/Applications/ASPAC/Non-Orchestrated/...`) |
| 3.2 | Toggle | Click the checkbox to enable service tasks | Checkbox becomes checked after page refreshes |
| 3.3 | Verify DB | Query: `SELECT ADPath FROM CustomerSystem WHERE InstanceName = '<name>'` | ADPath now contains orchestrated OU (e.g. `/root/Applications/ASPAC/OrchestratedSH0/...`) |
| 3.4 | Verify AD | Run: `Get-ADObject -Filter "Name -eq '<instanceName>'"` or check AD Users and Computers | AD object is now in the orchestrated OU |

### 4. Toggle: Disable Service Tasks (orchestrated → non-orchestrated)

| # | Step | Action | Verification |
|---|------|--------|-------------|
| 4.1 | Pre-condition | Identify a system with service tasks **enabled** (checkbox checked). Record its current ADPath. | ADPath contains orchestrated OU |
| 4.2 | Toggle | Click the checkbox to disable service tasks | Checkbox becomes unchecked after page refreshes |
| 4.3 | Verify DB | Query: `SELECT ADPath FROM CustomerSystem WHERE InstanceName = '<name>'` | ADPath now contains non-orchestrated OU |
| 4.4 | Verify AD | Check AD object location | AD object is now in the non-orchestrated OU |

### 5. No-op (Already in Desired State)

| # | Test | Steps | Expected Result |
|---|------|-------|-----------------|
| 5.1 | API no-op | Call `PUT /customersystem/updateServiceTask` with `enableServiceTask` matching the current state | Returns `200 OK`. No DB change, no AD move. ADPath unchanged. |

### 6. Direct API Testing

| # | Test | Steps | Expected Result |
|---|------|-------|-----------------|
| 6.1 | Valid request | `PUT /customersystem/updateServiceTask` with `{ "instanceName": "<name>", "enableServiceTask": true }` | `200 OK`, ADPath updated in DB, AD entry moved |
| 6.2 | Non-existent instance | `PUT /customersystem/updateServiceTask` with `{ "instanceName": "DOESNOTEXIST", "enableServiceTask": true }` | `404 Not Found` |
| 6.3 | Missing instanceName | `PUT /customersystem/updateServiceTask` with `{ "enableServiceTask": true }` | `400 Bad Request` (required field missing) |
| 6.4 | Viewer role | Call endpoint authenticated as Viewer | `403 Forbidden` |
| 6.5 | Unauthenticated | Call endpoint without credentials | `401 Unauthorized` |

### 7. Edge Cases

| # | Test | Steps | Expected Result |
|---|------|-------|-----------------|
| 7.1 | Rapid double-click | Click checkbox twice quickly on the same system | Only one request fires; checkbox is disabled during in-flight request (UI prevents double submission) |
| 7.2 | Toggle back and forth | Enable service tasks, wait for completion, then disable again | Both transitions succeed; ADPath and AD location match expected OU each time |
| 7.3 | Multiple systems | Toggle service tasks on two different systems | Each system's ADPath and AD location updated independently |

---

## Verification Queries

```sql
-- Check current ADPath and derived service task state for a system
SELECT InstanceName, ADPath, CustomerSystemState, DataCentre, LicenseType
FROM CustomerSystem
WHERE InstanceName = '<instanceName>';
```

```powershell
# Check AD object location (run from domain-joined machine)
Get-ADObject -Filter "Name -eq '<instanceName>'" -Properties DistinguishedName | Select DistinguishedName
```

---

## OU Reference (SAND)

| State | OU Path |
|-------|---------|
| Orchestrated (service tasks ON) | `/root/Applications/ASPAC/OrchestratedSH0` |
| Non-orchestrated (service tasks OFF) | `/root/Applications/ASPAC/Non-Orchestrated` |
