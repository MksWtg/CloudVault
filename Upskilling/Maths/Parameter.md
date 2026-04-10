A parameter is something a type depends on, but it does not change the structure/shape of the data. It is fixed for all constructors of the type. All constructors can be used regardless of parameter.

```haskell
data List (A : Set) : Set where
  []  : List A
  _::_ : A → List A → List A
```

`A` is a parameter.

We can use `nil` with `A` being `Bool`, we can use `cons` with `A` being `Bool`.



