The Interface Segregation Principle is the 4th SOLID principle. It states that classes should not be forced to depend on interfaces they do not use.

In other words, split large interfaces into smaller, specific ones so that implementing classes only need to implement what they actually need.

## Example of Violation

```C#
public interface IMultiDevicePrinter
{
    void Print(string content);
    void Scan(string content);
    void Fax(string content);
}
```

What are the problems with the above?
1) If you have a simple printer that can only print, you are forced to implement `Scan` and `Fax`, even though you don’t need them.

## Fixed Example

Split the interfaces.

```C#
public interface IPrinter
{
    void Print(string content);
}

public interface IScanner
{
    void Scan(string content);
}

public interface IFax
{
    void Fax(string content);
}
```

Now classes only implement what they need:

```C#
public class SimplePrinter : IPrinter
{
    public void Print(string content)
    {
        Console.WriteLine(content);
    }
}

public class AdvancedPrinter : IPrinter, IScanner, IFax
{
    public void Print(string content) { /* ... */ }
    public void Scan(string content) { /* ... */ }
    public void Fax(string content) { /* ... */ }
}
```