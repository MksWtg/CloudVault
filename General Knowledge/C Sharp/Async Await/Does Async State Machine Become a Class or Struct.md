Prerequisites: [[Async Await]]


- In debug build, to enable `EnC` (edit and continue), the state machine becomes a class for easier editing
- in release builds, `EnC` is not needed so the state machine becomes a struct for efficiency purposes (no need to reallocate memory).

More reading:
https://stackoverflow.com/questions/33871181/why-are-async-state-machines-classes-and-not-structs-in-roslyn

[Source Code](https://github.com/dotnet/roslyn/blob/e6a3ec3348ccdf25083d43502bf42519429148f2/src/Compilers/CSharp/Portable/Lowering/AsyncRewriter/AsyncRewriter.cs#L60)
