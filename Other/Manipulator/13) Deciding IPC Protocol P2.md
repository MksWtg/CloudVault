
```
i am writing a server and other devs will write a client that runs alongside the server on the same machine. my server will have methods such as T GetValue(); and SetValue(T);. Here are my requirements:

- i want to support as many machines as possible, obviously clients should be able to be written in python, cpp, node, but also haskell, and lean if possible

- given requirement 1, i want to make the IPC as fast as possible. 50Hz is a minimum bound, but ideally 200Hz+

- if somehow requirements 1 and 2 are met, then whatever is simplest for the client is best. But at this point I don't really care, 1 and 2 are the only important requirements
```