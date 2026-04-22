
Prerequisites: [[Patterns]]


Patterns can be segregated by category.

## Creational Patterns

Control how objects are created, when construction may be complex but the same boilerplate in every case.

#### Factory
```csharp
interface IShape { }
class Circle : IShape { }
class Square : IShape { }

class ShapeFactory
{
    public IShape Create(string type) =>
        type switch
        {
            "circle" => new Circle(),
            "square" => new Square(),
            _ => throw new ArgumentException()
        };
}
```


#### Sinlgeton

> In modern C# we would sooner use DI rather than manual singletons

```csharp
class Singleton
{
    private static readonly Singleton _instance = new();
    public static Singleton Instance => _instance;
    private Singleton() {}
}
```

#### Builder

Step by step construction of complex objects

```csharp
var person = new PersonBuilder()
    .WithName("Alex")
    .WithAge(30)
    .Build();
```

## Structural

Structural patterns deal with how objects fit together

#### Adapter

Wrapper around underlying API to make it fit an interface

```csharp
class OldLogger { public void Write(string msg) {} }

class LoggerAdapter
{
    private readonly OldLogger _old = new();
    public void Log(string msg) => _old.Write(msg);
}
```

#### Decorator

Just a wrapper

```csharp
class LoggingService : IService
{
    private readonly IService _inner;
    public LoggingService(IService inner) => _inner = inner;

    public void Execute()
    {
        Console.WriteLine("Before");
        _inner.Execute();
        Console.WriteLine("After");
    }
}
```

## Behavioral Pattern 

Deals with how objects communicate

#### Visitor

Problem: 

You have a fixed set of object types, and you want to add new operations on them without modifying those classes.

Element interface (fixed):

```csharp
interface IShape
{
    void Accept(IShapeVisitor visitor);
}
```

Elements (fixed):

```csharp
class Circle : IShape
{
    public void Accept(IShapeVisitor visitor)
    {
        visitor.Visit(this);
    }
}

class Rectangle : IShape
{
    public void Accept(IShapeVisitor visitor)
    {
        visitor.Visit(this);
    }
}
```

Visitor Interface (expand this):

```csharp
interface IShapeVisitor
{
    void Visit(Circle circle);
    void Visit(Rectangle rectangle);
}
```

Visitor (expand this):

```csharp
class AreaCalculator : IShapeVisitor
{
    public void Visit(Circle circle)
    {
        Console.WriteLine("Calculating area of circle");
    }

    public void Visit(Rectangle rectangle)
    {
        Console.WriteLine("Calculating area of rectangle");
    }
}
```

If your objects are fixed, there are no new objects, but there are lots of new operations being added to the objects, use this pattern.