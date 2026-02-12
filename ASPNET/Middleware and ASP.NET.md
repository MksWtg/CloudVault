In web development, requests come from the frontend and go the backend. Middleware sits between these. Middleware is code that runs after a request comes from the frontend, does something to the request and (sometimes) sends it to the controller which is the backend. Technically middleware sits on the server so it is part of the backend to, but since it is all grouped together and comes strictly before any of the actual server logic it is considered its own pipeline.

`Frontend -> Middleware -> Backend`

```C#
// Program.cs
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseMiddleware<RequestLoggingMiddleware>(); // Middleware 1: Custom

app.MapControllers(); // Middleware 2: Standard

app.Run();
```

(See the appendix for what a custom middleware might look like)

Whenever a request comes to this app from the frontend, two things happen. First logging middleware runs. This is a custom middleware (code below). Then `MapControllers` (standard ASPNET middleware) runs. This is a bit complicated and honestly I still don't 100% know (TODO: confirm this) but I think it reads all the methods in a controller and when a request comes through "guesses" which method it should map to in a smart way.

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