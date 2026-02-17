
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
- `await Task.Delay(3000)` is encountered: The thread is freed immediately. It does not wait 3 seconds. The method itself returns a Task to the caller, representing the future completion.
- After 3 seconds, the runtime schedules the continuation to run on some available thread

## Why Write Async Code?

The purpose of async code is to allow a program to start long running operations (like IO) without blocking threads, so the application can continue doing other work and finish faster. It improves efficiency and responsiveness. It is used in servers, UI apps, and network operations.

Question: What manages the returning of a thread to the pool and taking a new thread when code resumes?

Answer: 
