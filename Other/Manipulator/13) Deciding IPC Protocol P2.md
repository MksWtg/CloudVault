
```
i am writing a server and other devs will write a client that runs alongside the server on the same machine (my machine, an ARM ubuntu raspberry pi). my server will have methods such as T GetValue(A, B); and SetValue(A, B, C);. Here are my requirements:

- i want to support as many language stacks as possible, obviously clients should be able to make direct requests in a super minimal python file, or cpp or node. But also less traditional stacks like haskell, erlang, OCAML- if clients can't directly make requests in this due to a limitation of the language, they should be able to make requests using the typical method used by users of this language, e.g. interop. Basically, if there is a language that people can use to call APIs, it should work here.

- given requirement #1, i want to make the IPC as fast as possible. 50Hz is a minimum bound, but ideally 200Hz+

- if somehow requirements 1 and 2 are met, then whatever is simplest for the client is best. So fewer dependencies, fewer libraries, code that the client can just write and run and code I don't need to install dependencies for. For example, gRPC while good for contracts may be a large dependency.
  
Write me a server implementation in C (my server will be in C to support high performance needs) and show me how a client might look in haskell, call the client however typical API calls in haskell are made.
```
