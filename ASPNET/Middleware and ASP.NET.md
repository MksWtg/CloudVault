In web development, requests come from the frontend and go the backend. Middleware sits between these. Middleware is code that runs after a request comes from the frontend, does something to the request and (sometimes) sends it to the controller which is the backend. Technically middleware sits on the server so it is part of the backend to, but since it is all grouped together and comes strictly before any of the actual server logic it is considered its own pipeline.

`Frontend -> Middleware -> Backend`

```C#
// Program.cs
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseMiddleware<RequestLoggingMiddleware>(); // custom middleware

app.MapControllers();
app.Run();
```

(See the appendix for what a custom middleware might look like)

Whenever a request comes to this app from the frontend custom logging middleware runs.
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