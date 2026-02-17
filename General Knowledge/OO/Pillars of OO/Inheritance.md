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

Say we want to model a dog. As an animal, dogs eat and sleep too. But dogs can do dog specific behaviours, such as barking. S
```cs
class Dog : Animal  // Dog inherits from Animal
{
    public void Bark()
    {
        Console.WriteLine("Barking...");
    }
}
```