Inheritance is one of the four pillars of OO. It is a mechanism to share code and data between two classes, enabling code reuse.

In OO, a class represents a real world entity- with data representing data that the entity "owns" and methods representing actions that the entity can undertake. For example, an `Animal` class may have a `string` name field, an `int` age in years field, a `string` favourite type of food field, and methods `Speak` to speak and `Eat` to eat.

If you ever have to model another entity that has an 'is-a' relationship to an existing entity, use inheritance. For example, a dog is an animal. Since the new entity is conceptually a subset of the existing entity, all the logic and data the existing entity owned also applies to the new entity. New logic and data specific to the new entity demands a new container separate to the existing entity's container. We call this a 'subclass' or 'child' or 'derived class'. The original class becomes the 'superclass' or the 'parent' or the 'base'.

Examples of 'is-a' relationships are 'A dog is an animal', 'A teacher is a person' and 'A raspberry pi is a computer'. The more specific nouns would all be implemented as child classes that have access to fields, properties, and methods of the parents.

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

Say we want to model a dog. As an animal, dogs eat and sleep too. We want to share this logic. But dogs can do dog specific behaviours, such as barking. Such logic belongs in a subclass. In C#, subclassing occurs using the `:` syntax.

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
`private protected` members are inherited

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

Now despite calling `Speak()` on an identifier of type `Animal`, the method that gets called is the one defined in the `Dog` class. This is known as dynamic dispatch ([[Static vs Dynamic Dispatch]]).

## Constructors

If you want to use a constructor in the superclass that has one or more parameters, do you can do that with the `: base` syntax. For example, the base class `Animal` has a constructor with a parameter (and no constructor-less parameter). A child class therefore needs to invoke the base constructor.

```cs
class Animal
{
    public string Name;
    public Animal(string name)
    {
        Name = name;
    }

    public void Eat() => Console.WriteLine($"{Name} is eating");
}
```

The child invokes the base constructor using `base(name)`. This base constructor runs before the body of the child.

```cs
class Dog : Animal
{
    public string Breed;

    public Dog(string name, string breed) : base(name) // call base constructor
    {
        Breed = breed;
    }

    public void Bark() => Console.WriteLine("Woof!");
}
```

Usage:

```cs
class Program
{
    static void Main()
    {
        Dog dog = new Dog("Buddy", "Labrador");
        dog.Eat();  // inherited from Animal
        dog.Bark();
    }
}
```

## Abstract Method

An abstract method is a method declared without a body in an abstract class, which must be implemented by any non-abstract class that derives from it.

```cs
abstract class Animal
{
    public abstract void Speak(); // no implementation here
}

class Dog : Animal
{
    public override void Speak() // must provide implementation, otherwise compile error
    {
        Console.WriteLine("Woof!");
    }
}
```