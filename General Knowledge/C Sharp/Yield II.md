Prerequisites: [[Yield]]

Yield actually expands this:

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