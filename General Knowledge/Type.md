
In programming, a type is a fundamental property of data that describes what kind of data a value is, and what operations are allowed on it.

Consider the language agnostic code
```csharp
int x = 10;
// x is an identifier whose type is int
// 10 is an integer literal whose type is int.
```

Languages that have types are called typed and these are most languages.

E.g. C, Java, Python, Javascript, C#, Haskell, Idris, Scala

In these languages, any piece of data has a type. Every variable has a type. Keywords are not data so they are not typed. Only data has a type.

## Statically Typed vs Dynamically Typed

Prerequisites: [[Compile Time vs Runtime]]

In some languages, the types are known at compile time. These languages are statically typed. E.g. C#

In some languages, the types are only known at runtime- in general, the type of a variable is only known after it is assigned the value of another piece of data whose type is known. These languages are called dynamically typed. E.g. Python

## Strongly Typed vs Weakly Typed

Prerequisites: [[Compile Time vs Runtime]]

In some languages, only some types permit some operations and if you try to call an operation on a type that doesn't permit it, it will fail. At compile time or runtime.

In other languages, the language will coerce the type into another type and try to preserve meaning of the original data in the new type. For example, turning the string "0" into the number 0 when we try to add it to another number.


## Static and Dynamic vs Strong and Weak

They are independent things. Whether a language is dynamic does not affect whether it is strongly or weakly typed.

|         | Strong            | Weak            |
| ------- | ----------------- | --------------- |
| Static  | C#, Java, Haskell | C               |
| Dynamic | Python, Ruby      | JavaScript, PHP |

Note that weak but statically typed is a bit of a weird state. For a language to exist in this box you would need to know all types at compile time. But at the same time, allowing coercion into different types.

C somewhat loosely (or even vacuously) fits the bill, as you can even multiply characters like the letter `a` and it will just use the int representation and do the math. But it isn't really statically typed like regular static languages are, if you do an operation on a data type that shouldn't allow it, C might not complain and it might just compile.