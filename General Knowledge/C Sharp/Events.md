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