Active Directory is a directory (like a dictionary) that stores information about users, computers, and other resources. It controls how they are authenticated and what they are allowed to access.

1. Authentication: It verifies who you are when you log in by checking your username and password.
2. Authorization: It determines what you are allowed to access, such as files, applications, etc.
3. Centralized management: It lets admins manage users, computers, passwords, policies from one place instead of configuring each machine individually.

When you log into a work computer, the computer contacts AD to confirm your identity and retrieve your permissions and policies.

Computers that have the AD on them (as there are many copies of AD across many computers in case of failure) are called domain controllers or DCs. When you log on for the first time, this is the server/servers that is/are queried. If they go down, people will lose access to their laptops as they will not be able to authenticate with AD.