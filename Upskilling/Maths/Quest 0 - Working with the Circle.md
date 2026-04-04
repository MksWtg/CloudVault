
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


## Source Code Useful Bits

Here are some relevant pieces of source code to make sense of the above parts.

This is actually a really easy and helpful step- all we do is look at the bits we want that we don't have (equality, type).

#### S1 Definition

```haskell
data S¹ : Type₀ where
  base : S¹
  loop : base ≡ base
```

#### Type0 Definition

`Type₀`

```
renaming ( lzero to ℓ-zero
           ; lsuc  to ℓ-suc
           ; _⊔_   to ℓ-max
           ; Set   to Type
           ; Setω  to Typeω )
```

so Type₀ is just Set₀