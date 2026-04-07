Prerequisites:  [[1) Hopf 101]]
1) figure out how quaternions and block/quantumn come from hopf fibration
2) print the poster and the models, in fact in blender cut them up so theyre printable
3) mu equivalence, and the rest from the code

```haskell
data Susp (A : Type ℓ) : Type ℓ where
  north : Susp A
  south : Susp A
  merid : (a : A) → north ≡ south

μ-eq : (a : S¹) → S¹ ≃ S¹
μ-eq a = (λ z → a · z) , rotIsEquiv a

Hopf : Susp S¹ → Type₀
Hopf north = S¹
Hopf south = S¹
Hopf (merid a i₁) = ua (μ-eq a) i₁

TotalHopf : Type₀
TotalHopf = Σ (Susp S¹) Hopf
```