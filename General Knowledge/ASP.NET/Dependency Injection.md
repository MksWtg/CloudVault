
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