
Prerequisites: [[Inheritance]]

Composition and inheritance are ways to reuse code and structure relationships between classes.

## Inheritance

Inheritance allows a class to **derive from another class** and reuse its members. You use inheritance when the base class is a superset of the derived class. Anything that applies to the base applies to the derived.

```cs
// Base class
public class Animal
{
    public void Eat()
    {
        Console.WriteLine("Eating...");
    }
}

// Derived class
public class Dog : Animal  // Dog inherits from Animal
{
    public void Bark()
    {
        Console.WriteLine("Barking!");
    }
}

// Usage
Dog myDog = new Dog();
myDog.Eat();  // inherited from Animal
myDog.Bark(); // own method
```

## Composition

Composition occurs when a higher level class owns an instance of a lower level class. You use composition when logically the higher class owns an instance of the lower class.

```cs
// Component class
public class Engine
{
    public void Start()
    {
        Console.WriteLine("Engine starting...");
    }
}

// Composite class
public class Car
{
    private Engine engine;

    public Car()
    {
        engine = new Engine(); // Car has an Engine
    }

    public void StartCar()
    {
        engine.Start();
        Console.WriteLine("Car is ready to go!");
    }
}

// Usage
Car myCar = new Car();
myCar.StartCar();
```

## The Debate

There is a debate as to which is better- composition or inheritance. There is an argument that inheritance makes classes tightly coupled, so some people recommend to build solutions, especially in C#, with composition instead of inheritance.

https://en.wikipedia.org/wiki/Composition_over_inheritance

The article says the following:

> To favor composition over inheritance is a design principle that gives the design higher flexibility

> It is more natural to build business-domain classes out of various components than trying to find commonality between them and creating a family tree. For example, an accelerator pedal and a steering wheel share very few common traits, yet both are vital components in a car.

> Composition provides a more stable business domain in the long term as it is less prone to the quirks of the family members. In other words, it is better to compose what an object can do than extend what it is

In fact, modern languages such as Go and Rust intentionally exclud inheritance for this reason, while supporting contracts.

However, as with anything in software, it is impossible to generalize a rule. Use whatever makes the most sense in the moment and based off what the projected requirements are.
