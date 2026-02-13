
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