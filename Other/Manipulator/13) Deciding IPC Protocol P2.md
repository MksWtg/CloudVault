
```
i am writing a server and other devs will write a client that runs alongside the server on the same machine (my machine, an ARM ubuntu raspberry pi). my server will have methods such as T GetValue(A, B); and SetValue(A, B, C);. Here are my requirements:

- i want to support as many languages as possible, obviously clients should be able to be written in python, cpp, node, but also haskell, erlang, OCAML. This is absolute highest priority and must happen.

- given requirement 1, i want to make the IPC as fast as possible. 50Hz is a minimum bound, but ideally 200Hz+

- if somehow requirements 1 and 2 are met, then whatever is simplest for the client is best. So fewer dependencies, fewer libraries, code that the client can just write and run and code I don't need to install dependencies for.
  
Write me a server implementation in C (for speed) and show me how a client in haskell for example can reach it.
```
