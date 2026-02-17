
`async` and `await` are two keywords that are used to write asynchronous code in C#.

`async` is a modifier for methods. It signals to the compiler that the code in the method should be asynchronous (that it may use the `await` keyword). You cannot use `await` outside of `async` code, the code will not compile.

Under the hood, `async` makes the compiler generate a state machine based on the method. It splits the method at each await point into [[Continuations]]. The method immediately returns a `Task` (or `Task<T>`), which represents the eventual result.

## What is Asynchronous Code

Asynchronous code is NOT either of these things:
- It does not spawn multiple threads and run the code in a method in parallel. It still runs on one thread.
- It does not run the code in the method "out of order" like starting a long running function call and moving onto the next line immediately while the long running process runs

Asynchronous code is code that does not block the thread while waiting for a long-running operation to complete. Instead of stopping execution until a task finishes, it pauses the code on the long running operation (and in the background returns the thread to the thread pool so something else can use it) and takes another thread when the long running operation has finished.

### "Pausing" with an Example

```csharp
async Task ExampleAsync()
{
    Console.WriteLine("Start");
    await Task.Delay(3000);
    Console.WriteLine("End");
}
```

- `Console.WriteLine("Start")` runs immediately on a thread.
