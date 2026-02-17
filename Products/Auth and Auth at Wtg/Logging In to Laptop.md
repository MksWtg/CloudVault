
## Local vs Work Account

A local account exists only on your device, with credentials stored on the computer itself, and all authentication happens locally. A work (domain or Azure AD) account is managed by your organization, and logging in requires contacting the organization’s servers (domain controller or Azure AD) to verify your identity, allowing centralized management, policies, and access to network resources.

When you log in to a wisetech developer laptop you enter your username and password.
- First your computer parses the username- a username might look like `DOMAIN\username` or `username@domain.com` (where clearly the account is a work account) or `MACHINENAME\username` (where clearly the account is local). Sometimes the computer can't tell so it tries both.
- If the account is local, it authenticates you locally. If the account is `CORP` (Wtg employees have `CORP` accounts) the laptop contacts a domain controller, which is a special kind of server that runs [[Active Directory]]. This server can confirm if your credentials are OK or not. 
	- Wisetech has many domain controllers in case any of them go down. While computers can cache AD results, on the first login the computer needs access to AD to let you in. So whenever domain controllers go down, wisetech is in big trouble as employees get locked out.

At wisetech, being authenticated gives you access to the following apps that are super critical for working here:
- software