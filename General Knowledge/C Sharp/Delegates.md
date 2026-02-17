Delegates, like classes, refer to types. But unlike classes that are the types of objects, delegates are the types of methods. A delegate is just a type safe function pointers in C#. 

A delegate when defined is given a series of input types and an output type. This delegate can now reference any methods whose inputs match the input type and whose output matches the output type.

```csharp
public delegate int MathOperation(int x, int y);
```

Now we can instantiate `MathOperation`. An instance of `MathOperation` points to a method that takes two `int`s and returns an `int`.

```cs
class Program
{
    static int Add(int a, int b)
    {
        return a + b;
    }

    static void Main()
    {
        // Create a delegate instance pointing to Add
        MathOperation op = Add;

        int result = op(3, 4);  // calls Add(3, 4) indirectly
        Console.WriteLine(result);  // Output: 7
    }
}
```

## Multicast Delegates

Delegates can point to multiple methods at once. When invoking the delegate it will call all methods one by one in order.

```cs
public delegate void Notify(string message);

static void Hello(string msg) => Console.WriteLine("Hello " + msg);
static void Goodbye(string msg) => Console.WriteLine("Goodbye " + msg);

Notify notify = Hello;
notify += Goodbye;  // notify points to both Hello and Goodbye

notify("Alice"); 
// Output:
// Hello Alice
// Goodbye Alice
```

You can also subtract methods from delegates, even if they have not been added.

## Built-In Delegates

Prerequisites: [[Generics]]

C# provides three delegate types. They are all generic.

[Func](https://learn.microsoft.com/en-us/dotnet/api/system.func-2?view=net-10.0) takes at least one type parameter. A `Func` instance points to a method that returns this type as a result. Additional type parameters correspond to the types of the arguments provided to the method that `Func` points to.

You could use a `Func` for a function that takes two `int`s and returns one.
`Func<int, int, int> add = (a, b) => a + b;`

You could use a `Func` for a function that returns a `string`.
`public static string GetMessage() { return "Hello world"; }`

[Action](https://learn.microsoft.com/en-us/dotnet/api/system.action?view=net-10.0) takes zero or more type parameters. An `Action` instance points to a method that optionally accepts parameters but has a `void` return type.

You could use an `Action` for a method that prints to the console.
`Action<string> greet = name => Console.WriteLine("Hi");`

Or one that takes a parameter and prints to the console.
`Action<string> greet = name => Console.WriteLine("Hi " + name);`

[Predicate](https://learn.microsoft.com/en-us/dotnet/api/system.predicate-1?view=net-10.0) takes strictly one type parameter and points to a method that takes one argument and returns either `true` or `false` predicated on the argument.

You could use a `Predicate` to determine if an `int` is odd or even.
`Predicate<int> isEven = x => x % 2 == 0;`

These built-in delegate types have been more than enough for me, but if you need to define your own you can- if you want your code to be self docume