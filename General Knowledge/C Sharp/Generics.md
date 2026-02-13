Generic is something of an umbrella term in programming. Generally, it refers to the ability of the definition of a type to depend on another type. If your programming language allows type definitions to depend on other types, it is generic.

## Non Generic Type

```C#
class MyType // <- Type definition
{ /* some code here*/ }
```

Regardless of the implementation of `MyType`, the type itself is freestanding. Most types in C# are like this- for example, `Program`