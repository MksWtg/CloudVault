Prerequisites: Value Type vs Reference Type
Boxing in C# is the process of converting a value type (like int, double, struct) into a reference type (object or an interface it implements).

When you box a value, the value is wrapped inside an object that lives on the heap.

```csharp
int x = 42;
object o = x;   // boxing happens here
```

## Unboxing

To get the value back you must unbox it:

```csharp
int y = (int)o;   // unboxing
```