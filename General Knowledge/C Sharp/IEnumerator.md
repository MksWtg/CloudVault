An `IEnumerator<T>` lets you:
1. Move to the next element
2. Read the current element

Definition:

```csharp
public interface IEnumerator<T> : IDisposable
{
    T Current { get; }
    bool MoveNext();
    void Reset();
}
```


Example Implementation:
(we have two versions of Current for backwards compatibility with the non generic interface)

```csharp
public class MyRangeEnumerator : IEnumerator<int>
{
    private readonly int _max;
    private int _current;

    public MyRangeEnumerator(int max)
    {
        _max = max;
        _current = -1; // start BEFORE first element
    }

    public int Current => _current;

    object IEnumerator.Current => Current;

    public bool MoveNext()
    {
        if (_current + 1 >= _max)
            return false;

        _current++;
        return true;
    }

    public void Reset()
    {
        _current = -1;
    }

    public void Dispose()
    {
        // nothing to clean up here
    }
}
```