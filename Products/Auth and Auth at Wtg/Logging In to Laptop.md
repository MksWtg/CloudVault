
## Local vs Work Account

A local account exists only on your device, with credentials stored on the computer itself, and all authentication happens locally. A work (domain or Azure AD) account is managed by your organization, and logging in requires contacting the organization’s servers (domain controller or Azure AD) to verify your identity, allowing centralized management, policies, and access to network resources.

When you log in to a wisetech developer laptop you enter your username and password.
- First your computer parses the username- a username might look like `DOMAIN\username` or `username@domain.com` (where clearly the account is a work account) or `MACHINENAME\username` (where clearly the account is local).
- If the account is local, it authenticates you locally. If the account is `CORP` (Wtg employees have corp accounts)

When logging in 