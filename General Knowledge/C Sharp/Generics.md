Generic is something of an umbrella term in programming. Generally, it refers to the ability of the definition of a type to depend on another type. If your programming language allows type definitions to depend on other types, it is generic.

## Non Generic Type

```C#
class MyType // <- Type definition
{ /* some code here*/ }
```

Regardless of the implementation of `MyType`, the type itself is freestanding. Most types in C# are like this- for example, `Program`, `Console`, `String`, etc.

In type theoretic terms, the *kind* of `MyType` is `*` .

## Generic Type
```C#
class MyType<T> // <- Type definition
{ /* some code here*/ }
```

In the generic case, `MyType` is no longer a type in and of itself, it is an entire family of types indexed by parameter `T` which itself needs to be another type. The kind of `MyType` in this example is `* -> *` .

An example of a generic type in C# is `List`. A `List` does not refer to a single type, it is much closer to a function that accepts a type and produces a type. E.g. similar to the mathematical syntax `f(5)` we have `List<int>`. We pass `int` (the indexing type) as an argument to `List` (the type constructor) to get the new type `List<int>`.

Heads up, technical stuff ends here.

## Why Do We Have Generics?

1. Code reusability AND simultaneous type safety

### Situation: Code Duplication

Imagine we have a type of a list of integers, that can store as many integers as we want. We can add and remove and find integers in this list.

```C#
public class IntList
{
    private int[] _items = new int[10];
    private int _count = 0;

    public void Add(int item)
    {
        _items[_count++] = item;
    }

    public int Get(int index)
    {
        return _items[index];
    }
}
```
If we had a need for a list of strings, we would have to create a whole new type. And for a list of bools. But there is a lot of similar logic- adding and getting is kind of the same steps, just with strings instead.

```C#
public class StringList
{
    private string[] _items = new string[10];
    private int _count = 0;

    public void Add(string item)
    {
        _items[_count++] = item;
    }

    public string Get(int index)
    {
        return _items[index];
    }
}
```

Since we don't care what is inside the container (we never use the fact that `_items` is a list of `int`s or `string`s, for practical purposes it is a black box) is there any way we can abstract over it?

### New Situation: Type Unsafe

We can use the abstract `object` and reduce the duplicate code, reusing the same code for `int`s and `string`s.

```C#
public class ObjectList
{
    private object[] _items = new object[10];
    private int _count = 0;

    public void Add(object item)
    {
        _items[_count++] = item;
    }

    public object Get(int index)
    {
        return _items[index];
    }
}
```

Unfortunately, this code is not type safe:

```C#
ObjectList intList = new ObjectList();
list.Add(5);
list.Add("apple");

int number = (int)list.Get(0); // casting required
int number2 = (int)list.Get(1); // will fail at runtime
```

We have no way to enforce the types of the objects in `intList`, we surrender this control when we choose to use `object` as the type.

### The Solution

Generics solve this issue, they give us reusable code that is also type safe.

```C#
public class MyList<T>
{
    private T[] _items = new T[10];
    private int _count = 0;

    public void Add(T item)
    {
        _items[_count++] = item;
    }

    public T Get(int index)
    {
        return _items[index];
    }
}
```

Usage

```C#
MyList<int> intList = new MyList<int>();
intList.Add(5);
// intList.Add("apple"); <- this won't even compile, type safe

int value1 = intList.Get(0);  // No cast

MyList<int> strList = new MyList<string>(); // code reuse
intList.Add("apple");

string value2 = strList.Get(0);  // No cast
```

We can reuse the code and preserve type safety.

## Extension: Multiple Generic Parameters

Types can have multiple generic parameters.