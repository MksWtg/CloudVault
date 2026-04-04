
Goal: to prove that the fundamental group of S1 is Z.

Our definition of the circle in agda:

```haskell
data S¹ : Type where
  base : S¹
  loop : base ≡ base
```

We know that 