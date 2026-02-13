
You can read about what dependencies are here: [[Services in Software]]

Dependency injection is a design pattern where a class does not create its own dependencies. Instead, they are provided from the outside through the constructor.

## Example

Without DI:

```C#
public class OrderService
{
    private readonly ILoggerService _logger = new LoggerService();

    public void CreateOrder(string product)
    {
        _logger.Log($"Order created for {product}");
    }
}
```

With DI:
```C#
public class OrderService
{
    private readonly ILoggerService _logger;

    public OrderService(ILoggerService logger) // injected through constructor
    {
        _logger = logger;
    }

    public void CreateOrder(string product)
    {
        _logger.Log($"Order created for {product}");
    }
}
```

## Why Dependency Injection?

Main reasons:
1) Loose coupling: `OrderService` depends on an abstract `ILoggerService`, so we can swap out which concrete implementation of `ILoggerService` we want to use without modifying `OrderService`: they are loosely coupled.
2) Testing: you can mock dependencies and their behaviours TODO mock and moq article

Other reasons:
3) When your app grows, you don't need to do the work of instantiating all dependencies in the class itself (DI Containers are used for this, see below)
4) Configure how dependencies are treated in one spot (in `Program.cs`, or wherever registration occurs)
## DI Containers
As applications grow, services might depend on many other services. To avoid the boilerplate of instantiating a million dependencies every time a developer wants to instantiate a high level class, since instantiating is a fairly robotic process (especially because services are supposed to be stateless), dependencies are automatically provided to services. This is done through a DI library, or 'container'.


#### Without Container
```C#
var logger = new LoggerService();       // create dependency
var orderService = new OrderService(logger); // inject manually

orderService.CreateOrder("Laptop");
```

#### With Container

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

There is no manual instantiation using the `new` keyword, instantiation happens behind the scenes when a HTTP request is made and the controller is instantiated