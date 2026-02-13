Prerequisites: [[Services in Software]] [[Dependency Injection]]

In ASP.NET, instead of manually instantiating dependencies, ASP.NET can handle it for you. The library that does this is called the DI container.
#### Without Container

```C#
var logger = new LoggerService();       // create dependency
var orderService = new OrderService(logger); // inject manually

orderService.CreateOrder("Laptop");
```

#### With Container
Before the DI container can instantiate a dependency, the dependency needs to be registered.

>While services are not specific to ASP.NET and the generic software definition applies to ASP.NET, ASP.NET services are usually subject to specific conventions/patterns. For example, in ASP.NET services should be registered so the DI container can handle them.

Registration:
```C#
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddScoped<LoggerService>();  // register dependency
builder.Services.AddScoped<OrderService>();   // register dependent service

var app = builder.Build();
```

Use:
```C#
public class HomeController : Controller
{
    private readonly OrderService _orderService;

    public HomeController(OrderService orderService)
    {
        _orderService = orderService;
    }

    public IActionResult Index()
    {
        _orderService.CreateOrder("Laptop");
        return Content("Order created");
    }
}
```

There is no manual instantiation using the `new` keyword, instantiation happens behind the scenes when a HTTP request is made and the controller is instantiated.

> Note: as a rule of thumb for ASP.NET, and actually all software frameworks, if there is really only one way something can be done then the framework handles it for you. There is no easy way to instantiate controllers and their dependencies without all the plumbing. Since this plumbing would be the same for every webapp, ASP.NET handles it.

### Registering Controllers

 Controllers are the highest level of classes. They are stateless, and they require services as dependencies, so they can be treated as services themselves. Controllers are created via constructor injection using the DI container. They don't need to be registered manually, this is handled by ASP.NET.

### Registering Services: More Information

Services are registered in `Program.cs`.

Before you can register a service you need a `WebApplicationBuilder` object. This is typically created using `var builder = WebApplication.CreateBuilder(args);`.

The syntax for registering a service is:
`builder.Services.RegistrationMethod<ServiceType>();`.

`ServiceType` is the type of the service you want injected. E.g. `EmailSender`, `LoggerService`, etc.

`RegistrationMethod` can be one of three methods that specifies the 'lifetime' of the dependency, or how long ASP.NET will persist the same instance before making a new one.

### Different Registration Methods

| Method       | Meaning                                                                                                                                                       | Use Case                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AddTransient | Create a new instance every time the dependency is requested. In one HTTP request, if multiple controllers need this dependency, create a new one every time. | When the service is lightweight and stateless. Most dependencies are transient.                                                                                                                                                                                                                                                                                                                         |
| AddScoped    | In one HTTP request, no matter how many times this service is requested, recycle the same instance. For the next request, a new instance will be make.        | `DbContext`: It obviously can't be a singleton because every request has its own context. It also can't be transient because in a single request, two services might fetch the same entity from separate `DbContext` instances. Since each `DbContext` manages its own transaction implicitly, you can't reliably wrap a single request's operation in one transaction so there may be inconsistencies. |
| AddSingleton | Same instance for the entire application lifetime.                                                                                                            | Caching: You want the cached data to be available to all users and not recreated every request.                                                                                                                                                                                                                                                                                                         |

### Registering Abstract Classes and Interfaces

We already know that for loose coupling, we might specify our dependency as an interface or abstract class rather than a concrete type. This is very common and the best practice. These can also be handled by the DI container but we must specify the implementation to use when teh 
### Helpers For Common Registration

If you need to you can use these rather than creating custom helpers and boilerplate:

- `AddDbContext<MyDbContext>()`: Automatically scoped
- `AddHttpClient()`: Automatically transient
- `AddLogging()` Automatically singleton