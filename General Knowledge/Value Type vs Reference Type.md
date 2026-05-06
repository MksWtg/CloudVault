Prerequisite: [[Type]]

In programming language we create and manipulate data.

A piece of data, or the identifier that points to it, can be a value or a reference.

If data of a certain type is represented as a value, we call that type a `Value Type` and otherwise a Reference Type.

But what does it mean for data to be represented as a value or a reference?

## Value Type

An element of a value type stores the actual data directly.

```csharp
int a = 10;
int b = a;
b = 20;
```

a contains 10
b gets a copy of a
changing b does NOT affect a
a is still 10

## Reference Type

A reference type stores a reference (address) to the actual data.

The variable/identifier points to an object on the heap.

```csharp
class Person
{
    public string Name;
}

Person p1 = new Person();
p1.Name = "Alice";

Person p2 = p1;
p2.Name = "Bob";
```

Modifying `p2` modifies `p1` because they are two different names for the same object.