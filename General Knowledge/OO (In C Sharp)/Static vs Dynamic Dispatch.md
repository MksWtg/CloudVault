Dynamic dispatch is a concept in OO programming that determines at runtime which method implementation to call, rather than at compile time.


## Static Dispatch

```cs
class Animal
{
    public void Speak() { Console.WriteLine("Some sound"); }
}

Animal a = new Animal();
a.Speak(); // Compiler knows exactly which Speak() to call
```

## Dynamic Dispatch
```cs
class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Some sound...");
    }
}

class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Woof!");
    }
}

class Cat : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Meow!");
    }
}

class Program
{
    static void Main()
    {
        Animal myAnimal1 = new Dog();
        Animal myAnimal2 = new Cat();

        myAnimal1.Speak(); // Woof!   <- decided at runtime
        myAnimal2.Speak(); // Meow!   <- decided at runtime
    }
}
```