Prerequisites: [[Authentication vs Authorization]], [[OAuth]]

OpenID Connect (OIDC) is an authentication layer built on top of OAuth 2.0.

While OAuth 2.0 is designed for authorization, OIDC adds the ability for the app to know the user’s identity. It does this by introducing an ID token, usually a JWT, which contains information about the authenticated user such as their unique ID, name, email, and whether the email is verified.

When a user logs in through an OAuth provider like Google using OIDC, the provider authenticates the user, asks for consent for requested scopes, and then issues both an access token for API calls and an ID token that proves who the user is. This allows applications to implement single sign-on (SSO) or login functionality without ever handling the user’s password directly. Essentially, OAuth 2.0 tells the app what it can do, while OIDC tells the app who the user is, making them complementary technologies for modern authentication and authorization flows.