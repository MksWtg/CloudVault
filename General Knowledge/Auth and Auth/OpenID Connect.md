Prerequisites: [[Authentication vs Authorization]], [[OAuth]]

OpenID Connect (OIDC) is an authentication layer built on top of OAuth 2.0.

When you try to authenticate (log in) with an app (client), the client redirects you to the OIDC provider (e.g. google). After you login with google, or confirm your account if already logged in, the provider redirects you back to the client with an id token in the url. The client verifies that this token is signed by google. Then it reads the claims and creates a session for you. So really, it just outsources login