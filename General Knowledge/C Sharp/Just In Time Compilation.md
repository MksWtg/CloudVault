Prerequisites: [[Compiler]], [[JIT Compiled Language]], csc.exe

When you build C# code using dotnet build, msbuild, or csc.exe, it turns source code into an exe.
However, this exe is not ready to be executed straight up. It does not contain code ready to be executed by the machine, it contains machine agnostic intermediate code called CIL.

This code is only turned into machine code when you run the exe, shortly before execution.