`HttpContext` is a class in ASP.NET. Every time a new request comes into ASP.NET, a new `HttpContext` object is created that has all the information in the request such as:
- The method (`GET`, `POST`, `PUT`)
- Request information such as headers, the URL, form data, the query string
- The response status code
- Information about the authenticated user, session, etc.
- Client connection information

This is really important and valuable information! So `HttpContext` is a frequently accessed class.

## Accessing HttpContext Information

The process for getting data from `HttpContext` changes depending on where you try to access it. Prerequisites for reading forward: [[Dependency Injection]].

### Controllers
All controllers inherit from `ControllerBase` which has a `HttpContext` property (not to be confused with the `HttpContext` class). Every request creates a new controller instance (through DI) and a new `HttpContext` instance accessible through the `HttpContext` property.

### Middleware
The main executing method for middleware is passed `HttpContext` as a parameter. The signature is: `public async Task Invoke(HttpContext context)`.

### Services
A service is a class with a group of methods that are all related, the service class acts as a logical organization tool for the methods. Services in ASP.NET should be registered so that their dependencies can be injected. 

To access `HttpContext` within a service, ensure it accepts an `IHttpContextAccessor` object as a dependency in the constructor.

```C#
public class MyService
{
    private readonly IHttpContextAccessor _accessor;

    public MyService(IHttpContextAccessor accessor)
    {
        _accessor = accessor;
    }
}
```

Then `HttpContext` can be accessed in the class via: `_accessor.HttpContext`.