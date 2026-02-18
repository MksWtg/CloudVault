A JWT (JSON Web Token) is a string made of 3 parts: `xxxxx.yyyyy.zzzzz`. The first part is the header, the second part is the payload, the third part is the signature.

The header has metadata, e.g. the algorithm and jwt type
The payload contains claims about the user e.g. the username, role, etc.
The signature is created using a secret key from the server.

## JWT Authentication

When the user signs in for the first time, the server creates and signs a JWT and sends it to the browser, that stores it.

Every time the client sends a request, it sends the JWT with it. The server can verify the signature based on its own secret key to verify the client has been previously vetted by the server.

So the JWT is a means to authenticate a user.

Why is JWT authentication useful?
- Stateless (no session storage)
✅ Scales well
✅ Works great for APIs
✅ Ideal for microservices
✅ Language-independent


