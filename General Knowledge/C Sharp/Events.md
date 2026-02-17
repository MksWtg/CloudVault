Prerequisites: [[Delegates]]

An event in C# is a special kind of delegate that allows a class (the publisher) to notify other classes (subscribers) when something happens.

## Example

A typical publisher looks like this. The event (`OnNotify`) needs a delegate (`Notify`) that describes the type of method that the event can call.
```cs
class Publisher
{
    // Define a delegate that describes the type of method the event can call
    public delegate void Notify(string message);

    // Declare the event using the delegate
    public event Notify OnNotify;

    public void DoSomething()
    {
        Console.WriteLine("Publisher: Doing something important...");
        // Trigger the event
        OnNotify?.Invoke("Something happened!");
    }
}
```

A typical subscriber looks like this.

```cs
class Subscriber
{
    public void React(string message)
    {
        Console.WriteLine("Subscriber received: " + message);
    }
}
```

The subscriber does not need to know about the publisher.

### Use
```cs
class Program
{
    static void Main()
    {
        Publisher publisher = new Publisher();
        Subscriber subscriber = new Subscriber();

        // Subscribe to the event
        publisher.OnNotify += subscriber.React;

        publisher.DoSomething();
    }
}
```

## Purpose
We have a situation where there exists a publisher, that knows it is being subscribed to, but not who is subscribing to it. It can send a notification trusting that those listening know what to do.

This is better than just a public delegate, because public delegates are unsafe. Any subscriber can invoke a delegate. But only the owning class can invoke the event.

Delegates anyone can invoke, overwrite, or clear.
Events outsiders cannot invoke or overwrite, they can only add/remove handlers.

## Behind the Scenes
Every event in C# has underlying accessor methods:
```cs
public event Notify OnNotify
{
    add { /* add the handler to the delegate list */ }
    remove { /* remove the handler from the delegate list */ }
}
```
