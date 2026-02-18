The `yield` keyword is used to create iterators- methods that return a sequence of values one at a time, instead of building and returning a full collection at once.

## Yield Return
Returns one value at a time and pauses the method’s execution until the next value is requested.

## Yield Break
Stops the iteration early.

```cs
using System;
using System.Collections.Generic;

public class Example
{
    public static IEnumerable<int> GetNumbers()
    {
        yield return 1;
        yield return 2;
        yield return 3;
    }

    public static void Main()
    {
        foreach (var num in GetNumbers())
        {
            Console.WriteLine(num);
        }
    }
}
```

`GetNumbers()` does not return a list. It returns numbers one at a time. Each time `foreach` asks for the next value, execution resumes after the previous `yield return`.

### Behind the Scenes
The compiler: converts your method into a state machine, and automatically creates an implementation of `IEnumerator`. It manages the iteration state.

So yield saves you from writing a lot of boilerplate iterator code.

