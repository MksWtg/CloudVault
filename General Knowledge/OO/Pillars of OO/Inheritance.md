Inheritance is one of the four pillars of OO. It is a mechanism to share code and data between two classes, enabling code reuse.

In OO, a class represents a real world entity- with data representing data that the entity "owns" and methods representing actions that the entity can undertake. For example, a `Dog` class may have a `string` name field, an `int` age in years field, a `string` favourite type of food field, and methods `Speak` to speak and `Eat` to eat.

If you ever have to model another entity that has an 'is-a' relationship to an existing entity, use inheritance. Since the new entity is conceptually a subset of the existing entity, all the logic and data the existing entity owned also applies to the new entity. New logic and data specific to the new entity demands a new container separate to the existing entity's container. We call this a 'subclass'.

## Example: Animal

The base class, `Animal`, provides methods to eat and sleep as all animals eat and sleep.
```cs
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Eating...");
    }

    public void Sleep()
    {
        Console.WriteLine("Sleeping...");
    }
}
```

Say we want to model a dog. As an animal, dogs eat and sleep too. But dogs can do dog specific behaviours, such as barking. Such logic belongs in a subclass. In C#, subclassing occurs using the `:` syntax.

```cs
class Dog : Animal  // Dog inherits from Animal
{
    public void Bark()
    {
        Console.WriteLine("Barking...");
    }
}
```

Usage:
```cs
class Program
{
    static void Main()
    {
        Dog dog = new Dog();
        dog.Eat();   // Inherited from Animal
        dog.Sleep(); // Inherited from Animal
        dog.Bark();  // Defined in Dog
    }
}
```

## Access Modifiers

Prerequisites: [[Access Modifiers]]

`public` members are inherited
`protected` members are inherited
`private` members are not inherited

## Virtual and Override

A method in the superclass can be annotated with the `virtual` modifier. This enables it to be overridden in the subclass by redeclaring the same method, using the `override` modifier.

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
```

Usage:
```cs
Animal myAnimal = new Dog();
myAnimal.Speak(); // Calls Dog's Speak()
```

Now despite calling `Speak()` on an identifier of type `Animal`, the method that gets called is the one defined in the `Dog` class. This is known as dynamic dispatch.