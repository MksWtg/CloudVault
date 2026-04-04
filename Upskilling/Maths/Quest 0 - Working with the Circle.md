
Goal: to prove that the fundamental group of S1 is Z.

Our definition of the circle in agda:

```haskell
data S¹ : Type where
  base : S¹
  loop : base ≡ base
```

Off the bat so many questions.
1) What is the Sort `Type`
2) What is the equality `≡`
3) How is the equality in #2 able to produce an value of type `S1`