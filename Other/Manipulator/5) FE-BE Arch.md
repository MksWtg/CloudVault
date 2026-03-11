
```
i want these requirements:

1) user can run arbitrary code in the backend. literally whatever they want. including making requests to any port. only user's code might make requests to this backend.

2) user can write arbitrary html, css, js in the frontend (but no libraries). They have access to components that i allow. they provide their custom code as a file that i load in. this can make requests to anything, but nothing makes requests to it. except the backend maybe, as the user writes the backend. if the frontend makes a request to a random internet api, thats fair game.

3) both fe and be run inside containers for dependency reasons.

4) i need you to make this reasonably secure. the user isn't downright malicious but they might do dumb stuff.
```