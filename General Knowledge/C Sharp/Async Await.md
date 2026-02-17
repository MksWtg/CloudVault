
`async` and `await` are two keywords that are used to write asynchronous code in C#.

`async` is a modifier for methods. It signals to the compiler that the code in the method should be asynchronous (that it may use the `await` keyword). You cannot use `await` outside of `async` code, the code will not compile.

Under the hood, `async` makes the compiler generate a state machine based on the method. It splits the method at each await point into [[Continuations]]. The method immediately returns a `Task` (or `Task<T>`), which represents the eventual result.

## What is Asynchronous Code



