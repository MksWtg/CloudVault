An index is a value that a type depends on and affects its structure/shape. Indexes are explicit in dependent types.

```haskell
data Vec (A : Set) : Nat → Set where
  []  : Vec A 0
  _::_ : {n : Nat} → A → Vec A n → Vec A (suc n)
```

`n` indexes `Vec`.

Determines which constructors are allowed; changes the "shape".

```haskell
data Expr : Set → Set where
  Lit  : {A : Set} → A → Expr A
  Add  : Expr Nat → Expr Nat → Expr Nat
  Pair : {A B : Set} → Expr A → Expr B → Expr (A × B)
```

Here `Expr` is indexed by a type, it controls the constructors that can be used. If we try `Expr Bool` there is only one constructor we can use, `Lit`.