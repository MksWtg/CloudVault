A JWT (JSON Web Token) is a string made of 3 parts: `xxxxx.yyyyy.zzzzz`. The first part is the header, the second part is the payload, the third part is the signature.

The header has metadata, e.g. the algorithm and jwt type
The payload contains claims about the user e.g. the username, role, etc.
The signature is created using a secret key from the server.

## JWT Authentication

When the user signs in for the first time, the server creates and signs a JWT and sends it to the browser, that stores it.

Every time the client sends a request, it sends the JWT with it. The server can verify the signature based on its own secret key to verify the client has been previously vetted by the server.

So the JWT is a means to authenticate a user.

Why is JWT authentication useful?
- Stateless (no need to store a session in the DB to prove a user is logged in)
- Scales well
- Works great for APIs since it comes with the request
- Language-independent

### Issues

JWT is a bearer token, whoever has it is treated as the user. So it must be protected.
1) Store JWT in HTTP-Only Cookies so javascript can't access it
2) Always use HTTPS to encrypt data so noone can get the raw JWT by watching the data


