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