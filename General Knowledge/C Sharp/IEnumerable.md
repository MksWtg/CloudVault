Prerequisites: [[IEnumerator]], [[Interface]]

`IEnumerable` is one of the core interfaces that represents a sequence you can iterate over.

It is 'something you can use in a foreach loop.'


An `IEnumerable` only has one method:

```csharp
IEnumerator<T> GetEnumerator();
```

Implementation:

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

public class MyRange : IEnumerable<int>
{
    private readonly int _max;

    public MyRange(int max)
    {
        _max = max;
    }

    public IEnumerator<int> GetEnumerator()
    {
        return new MyRangeEnumerator(_max);
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }
}
```

Now a foreach like:

```csharp
foreach (var x in numbers)
{
    Console.WriteLine(x);
}
```

Becomes:

```csharp
var enumerator = numbers.GetEnumerator();
try
{
    while (enumerator.MoveNext())
    {
        var x = enumerator.Current;
        Console.WriteLine(x);
    }
}
finally
{
    (enumerator as IDisposable)?.Dispose();
}
```