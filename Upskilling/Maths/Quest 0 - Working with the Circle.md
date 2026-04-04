
Goal: to prove that the fundamental group of S1 is Z.

Our definition of the circle in agda:

```haskell
data S¹ : Type where
  base : S¹ -- this constructor produces an S1
  loop : base ≡ base -- triple equals is a dependent type constructor. indexed by an element x of type A and produces a Type. The data constructor is refl, and calling refl with the element x will produce the type 'x = x'. remember in 'zero : Nat' zero is an element of type Nat. Here refl is an element of type 'x ≡ x'.
```

```haskell
data _≡_ {A : Set} (x : A) : A → Set where  
refl : x ≡ x
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

so `Type₀` is just `Set₀`, which is `Set0`.

#### ≡ Definition

What about `_≡_`?

```haskell
infix 4 _[_≡_] -- precedence

_[_≡_] : ∀ {ℓ} (A : I → Type ℓ ) → A i0 → A i1 → Type ℓ
_[_≡_] = PathP
```

for universe `l`,  We explicitly give a function from the unit interval `I` to any universe `Type` (so a type, a type of types etc.) Then two types `A i0` so the type given by indexing `A` by `i0` and `A i1`. This returns a new type- the type that `A i0` and `A i1` are equal? A path from `A i0` to `A i1`? And there is one constructor, which has the same name as the type, and it invokes `PathP` O.o. Gotta figure out what this is. This new method of equality (contrasted against the old method given below) has to, in the s1 definition, produce an s1. So despite being delegated to PathP it has to do the same

So now we need to figure out where `I`, `i0`, `i1`, and `PathP` come from.

#### PathP

`PathP` is a type constructor. The source code is in haskell

```haskell
(builtinPathP |-> builtinPostulateC CWithoutGlue (hPi "a" (el primLevel) $
  nPi "A" (tinterval --> return (sort $ varSort 0)) $
  (El (varSort 1) <$> varM 0 <@> primIZero) -->
  (El (varSort 1) <$> varM 0 <@> primIOne) -->
  return (sort $ varSort 1)))
```

The important thing to know is it has declaration

```haskell
PathP : ∀ {ℓ} (A : I → Set ℓ) → A i0 → A i1 → Set ℓ
```

#### `I`, `i0`, `i1`


