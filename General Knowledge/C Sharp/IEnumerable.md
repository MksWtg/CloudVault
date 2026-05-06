Prerequisites: [[IEnumerator]]

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