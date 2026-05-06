Prerequisites: [[Yield]]

Yield expands this:

```csharp
IEnumerable<int> CountTo3()
{
    yield return 1;
    yield return 2;
    yield return 3;
}
```

To this:

```csharp
class CountTo3StateMachine : IEnumerable<int>, IEnumerator<int>
{
    private int state;
    private int current;

    public CountTo3StateMachine(int state)
    {
        this.state = state;
    }

    public int Current => current;
    object IEnumerator.Current => current;

    public bool MoveNext()
    {
        switch (state)
        {
            case 0:
                state = 1;
                current = 1;
                return true;

            case 1:
                state = 2;
                current = 2;
                return true;

            case 2:
                state = 3;
                current = 3;
                return true;

            case 3:
                break;
        }

        return false;
    }

    public void Reset() => throw new NotSupportedException();

    public void Dispose() { }

	// in the first call we must return this object, every new call returns a new iterator
    public IEnumerator<int> GetEnumerator()
    {
        if (state == 0)
        {
            state = -1;
            return this;
        }
        return new CountTo3StateMachine(0);
    }

    IEnumerator IEnumerable.GetEnumerator() => GetEnumerator();
}
```

So the original method becomes:

```csharp
IEnumerable<int> CountTo3()
{
    return new CountTo3StateMachine(0);
}
```

If we have code like this:

```csharp
// Line A
var seq = CountTo3();

// line B
foreach (var a in seq) { ... }

// line C
foreach (var b in seq) { ... }
```

On the first invocation (line `A`), we call `seq = CountTo3()` which returns `new CountTo3StateMachine(0);`, this sets the state to `0`. Then immediately for the foreach loop we call `GetEnumerator()` on this object, which sets the state to `-1` and returns itself (to be used as an `IEnumerator` this time).

After iteration, internal `state` is `3`.

The next time, for line `C` we call `GetEnumerator` again. Since state is not `0` the `IEnumerator` has been used, so it returns a new instance of `new CountTo3StateMachine(0);`.

This lets us keep iterating over seq.