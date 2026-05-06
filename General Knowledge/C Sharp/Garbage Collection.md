Prerequisites: [[CLR]]

C# is a managed language- this means the programmer does not manually allocate and deallocate memory for data, but instead the language (in this case the CLR) handles it.

Memory allocation happens automatically when the `new` keyword is used.
E.g.

```csharp
Car c = new Car();
```

`new` triggers memory allocation.

The garbage collector is the mechanism in the CLR that deallocates memory.

Garbage collection happens non deterministically (as in, the C# language specification does not specify when garbage collection will occur).