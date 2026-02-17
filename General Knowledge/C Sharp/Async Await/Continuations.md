A continuation is the piece of code that runs after an operation completes.

It says “what should happen next” once a job finishes.

## Simple Example

```csharp
int AddOne(int x)
{
    return x + 1;
}

int result = AddOne(5);
Console.WriteLine(result);
```

The continuation after `AddOne(5)` is `Console.WriteLine(result);`.

## Explicit Continuation

Instead of executing code procedurally/imperatively, we can name the continuation to make it more explicit.

```csharp
void AddOne(int x, Action<int> continuation)
{
    continuation(x + 1);
}
```

And use it in the following way:

```csharp
AddOne(5, result =>
{
    Console.WriteLine(result);
});
```

## Significance For Async Await

The `async` and `await` keywords are syntactic sugar over continuations.

```csharp
async Task ExampleAsync()
{
    int number = await GetNumberAsync();
    Console.WriteLine(number);
}
```

The following happen in order:
1) `GetNumberAsync()` returns a `Task<int>` immediately
2) `await` pauses the method until the task completes.
3) The rest of the method (`Console.WriteLine(number)`) is turned into a continuation that runs when the task finishes

Under the hood, this looks roughly like:

```csharp
Task<int> task = GetNumberAsync(); // start async operation

task.ContinueWith(t =>
{
    int number = t.Result;
    Console.WriteLine(number);
});

```

C# transforms async/await into a state machine. each await point becomes a suspension point, and the remainder of the method after the await is saved as a continuation delegate. When the awaited `Task` completes, the continuation is invoked.

- The `Task` completion notification can come from several sources, like the thread pool worker, IO completion system (like IOCP on windows), etc.
- Task Scheduler is responsible for deciding on which thread a continuation runs

### Multiple Tasks

An `async` method like:
```csharp
async Task ProcessAsync()
{
    int a = await GetAAsync();
    int b = await GetBAsync();
    Console.WriteLine(a + b);
}
```

May become:
```csharp
GetAAsync().ContinueWith(tA =>
{
    int a = tA.Result;
    GetBAsync().ContinueWith(tB =>
    {
        int b = tB.Result;
        Console.WriteLine(a + b);
    });
});
```

It gets split into a delegate at each `await`.