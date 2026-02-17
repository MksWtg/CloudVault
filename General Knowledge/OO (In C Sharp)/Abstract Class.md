Perquisites: [[Inheritance]]

An abstract class is a class that cannot be instantiated directly and is as a base class for other classes. It can contain abstract methods (methods without implementation) as well as concrete methods (methods with implementation). Abstract classes are used to define a common template or contract for derived classes.

Use the abstract keyword to define abstract classes:

```cs
abstract class Shape
{
    // Abstract method (no implementation)
    public abstract void Draw();

    // Concrete method (has implementation)
    public void Move(int x, int y)
    {
        Console.WriteLine($"Shape moved to ({x},{y})");
    }
}
```

You cannot instantiate the abstract class:

`Shape s = new Shape(); // ❌ Error`

Usage:

```cs
class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a Circle");
    }
}

class Program
{
    static void Main()
    {
        Shape myShape = new Circle();
        myShape.Draw();  // Output: Drawing a Circle
        myShape.Move(10, 20);  // Output: Shape moved to (10,20)
    }
}
```

The abstract type is still a valid type for references though.

```cs
Shape circle = new Circle(); // ✅ Allowed
circle.Draw();
circle.Move(5, 10);
```