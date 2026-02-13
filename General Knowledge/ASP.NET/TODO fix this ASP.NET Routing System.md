Routing in ASP.NET is a system that matches incoming HTTP requests to endpoints (like controller actions or Razor Pages) and is managed by the routing middleware. This process happens in the middleware pipeline using two key methods: `UseRouting()` and `UseEndpoints()`. See [[Middleware in ASP.NET]] for more information.

## UseRouting()

- Sets `HttpContext.Endpoint`
- This is executed later by the endpoint middleware

## UseEndpoints()

TODO