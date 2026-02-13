In software, a service is a class with a group of methods that are all related. The service class acts as a logical organization tool for the methods. Services are typically stateless (they contain logic to do things but don't remember information from previous invocations).

### Services Have Dependencies
Since services have clear concerns, any work that needs to be done that requires data or logic that the service does not have access to is handled by 'dependencies'. An instance of the class that does have the power/permission/data to execute an operation (typically another service) is owned by service class. This object is known as a dependency, as the primary service depends on it to function. The primary service now has the ability to invoke specific functionalities through the specialized dependency.

As an example, here is a 'low level' logging class that has the 'power' to log things:
```C#
public class LoggerService
{
    public void Log(string message)
    {
        Console.WriteLine($"[LOG] {message}");
    }
}
```

Multiple 'higher level' classes need logging, so they all depend on this lower level logging class:
```C#
public class OrderService
{
    private readonly LoggerService _logger;

    public OrderService()
    {
        _logger = new LoggerService();
    }

    public void CreateOrder(string product)
    {
        _logger.Log($"Order created for {product}");
    }
}
```

Note how the logging instance is created in the constructor so it can be used in the rest of the class.

As applications grow, services might depend on many other services. To avoid the boilerplate of instantiating a million dependencies every time a developer wants to instantiate a high level class, since instantiating is a fairly robotic process (especially because services are supposed to be stateless), dependencies are automatically provided to services. This process is called "dependency injection".