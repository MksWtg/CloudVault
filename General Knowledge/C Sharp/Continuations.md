A continuation is the piece of code that runs after an operation completes.

It says “what should happen next” once a job finishes.

### Simple Example

```csharp
int AddOne(int x)
{
    return x + 1;
}

int result = AddOne(5);
Console.WriteLine(result);
```

The continuation after `AddOne(5)` is `Console.WriteLine(result);`.

### Explicit Continuation

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

### Significance For Async Await

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
3) The rest of the method (Console.WriteLine(number)) is turned into a continuation that runs when the task finishes.