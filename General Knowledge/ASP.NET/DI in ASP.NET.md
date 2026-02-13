Prerequisites: [[Dependency Injection]]

In ASP.NET, instead of manually instantiating dependencies, ASP.NET can handle it for you. The library that does this is called the DI container.
#### Without Container

```C#
var logger = new LoggerService();       // create dependency
var orderService = new OrderService(logger); // inject manually

orderService.CreateOrder("Laptop");
```

#### With Container
Before the DI container can instantiate a dependency, the dependency needs to be registered.

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

In ASP.NET, controllers are created via constructor injection using the DI container. You can control what 