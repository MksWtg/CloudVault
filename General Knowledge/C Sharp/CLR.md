The CLR (Common Language Runtime) is the core execution engine of .NET. It’s the part of the system that actually runs your C# program after it’s compiled.

When you compile .NET code you get an .exe

But you can't just run this .exe

It contains machine agnostic IL that needs to be turned into machine code.

Running this code requires garbage collection since C# is a managed language. It does the syscalls to create threads when you have multithreaded code.

