
A type constructor is a type-level function that takes types or values as input and produces a new type.

```haskell
data List (A : Set) : Set where
  []  : List A
  _::_ : A → List A → List A
```

In the above, `List` is a type constructor.