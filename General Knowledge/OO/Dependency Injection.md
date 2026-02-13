
You can read about what dependencies are here: [[Services in Software]]

Dependency injection (DI) is a design pattern where a class does not create its own dependencies. Instead, they are provided from the outside through the constructor.

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
1) Loose coupling: `OrderService` depends on an abstract `ILoggerService`, so we can swap out which concrete implementation of `ILoggerService` we want to use without modifying `OrderService`. They are loosely coupled.
2) Testing: you can mock dependencies and their behaviours TODO mock and moq article

Other reasons:
3) When the number of dependencies grow, you don't need to do the work of instantiating all dependencies in the class itself (DI Containers are used for this, see below)
4) Configure how dependencies are treated in one spot (in `Program.cs`, or wherever registration occurs) rather than independently in each class. As in, whether to make dependencies' scopes transient, scoped to a single request or singletons.
5) Instantiation is not a responsibility of services, logic is. So instantiation should occur somewhere else.
## DI Containers

As applications grow, services might depend on many other services. To avoid the boilerplate of instantiating a million dependencies every time a developer wants to instantiate a high level class, since instantiating is a fairly robotic process (especially because services are supposed to be stateless), dependencies are automatically provided to services. This is done through a DI library, or 'Container'.