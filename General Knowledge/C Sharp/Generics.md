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

An example of a of generic types in C# are `List`. a `List` does not refer to a single type, it is much closer to a function that accepts a type and produces a type. E.g. similar to the mathematical syntax `f(5)` we have `List<int>`)