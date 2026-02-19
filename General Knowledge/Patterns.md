A pattern is essentially a reusable solution to a common problem.

## Example

### Problem

You have a class.
- You only ever need one instance of it.
- Multiple parts of your program need global access to that instance.
- You want to control creation of that object and prevent multiple instances accidentally being made

For example, one centralized pool of database connections, one configuration source, one logger.

### Solution

```cs
public class Logger
{
    private static Logger _instance;

    // Private constructor prevents external instantiation
    private Logger() { }

    // Global access point
    public static Logger Instance
    {
        get
        {
            if (_instance == null)
                _instance = new Logger();
            return _instance;
        }
    }

    public void Log(string message)
    {
        Console.WriteLine(message);
    }
}
```

This solution is called the **singleton** pattern. Any of the above problems that require one global instance can basically copy paste this code with some small tweaks and use that as an effective solution.

## Other Examples

- Factory
- Abstract Factory
- Builder
- Prototype
- Adapter
- Decorator
- Facade
- Proxy
- Composite