
Console has the option to be built with NTLM or OIDC Authentication.

## NTLM

1) You access Console in your browser
2) Server responds with 401 Unauthorized and indicates it supports NTLM
3) Browser responds saying it supports NTLM
4) Server sends a challenge to the browser
5) Browser uses windows login credentials to encrypt the challenge and send it back.
	1) It accesses a security token that is generated when you login via a security API called SSPI.
6) The server verified the encrypted response against AD, which is synced with Entra ID
	1) If the server can validate it with AD, it sends 200 OK. This is authentication without passwords.
