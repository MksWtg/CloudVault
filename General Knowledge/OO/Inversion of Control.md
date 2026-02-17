
Prerequisites: [[DI in ASP.NET]]

Inversion of Control (IoC) is an abstract pattern in software.

Traditionally, your code begins executing through an entrypoint such as a `Main` method or `main` function. Code executes line by line. If you call an external library, or query a DB, or hit an API endpoint, you are in control of execution: you make a request and decide what to do with the response.

`Your Code -> Library`

IoC is when this pattern is inverted: you trust a framework to handle running the code. *It* decides when to run your code. It is in control. Control has been inverted.

`Framework -> Your Code`

## Example: ASP.NET

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

### Example: Template Pattern

ASP.NET is 