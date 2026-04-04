An index is a value that a type depends on and affects its structure/shape. Indexes are explicit in dependent types.

```haskell
data Vec (A : Set) : Nat → Set where
  []  : Vec A 0
  _::_ : {n : Nat} → A → Vec A n → Vec A (suc n)
```

`n` indexes `Vec`

