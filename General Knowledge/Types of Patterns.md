
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

Step by step constru
```csharp
var person = new PersonBuilder()
    .WithName("Alex")
    .WithAge(30)
    .Build();
```

## Structural

Structural patterns deal with how objects fit together

#### Adapter

Sits in front 