A data constructor is a function that produces values of a specific type defined by a type constructor.

```haskell
data List (A : Set) : Set where
  []  : List A        -- data constructor producing an empty list
  _::_ : A → List A → List A  -- data constructor producing a list by cons
```

The last term in the data constructor must be the type that the data constructor is producing (`List`).

It needs to provide all the params/indices needed by the type constructor.