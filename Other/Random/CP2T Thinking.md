
> Note: we create logins (add only). We create and rename and even delete users (create, update, delete).

Main method:
`EnsureServerLoginsForUserRepositoryExist()` calls:
- `RenameSourceLoginsToTargetPrefix()` IF AND ONLY IF source and target db name are different. E.g. if we are restoring M22PRD to M22TST, even if M22TST instance already exists with logins and users. Or if it is fresh. However, if we are restoring M22TST on top of M22TST we don't care about this operation.
	- `GetEnterpriseDbUsersInDatabase()` Get all EnterpriseDbUsers e.g. EnterpriseDbUser_Odyssey2_Mukund1234 -> This gets all the users in the .bak and their SIDs.
	- For each user: rename this into the target (remember source is necessarily not the same as target), so EnterpriseDbUser_M22PRD_Mukund1234 becomes EnterpriseDbUser_M22TST_Mukund1234
	- `EnsureServerLoginExists()` Create a login for this user -> this is literally just creating a login with a random password, not mapping it to any login, the login name comes from each EnterpriseDbUser in the .bak, with its name updated. It is just a login.
		- `GetRandomAlphanumericString()` to get the pword
	- `RemapDatabaseUser()` IF the DB is new e.g. M22TST does not exist yet, there are no old logins and users to preserve. We rename ever user to the new name and to the created login
	- `EnsureDatabaseUserExists()` IF M22TST already exists we want to preserve existing logins and users and simply add new logins and users on top for the renamed target db. If the target user does not exist, create it
- `EnsureServerLoginsForDatabaseUsersExist()` Regardless:
	- `GetEnterpriseDbUsersInDatabase()` get all enterprise DB users
	- for each user:
	- `EnsureServerLoginExistsWithSid()` if there exists a login with the same name as the user, presumably this has the same ID and is mapped. If there doesn't, create the login with random pword, map it to user

Lets consider two separate situations:
1) target db does not already exist, we want to create logins for the new users, give them random passwords, rename the old users to new users, map these to the created logins
2) if the target db does already exist, we want to do the same thing but keep the old users (just in case)


|     |     |     |
| --- | --- | --- |
|     |     |     |
|     |     |     |

