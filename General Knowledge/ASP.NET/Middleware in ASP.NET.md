In web development, requests come from the frontend and go the backend. Middleware sits between these. Middleware is code that runs after a request comes from the frontend, does something to the request and (sometimes) sends it to the controller which is the backend. 

When the backend has a response for the frontend, it passes it back through the middleware.

Technically middleware sits on the server so it is part of the backend to, but since it is all grouped together and comes strictly before any of the actual server logic it is considered its own pipeline.

`Frontend -> Middleware -> Backend`
`Backend -> Middleware -> Frontend`

Whenever a request comes to this app from the frontend custom logging middleware runs.
```C#
// Program.cs
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseMiddleware<RequestLoggingMiddleware>(); // custom middleware

app.MapControllers();
app.Run();
```

(See the appendix for what a custom middleware might look like).

## Anatomy of a Middleware 

Middleware is built like this:

```C#
app.Use(async (context, next) => {     
	// Code BEFORE next     
	await next();     
	// Code AFTER next 
});
```

There are two parts:
1) Before `next()` runs on the way in (request phase)
2) After `next()` runs on the way out (response phase)

If you chain multiple middlwares together, the request middleware runs in order while the response middlewares run in reverse order.

>Note: `next()` is the delegate that calls the next middleware- ASP.NET connects it to the next middleware.
## Appendix

```C#
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;
using System;

public class RequestLoggingMiddleware
{
    private readonly RequestDelegate _next;

    public RequestLoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

	// Everytime a request comes in, this code runs
    public async Task InvokeAsync(HttpContext context)
    {
        // Before the next middleware
        Console.WriteLine($"Incoming request: {context.Request.Method} {context.Request.Path}");
        await _next(context); // Call the next middleware
        // After the next middleware
        Console.WriteLine($"Outgoing response: {context.Response.StatusCode}");
    }
}
```