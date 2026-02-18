
Prerequisites: [[DI in ASP.NET]]

Inversion of Control (IoC) is a pattern in software.

Traditionally, your code begins executing through an entrypoint such as a `Main` method or `main` function. Code executes line by line. If you call an external library, or query a DB, or hit an API endpoint, you are in control of execution: you make a request and decide what to do with the response.

`Your Code -> Library`

IoC is when this pattern is inverted: you trust a framework to handle running the code. *It* decides when to run your code. It is in control. Control has been inverted.

`Framework -> Your Code`

> IoC is abstract, and sometimes there is argument as to whether or not some code is IoC. Some examples are "more" IoC than others.
## Example: ASP.NET and DI

This is the classic IoC example.

An ASP.NET program starts with a `Main` method. Contained in this method is the standard boilerplate:

```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();
app.Run();
```

After `app.Run` executes, you are no longer in control. From this point, here is the flow of control:

`Client Request -> ASP.NET -> Your Code`

The framework will call your code.

### What Happens When a Request is Made?

1) Browser sends a request `GET /Home/Index`
2) ASP.NET processes the request through middleware
3) ASP.NET routing system determines which controller to send the request to
4) ASP.NET sees controller signature `public HomeController(IMessageService service)` and requests DI Container to instantiate the controller and the `IMessageService`.
5) ASP.NET calls the right method in the controller

Since ASP.NET is doing everything when and where it decides, and only calling your code when it sees fit, control has been inverted.

## Example: Template Pattern

[Source](https://stackoverflow.com/questions/23692298/is-template-method-design-pattern-an-example-of-inversion-of-control)

As the writer of a framework, I may write a general method:

```csharp
public abstract class DataProcessor
{
    public void Process() // Template method
    {
        ReadData();
        ProcessData();   // customizable step
        SaveData();
    }

    protected abstract void ProcessData();

    private void ReadData()
    {
        Console.WriteLine("Reading data...");
    }

    private void SaveData()
    {
        Console.WriteLine("Saving data...");
    }
}
```

Note how this class is abstract. I provide this method to the client, who will implement a specific processor (by inheriting from `DataProcessor`). As part of this they will be forced to implement `ProcessData`.

```cs
public class CsvProcessor : DataProcessor
{
    protected override void ProcessData()
    {
        Console.WriteLine("Processing CSV data");
    }
}
```

To invoke it, they may call:
```cs
var processor = new CsvProcessor();
processor.Process();
```

After `Process` executes, the user is no longer in control. Base `DataProcessor` runs and gets to determine when the user's code `ProcessData` should be called.

## Example: Event Driven IoC

This example may show up in UI. It uses events and delegaets.

```cs
using System;

public class Button
{
    public event EventHandler Click;

    public void SimulateClick()
    {
        Click?.Invoke(this, EventArgs.Empty);
    }
}

class Program
{
    static void Main()
    {
        var button = new Button();

        // Register a handler — "we'll call you when click happens"
        button.Click += OnButtonClick;

        // Later, the framework/system calls your handler
        button.SimulateClick();
    }

    static void OnButtonClick(object sender, EventArgs e)
    {
        Console.WriteLine("Button clicked!");
    }
}
```

- `Program` (developer) doesn’t control when `OnButtonClick` is invoked. `Button` (the system) controls invocation.