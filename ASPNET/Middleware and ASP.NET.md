In web development, requests come from the frontend and go the backend. Middleware sits between these. Middleware is code that runs after a request comes from the frontend, does something to the request and (sometimes) sends it to the controller which is the backend. Technically middleware sits on the server so it is part of the backend to, but since it is all grouped together and comes strictly before any of the actual server logic it is considered its own pipeline.

`Frontend -> Middleware -> Backend`

```C#
// Program.cs
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseMiddleware<RequestLoggingMiddleware>(); // Middleware 1

app.MapControllers(); // Middleware 2

app.Run();
```

Whenever a request comes to this app from the frontend, two things happen. First logging middleware runs