

Axiom\Choice.agda:32:choiceMap : {A : Type ℓ} {B : A → Type ℓ'} (n : ℕ)
Axiom\Choice.agda:40:satAC : (ℓ' : Level) (n : ℕ) (A : Type ℓ)  → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Axiom\Choice.agda:41:satAC ℓ' n A = (B : A → Type ℓ') → isEquiv (choiceMap {A = A} {B} n)
Axiom\Choice.agda:44:AC∃-map : {A : Type ℓ} {B : A → Type ℓ'}
Axiom\Choice.agda:45:     {C : (a : A) → B a → Type ℓ''}
Axiom\Choice.agda:52:satAC∃ : ∀ {ℓ} (ℓ' ℓ'' : Level) (A : Type ℓ) → Type _
Axiom\Choice.agda:53:satAC∃ ℓ' ℓ'' A = (B : A → Type ℓ') (C : (a : A) → B a → Type ℓ'')
Axiom\Choice.agda:56:satAC→satAC∃ : {A : Type ℓ}
Axiom\Choice.agda:64:-- All types satisfy (-2) level axiom of choice
Axiom\Choice.agda:65:satAC₀ : {A : Type ℓ} → satAC ℓ' 0 A
Axiom\Choice.agda:81:  ac-map' : ∀ {ℓ} (n m : ℕ) (B : Fin (suc m) → Type ℓ)
Axiom\ExcludedMiddle.agda:25:    A B C : Type ℓ
Axiom\ExcludedMiddle.agda:27:LEM : (ℓ : Level) → Type (ℓ-suc ℓ)
Axiom\ExcludedMiddle.agda:28:LEM ℓ = ∀ {A : Type ℓ} → isProp A → Dec A
Axiom\ExcludedMiddle.agda:35:  Diaconescu : (∀ (A : Type ℓ) → satAC∃ ℓ-zero ℓ A) → LEM ℓ
Axiom\ExcludedMiddle.agda:41:    𝟚/A : Type ℓ
Axiom\ExcludedMiddle.agda:59:      𝟚/A-effective-motive : ∀ b' → Type _
Axiom\ExcludedMiddle.agda:68:        helper : 𝟚/A → Type ℓ
Axiom\Omniscience.agda:12:  renaming (Bool to 𝟚; Bool→Type to ⟨_⟩)
Axiom\Omniscience.agda:23:    A : Type ℓ
Axiom\Omniscience.agda:29:LLPO : Type ℓ → Type ℓ
Axiom\Omniscience.agda:39:LLPO∞ : Type ℓ → Type ℓ
Axiom\Omniscience.agda:51:WLPO : Type ℓ → Type ℓ
Axiom\Omniscience.agda:54:WLPO' : Type ℓ → Type ℓ
Axiom\Omniscience.agda:94:LPO : Type ℓ → Type ℓ
Axiom\Omniscience.agda:103:LPO∞ : Type ℓ → Type ℓ
Axiom\UniquenessOfIdentity.agda:21:-- Define uniqueness of identity proofs and Axiom K for an individual type
Axiom\UniquenessOfIdentity.agda:23:module _ (A : Type ℓ) where
Axiom\UniquenessOfIdentity.agda:25:  UIP : Type ℓ
Axiom\UniquenessOfIdentity.agda:28:  AxiomK : (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Axiom\UniquenessOfIdentity.agda:29:  AxiomK ℓ' = (x : A) (P : x ≡ x → Type ℓ') → P refl → (∀ p → P p)
Axiom\UniquenessOfIdentity.agda:33:module _ {A : Type ℓ} where
Axiom\UniquenessOfIdentity.agda:49:¬UIPType : ∀ {ℓ} → ¬ UIP (Type ℓ)
Axiom\UniquenessOfIdentity.agda:50:¬UIPType {ℓ} uip =
Categories\Adjoint.agda:50:    : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD'))
Categories\Adjoint.agda:57:  record _⊣_ : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Adjoint.agda:187:  record _⊣_ {C : Category ℓC ℓC'} {D : Category ℓD ℓD'} (F : Functor C D) (G : Functor D C) : Type (ℓ-max
(ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Adjoint.agda:228:  isLeftAdjoint : {C : Category ℓC ℓC'} {D : Category ℓD ℓD'} (F : Functor C D) → Type (ℓ-max (ℓ-max ℓC
ℓC') (ℓ-max ℓD ℓD'))
Categories\Adjoint.agda:231:  isRightAdjoint : {C : Category ℓC ℓC'} {D : Category ℓD ℓD'} (G : Functor D C) → Type (ℓ-max (ℓ-max ℓC
ℓC') (ℓ-max ℓD ℓD'))
Categories\Category.agda:8:  Wild Category        Type   Type   No           (called precategory in UniMath)
Categories\Category.agda:9:  Category             Type   Set    No
Categories\Category.agda:10:  Univalent Category   Type   Set    Yes
Categories\Morphism.agda:42:  isMonic : Hom[ x , y ] → Type (ℓ-max ℓ ℓ')
Categories\Morphism.agda:68:  isEpic : (Hom[ x , y ]) → Type (ℓ-max ℓ ℓ')
Categories\Morphism.agda:82:  isSplitMon : (Hom[ x , y ]) → Type ℓ'
Categories\Morphism.agda:86:  isSplitEpi : (Hom[ x , y ]) → Type ℓ'
Categories\Morphism.agda:89:  record areInv (f : Hom[ x , y ]) (g : Hom[ y , x ]) : Type ℓ' where
Categories\UnderlyingGraph.agda:38:  Interp : Type _
Categories\Yoneda.agda:39:      natType = (FUNCTOR C (SET ℓ')) [ C [ c ,-] , F ]
Categories\Yoneda.agda:40:      setType = fst (F ⟅ c ⟆)
Categories\Yoneda.agda:43:      ϕ : natType → setType
Categories\Yoneda.agda:48:      Ψ : setType → natType
Categories\Yoneda.agda:56:      theIso : Iso natType setType
Categories\Yoneda.agda:79:          -- type aliases for natural transformation
Categories\Yoneda.agda:80:          NOType = N-ob-Type (C [ c ,-]) F
Categories\Yoneda.agda:81:          NHType = N-hom-Type (C [ c ,-]) F
Categories\Yoneda.agda:84:          αh≡βh : PathP (λ i → NHType (αo≡βo i)) αh βh -- αh βh
Categories\Yoneda.agda:87:              isProp-hom : (ϕ : NOType) → isProp (NHType ϕ)
Categories\Yoneda.agda:92:              isPropHomP : isOfHLevelDep 1 (λ ηo → NHType ηo)
Categories\Abelian\Base.agda:23:    record IsKernel {k : ob} (ker : Hom[ k , x ]) : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:29:    record Kernel : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:40:    record IsCokernel {c : ob} (coker : Hom[ y , c ]) : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:46:    record Cokernel : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:56:record PreAbCategoryStr (C : AdditiveCategory ℓ ℓ') : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:67:record PreAbCategory (ℓ ℓ' : Level) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Abelian\Base.agda:77:record AbelianCategoryStr (C : PreAbCategory ℓ ℓ') : Type (ℓ-max ℓ ℓ') where
Categories\Abelian\Base.agda:81:    _=ker_ : ∀ {k x y} → Hom[ k , x ] → Hom[ x , y ] → Type (ℓ-max ℓ ℓ')
Categories\Abelian\Base.agda:84:    _=coker_ : ∀ {c x y} → Hom[ y , c ] → Hom[ x , y ] → Type (ℓ-max ℓ ℓ')
Categories\Abelian\Base.agda:95:record AbelianCategory (ℓ ℓ' : Level): Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Additive\Base.agda:20:  record PreaddCategoryStr : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Categories\Additive\Base.agda:44:record PreaddCategory (ℓ ℓ' : Level) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Additive\Base.agda:59:  record ZeroObject : Type (ℓ-max ℓ ℓ') where
Categories\Additive\Base.agda:70:          : Type (ℓ-max ℓ ℓ') where
Categories\Additive\Base.agda:80:  record Biproduct (x y : ob) : Type (ℓ-max ℓ ℓ') where
Categories\Additive\Base.agda:93:  record AdditiveCategoryStr : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Categories\Additive\Base.agda:104:record AdditiveCategory (ℓ ℓ' : Level) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Additive\Quotient.agda:23:  module _ (_~_ : {x y : ob} (f g : Hom[ x , y ] ) → Type ℓq)
Categories\Additive\Quotient.agda:79:  module _ (_~_ : {x y : ob} (f g : Hom[ x , y ] ) → Type ℓq)
Categories\Category\Base.agda:14:record Category ℓ ℓ' : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Category\Base.agda:18:    ob : Type ℓ
Categories\Category\Base.agda:19:    Hom[_,_] : ob → ob → Type ℓ'
Categories\Category\Base.agda:42:_[_,_] : (C : Category ℓ ℓ') → (x y : C .ob) → Type ℓ'
Categories\Category\Base.agda:45:_End[_] : (C : Category ℓ ℓ') → (x : C .ob) → Type ℓ'
Categories\Category\Base.agda:66:record isIso (C : Category ℓ ℓ'){x y : C .ob}(f : C [ x , y ]) : Type ℓ' where
Categories\Category\Base.agda:89:CatIso : (C : Category ℓ ℓ') (x y : C .ob) → Type ℓ'
Categories\Category\Base.agda:120:record isUnivalent (C : Category ℓ ℓ') : Type (ℓ-max ℓ ℓ') where
Categories\Category\Path.agda:32:record CategoryPath (C C' : Category ℓ ℓ') : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Category\Path.agda:36:   Hom≡ : PathP (λ i → ob≡ i → ob≡ i → Type ℓ') (C .Hom[_,_]) (C' .Hom[_,_])
Categories\Category\Path.agda:125:     SquareP (λ i j → (p≡ i) j → (p≡ i) j → Type ℓ')
Categories\Category\Properties.agda:33:-- The following does *not* type check because of no-eta-equality.
Categories\Dagger\Base.agda:17:  record IsDagger (_† : {x y : ob} → Hom[ x , y ] → Hom[ y , x ]) : Type (ℓ-max ℓ ℓ') where
Categories\Dagger\Base.agda:39:  record DaggerStr : Type (ℓ-max ℓ ℓ') where
Categories\Dagger\Base.agda:47:record †Category (ℓ ℓ' : Level) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Dagger\Functor.agda:22:  record Is†Functor (F : Functor (C .cat) (D .cat)) : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Dagger\Functor.agda:32:  †Functor : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD'))
Categories\Dagger\Properties.agda:5:open import Cubical.Foundations.Isomorphism as TypeIso using () renaming (Iso to TypeIso)
Categories\Dagger\Properties.agda:31:    .Hom≡ → funExt λ x → funExt λ y → TypeIso.isoToPath λ where
Categories\Dagger\Properties.agda:32:      .TypeIso.fun → _†
Categories\Dagger\Properties.agda:33:      .TypeIso.inv → _†
Categories\Dagger\Properties.agda:34:      .TypeIso.sec → †-invol
Categories\Dagger\Properties.agda:35:      .TypeIso.ret → †-invol
Categories\Dagger\Properties.agda:78:  is†Monic is†Epic is†Iso is†PartialIso : Hom[ x , y ] → Type ℓ'
Categories\Dagger\Properties.agda:84:  isSelfAdjoint is†Idem : Hom[ x , x ] → Type ℓ'
Categories\Dagger\Properties.agda:88:  isPositive : Hom[ x , x ] → Type (ℓ-max ℓ ℓ')
Categories\Dagger\Properties.agda:138:  is†Unitary : CatIso C x y → Type ℓ'
Categories\Dagger\Properties.agda:144:  isUnitary†Cat : Type (ℓ-max ℓ ℓ')
Categories\Dagger\Properties.agda:147:  †CatIso : ob → ob → Type ℓ'
Categories\Dagger\Properties.agda:207:  record is†Univalent : Type (ℓ-max ℓ ℓ') where
Categories\Dagger\Properties.agda:228:    makeIs†Univalent .is†Univalent.univ {x} {y} = TypeIso.isoToIsEquiv iso where
Categories\Dagger\Properties.agda:230:      iso : TypeIso (x ≡ y) (†CatIso x y)
Categories\Dagger\Properties.agda:231:      iso .TypeIso.fun = pathTo†Iso
Categories\Dagger\Properties.agda:232:      iso .TypeIso.inv = †IsoToPath
Categories\Dagger\Properties.agda:233:      iso .TypeIso.sec f = Σ≡Prop (λ _ → isPropAreInv _) (†IsoToPath-β f)
Categories\Dagger\Properties.agda:234:      iso .TypeIso.ret = J (λ y p → †IsoToPath (pathTo†Iso p) ≡ p) (
Categories\Displayed\Adjoint.agda:26:    : Type (ℓ-max (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓCᴰ ℓCᴰ')) (ℓ-max (ℓ-max ℓD ℓD') (ℓ-max ℓDᴰ ℓDᴰ')))
where
Categories\Displayed\Base.agda:15:record Categoryᴰ (C : Category ℓC ℓC') ℓCᴰ ℓCᴰ' : Type (ℓ-suc (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓCᴰ
ℓCᴰ'))) where
Categories\Displayed\Base.agda:19:    ob[_] : ob → Type ℓCᴰ
Categories\Displayed\Base.agda:20:    Hom[_][_,_] : {x y : ob} → Hom[ x , y ] → ob[ x ] → ob[ y ] → Type ℓCᴰ'
Categories\Displayed\Base.agda:28:  _≡[_]_ : ∀ {x y xᴰ yᴰ} {f g : Hom[ x , y ]} → Hom[ f ][ xᴰ , yᴰ ] → f ≡ g → Hom[ g ][ xᴰ , yᴰ ] →
Type ℓCᴰ'
Categories\Displayed\Base.agda:55:    : Type ℓCᴰ'
Categories\Displayed\Base.agda:64:  CatIsoᴰ : {a b : ob} → CatIso C a b → ob[ a ] → ob[ b ] → Type ℓCᴰ'
Categories\Displayed\Cartesian.agda:38:    → Type (ℓ-max (ℓ-max ℓB ℓ'B) (ℓ-max ℓC ℓ'C))
Categories\Displayed\Cartesian.agda:50:  Opcleavage : Type (ℓ-max (ℓ-max ℓB ℓ'B) (ℓ-max ℓC ℓ'C))
Categories\Displayed\Cartesian.agda:57:  isOpfibration : Type (ℓ-max (ℓ-max ℓB ℓ'B) (ℓ-max ℓC ℓ'C))
Categories\Displayed\Cartesian.agda:60:  record isDiscreteOpfibration : Type (ℓ-max (ℓ-max ℓB ℓ'B) (ℓ-max ℓC ℓ'C)) where
Categories\Displayed\Functor.agda:22:  : Type (ℓ-max (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) (ℓ-max (ℓ-max ℓCᴰ ℓCᴰ') (ℓ-max ℓDᴰ ℓDᴰ')))
where
Categories\Displayed\HLevels.agda:27:  hasContrHoms : Type _
Categories\Displayed\HLevels.agda:32:  hasPropHoms : Type _
Categories\Displayed\NaturalTransformation.agda:24:    : Type (ℓ-max ℓC (ℓ-max ℓC' (ℓ-max ℓCᴰ (ℓ-max ℓCᴰ' ℓDᴰ')))) where
Categories\Displayed\Instances\LeftAdjointToReindex.agda:41:                Type ℓD'
Categories\Displayed\Instances\PropertyOver.agda:24:module _ (C : Category ℓC ℓC') (P : Category.ob C → Type ℓP) where
Categories\Displayed\Instances\StructureOver\Base.agda:20:  Type (ℓ-suc (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓCᴰ ℓCᴰ'))) where
Categories\Displayed\Instances\StructureOver\Base.agda:23:    ob[_] : ob → Type ℓCᴰ
Categories\Displayed\Instances\StructureOver\Base.agda:24:    Hom[_][_,_] : {x y : ob} → Hom[ x , y ] → ob[ x ] → ob[ y ] → Type ℓCᴰ'
Categories\Displayed\Section\Base.agda:109:  record Section : Type (ℓ-max (ℓ-max ℓC ℓC')
Categories\Displayed\Section\Base.agda:152:  GlobalSection : Type _
Categories\DistLatticeSheaf\Base.agda:55:   DLPreSheaf : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Categories\DistLatticeSheaf\Base.agda:94:  isDLSheafPullback : (F : DLPreSheaf) → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Categories\DistLatticeSheaf\Base.agda:105:  DLSheafPullback : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Categories\DistLatticeSheaf\Base.agda:111:  isDLSheaf : (F : DLPreSheaf) → Type _
Categories\DistLatticeSheaf\Base.agda:537: isDLBasisSheafPullback : DLBasisPreSheaf → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Categories\DistLatticeSheaf\Base.agda:549: DLBasisSheafPullback : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Categories\DistLatticeSheaf\Base.agda:586: isDLBasisSheaf : DLBasisPreSheaf → Type _
Categories\DistLatticeSheaf\Diagram.agda:41:  data DLShfDiagOb (n : ℕ) : Type ℓ where
Categories\DistLatticeSheaf\Diagram.agda:45:  data DLShfDiagHom (n : ℕ) : DLShfDiagOb n → DLShfDiagOb n → Type ℓ where
Categories\DistLatticeSheaf\Diagram.agda:56:    Code : (x y : DLShfDiagOb n) → Type
Categories\DistLatticeSheaf\Extension.agda:470:                B : I → Type ℓ''
Categories\DistLatticeSheaf\Extension.agda:548:      CommHypType : {n : ℕ} {β : FinVec (fst L) n} (β∈L' : ∀ i → β i ∈ L')
Categories\DistLatticeSheaf\Extension.agda:550:                  → Type ℓ''
Categories\DistLatticeSheaf\Extension.agda:551:      CommHypType β∈L' ccβ = ∀ i j →
Categories\DistLatticeSheaf\Extension.agda:569:                 → CommHypType β∈L' ccβ
Categories\DistLatticeSheaf\Extension.agda:570:                 → CommHypType (β∈L' ∘ suc) (coneSuc ccβ)
Categories\DistLatticeSheaf\Extension.agda:575:                  (ch : CommHypType β∈L' ccβ)
Categories\DistLatticeSheaf\Extension.agda:593:         (chₛ : CommHypType βₛ∈L' ccβₛ)
Categories\DistLatticeSheaf\Extension.agda:618:                          (ch : CommHypType β∈L' ccβ)
Categories\DistLatticeSheaf\Extension.agda:647:             (ch : CommHypType β∈L' ccβ)
Categories\DistLatticeSheaf\Extension.agda:656:                      (ch : CommHypType β∈L' ccβ)
Categories\DistLatticeSheaf\Extension.agda:666:                      (ch : CommHypType β∈L' ccβ)
Categories\Equivalence\AdjointEquivalence.agda:70:  record AdjointEquivalence : Type (ℓ-max (ℓ-max ℓC ℓ'C) (ℓ-max ℓD ℓ'D)) where
Categories\Equivalence\Base.agda:19:                     (func : Functor C D) : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Equivalence\Base.agda:30:              → (func : Functor C D) → Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD'))
Categories\Equivalence\Base.agda:34:               Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Equivalence\Properties.agda:119:    MorC : C .ob × C .ob → Type _
Categories\Equivalence\Properties.agda:122:    MorD : D .ob × D .ob → Type _
Categories\Equivalence\WeakEquivalence.agda:44:        (func : Functor C D) : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Equivalence\WeakEquivalence.agda:51:  : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Equivalence\WeakEquivalence.agda:132:  HomPathP : PathP (λ i → ua ob≃ i → ua ob≃ i → Type ℓC')
Categories\Functor\Base.agda:19:         Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\Functor\ComposeProperty.agda:52:    Mor : (d : D .ob) → Type _
Categories\Functor\ComposeProperty.agda:153:    Obj : (d : D .ob) → Type _
Categories\Functor\ComposeProperty.agda:220:    Mor : (d d' : D .ob)(f : D [ d , d' ]) → Type _
Categories\Functor\Equality.agda:28:  FunctorSingl : Type _
Categories\Functor\Equality.agda:35:    FunctorEq : Type _
Categories\Functor\Properties.agda:88:  -- hacky lemma helping with type inferences
Categories\Functor\Properties.agda:143:isConservative : (F : Functor C D) → Type _
Categories\Instances\CommAlgebras.agda:531:module PreSheafFromUniversalProp (C : Category ℓ ℓ') (P : ob C → Type ℓ)
Categories\Instances\Cospan.agda:10:data 𝟛 : Type ℓ-zero where
Categories\Instances\Discrete.agda:1:-- Discrete category over a type A
Categories\Instances\EilenbergMoore.agda:36:  record IsEMAlgebra (algA : Algebra M) : Type ℓC' where
Categories\Instances\EilenbergMoore.agda:50:  EMAlgebra : Type (ℓ-max ℓC ℓC')
Categories\Instances\Elements.agda:27:  Element : ∀ {ℓS} (F : Functor C (SET ℓS)) → Type (ℓ-max ℓ ℓS)
Categories\Instances\Elements.agda:87:  Elementᴾ : ∀ {ℓS} → Functor (C ^op) (SET ℓS) → Type (ℓ-max ℓ ℓS)
Categories\Instances\EssentialImage.agda:29:  isInEssentialImage : D .ob → Type (ℓ-max ℓC ℓD')
Categories\Instances\FullSubcategory.agda:21:module _ (C : Category ℓC ℓC') (P : Category.ob C → Type ℓP) where
Categories\Instances\FullSubcategory.agda:75:         (D : Category ℓD ℓD') (Q : Category.ob D → Type ℓQ) where
Categories\Instances\FullSubcategory.agda:88:module _ (C : Category ℓC ℓC') (P : Category.ob C → Type ℓP)
Categories\Instances\FullSubcategory.agda:89:         (D : Category ℓD ℓD') (Q : Category.ob D → Type ℓQ) where
Categories\Instances\FullSubcategory.agda:102:module _ (C : Category ℓC ℓC') (P : Category.ob C → Type ℓP) where
Categories\Instances\FullSubcategory.agda:114:module _ (C : Category ℓC ℓC') (P : Category.ob C → Type ℓP)
Categories\Instances\FullSubcategory.agda:115:         (D : Category ℓD ℓD') (Q : Category.ob D → Type ℓQ)
Categories\Instances\FullSubcategory.agda:116:         (E : Category ℓE ℓE') (R : Category.ob E → Type ℓR) where
Categories\Instances\FullSubcategory.agda:142:  {P : C .ob → Type ℓP}(isPropP : (c : C .ob) → isProp (P c))
Categories\Instances\FunctorAlgebras.agda:23:  IsAlgebra : ob C → Type ℓC'
Categories\Instances\FunctorAlgebras.agda:26:  record Algebra : Type (ℓ-max ℓC ℓC') where
Categories\Instances\FunctorAlgebras.agda:33:  IsAlgebraHom : (algA algB : Algebra) → C [ carrier algA , carrier algB ] → Type ℓC'
Categories\Instances\FunctorAlgebras.agda:36:  record AlgebraHom (algA algB : Algebra) : Type ℓC' where
Categories\Instances\FunctorAlgebras.agda:43:  RepAlgebraHom : (algA algB : Algebra) → Type ℓC'
Categories\Instances\Power.agda:16:PowerCategory : (X : Type ℓ) (C : Category ℓc ℓc') → Category _ _
Categories\Instances\Product.agda:1:-- Product of type-many categories
Categories\Instances\Product.agda:18:module _ (A : Type ℓA) (catC : A → Category ℓC ℓC') where
Categories\Instances\Quotient.agda:20:  module _ (_~_ : {x y : ob} (f g : Hom[ x , y ] ) → Type ℓq)
Categories\Instances\Free\Functor.agda:44:            → Type (((ℓ-max ℓg (ℓ-max ℓg' (ℓ-max ℓh ℓh'))))) where
Categories\Instances\Free\Functor.agda:214:          aom-type : ∀ {v w} → (f : FH [ v , w ]) → Type _
Categories\Instances\Free\Functor.agda:215:          aom-type {v}{w} f = PathP (λ i → 𝓓 [ aoo v i , aoo w i ])
Categories\Instances\Free\Functor.agda:219:          aom-id : ∀ {v} → aom-type {v} idₑ
Categories\Instances\Free\Functor.agda:223:                  → aom-type f
Categories\Instances\Free\Functor.agda:224:                  → aom-type g
Categories\Instances\Free\Functor.agda:225:                  → aom-type (f ⋆ₑ g)
Categories\Instances\Free\Functor.agda:293:                      the-type = (G .Node → 𝓓 .ob)
Categories\Instances\Free\Functor.agda:294:                      A = (λ (f : the-type) → 𝓓 [ f v , f w ])
Categories\Instances\Free\Functor.agda:295:          aom : ∀ {v w : H .Node} (f : FH [ v , w ]) → aom-type f
Categories\Instances\Free\Category\Base.agda:32:    data Exp : G .Node → G .Node → Type (ℓ-max ℓg ℓg') where
Categories\Instances\Free\Category\Base.agda:67:          aom-t : ∀ {c c'} (e : Exp c c') → Type _
Categories\Instances\Free\Category\Quiver.agda:40:  data Exp : Q .fst → Q .fst → Type (ℓ-max ℓg ℓg') where
Categories\Instances\Free\Category\Quiver.agda:60:  Interp : (𝓒 : Category ℓc ℓc') → Type (ℓ-max (ℓ-max (ℓ-max ℓg ℓg') ℓc) ℓc')
Categories\Instances\Free\Category\Quiver.agda:70:    Interpᴰ : Type _
Categories\Instances\Slice\Base.agda:22:TypeC : Type (ℓ-suc (ℓ-max ℓ ℓ'))
Categories\Instances\Slice\Base.agda:23:TypeC = Type (ℓ-max ℓ ℓ')
Categories\Instances\Slice\Base.agda:27:record SliceOb : TypeC where
Categories\Instances\Slice\Base.agda:35:record SliceHom (a b : SliceOb) : Type ℓ' where
Categories\Instances\Slice\Base.agda:72:-- If the type of objects of C forms a set then so does the type of objects of the slice cat
Categories\Instances\Slice\Base.agda:108:-- SliceHom is isomorphic to the Sigma type with the same components
Categories\Instances\Slice\Base.agda:148:      -- we want all paths between (dependent) paths of this type to be equal
Categories\Instances\Slice\Base.agda:198:        -- this is just here because the type checker can't seem to infer xf and yg
Categories\Limits\BinCoproduct.agda:22:    isBinCoproduct : Type (ℓ-max ℓ ℓ')
Categories\Limits\BinCoproduct.agda:30:  record BinCoproduct (x y : ob) : Type (ℓ-max ℓ ℓ') where
Categories\Limits\BinCoproduct.agda:38:  BinCoproducts : Type (ℓ-max ℓ ℓ')
Categories\Limits\BinCoproduct.agda:41:  hasBinCoproducts : Type (ℓ-max ℓ ℓ')
Categories\Limits\BinProduct.agda:22:    isBinProduct : Type (ℓ-max ℓ ℓ')
Categories\Limits\BinProduct.agda:30:  record BinProduct (x y : ob) : Type (ℓ-max ℓ ℓ') where
Categories\Limits\BinProduct.agda:53:  BinProducts : Type (ℓ-max ℓ ℓ')
Categories\Limits\BinProduct.agda:56:  hasBinProducts : Type (ℓ-max ℓ ℓ')
Categories\Limits\Initial.agda:22:  isInitial : (x : ob) → Type (ℓ-max ℓ ℓ')
Categories\Limits\Initial.agda:25:  Initial : Type (ℓ-max ℓ ℓ')
Categories\Limits\Initial.agda:42:  hasInitial : Type (ℓ-max ℓ ℓ')
Categories\Limits\Initial.agda:60:  -- The type of initial objects of a univalent category is a proposition,
Categories\Limits\Initial.agda:73:  preservesInitial : Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD'))
Categories\Limits\Limits.agda:30:  record Cone (D : Functor J C) (c : ob C) : Type (ℓ-max (ℓ-max ℓJ ℓJ') ℓC') where
Categories\Limits\Limits.agda:114:            → C [ c1 , c2 ] → Type (ℓ-max ℓJ ℓC')
Categories\Limits\Limits.agda:137:  isLimCone : (D : Functor J C) (c0 : ob C) → Cone D c0 → Type ℓ
Categories\Limits\Limits.agda:151:  record LimCone (D : Functor J C) : Type ℓ where
Categories\Limits\Limits.agda:348:Limits : {ℓJ ℓJ' ℓC ℓC' : Level} → Category ℓC ℓC' → Type _
Categories\Limits\Limits.agda:351:hasLimits : {ℓJ ℓJ' ℓC ℓC' : Level} → Category ℓC ℓC' → Type _
Categories\Limits\Limits.agda:355:LimitsOfShape : {ℓJ ℓJ' ℓC ℓC' : Level} → Category ℓJ ℓJ' → Category ℓC ℓC' → Type _
Categories\Limits\Limits.agda:374:  preservesLimits : Type _
Categories\Limits\Pullback.agda:24:  record Cospan : Type (ℓ-max ℓ ℓ') where
Categories\Limits\Pullback.agda:35:    (H : p₁ ⋆ cspn .s₁ ≡ p₂ ⋆ cspn .s₂) → Type (ℓ-max ℓ ℓ')
Categories\Limits\Pullback.agda:47:  record Pullback (cspn : Cospan) : Type (ℓ-max ℓ ℓ') where
Categories\Limits\Pullback.agda:87:  Pullbacks : Type (ℓ-max ℓ ℓ')
Categories\Limits\Pullback.agda:90:  hasPullbacks : Type (ℓ-max ℓ ℓ')
Categories\Limits\Terminal.agda:19:  isTerminal : (x : ob) → Type (ℓ-max ℓ ℓ')
Categories\Limits\Terminal.agda:22:  Terminal : Type (ℓ-max ℓ ℓ')
Categories\Limits\Terminal.agda:39:  hasTerminal : Type (ℓ-max ℓ ℓ')
Categories\Limits\Terminal.agda:64:  -- The type of terminal objects of a univalent category is a proposition,
Categories\Limits\Terminal.agda:72:                   → Type (ℓ-max (ℓ-max (ℓ-max ℓc ℓc') ℓd) ℓd')
Categories\Monad\Base.agda:20:  IsPointed : Type (ℓ-max ℓ ℓ')
Categories\Monad\Base.agda:23:  record IsMonad : Type (ℓ-max ℓ ℓ') where
Categories\Monad\Base.agda:54:  Monad : Type (ℓ-max ℓ ℓ')
Categories\Monad\Base.agda:66:  record IsMonadHom : Type (ℓ-max ℓ ℓ') where
Categories\Monad\Base.agda:78:  MonadHom : Type (ℓ-max ℓ ℓ')
Categories\Monoidal\Base.agda:17:  record TensorStr : Type (ℓ-max ℓ ℓ') where
Categories\Monoidal\Base.agda:33:  record StrictMonStr : Type (ℓ-max ℓ ℓ') where
Categories\Monoidal\Base.agda:60:  record MonoidalStr : Type (ℓ-max ℓ ℓ') where
Categories\Monoidal\Base.agda:118:record StrictMonCategory ℓ ℓ' : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Monoidal\Base.agda:127:record MonoidalCategory ℓ ℓ' : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Categories\Monoidal\Enriched.agda:13:  record EnrichedCategory : Type (ℓ-max (ℓ-max ℓV ℓV') (ℓ-suc ℓE)) where
Categories\Monoidal\Enriched.agda:15:      ob : Type ℓE
Categories\Monoidal\Strict\Monoid.agda:16:    record Monoid : Type (ℓ-max ℓ ℓ') where
Categories\Monoidal\Strict\Monoid.agda:28:    record Monoid[_,_] (monA monB : Monoid) : Type ℓ' where
Categories\NaturalTransformation\Base.agda:28:  -- type aliases because it gets tedious typing it out all the time
Categories\NaturalTransformation\Base.agda:29:  N-ob-Type : (F G : Functor C D) → Type _
Categories\NaturalTransformation\Base.agda:30:  N-ob-Type F G = (x : C .ob) → D [(F .F-ob x) , (G .F-ob x)]
Categories\NaturalTransformation\Base.agda:32:  N-hom-Type : (F G : Functor C D) → N-ob-Type F G → Type _
Categories\NaturalTransformation\Base.agda:33:  N-hom-Type F G ϕ = {x y : C .ob} (f : C [ x , y ]) → (F .F-hom f) ⋆ᴰ (ϕ y) ≡ (ϕ x) ⋆ᴰ
(G .F-hom f)
Categories\NaturalTransformation\Base.agda:35:  record NatTrans (F G : Functor C D) : Type (ℓ-max (ℓ-max ℓC ℓC') ℓD') where
Categories\NaturalTransformation\Base.agda:39:      N-ob : N-ob-Type F G
Categories\NaturalTransformation\Base.agda:41:      N-hom :  N-hom-Type F G N-ob
Categories\NaturalTransformation\Base.agda:43:  record NatIso (F G : Functor C D): Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
Categories\NaturalTransformation\Base.agda:73:  _⇒_ : Functor C D → Functor C D → Type (ℓ-max (ℓ-max ℓC ℓC') ℓD')
Categories\NaturalTransformation\Base.agda:78:  _≅ᶜ_ : Functor C D → Functor C D → Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD'))
Categories\NaturalTransformation\Properties.agda:56:      NatTransΣ : Type (ℓ-max (ℓ-max ℓC ℓC') ℓD')
Categories\NaturalTransformation\Properties.agda:70:      NatTrans-≡-intro : ∀ {αo βo : N-ob-Type F G}
Categories\NaturalTransformation\Properties.agda:71:                           {αh : N-hom-Type F G αo}
Categories\NaturalTransformation\Properties.agda:72:                           {βh : N-hom-Type F G βo}
Categories\Presheaf\Base.agda:14:Presheaf : Category ℓ ℓ' → (ℓS : Level) → Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-suc ℓS))
Categories\Presheaf\KanExtension.agda:55:      Raw : Type ℓ
Categories\Presheaf\KanExtension.agda:58:      data _≈_ : (u v : Raw) → Type ℓ where
Categories\Presheaf\KanExtension.agda:227:    record End (d : D.ob) : Type ℓ where
Categories\Presheaf\KanExtension.agda:264:    -- We use that End is equivalent to a Σ-type to prove its HLevel more easily
Categories\Presheaf\Morphism.agda:48:  PshHom : Type (ℓ-max (ℓ-max (ℓ-max ℓc ℓc') ℓp) ℓq)
Categories\Presheaf\Morphism.agda:77:                            → Type (ℓ-max (ℓ-max ℓd ℓd') ℓq)
Categories\Presheaf\Morphism.agda:81:    preservesRepresentations : Type _
Categories\Presheaf\Properties.agda:214:          natuType : fst (A ⟅ c ⟆) → Type _
Categories\Presheaf\Properties.agda:215:          natuType xX@(x , X) = ((F ⟪ f ⟫) x , (η ⟦ d , (F ⟪ f ⟫) x ⟧) ((P ⟪ f , refl ⟫) X)) ≡
((F ⟪ f ⟫) x , (Q ⟪ f , refl ⟫) ((η ⟦ c , x ⟧) X))
Categories\Presheaf\Properties.agda:216:          natu : ∀ (xX : fst (A ⟅ c ⟆)) → natuType xX
Categories\Presheaf\Properties.agda:239:    -- a type is isomorphic to the disjoint union of all its fibers
Categories\Presheaf\Properties.agda:240:    typeSectionIso : ∀ {A B : Type ℓS} {isSetB : isSet B} → (ϕ : A → B)
Categories\Presheaf\Properties.agda:242:    typeSectionIso ϕ .fun a = (ϕ a) , (a , refl)
Categories\Presheaf\Properties.agda:243:    typeSectionIso ϕ .inv (b , (a , eq)) = a
Categories\Presheaf\Properties.agda:244:    typeSectionIso {isSetB = isSetB} ϕ .sec (b , (a , eq))
Categories\Presheaf\Properties.agda:248:    typeSectionIso ϕ .ret a = refl
Categories\Presheaf\Properties.agda:251:    -- just applies typeSectionIso
Categories\Presheaf\Properties.agda:259:        A⇒LK .N-ob c = typeSectionIso {isSetB = snd (F ⟅ c ⟆)} (ϕ ⟦ c ⟧) .fun
Categories\Presheaf\Properties.agda:275:    -- isomorphism follows from typeSectionIso
Categories\Presheaf\Properties.agda:282:        isIsoCf c = Morphism.CatIso→isIso (Iso→CatIso (typeSectionIso {isSetB = snd (F ⟅ c ⟆)}
(ϕ ⟦ c ⟧)))
Categories\Presheaf\Properties.agda:292:    -- says that a type family at x is isomorphic to the fiber over x of that type family
packaged up
Categories\Presheaf\Properties.agda:293:    typeFiberIso : ∀ {ℓ ℓ'} {A : Type ℓ} {isSetA : isSet A} {x} (B : A → Type ℓ')
Categories\Presheaf\Properties.agda:295:    typeFiberIso {x = x} _ .fun b = (x , b) , refl
Categories\Presheaf\Properties.agda:296:    typeFiberIso _ .inv ((a , b) , eq) = subst _ eq b
Categories\Presheaf\Properties.agda:297:    typeFiberIso {isSetA = isSetA} {x = x} B .sec ((a , b) , eq)
Categories\Presheaf\Properties.agda:299:    typeFiberIso {x = x} _ .ret b = sym (transport-filler refl b)
Categories\Presheaf\Properties.agda:302:    -- applies typeFiberIso (inv)
Categories\Presheaf\Properties.agda:310:        γ-ob el@(c , _) = typeFiberIso {isSetA = snd (F ⟅ c ⟆)} (λ x → fst (P ⟅ c , x ⟆)) .inv
Categories\Presheaf\Properties.agda:360:            -- extracted out type since need to use in in 'left' body as well
Categories\Presheaf\Properties.agda:361:            leftTy : (x' ≡ x) → Type _
Categories\Presheaf\Properties.agda:379:        isIsoC' cx@(c , _) = Morphism.CatIso→isIso (Iso→CatIso (invIso (typeFiberIso {isSetA =
snd (F ⟅ c ⟆)} _)))
Categories\Presheaf\Properties.agda:396:PshIso : (C : Category ℓ ℓ') (P : Presheaf C ℓS) (Q : Presheaf C ℓS') → Type _
Categories\Presheaf\Representable.agda:18:    implemented with a custom record type UniversalElement and is
Categories\Presheaf\Representable.agda:59:  Representation : Type (ℓ-max (ℓ-max ℓo (ℓ-suc ℓh)) (ℓ-suc ℓp))
Categories\Presheaf\Representable.agda:63:  Representable : Type (ℓ-max (ℓ-max ℓo (ℓ-suc ℓh)) (ℓ-suc ℓp))
Categories\Presheaf\Representable.agda:68:  TerminalElement : Type (ℓ-max (ℓ-max ℓo ℓh) ℓp)
Categories\Presheaf\Representable.agda:71:  hasTerminalElement : Type (ℓ-max (ℓ-max ℓo ℓh) ℓp)
Categories\Presheaf\Representable.agda:75:              → Type (ℓ-max (ℓ-max ℓo ℓh) ℓp)
Categories\Presheaf\Representable.agda:82:  record UniversalElement : Type (ℓ-max (ℓ-max ℓo ℓh) ℓp) where
Categories\Presheaf\Representable.agda:91:  hasUniversalElement : Type (ℓ-max (ℓ-max ℓo ℓh) ℓp)
Categories\Presheaf\NonPresheaf\Forget.agda:22:NonPresheaf : Category ℓ ℓ' → (ℓS : Level) → Type (ℓ-max ℓ (ℓ-suc ℓS))
Categories\Profunctor\Base.agda:49:  Cat : Type _
Categories\Profunctor\Base.agda:70:  record Profunctor⊶ (C D : Cat) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Categories\Profunctor\Base.agda:83:    Het[_,_] : C.ob → D.ob → Type ℓ'
Categories\Profunctor\Base.agda:163:  Profunctor⊷ : ∀ (C D : Cat) → Type _
Categories\Profunctor\Base.agda:168:  record Homomorphism {C D : Cat} (P Q : C ⊶ D) : Type (ℓ-max ℓ ℓ') where
Categories\Profunctor\Base.agda:187:  homomorphism : {C D : Cat} → C ⊶ D → C ⊶ D → Type _
Categories\Profunctor\Base.agda:209:  _Represents_ : {C D : Cat} (F : Functor C D) (R : C ⊶ D) → Type _
Categories\Profunctor\Base.agda:213:  Representable : {C D : Cat} → C ⊶ D → Type _
Categories\Profunctor\Base.agda:216:  record Representable' {C D : Cat} (R : C ⊶ D) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Categories\RezkCompletion\Base.agda:31:isRezkCompletion : (F : Functor C D) → Typeω
Categories\RezkCompletion\Construction.agda:42:-- another one is using a higher inductive type
Categories\RezkCompletion\Construction.agda:73:{- The Construction by Higher Inductive Type -}
Categories\RezkCompletion\Construction.agda:86:    IsoC : ob C → ob C → Type ℓ'
Categories\RezkCompletion\Construction.agda:92:  RezkOb : Type (ℓ-max ℓ ℓ')
Categories\RezkCompletion\Construction.agda:107:  elim : {P : RezkOb → Type ℓ''} → _ → (f : _) → (feq : _) → _ → ∀ x → P x
Categories\RezkCompletion\Construction.agda:110:  elimSet : {P : RezkOb → Type ℓ''} → _ → (f : _) → _ → ∀ x → P x
Categories\RezkCompletion\Construction.agda:113:  elimProp : {P : RezkOb → Type ℓ''} → _ → _ → ∀ x → P x
Categories\RezkCompletion\Construction.agda:116:  rec : {P : Type ℓ''} → _ → (f : _) → (feq : _) → _ → RezkOb → P
Categories\RezkCompletion\Construction.agda:119:  module _ {P : RezkOb → RezkOb → Type ℓ''}
Categories\RezkCompletion\Construction.agda:132:  module _ {P : RezkOb → RezkOb → Type ℓ''}
Categories\RezkCompletion\Construction.agda:140:  module _ {P : RezkOb → RezkOb → RezkOb → Type ℓ''}
Categories\RezkCompletion\Construction.agda:155:  module _ {P : Type ℓ''}
Categories\RezkCompletion\Construction.agda:219:    H-inc-ua f = TypeOfHLevel≡ 2 $ isoToPath λ where
Categories\RezkCompletion\Construction.agda:226:    H-ua-inc f = TypeOfHLevel≡ 2 $ isoToPath λ where
Categories\RezkCompletion\Construction.agda:232:    typeSquare : ∀ {A B C D : Type ℓ''} {P : A ≡ B} {Q : C ≡ D} {R S}
Categories\RezkCompletion\Construction.agda:235:    typeSquare h = compPath→Square $ isInjectiveTransport $ funExt λ x →
Categories\RezkCompletion\Construction.agda:240:    H-ua-inc-ua g f = ΣSquareSet (λ _ → isProp→isSet isPropIsSet) $ typeSquare λ h →
Categories\RezkCompletion\Construction.agda:255:    H-inc-sq f g = ΣSquareSet (λ _ → isProp→isSet isPropIsSet) $ typeSquare λ h →
Categories\RezkCompletion\Construction.agda:270:    H-sq-inc f g = ΣSquareSet (λ _ → isProp→isSet isPropIsSet) $ typeSquare λ h →
Categories\RezkCompletion\Construction.agda:283:  RezkHom : RezkOb → RezkOb → Type ℓ'
Categories\RezkCompletion\Construction.agda:290:    tr : {A : Type ℓ''} → transport refl ≡ idfun A
Categories\Site\Cover.agda:21:  Cover : (ℓpat : Level) → ob C → Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-suc ℓpat))
Categories\Site\Cover.agda:22:  Cover ℓpat c = TypeWithStr ℓpat λ patches → patches → ob (SliceCat C c)
Categories\Site\Coverage.agda:30:  record Coverage (ℓcov ℓpat : Level) : Type (ℓ-max ℓ (ℓ-max ℓ' (ℓ-suc (ℓ-max ℓcov ℓpat)))) where
Categories\Site\Coverage.agda:33:      covers : (c : ob) → TypeWithStr ℓcov λ Cov → Cov → (Cover C ℓpat c)
Categories\Site\Sheaf.agda:39:    FamilyOnCover : Type (ℓ-max ℓP ℓ'')
Categories\Site\Sheaf.agda:42:    isCompatibleFamily : FamilyOnCover → Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓP) ℓ'')
Categories\Site\Sheaf.agda:56:    CompatibleFamily : Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓP) ℓ'')
Categories\Site\Sheaf.agda:81:    hasAmalgamationPropertyForCover : Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓP) ℓ'')
Categories\Site\Sheaf.agda:99:  isSeparated : Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓcov) ℓpat) ℓP)
Categories\Site\Sheaf.agda:113:  isSheaf : Type (ℓ-max (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓcov) ℓpat) ℓP)
Categories\Site\Sheaf.agda:136:  Sheaf : Type (ℓ-max (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓcov) ℓpat) (ℓ-suc ℓF))
Categories\Site\Sheaf.agda:152:  isSubcanonical : Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓcov) ℓpat)
Categories\Site\Sieve.agda:25:  record Sieve (ℓsie : Level) (c : ob) : Type (ℓ-max ℓ (ℓ-max ℓ' (ℓ-suc ℓsie))) where
Categories\Site\Sieve.agda:28:      passes : {d : ob} → Hom[ d , c ] → Type ℓsie
Categories\Site\Sieve.agda:48:    Type (ℓ-max (ℓ-max (ℓ-max ℓ ℓ') ℓS') ℓS)
Categories\Site\Sieve.agda:81:    Type (ℓ-max ℓcov ℓsie)
Categories\Site\Instances\ZariskiCommRing.agda:38:-- the type of unimodular vectors, i.e. generators of the 1-ideal
Categories\Site\Instances\ZariskiCommRing.agda:39:record UniModVec (R : CommRing ℓ) : Type ℓ where
Categories\Site\Sheafification\Base.agda:4:-- using a quotient inductive type (QIT).
Categories\Site\Sheafification\Base.agda:40:  data ⟨sheafification⟅_⟆⟩ : ob → Type (ℓ-max ℓ (ℓ-max ℓ' (ℓ-max ℓcov (ℓ-max ℓpat ℓP))))
where
Categories\Site\Sheafification\ElimProp.agda:38:    (B : {c : ob} → ⟨ sheafification ⟅ c ⟆ ⟩ → Type ℓB)
Categories\Site\Sheafification\ElimProp.agda:73:    {B : {c : ob} → ⟨ sheafification ⟅ c ⟆ ⟩ → Type ℓB}
Categories\Site\Sheafification\ElimProp.agda:153:    {B : {c : ob} → ⟨ sheafification ⟅ c ⟆ ⟩ → Type ℓB}
Categories\Site\Sheafification\ElimProp.agda:161:      B' : {c : ob} → ⟨ sheafification ⟅ c ⟆ ⟩ → Type (ℓ-max (ℓ-max ℓ ℓ') ℓB)
Categories\Site\Sheafification\UniversalProperty.agda:131:          B : {c : ob} → ⟨ sheafification ⟅ c ⟆ ⟩ → Type _
Categories\TypesOfCategories\TypeCategory.agda:2:module Cubical.Categories.TypesOfCategories.TypeCategory where
Categories\TypesOfCategories\TypeCategory.agda:20:record isTypeCategory {ℓ ℓ' ℓ''} (C : Category ℓ ℓ')
Categories\TypesOfCategories\TypeCategory.agda:21:       : Type (ℓ-max ℓ (ℓ-max ℓ' (ℓ-suc ℓ''))) where
Categories\TypesOfCategories\TypeCategory.agda:26:    -- a Type of types over a context
Categories\TypesOfCategories\TypeCategory.agda:27:    Ty[_] : ob → Type ℓ''
Categories\TypesOfCategories\TypeCategory.agda:28:    -- extend a context with a type
Categories\TypesOfCategories\TypeCategory.agda:57:-- presheaves are type contexts
Categories\TypesOfCategories\TypeCategory.agda:59:  open isTypeCategory
Categories\TypesOfCategories\TypeCategory.agda:65:    isSurjSET : ∀ {ℓ} {A B : SET ℓ .ob} → (f : SET ℓ [ A , B ]) → Type _
Categories\TypesOfCategories\TypeCategory.agda:68:    -- types over Γ are types with a "projection" (aka surjection) to Γ
Categories\TypesOfCategories\TypeCategory.agda:69:    PSTy[_] : PresheafCategory C ℓ'' .ob → Type _
Categories\TypesOfCategories\TypeCategory.agda:74:    -- just directly use types from above as context extensions
Categories\TypesOfCategories\TypeCategory.agda:184:  isTypeCategoryPresheaf : isTypeCategory (PresheafCategory C ℓ'')
Categories\TypesOfCategories\TypeCategory.agda:185:  isTypeCategoryPresheaf .Ty[_] Γ = PSTy[ Γ ]
Categories\TypesOfCategories\TypeCategory.agda:186:  isTypeCategoryPresheaf .cext = PSCext
Categories\TypesOfCategories\TypeCategory.agda:187:  isTypeCategoryPresheaf .reindex = PSReindex
Categories\TypesOfCategories\TypeCategory.agda:188:  isTypeCategoryPresheaf .q⟨_,_⟩ = PSq
Categories\TypesOfCategories\TypeCategory.agda:189:  isTypeCategoryPresheaf .sq = PSSq
Categories\TypesOfCategories\TypeCategory.agda:190:  isTypeCategoryPresheaf .isPB = PSIsPB
Codata\Conat\Base.agda:11:datatype, another way of definition is to define an inductive datatype that
Codata\Conat\Base.agda:18:of Sized Types.
Codata\Conat\Base.agda:29:record Conat : Type₀
Codata\Conat\Bounded.agda:28:_≺_ : ℕ → Conat → Type _
Codata\Conat\Bounded.agda:29:_≺′_ : ℕ → Conat′ → Type _
Codata\Conat\Bounded.agda:50:  apart : ℕ → ℕ → Type
Codata\Conat\Bounded.agda:72:_#_ : ∀{P : ℕ → Type ℓ} → (l r : Σ ℕ P) → Type
Codata\Conat\Bounded.agda:75:#→≢ : ∀{P : ℕ → Type ℓ} → (l r : Σ ℕ P) → l # r → ¬ l ≡ r
Codata\Conat\Bounded.agda:78:isProp# : ∀{P : ℕ → Type ℓ} (l r : Σ ℕ P) → isProp (l # r)
Codata\Conat\Bounded.agda:81:isProp#Depᵣ : ∀{P : ℕ → Type ℓ} (r : Σ ℕ P) → isPropDep (_# r)
Codata\Conat\Bounded.agda:84:Bounded : Conat → Type
Codata\Conat\Bounded.agda:87:Bounded′ : Conat′ → Type
Codata\Conat\Properties.agda:31:  renaming (Bool→Type to ⟨_⟩)
Codata\Conat\Properties.agda:52:Unwrap-prev : Conat′ → Type₀
Codata\Conat\Properties.agda:115:conat-absurd : ∀ {y : Conat} {ℓ} {Whatever : Type ℓ} → zero ≡ suc y → Whatever
Codata\Conat\Properties.agda:118:  diag : Conat′ → Type₀
Codata\Conat\Properties.agda:168:  record _≈_ (x y : Conat) : Type₀
Codata\Conat\Properties.agda:169:  data _≈′_ (x y : Conat′) : Type₀
Codata\Conat\Properties.agda:170:  _≈′′_ : Conat′ → Conat′ → Type₀
Codata\Containers\Coalgebras.agda:16:module Coalgs (S : Type ℓ) (Q : S → Type ℓ') where
Codata\Containers\CoinductiveContainers.agda:3:Adapted from 'Containers: Constructing strictly positive types'
Codata\Containers\CoinductiveContainers.agda:22:         (Ind : Type)
Codata\Containers\CoinductiveContainers.agda:23:         (S : Type)
Codata\Containers\CoinductiveContainers.agda:25:         (P : Ind → S → Type)
Codata\Containers\CoinductiveContainers.agda:26:         (Q : S → Type)
Codata\Containers\CoinductiveContainers.agda:28:         (X : Ind → Type)
Codata\Containers\CoinductiveContainers.agda:29:         (Y : Type)
Codata\Containers\CoinductiveContainers.agda:88:      data R : M S Q → M S Q → Type where
Codata\Containers\CoinductiveContainers.agda:100:          MCoind : {S : Type} {Q : S → Type} (R : M S Q → M S Q → Type)
Codata\Containers\CoinductiveContainers.agda:106:              where QQ : I → Type
Codata\Containers\CoinductiveContainers.agda:180:          propElim : ∀ {ℓ ℓ'} {A : Type ℓ} (t : isProp A) → (D : A → Type ℓ') →
Codata\M\Container.agda:29:-- Σ[ A ∈ (Type ℓ) ] (A → Type ℓ)
Codata\M\Container.agda:30:Container : ∀ ℓ -> Type (ℓ-suc ℓ)
Codata\M\Container.agda:31:Container ℓ = TypeWithStr ℓ (λ x → x → Type ℓ)
Codata\M\Container.agda:37:P₀ : ∀ {ℓ} (S : Container ℓ) -> Type ℓ -> Type ℓ
Codata\M\Container.agda:48:record Chain ℓ : Type (ℓ-suc ℓ) where
Codata\M\Container.agda:51:    X : ℕ -> Type ℓ
Codata\M\Container.agda:56:limit-of-chain : ∀ {ℓ} -> Chain ℓ → Type ℓ
Codata\M\Container.agda:63:-- Limit type of a Container , and Shift of a Limit --
Codata\M\Container.agda:66:Wₙ : ∀ {ℓ} -> Container ℓ -> ℕ -> Type ℓ
Codata\M\Container.agda:84:-- M type is limit of a sequence --
Codata\M\Container.agda:87:M : ∀ {ℓ} -> Container ℓ → Type ℓ
Codata\M\helper.agda:30:  ∀ {ℓ} {A B C : Type ℓ} (isom : Iso A B)
Codata\M\helper.agda:38:    ∀ {ℓ} {A B C : Type ℓ} (isom : Iso A B)
Codata\M\helper.agda:45:  ∀ {ℓ} {A B C : Type ℓ} (isom : Iso A B)
Codata\M\helper.agda:58:  ∀ {ℓ} {A B C : Type ℓ} (isom : Iso A B)
Codata\M\helper.agda:65:  ∀ {ℓ} {A B C : Type ℓ} (isom : Iso A B) →
Codata\M\helper.agda:72:    ∀ {ℓ} {A B : Type ℓ}
Codata\M\helper.agda:94:  ∀ {ℓ} {A B : Type ℓ}
Codata\M\helper.agda:102:  ∀ {ℓ} {A B : Type ℓ}
Codata\M\helper.agda:110:  ∀ {ℓ} {A B : Type ℓ}
Codata\M\itree.agda:19:-- Delay monad defined as an M-type
Codata\M\itree.agda:20:delay-S : (R : Type₀) -> Container ℓ-zero
Codata\M\itree.agda:23:delay : (R : Type₀) -> Type₀
Codata\M\itree.agda:26:delay-ret : {R : Type₀} -> R -> delay R
Codata\M\itree.agda:29:delay-tau : {R : Type₀} -> delay R -> delay R
Codata\M\itree.agda:33:tree-S : (E : Type₀ -> Type₁) (R : Type₀) -> Container (ℓ-suc ℓ-zero)
Codata\M\itree.agda:34:tree-S E R = (R ⊎ (Σ[ A ∈ Type₀ ] (E A))) , (λ { (inl _) -> ⊥* ; (inr (A , e)) -> Lift _ A } )
Codata\M\itree.agda:36:tree : (E : Type₀ -> Type₁) (R : Type₀) -> Type₁
Codata\M\itree.agda:50:itree-S : ∀ (E : Type₀ -> Type₁) (R : Type₀) -> Container (ℓ-suc ℓ-zero)
Codata\M\itree.agda:51:itree-S E R = ((Unit ⊎ R) ⊎ (Σ[ A ∈ Type₀ ] (E A))) , (λ { (inl (inl _)) -> Unit* ; (inl (inr _)) -> ⊥* ; (inr
(A , e)) -> Lift _ A } )
Codata\M\itree.agda:53:itree :  ∀ (E : Type₀ -> Type₁) (R : Type₀) -> Type₁
Codata\M\itree.agda:59:tau' : {E : Type₀ -> Type₁} -> {R : Type₀} -> itree E R -> P₀ (itree-S E R) (itree E R)
Codata\M\itree.agda:62:vis' : ∀ {E} {R}  -> ∀ {A : Type₀} -> E A -> (A -> itree E R) -> P₀ (itree-S E R) (itree E R)
Codata\M\itree.agda:68:tau : {E : Type₀ -> Type₁} -> {R : Type₀} -> itree E R -> itree E R
Codata\M\itree.agda:71:vis : ∀ {E} {R}  -> ∀ {A : Type₀} -> E A -> (A -> itree E R) -> itree E R
Codata\M\M.agda:2:-- M type implemetation based on
Codata\M\M.agda:4:-- "Non-wellfounded trees in Homotopy Type Theory"
Codata\M\MRecord.agda:1:{- Alternative definition of M as a record type, together with some of its properties
Codata\M\MRecord.agda:15:record M (S : Type ℓ) (P : S → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Codata\M\MRecord.agda:24:record M-R {S : Type ℓ} {Q : S → Type ℓ'} (R : M S Q → M S Q → Type ℓ'')
Codata\M\MRecord.agda:25:           (m₀ m₁ : M S Q) : Type (ℓ-max ℓ (ℓ-max ℓ' ℓ'')) where
Codata\M\MRecord.agda:33:ηEqM : {S' : Type ℓ} {Q' : S' → Type ℓ'} (m : M S' Q') → sup-M (shape m) (pos m) ≡ m
Codata\M\stream.agda:20:stream : ∀ (A : Type₀) -> Type₀
Codata\M\Coalg\Base.agda:25:Coalg₀ : ∀ {ℓ} {S : Container ℓ} -> Type (ℓ-suc ℓ)
Codata\M\Coalg\Base.agda:26:Coalg₀ {ℓ} {S = S} = Σ[ C ∈ Type ℓ ] (C → P₀ S C)
Codata\M\Coalg\Base.agda:32:Cone₀ : ∀ {ℓ} {S : Container ℓ} {C,γ : Coalg₀ {S = S}} -> Type ℓ
Codata\M\Coalg\Base.agda:35:Cone₁ : ∀ {ℓ} {S : Container ℓ} {C,γ : Coalg₀ {S = S}} -> (f : Cone₀ {C,γ = C,γ}) -> Type ℓ
Codata\M\Coalg\Base.agda:38:Cone : ∀ {ℓ} {S : Container ℓ} (C,γ : Coalg₀ {S = S}) -> Type ℓ
Codata\M\M\Base.agda:3:-- Construction of M-types from
Codata\M\M\Base.agda:5:-- "Non-wellfounded trees in Homotopy Type Theory"
Codata\M\M\Base.agda:37:  limit-collapse : ∀ {ℓ} {S : Container ℓ} (X : ℕ → Type ℓ) (l : (n : ℕ) → X n → X (suc n)) → (x₀ : X 0) → ∀ (n
: ℕ) → X n
Codata\M\M\Base.agda:42:  ∀ {ℓ} {S : Container ℓ} (X : ℕ → Type ℓ) (l : (n : ℕ) → X n → X (suc n))
Codata\M\M\Base.agda:82:-- "Non-wellfounded trees in Homotopy Type Theory"
Codata\M\M\Base.agda:179:-- Property of functions into M-types
Codata\M\M\Base.agda:181:lift-to-M : ∀ {ℓ} {A : Type ℓ} {S : Container ℓ}
Codata\M\M\Properties.agda:32:  -- substituting refl makes type-checking work a lot faster, but introduces a transport
Codata\M\M\Properties.agda:51:in-inj : ∀ {ℓ} {S : Container ℓ} {Z : Type ℓ} → ∀ {f g : Z → P₀ S (M S)} → (in-fun ∘ f ≡ in-fun ∘ g) ≡ (f
≡ g)
Codata\M\M\Properties.agda:54:out-inj : ∀ {ℓ} {S : Container ℓ} {Z : Type ℓ} → ∀ {f g : Z → M S} → (out-fun ∘ f ≡ out-fun ∘ g) ≡ (f ≡ g)
Codata\Stream\Base.agda:6:record Stream (A : Type₀) : Type₀ where
Codata\Stream\Properties.agda:40:elimS : ∀ {A} (P : Stream A → Type₀) (c : ∀ x xs → P (x , xs)) (xs : Stream A) → P xs
Codata\Stream\Properties.agda:56:  record _≈_ {A : Type₀} (x y : Stream A) : Type₀ where
Codata\Stream\Properties.agda:64:  bisim : {A : Type₀} → {x y : Stream A} → x ≈ y → x ≡ y
Codata\Stream\Properties.agda:68:  misib : {A : Type₀} → {x y : Stream A} → x ≡ y → x ≈ y
Codata\Stream\Properties.agda:72:  iso1 : {A : Type₀} → {x y : Stream A} → (p : x ≡ y) → bisim (misib p) ≡ p
Codata\Stream\Properties.agda:76:  iso2 : {A : Type₀} → {x y : Stream A} → (p : x ≈ y) → misib (bisim p) ≡ p
Codata\Stream\Properties.agda:80:  path≃bisim : {A : Type₀} → {x y : Stream A} → (x ≡ y) ≃ (x ≈ y)
Codata\Stream\Properties.agda:83:  path≡bisim : {A : Type₀} → {x y : Stream A} → (x ≡ y) ≡ (x ≈ y)
Codata\Stream\Properties.agda:87:  refl≈ : {A : Type₀} {x : Stream A} → x ≈ x
Codata\Stream\Properties.agda:91:  cast : ∀ {A : Type₀} {x y : Stream A} (p : x ≡ y) → x ≈ y
Codata\Stream\Properties.agda:94:  misib-refl : ∀ {A : Type₀} {x : Stream A} → misib {x = x} refl ≡ refl≈
Codata\Stream\Properties.agda:98:  misibTransp : ∀ {A : Type₀} {x y : Stream A} (p : x ≡ y) → cast p ≡ misib p
Codata\Stream\Properties.agda:101:module Stream≅Nat→ {A : Type₀} where
Cohomology\Base.agda:2:  This file defines cohomology of a type with
Cohomology\Base.agda:5:    - the only difference is the carrier type.
Cohomology\Base.agda:8:    to maps between types
Cohomology\Base.agda:46:module _ (X : Type ℓ) (A : (x : X) → Spectrum ℓ) where
Cohomology\Base.agda:50:  CohomType : ℤ → Type ℓ
Cohomology\Base.agda:51:  CohomType k = ∥  (fst (CohomClasses k)) ∥₂
Cohomology\Base.agda:82:      Use an equivalent type, where the group structure is just
Cohomology\Base.agda:104:    CohomType' : Type ℓ
Cohomology\Base.agda:105:    CohomType' = fst (abGroupStr.π₂AbGroup k)
Cohomology\Base.agda:108:      shiftΩTwicePath : fst (abGroupStr.π₂AbGroup k) ≡ CohomType k
Cohomology\Base.agda:112:    Cohom = CohomType k , subst AbGroupStr shiftΩTwicePath (snd (abGroupStr.π₂AbGroup k))
Cohomology\Base.agda:121:  Functoriality in the type argument
Cohomology\Base.agda:123:module _ {Y X : Type ℓ} (f : Y → X) (A : (x : X) → Spectrum ℓ) where
Cohomology\EilenbergMacLane\Base.agda:53:coHom : (n : ℕ) (G : AbGroup ℓ) (A : Type ℓ') → Type _
Cohomology\EilenbergMacLane\Base.agda:56:module _ {n : ℕ} {G : AbGroup ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\Base.agda:66:module _ (n : ℕ) {G : AbGroup ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\Base.agda:80:module _ (n : ℕ) {G : AbGroup ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\Base.agda:108:coHomGr : (n : ℕ) (G : AbGroup ℓ) (A : Type ℓ') → AbGroup (ℓ-max ℓ ℓ')
Cohomology\EilenbergMacLane\Base.agda:122:coHomRed : (n : ℕ) (G : AbGroup ℓ) (A : Pointed ℓ') → Type _
Cohomology\EilenbergMacLane\Base.agda:318:+ₕ≡id-ℤ/2 : ∀ {ℓ}  {A : Type ℓ} (n : ℕ) (x : coHom n ℤ/2 A) → x +ₕ x ≡ 0ₕ n
Cohomology\EilenbergMacLane\Base.agda:323:-ₕConst-ℤ/2 : (n : ℕ) {A : Type ℓ} (x : coHom n ℤ/2 A) → -ₕ x ≡ x
Cohomology\EilenbergMacLane\Base.agda:331:coHomFun : ∀ {ℓ''} {A : Type ℓ} {B : Type ℓ'} {G : AbGroup ℓ''}
Cohomology\EilenbergMacLane\Base.agda:336:coHomHom : ∀ {ℓ''} {A : Type ℓ} {B : Type ℓ'} {G : AbGroup ℓ''}
Cohomology\EilenbergMacLane\Base.agda:344:coHomEquiv : ∀ {ℓ''} {A : Type ℓ} {B : Type ℓ'} {G : AbGroup ℓ''}
Cohomology\EilenbergMacLane\Base.agda:374:substℕ-coHom : {A : Type ℓ} {G : AbGroup ℓ'} {n m : ℕ}
Cohomology\EilenbergMacLane\Base.agda:413:  {A : Type ℓ'} (n : ℕ) (a : A) {B : coHom (suc n) G A → Type ℓ''}
Cohomology\EilenbergMacLane\Base.agda:421:  helper :  (n : ℕ) {B : coHom (suc n) G A → Type ℓ''}
Cohomology\EilenbergMacLane\Base.agda:431:coHomTruncEquiv : {A : Type ℓ} (G : AbGroup ℓ) (n : ℕ)
Cohomology\EilenbergMacLane\CupProduct.agda:45:module _ {G'' : Ring ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\CupProduct.agda:109:-ₕ^[_·_] : {G' : AbGroup ℓ} {A : Type ℓ'} (n m : ℕ) {k : ℕ}
Cohomology\EilenbergMacLane\CupProduct.agda:113:-ₕ^[_·_]-even : {G' : AbGroup ℓ} {A : Type ℓ'} (n m : ℕ) {k : ℕ}
Cohomology\EilenbergMacLane\CupProduct.agda:120:-ₕ^[_·_]-odd : {G' : AbGroup ℓ} {A : Type ℓ'} (n m : ℕ) {k : ℕ}
Cohomology\EilenbergMacLane\CupProduct.agda:127:comm⌣ : {G'' : CommRing ℓ} {A : Type ℓ'} (n m : ℕ)
Cohomology\EilenbergMacLane\CupProduct.agda:144:⌣[]-syntax : {A : Type ℓ} {n m : ℕ} (R : Ring ℓ')
Cohomology\EilenbergMacLane\CupProduct.agda:150:⌣[]C-syntax : {A : Type ℓ} {n m : ℕ} (R : CommRing ℓ')
Cohomology\EilenbergMacLane\CupProduct.agda:156:⌣[,,]-syntax : {A : Type ℓ} (n m : ℕ) (R : Ring ℓ')
Cohomology\EilenbergMacLane\CupProduct.agda:162:⌣[,,]C-syntax : {A : Type ℓ} (n m : ℕ) (R : CommRing ℓ')
Cohomology\EilenbergMacLane\CupProduct.agda:174:comm⌣ℤ/2 : {A : Type ℓ'} (n m : ℕ)
Cohomology\EilenbergMacLane\CupProduct.agda:189:module _ {G'' : Ring ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\CupProduct.agda:204:module _ {G'' : CommRing ℓ} {A : Type ℓ'} where
Cohomology\EilenbergMacLane\EilenbergSteenrod.agda:290:      lem : ∀ {ℓ} {A : Type ℓ} {x y z : A}
Cohomology\EilenbergMacLane\Gysin.agda:133:    killTransp : (A : ℕ → Type ℓ) (-ₖ_ : {n : ℕ} → A n → A n) (a : ℕ)
Cohomology\EilenbergMacLane\Gysin.agda:500:         (P : fst B → Type ℓ')
Cohomology\EilenbergMacLane\Gysin.agda:522:  EP : Type _
Cohomology\EilenbergMacLane\Gysin.agda:555:  FP : Type _
Cohomology\EilenbergMacLane\Gysin.agda:595:  -- step 2: show (FP∙ →∙ A) ≃ ((b : fst B) → Q b →∙ A) for any pointed type A
Cohomology\EilenbergMacLane\Gysin.agda:884:         (P : fst B → Type ℓ')
Cohomology\EilenbergMacLane\Gysin.agda:1068:         (P : fst B → Type ℓ')
Cohomology\EilenbergMacLane\MayerVietoris.agda:32:          (A : Type ℓ) (B : Type ℓ') (C : Type ℓ'')
Cohomology\EilenbergMacLane\RingStructure.agda:43:module _ (R : Ring ℓ') (A : Type ℓ) where
Cohomology\EilenbergMacLane\RingStructure.agda:64:  H* : Type _
Cohomology\EilenbergMacLane\RingStructure.agda:69:  {X : Type ℓ'}
Cohomology\EilenbergMacLane\RingStructure.agda:70:  {Y : Type ℓ''}
Cohomology\EilenbergMacLane\RingStructure.agda:172:  {X : Type ℓ'}
Cohomology\EilenbergMacLane\RingStructure.agda:173:  {Y : Type ℓ''}
Cohomology\EilenbergMacLane\Groups\Connected.agda:24:module _ {A : Type ℓ} (conA : isConnected 2 A) (G : AbGroup ℓ') where
Cohomology\EilenbergMacLane\Groups\KleinBottle.agda:57:module ConnK² {B : Type ℓ'} where
Cohomology\EilenbergMacLane\Groups\KleinBottle.agda:58:  elim₁ : {A : (KleinBottle → B) → Type ℓ}
Cohomology\EilenbergMacLane\Groups\KleinBottle.agda:93:  elim₂ : {A : (KleinBottle → B) → Type ℓ}
Cohomology\EilenbergMacLane\Groups\KleinBottle.agda:152:  sideSq : ∀ {ℓ} {A : Type ℓ} {x : A} (p : x ≡ x) → Square p p p p
Cohomology\EilenbergMacLane\Groups\KleinBottle.agda:293:KleinFun-triv : ∀ {ℓ} {A : Type ℓ} {a : A} → KleinFun a refl refl refl ≡ λ _ → a
Cohomology\EilenbergMacLane\Groups\RP2.agda:53:    A : Type ℓ
Cohomology\EilenbergMacLane\Groups\RP2.agda:55:module RP²Conn {B : (RP² → A) → Type ℓ} where
Cohomology\EilenbergMacLane\Groups\RP2.agda:104:Isoℤ/2-morph : {A : Type} (f : A ≃ fst ℤ/2) (0A : A)
Cohomology\EilenbergMacLane\Groups\RP2.agda:382:    lem1 : ∀ {ℓ} {A : Type ℓ} (x : A) (p : x ≡ x) (P Q : refl ≡ p)
Cohomology\EilenbergMacLane\Groups\RP2wedgeS1.agda:44:{- Todo: fix type-checking (very slow right now) -}
Cohomology\EilenbergMacLane\Groups\RPinf.agda:55:  nonConst→∙ : (b : EM ℤ/2 1) → Type _
Cohomology\EilenbergMacLane\Groups\RPinf.agda:72:  Σ¬Iso : ∀ {ℓ} {B A : Type ℓ}
Cohomology\EilenbergMacLane\Groups\Sn.agda:48:    A : Type ℓ
Cohomology\EilenbergMacLane\Groups\Sn.agda:71:Sⁿ-connElim : (n : ℕ) {B : (S₊ (suc (suc n)) → A) → Type ℓ'}
Cohomology\EilenbergMacLane\Groups\Sn.agda:85:S¹-connElim : {B : (S¹ → A) → Type ℓ'}
Cohomology\EilenbergMacLane\Groups\Torus.agda:65:coHomPointedElimT² : ∀ {ℓ ℓ'} {G : AbGroup ℓ} (n : ℕ) {B : coHom (suc n) G (S¹ × S¹) →
Type ℓ'}
Cohomology\EilenbergMacLane\Groups\Torus.agda:91:  lem : ∀ {ℓ ℓ'} {G : AbGroup ℓ} (n : ℕ) {B : coHom (2 + n) G (S¹ × S¹) → Type ℓ'}
Cohomology\EilenbergMacLane\Groups\Torus.agda:107:coHomPointedElimT²' : ∀ {ℓ ℓ'} {G : AbGroup ℓ} (n : ℕ) {B : coHom (2 + n) G (S¹ × S¹)
→ Type ℓ'}
Cohomology\EilenbergMacLane\Groups\Torus.agda:123:  coHomPointedElimT²'' :  ∀ {ℓ ℓ'} {G : AbGroup ℓ} (n : ℕ) {B : coHom (2 + n) G (S¹ ×
S¹) → Type ℓ'}
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:96:Res : ∀ {ℓ} {A B : Type ℓ} {x y : A} (f : A → A → B)
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:109:Res-refl : ∀ {ℓ} {A B : Type ℓ} {x : A} (f : A → A → B)
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:119:cong₂Funct-cong-sym : ∀ {ℓ} {A B : Type ℓ} {x y : A}
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:149:  lem : ∀ {ℓ} {A : Type ℓ} {x y z w t : A}
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:472:  ⌣-commℤ/2₁,₁ : ∀ {ℓ} {A : Type ℓ} (x y : coHom 1 ℤ/2 A)
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:586:-- Some abstract stuff for faster type checking
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:617:  -ConstH* : ∀ {ℓ} {A : Type ℓ} → (x : fst (H*R ℤ/2Ring A))
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:626:  +TrivH* : ∀ {ℓ} {A : Type ℓ}
Cohomology\EilenbergMacLane\Rings\KleinBottle.agda:654:    -- verbose definition (speeds up type checking a bit)
Cohomology\EilenbergMacLane\Rings\RP2.agda:81:    -- silly lemma for faster type checking
Cohomology\EilenbergMacLane\Rings\RP2.agda:98:  Typ : (p : fst ((Ω^ 2) (EM∙ (ℤ/2 ⨂ ℤ/2) 2))) → Type
Cohomology\EilenbergMacLane\Rings\RP2wedgeS1.agda:134:  -- silly lemma for faster type checking
Cohomology\EilenbergMacLane\Rings\RP2wedgeS1.agda:168:  Typ : (p : fst ((Ω^ 2) (EM∙ (ℤ/2 ⨂ ℤ/2) 2))) → Type
Cohomology\EilenbergMacLane\Rings\RP2wedgeS1.agda:269:ℤ/2[x,y]/<y³,xy,x²> : Type ℓ-zero
Cohomology\EilenbergMacLane\Rings\Z2-properties.agda:35:  (X : Type ℓ-zero)
Cohomology\EilenbergMacLane\Rings\Z2-properties.agda:39:  H*ℤ/2 : Type ℓ-zero
Cohomology\EilenbergMacLane\Rings\Z2-properties.agda:64:  {X : Type ℓ-zero}
Cohomology\EilenbergMacLane\Rings\Z2-properties.agda:76:-- X have to explicit or it doesn't type check when used in another file
Cohomology\EilenbergMacLane\Rings\Z2-properties.agda:78:  (X : Type ℓ-zero)
Core\Glue.agda:7:- Glue types
Core\Glue.agda:15:  using ( isEquiv       -- ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) → Type (ℓ ⊔ ℓ')
Core\Glue.agda:19:        ; _≃_           -- ∀ {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') → Type (ℓ ⊔ ℓ')
Core\Glue.agda:21:        ; equivFun      -- ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → A ≃ B → A → B
Core\Glue.agda:23:        ; equivProof    -- ∀ {ℓ ℓ'} (T : Type ℓ) (A : Type ℓ') (w : T ≃ A) (a : A) φ →
Core\Glue.agda:26:        ; primGlue      -- ∀ {ℓ ℓ'} (A : Type ℓ) {φ : I} (T : Partial φ (Type ℓ'))
Core\Glue.agda:27:                        -- → (e : PartialP φ (λ o → T o ≃ A)) → Type ℓ'
Core\Glue.agda:29:        ; prim^unglue   -- ∀ {ℓ ℓ'} {A : Type ℓ} {φ : I} {T : Partial φ (Type ℓ')}
Core\Glue.agda:35:  renaming ( prim^glue   to glue         -- ∀ {ℓ ℓ'} {A : Type ℓ} {φ : I} {T : Partial φ (Type ℓ')}
Core\Glue.agda:45:Glue : (A : Type ℓ) {φ : I}
Core\Glue.agda:46:       → (Te : Partial φ (Σ[ T ∈ Type ℓ' ] T ≃ A))
Core\Glue.agda:47:       → Type ℓ'
Core\Glue.agda:51:unglue : {A : Type ℓ} (φ : I) {T : Partial φ (Type ℓ')}
Core\Glue.agda:55:-- People unfamiliar with [Glue], [glue] and [uglue] can find the types below more
Core\Glue.agda:60:-- Cubical Type Theory: a constructive interpretation of the univalence axiom
Core\Glue.agda:64:  module GluePrims (A : Type ℓ) {φ : I} (Te : Partial φ (Σ[ T ∈ Type ℓ' ] T ≃ A)) where
Core\Glue.agda:65:    T : Partial φ (Type ℓ')
Core\Glue.agda:70:    -- Glue can be seen as a subtype of Type that, at φ, is definitionally equal to the left type
Core\Glue.agda:72:    Glue-S : Type ℓ' [ φ ↦ T ]
Core\Glue.agda:101:    -- typechecking glue enforces this, e.g. you can not simply write
Core\Glue.agda:111:  module GlueTransp (A : I → Type ℓ) (Te : (i : I) → Partial (i ∨ ~ i) (Σ[ T ∈ Type ℓ' ] T ≃ A i)) where
Core\Glue.agda:112:    A0 A1 : Type ℓ
Core\Glue.agda:115:    T : (i : I) → Partial (i ∨ ~ i) (Type ℓ')
Core\Glue.agda:119:    T0 T1 : Type ℓ'
Core\Glue.agda:131:    invEq : ∀ {X : Type ℓ'} {ℓ''} {Y : Type ℓ''} (w : X ≃ Y) → Y → X
Core\Primitives.agda:34:           ; Set   to Type
Core\Primitives.agda:35:           ; Setω  to Typeω )
Core\Primitives.agda:50:-- * Dependent path type. (Path over Path)
Core\Primitives.agda:53:-- just like function types.
Core\Primitives.agda:55:-- PathP : ∀ {ℓ} (A : I → Type ℓ) → A i0 → A i1 → Type ℓ
Core\Primitives.agda:59:_[_≡_] : ∀ {ℓ} (A : I → Type ℓ) → A i0 → A i1 → Type ℓ
Core\Primitives.agda:63:-- Non dependent path types
Core\Primitives.agda:65:Path : ∀ {ℓ} (A : Type ℓ) → A → A → Type ℓ
Core\Primitives.agda:69:--  _≡_ : ∀ {ℓ} {A : Type ℓ} → A → A → Type ℓ
Core\Primitives.agda:82:-- * Types of partial elements, and their dependent version.
Core\Primitives.agda:88:-- Partial : ∀ {ℓ} → I → Type ℓ → SSet ℓ
Core\Primitives.agda:89:-- PartialP : ∀ {ℓ} → (φ : I) → Partial φ (Type ℓ) → SSet ℓ
Core\Primitives.agda:95:  sys : ∀ i → Partial (i ∨ ~ i) Type₁
Core\Primitives.agda:96:  sys i (i = i0) = Type₀
Core\Primitives.agda:97:  sys i (i = i1) = Type₀ → Type₀
Core\Primitives.agda:101:  sys' : ∀ i → Partial (i ∨ ~ i) Type₁
Core\Primitives.agda:102:  sys' i = λ { (i = i0) → Type₀
Core\Primitives.agda:103:             ; (i = i1) → Type₀ → Type₀
Core\Primitives.agda:107:  sys2 : ∀ i j → Partial (i ∨ (i ∧ j)) Type₁
Core\Primitives.agda:108:  sys2 i j = λ { (i = i1)          → Type₀
Core\Primitives.agda:109:               ; (i = i1) (j = i1) → Type₀
Core\Primitives.agda:113:  sys3 : Partial i0 Type₁
Core\Primitives.agda:117:-- * There are cubical subtypes as in CCHM. Note that these are not
Core\Primitives.agda:120:_[_↦_] : ∀ {ℓ} (A : Type ℓ) (φ : I) (u : Partial φ A) → SSet ℓ
Core\Primitives.agda:128:-- inS : ∀ {ℓ} {A : Type ℓ} {φ} (u : A) → A [ φ ↦ (λ _ → u) ]
Core\Primitives.agda:132:-- outS : ∀ {ℓ} {A : Type ℓ} {φ : I} {u : Partial φ A} → A [ φ ↦ u ] → A
Core\Primitives.agda:137:-- compCCHM : ∀ {ℓ} (A : (i : I) → Type ℓ) (φ : I) (u : ∀ i → Partial φ (A i)) (a : A i0) → A i1
Core\Primitives.agda:147:-- transp : ∀ {ℓ} (A : I → Type ℓ) (φ : I) (a : A i0) → A i1
Core\Primitives.agda:157:-- hcomp : ∀ {ℓ} {A : Type ℓ} {φ : I} (u : I → Partial φ A) (a : A) → A
Core\Primitives.agda:165:hfill : {A : Type ℓ}
Core\Primitives.agda:177:-- builtin one as it doesn't require u0 to be a cubical subtype. This
Core\Primitives.agda:179:-- comp : (A : ∀ i → Type (ℓ' i))
Core\Primitives.agda:190:fill : (A : ∀ i → Type (ℓ' i))
Core\Primitives.agda:202:-- Σ-types
Core\Primitives.agda:205:Σ-syntax : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
CW\Approximation.agda:53:  (f : realise C → realise D) (m : ℕ) → Type (ℓ-max ℓ ℓ')
CW\Approximation.agda:83:  → Type (ℓ-max ℓ ℓ')
CW\Approximation.agda:167:        fib-f-incl : (c : fst C (suc (suc m))) → Type _
CW\Approximation.agda:240:      Goalₗ : (n : Fin (suc (suc (suc m)))) → Type _
CW\Approximation.agda:322:    mainlem : ∀ {ℓ ℓ'} (D : ℕ → Type ℓ) (C : ℕ → Type ℓ') (n : ℕ)
CW\Approximation.agda:402:  module SeqHomotopyTypes {ℓ ℓ'} {C : Sequence ℓ} {D : Sequence ℓ'} (m : ℕ)
CW\Approximation.agda:411:    cell-hom : (n : Fin (suc m)) (c : obj C (fst n)) → Type ℓ'
CW\Approximation.agda:416:      → cell-hom (fsuc n) (Sequence.map C c) → Type ℓ'
CW\Approximation.agda:427:  open SeqHomotopyTypes m f-c g-c
CW\Approximation.agda:560:      D∞PushSquare : Type ℓ'
CW\Approximation.agda:652:        → Type _
CW\Approximation.agda:752:    open SeqHomotopyTypes
CW\Approximation.agda:768:        → Type _
CW\Base.agda:42:yieldsCWskel : (ℕ → Type ℓ) → Type ℓ
CW\Base.agda:49:CWskel : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:50:CWskel ℓ = Σ[ X ∈ (ℕ → Type ℓ) ] (yieldsCWskel X)
CW\Base.agda:66:yieldsFinCWskel : (n : ℕ) (X : ℕ → Type ℓ) → Type ℓ
CW\Base.agda:71:finCWskel : (ℓ : Level) → (n : ℕ) → Type (ℓ-suc ℓ)
CW\Base.agda:72:finCWskel ℓ n = Σ[ C ∈ (ℕ → Type ℓ) ] (yieldsFinCWskel n C)
CW\Base.agda:74:isFinCWskel : ∀ {ℓ} (C : CWskel ℓ) → Type ℓ
CW\Base.agda:88:realise : CWskel ℓ → Type ℓ
CW\Base.agda:92:hasCWskel : (X : Type ℓ) → Type (ℓ-suc ℓ)
CW\Base.agda:95:isCW : (X : Type ℓ) → Type (ℓ-suc ℓ)
CW\Base.agda:98:CW : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:99:CW ℓ = Σ[ A ∈ Type ℓ ] (isCW A)
CW\Base.agda:101:CWexplicit : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:102:CWexplicit ℓ = Σ[ A ∈ Type ℓ ] (hasCWskel A)
CW\Base.agda:111:isFinIsCW : {X : Type ℓ} → hasCWskel X → Type ℓ
CW\Base.agda:114:hasFinCWskel : (X : Type ℓ) → Type (ℓ-suc ℓ)
CW\Base.agda:118:isFinCW : (X : Type ℓ) → Type (ℓ-suc ℓ)
CW\Base.agda:121:finCW : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:122:finCW ℓ = Σ[ A ∈ Type ℓ ] (isFinCW A)
CW\Base.agda:124:finCW∙ : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:127:finCWexplicit : (ℓ : Level) → Type (ℓ-suc ℓ)
CW\Base.agda:128:finCWexplicit ℓ = Σ[ A ∈ Type ℓ ] (hasFinCWskel A)
CW\Base.agda:130:hasFinCWskel→hasCWskel : (X : Type ℓ) → hasFinCWskel X → hasCWskel X
CW\Base.agda:154:_→ᶜʷ_ : CW ℓ → CW ℓ' → Type (ℓ-max ℓ ℓ')
CW\Base.agda:158:cofibCW : ∀ {ℓ} (n : ℕ) (C : CWskel ℓ) → Type ℓ
CW\Base.agda:175:δ-pre :  {A : Type ℓ} {B : Type ℓ'} (conn : A → B)
CW\Base.agda:184:-- send the stage n to the realization (the same as incl, but with explicit args and type)
CW\Connected.agda:77:yieldsConnectedCWskel : (A : ℕ → Type ℓ) (n : ℕ) → Type _
CW\Connected.agda:82:yieldsCombinatorialConnectedCWskel : (A : ℕ → Type ℓ) (n : ℕ) → Type _
CW\Connected.agda:86:connectedCWskel : (ℓ : Level) (n : ℕ) → Type (ℓ-suc ℓ)
CW\Connected.agda:87:connectedCWskel ℓ n = Σ[ X ∈ (ℕ → Type ℓ) ] (yieldsConnectedCWskel X n)
CW\Connected.agda:94:combinatorialConnectedCWskel : (ℓ : Level) (n : ℕ) → Type (ℓ-suc ℓ)
CW\Connected.agda:96:  Σ[ X ∈ (ℕ → Type ℓ) ] (yieldsCombinatorialConnectedCWskel X n)
CW\Connected.agda:103:isConnectedCW : ∀ {ℓ} (n : ℕ) → Type ℓ → Type (ℓ-suc ℓ)
CW\Connected.agda:107:isConnectedCW' : ∀ {ℓ} (n : ℕ) → Type ℓ → Type (ℓ-suc ℓ)
CW\Connected.agda:111:ConnectedCW : (ℓ : Level) (n : ℕ) → Type (ℓ-suc ℓ)
CW\Connected.agda:112:ConnectedCW ℓ n = Σ[ X ∈ Type ℓ ] isConnectedCW n X
CW\Connected.agda:131:inhabitedFibres?-Fin×S⁰ : {A : Type ℓ}
CW\Connected.agda:140:  allConst? : {A : Type ℓ} {n : ℕ} (dis : Discrete A)
CW\Connected.agda:162:  F∘inl : Fin (suc (suc m)) → Type
CW\Connected.agda:170:  F : Pushout f fst → Type
CW\Connected.agda:200:  inrT : Fin n → Type
CW\Connected.agda:205:  inlT : Fin (suc (suc m)) → Type
CW\Connected.agda:220:  T : Pushout f fst → Type
CW\Connected.agda:254:module shrinkPushoutLemma (A : Type ℓ) (B : Type ℓ')
CW\Connected.agda:563:module _ (A : ℕ → Type ℓ) (sk+c : yieldsCombinatorialConnectedCWskel A 0) where
CW\Connected.agda:585:  collapse₁CWskel : ℕ → Type _
CW\Connected.agda:648:makeConnectedCW : ∀ {ℓ} (n : ℕ) {C : Type ℓ}
CW\Connected.agda:1116:                cohTy : Type _
CW\Connected.agda:1207:            -- The type family
CW\Connected.agda:1209:              → Trichotomyᵗ m 3+n → Type ℓ
CW\Connected.agda:1352:connectedCWContr : {ℓ : Level} (n m : ℕ) (l : m <ᵗ suc n) (X : Type ℓ)
CW\Connected.agda:1371:connectedCW≃SphereBouquet : {ℓ : Level} (n : ℕ) (X : Type ℓ) (cwX : isConnectedCW n X)
CW\Connected.agda:1391:module _ {ℓ : Level} (n : ℕ) (X : Type ℓ) (cwX : isConnectedCW n X)
CW\Homotopy.agda:56:record cellHom {C : CWskel ℓ} {D : CWskel ℓ'} (f g : cellMap C D) : Type (ℓ-max ℓ ℓ') where
CW\Homotopy.agda:69:                  (f g : finCellMap m C D) : Type (ℓ-max ℓ ℓ') where
CW\Homotopy.agda:140:    → cofibCW (fst n) D) → Type (ℓ-max ℓ ℓ')
CW\Homotopy.agda:646:  suspIso-suspFun : ∀ {ℓ ℓ' ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'}
CW\Homotopy.agda:647:    {C : Type ℓ''} {D : Type ℓ'''}
CW\HurewiczTheorem.agda:80:-- Generators of ℤ[k] with locked definitions for faster type checking
CW\HurewiczTheorem.agda:162:      goalTy : (f g : S₊∙ (suc n) →∙ (realise Xsk , CW↪∞ Xsk 1 x₀)) → Type _
CW\HurewiczTheorem.agda:311:       wraplem : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A) (p : x ≡ y) (l1 l2 : y ≡ y)
CW\HurewiczTheorem.agda:898:     transportRefl-transportRefl : ∀ {ℓ} {A : Type ℓ} (x : A)
CW\HurewiczTheorem.agda:906:      gen : ∀ {ℓ} {A : Type ℓ} (x y : A) (p : x ≡ y)
CW\HurewiczTheorem.agda:935:     pathLem : ∀ {ℓ} {A : Type ℓ} {x : A}
CW\HurewiczTheorem.agda:1242:   module _ (X : Type) (cw : hasCWskel X) (cw' : isConnectedCW n X)
CW\Map.agda:58:cellMap : (C : CWskel ℓ) (D : CWskel ℓ') → Type (ℓ-max ℓ ℓ')
CW\Map.agda:76:  finCellMap : (C : CWskel ℓ) (D : CWskel ℓ') → Type (ℓ-max ℓ ℓ')
CW\Map.agda:232:      bouquet : (C : CWskel ℓ) (n m : ℕ) → Type
CW\Map.agda:351:      bouquet : (C : CWskel ℓ) (n : ℕ) → Type
CW\Properties.agda:71:CWskel→Prop : (C : CWskel ℓ) {A : (n : ℕ) → fst C n → Type ℓ'}
CW\Properties.agda:98:CW→Prop : (C : CWskel ℓ) {A : realise C → Type ℓ'}
CW\Properties.agda:114:  module _ (n : ℕ) {B : fst C (suc n) → Type ℓ'}
CW\Properties.agda:122:      gen : ∀ {ℓ ℓ'} {A B : Type ℓ} (C : A → Type ℓ')
CW\Properties.agda:128:      gen-coh : ∀ {ℓ ℓ'} {A B : Type ℓ} (C : A → Type ℓ')
CW\Properties.agda:133:        EquivJ (λ A e → (C : A → Type ℓ') (h : (x : B) → C (invEq e x))
CW\Properties.agda:149:  module _ (n : ℕ) {B : fst C (suc (suc n)) → Type ℓ'}
CW\Strictification.agda:37:  strictifyFam : ℕ → Type ℓ
CW\Strictification.agda:64:  strict≡Gen : ∀ {ℓ ℓ'} {A : Type ℓ} {C D : Type ℓ'}
CW\Strictification.agda:72:  strict≡GenT' : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C D : Type ℓ''}
CW\Strictification.agda:73:    {E : Type (ℓ-max ℓ (ℓ-max ℓ' ℓ''))} (g : A → B)
CW\Strictification.agda:104:    strict≡GenId : ∀ {ℓ ℓ'} {A : Type ℓ} {C : Type ℓ'} (α : A → C)(x : A)
CW\Strictification.agda:163:module _ {ℓ ℓ'} {P : CWskel ℓ → Type ℓ'}
CW\Strictification.agda:175:    H : ∀ {ℓ} {A : Type ℓ}  (F : A → A) (s : (λ x → x) ≡ F) (a : A)
CW\Subcomplex.agda:53:  subComplexFam : (m : ℕ) → Trichotomyᵗ m n → Type ℓ
CW\Subcomplex.agda:177:    subComplexFam : ℕ → Type ℓ
CW\Subcomplex.agda:245:makeNiceFinCWskel : ∀ {ℓ} {A : Type ℓ} → hasFinCWskel A → hasFinCWskel A
CW\Subcomplex.agda:268:makeNiceFinCWElim : ∀ {ℓ ℓ'} {A : finCW ℓ → Type ℓ'}
CW\Subcomplex.agda:273:makeNiceFinCWElim' : ∀ {ℓ ℓ'} {C : Type ℓ} {A : isFinCW C → Type ℓ'}
CW\Homology\Base.agda:157:  module _ {C : Type ℓ} {D : Type ℓ'} (f : C → D) (n : ℕ) where
CW\Instances\Empty.agda:2:The empty type as a CW complex
CW\Instances\Lift.agda:36:  hasCWskelLift : {A : Type ℓA} → hasCWskel A → hasCWskel (Lift ℓ A)
CW\Instances\Lift.agda:54:  hasFinCWskelLift : {A : Type ℓA}
CW\Instances\Pushout.agda:57:  module _ {ℓ : Level} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : x ≡ z) where
CW\Instances\Pushout.agda:101:  pushoutA : ℕ → Type ℓ
CW\Instances\Pushout.agda:230:  modifySₙ : CWskel ℓ → ℕ → Type ℓ
CW\Instances\Pushout.agda:296:  modifiedPushout : (n : ℕ) → Type ℓ
CW\Instances\Pushout.agda:756:module _ {ℓ ℓ' : Level} (P : Type ℓ → Type ℓ') (P1 : P Unit*) (P0 : P ⊥*)
CW\Instances\Pushout.agda:757:         (Ppush : (A B C : Type ℓ) (f : A → B) (g : A → C)
CW\Instances\Pushout.agda:760:   L : Type → Type ℓ
CW\Instances\Pushout.agda:766:   P⊎ : {B C : Type ℓ} → P B → P C → P (B ⊎ C)
CW\Instances\Pushout.agda:826:  elimPropFinCWFun : (B : Type ℓ) → hasFinCWskel B → P B
CW\Instances\Sigma.agda:2:CW structure on Σ-types (and binary products)
CW\Instances\Sn.agda:47:-- Defining family of types
CW\Instances\Sn.agda:49:  Sfam : (m : ℕ) → Trichotomyᵗ m (suc n) → Type
CW\Instances\Sn.agda:60:Sfam : (n : ℕ) → ℕ → Type
CW\Instances\Sn.agda:246:-- Proof that our CW structure converges to Sⁿ as a plain type
CW\Instances\Sn.agda:386:  SQ' : ∀ {ℓ} {A : Type ℓ} (x y : A) (p : x ≡ y)
CW\Instances\SphereBouquetMap.agda:40:    → (m : ℕ) → Trichotomyᵗ m (suc (suc n)) → Type
CW\Instances\SphereBouquetMap.agda:214:SphereBouquet/EqBottomMainGenLem : {C : Type} {c1 c2 : ℕ} (n : ℕ)
CW\Instances\Unit.agda:2:The unit type as a CW complex
Data\Equality.agda:3:This module converts between the path types and the inductively
Data\Equality.agda:4:defined equality types. It provides the following for the inductively
Data\Equality.agda:5:defined equality type _≡_.
Data\FinInd.agda:3:Definition of finitely indexed types
Data\FinInd.agda:5:A type is finitely indexed if, for some `n`, there merely exists a
Data\FinInd.agda:6:surjective function from `Fin n` to it. Note that a type doesn't need
Data\FinInd.agda:30:    A : Type ℓ
Data\FinInd.agda:32:isFinInd : Type ℓ → Type ℓ
Data\FinType.agda:2:module Cubical.Data.FinType where
Data\FinType.agda:4:open import Cubical.Data.FinType.Base public
Data\FinType.agda:5:open import Cubical.Data.FinType.Properties public
Data\SubFinSet.agda:30:    A B : Type ℓ
Data\SubFinSet.agda:32:isSubFinSet : Type ℓ → Type ℓ
Data\BinNat\BinNat.agda:75:data Binℕ : Type₀
Data\BinNat\BinNat.agda:76:data Pos : Type₀
Data\BinNat\BinNat.agda:115:posInd : {P : Pos → Type₀} → P pos1 → ((p : Pos) → P p → P (sucPos p)) → (p : Pos) → P p
Data\BinNat\BinNat.agda:246:  in -- Then transport oddBinℕnotEvenBinℕ in a suitable equality type
Data\BinNat\BinNat.agda:273:record NatImpl (A : Type₀) : Type₀ where
Data\BinNat\BinNat.agda:319:record Double {ℓ} (A : Type ℓ) : Type (ℓ-suc ℓ) where
Data\BinNat\BinNat.agda:328:doubles : ∀ {ℓ} {A : Type ℓ} (D : Double A) → ℕ → A → A
Data\BinNat\BinNat.agda:376:record propDouble {ℓ} {A : Type ℓ} (D : Double A) : Type ℓ where
Data\BinNat\BinNat.agda:382:-- The property we want to prove takes too long to typecheck for ℕ:
Data\BinNat\BinNat.agda:405:data binnat : Type₀ where
Data\Bool\Base.agda:17:    A : Type ℓ
Data\Bool\Base.agda:55:Bool→Type : Bool → Type₀
Data\Bool\Base.agda:56:Bool→Type true = Unit
Data\Bool\Base.agda:57:Bool→Type false = ⊥
Data\Bool\Base.agda:59:Bool→Type* : Bool → Type ℓ
Data\Bool\Base.agda:60:Bool→Type* true = Unit*
Data\Bool\Base.agda:61:Bool→Type* false = ⊥*
Data\Bool\Base.agda:63:True : Dec A → Type₀
Data\Bool\Base.agda:64:True Q = Bool→Type (Dec→Bool Q)
Data\Bool\Base.agda:66:False : Dec A → Type₀
Data\Bool\Base.agda:67:False Q = Bool→Type (not (Dec→Bool Q))
Data\Bool\Base.agda:88:Bool* : ∀ {ℓ} → Type ℓ
Data\Bool\Base.agda:98:Bool*∙ : ∀ {ℓ} → Σ[ X ∈ Type ℓ ] X
Data\Bool\Properties.agda:28:    A : Type ℓ
Data\Bool\Properties.agda:30:elim : ∀ {ℓ} {A : Bool → Type ℓ}
Data\Bool\Properties.agda:66:  : (P : {b : Bool} → b ≡ b → Type ℓ)
Data\Bool\Properties.agda:196:  data Table (A : Type₀) (P : Bool ≡ A) : Type₀ where
Data\Bool\Properties.agda:247:_≤_ : Bool → Bool → Type
Data\Bool\Properties.agda:251:_≥_ : Bool → Bool → Type
Data\Bool\Properties.agda:267:isProp-Bool→Type : ∀ b → isProp (Bool→Type b)
Data\Bool\Properties.agda:268:isProp-Bool→Type false = isProp⊥
Data\Bool\Properties.agda:269:isProp-Bool→Type true = isPropUnit
Data\Bool\Properties.agda:271:isPropDep-Bool→Type : isPropDep Bool→Type
Data\Bool\Properties.agda:272:isPropDep-Bool→Type = isOfHLevel→isOfHLevelDep 1 isProp-Bool→Type
Data\Bool\Properties.agda:289:BoolProp≃BoolProp* : {a : Bool} → Bool→Type a ≃ Bool→Type* {ℓ} a
Data\Bool\Properties.agda:293:Bool→TypeInj : (a b : Bool) → Bool→Type a ≃ Bool→Type b → a ≡ b
Data\Bool\Properties.agda:294:Bool→TypeInj true true _ = refl
Data\Bool\Properties.agda:295:Bool→TypeInj true false p = Empty.rec (p .fst tt)
Data\Bool\Properties.agda:296:Bool→TypeInj false true p = Empty.rec (invEq p tt)
Data\Bool\Properties.agda:297:Bool→TypeInj false false _ = refl
Data\Bool\Properties.agda:299:Bool→TypeInj* : (a b : Bool) → Bool→Type* {ℓ} a ≃ Bool→Type* {ℓ} b → a ≡ b
Data\Bool\Properties.agda:300:Bool→TypeInj* true true _ = refl
Data\Bool\Properties.agda:301:Bool→TypeInj* true false p = Empty.rec* (p .fst tt*)
Data\Bool\Properties.agda:302:Bool→TypeInj* false true p = Empty.rec* (invEq p tt*)
Data\Bool\Properties.agda:303:Bool→TypeInj* false false _ = refl
Data\Bool\Properties.agda:305:isPropBool→Type : {a : Bool} → isProp (Bool→Type a)
Data\Bool\Properties.agda:306:isPropBool→Type {a = true} = isPropUnit
Data\Bool\Properties.agda:307:isPropBool→Type {a = false} = isProp⊥
Data\Bool\Properties.agda:309:isPropBool→Type* : {a : Bool} → isProp (Bool→Type* {ℓ} a)
Data\Bool\Properties.agda:310:isPropBool→Type* {a = true} = isPropUnit*
Data\Bool\Properties.agda:311:isPropBool→Type* {a = false} = isProp⊥*
Data\Bool\Properties.agda:313:DecBool→Type : {a : Bool} → Dec (Bool→Type a)
Data\Bool\Properties.agda:314:DecBool→Type {a = true} = yes tt
Data\Bool\Properties.agda:315:DecBool→Type {a = false} = no (λ x → x)
Data\Bool\Properties.agda:317:DecBool→Type* : {a : Bool} → Dec (Bool→Type* {ℓ} a)
Data\Bool\Properties.agda:318:DecBool→Type* {a = true} = yes tt*
Data\Bool\Properties.agda:319:DecBool→Type* {a = false} = no (λ (lift x) → x)
Data\Bool\Properties.agda:321:Dec→DecBool : {P : Type ℓ} → (dec : Dec P) → P → Bool→Type (Dec→Bool dec)
Data\Bool\Properties.agda:325:DecBool→Dec : {P : Type ℓ} → (dec : Dec P) → Bool→Type (Dec→Bool dec) → P
Data\Bool\Properties.agda:328:Dec≃DecBool : {P : Type ℓ} → (h : isProp P)(dec : Dec P) → P ≃ Bool→Type (Dec→Bool dec)
Data\Bool\Properties.agda:329:Dec≃DecBool h dec = propBiimpl→Equiv h isPropBool→Type (Dec→DecBool dec) (DecBool→Dec dec)
Data\Bool\Properties.agda:331:Bool≡BoolDec : {a : Bool} → a ≡ Dec→Bool (DecBool→Type {a = a})
Data\Bool\Properties.agda:335:Dec→DecBool* : {P : Type ℓ} → (dec : Dec P) → P → Bool→Type* {ℓ} (Dec→Bool dec)
Data\Bool\Properties.agda:339:DecBool→Dec* : {P : Type ℓ} → (dec : Dec P) → Bool→Type* {ℓ} (Dec→Bool dec) → P
Data\Bool\Properties.agda:342:Dec≃DecBool* : {P : Type ℓ} → (h : isProp P)(dec : Dec P) → P ≃ Bool→Type* {ℓ} (Dec→Bool dec)
Data\Bool\Properties.agda:343:Dec≃DecBool* h dec = propBiimpl→Equiv h isPropBool→Type* (Dec→DecBool* dec) (DecBool→Dec* dec)
Data\Bool\Properties.agda:345:Bool≡BoolDec* : {a : Bool} → a ≡ Dec→Bool (DecBool→Type* {ℓ} {a = a})
Data\Bool\Properties.agda:349:Bool→Type× : (a b : Bool) → Bool→Type (a and b) → Bool→Type a × Bool→Type b
Data\Bool\Properties.agda:350:Bool→Type× true true _ = tt , tt
Data\Bool\Properties.agda:351:Bool→Type× true false p = Empty.rec p
Data\Bool\Properties.agda:352:Bool→Type× false true p = Empty.rec p
Data\Bool\Properties.agda:353:Bool→Type× false false p = Empty.rec p
Data\Bool\Properties.agda:355:Bool→Type×' : (a b : Bool) → Bool→Type a × Bool→Type b → Bool→Type (a and b)
Data\Bool\Properties.agda:356:Bool→Type×' true true _ = tt
Data\Bool\Properties.agda:357:Bool→Type×' true false (_ , p) = Empty.rec p
Data\Bool\Properties.agda:358:Bool→Type×' false true (p , _) = Empty.rec p
Data\Bool\Properties.agda:359:Bool→Type×' false false (p , _) = Empty.rec p
Data\Bool\Properties.agda:361:Bool→Type×≃ : (a b : Bool) → Bool→Type a × Bool→Type b ≃ Bool→Type (a and b)
Data\Bool\Properties.agda:362:Bool→Type×≃ a b =
Data\Bool\Properties.agda:363:  propBiimpl→Equiv (isProp× isPropBool→Type isPropBool→Type) isPropBool→Type
Data\Bool\Properties.agda:364:    (Bool→Type×' a b) (Bool→Type× a b)
Data\Bool\Properties.agda:366:Bool→Type⊎ : (a b : Bool) → Bool→Type (a or b) → Bool→Type a ⊎ Bool→Type b
Data\Bool\Properties.agda:367:Bool→Type⊎ true true _ = inl tt
Data\Bool\Properties.agda:368:Bool→Type⊎ true false _ = inl tt
Data\Bool\Properties.agda:369:Bool→Type⊎ false true _ = inr tt
Data\Bool\Properties.agda:370:Bool→Type⊎ false false p = Empty.rec p
Data\Bool\Properties.agda:372:Bool→Type⊎' : (a b : Bool) → Bool→Type a ⊎ Bool→Type b → Bool→Type (a or b)
Data\Bool\Properties.agda:373:Bool→Type⊎' true true _ = tt
Data\Bool\Properties.agda:374:Bool→Type⊎' true false _ = tt
Data\Bool\Properties.agda:375:Bool→Type⊎' false true _ = tt
Data\Bool\Properties.agda:376:Bool→Type⊎' false false (inl p) = Empty.rec p
Data\Bool\Properties.agda:377:Bool→Type⊎' false false (inr p) = Empty.rec p
Data\Bool\Properties.agda:379:PropBoolP→P : (dec : Dec A) → Bool→Type (Dec→Bool dec) → A
Data\Bool\Properties.agda:382:P→PropBoolP : (dec : Dec A) → A → Bool→Type (Dec→Bool dec)
Data\Bool\Properties.agda:386:DecΠBool : {A : Bool → Type ℓ} → (∀ b → Dec (A b)) → Dec (∀ b → A b)
Data\Bool\Properties.agda:389:¬ΠBool→¬Σ : {A : Bool → Type ℓ} → (∀ b → Dec (A b)) → ¬ (∀ b → A b) → Σ[ b ∈ Bool ] (¬ (A b))
Data\Bool\Properties.agda:398:Bool≡≃ : (a b : Bool) → (a ≡ b) ≃ Bool→Type (Bool≡ a b)
Data\Bool\Properties.agda:405:-- Bool is equivalent to bi-point type
Data\Bool\Properties.agda:440:ΣBool : (b : Bool) (c : (Bool→Type b) → Bool) → Bool
Data\Bool\Properties.agda:444:ΣBoolΣIso : {b : Bool} {c : (Bool→Type b) → Bool} →
Data\Bool\Properties.agda:445:  Iso (Bool→Type (ΣBool b c)) (Σ[ z ∈ Bool→Type b ] Bool→Type (c z))
Data\Bool\Properties.agda:452:ΣBool≃Σ : {b : Bool} {c : (Bool→Type b) → Bool} →
Data\Bool\Properties.agda:453:  (Bool→Type (ΣBool b c)) ≃ (Σ[ z ∈ Bool→Type b ] Bool→Type (c z))
Data\Bool\SwitchStatement.agda:32:switch_cases_ : {A : Type ℓ} {B : Type ℓ'} → (A → Bool) → ((A → Bool) → B) → B
Data\Bool\SwitchStatement.agda:35:case_⇒_break_ : {A : Type ℓ} {B : Type ℓ'} → A → B → (otherCases : (A → Bool) → B) → (A → Bool) → B
Data\Bool\SwitchStatement.agda:38:default⇒_ : {A : Type ℓ} {B : Type ℓ'} → B → (A → Bool) → B
Data\Cardinal\Base.agda:24:Card : Type (ℓ-suc ℓ)
Data\Containers\Algebras.agda:19:module Algs (S : Type ℓ)
Data\Containers\Algebras.agda:20:            (Q : S → Type ℓ') where
Data\Containers\Algebras.agda:25:  record ContFuncIso : Type (ℓ-max (ℓ-suc ℓ'') (ℓ-max ℓ ℓ')) where
Data\Containers\Algebras.agda:28:      carrier : Type ℓ''
Data\Containers\Algebras.agda:42:  data Pos {Ind : Type ℓ'''} (P : Ind → S → Type ℓ'') (FP : ContFuncIso {ℓ}) (i : Ind) :
Data\Containers\Algebras.agda:43:           carrier FP → Type (ℓ-max (ℓ-suc ℓ) (ℓ-max ℓ'' ℓ')) where
Data\Containers\Base.agda:33:record GenContainer (C : Category ℓ ℓ') : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Data\Containers\Base.agda:36:    S : Type ℓ'
Data\Containers\Base.agda:44:  -- Category Cont with objects of type GenContainer C
Data\Containers\Base.agda:45:  record _⇒c_ (C₁ C₂ : GenContainer C) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Data\Containers\Base.agda:88:  -- Type alias for (S : Type) (P : S → C .ob) (X : C .ob) ↦ Σ S (λ s → C [ P s , X ])
Data\Containers\Base.agda:89:  cont-func : (S : Type ℓ') (P : S → C .ob) (X : C .ob) → Type ℓ'
Data\Containers\Base.agda:92:  isSetContFunc : (A : Type ℓ') (B : A → C .ob) (X : C .ob) (isSetA : isSet A) → isSet (cont-func A B X)
Data\Containers\Base.agda:95:  cont-mor : {A : Type ℓ'} {B : A → C .ob} {X Y : C .ob} (f : C [ X , Y ]) →
Data\Containers\ContainerExtensionProofs.agda:4:- First one is adapted from 'Containers: Constructing strictly positive types'
Data\Containers\ContainerExtensionProofs.agda:46:    -- Adapted from 'Containers: Constructing strictly positive types'
Data\Containers\ContainerExtensionProofs.agda:78:        compHetHomP : {A : I → Type ℓ'} {x : A i0} {y : A i1} {z : A i1} →
Data\Containers\InductiveContainers.agda:3:Adapted from 'Containers: Constructing strictly positive types'
Data\Containers\InductiveContainers.agda:15:                           (Ind : Type)
Data\Containers\InductiveContainers.agda:16:                           (S : Type)
Data\Containers\InductiveContainers.agda:17:                           (P : Ind → S → Type)
Data\Containers\InductiveContainers.agda:18:                           (Q : S → Type)
Data\Containers\InductiveContainers.agda:19:                           (X : Ind → Type)
Data\Containers\InductiveContainers.agda:20:                           (Y : Type)
Data\DescendingList\Base.agda:10: (A : Type₀)
Data\DescendingList\Base.agda:11: (_≥_ : A → A → Type₀)
Data\DescendingList\Base.agda:19:data DL : Type₀
Data\DescendingList\Base.agda:20:data _≥ᴴ_ (x : A) : DL → Type₀
Data\DescendingList\Examples.agda:33:data _≤_ : ℕ → ℕ → Type where
Data\DescendingList\Examples.agda:37:_≥_ : ℕ → ℕ → Type
Data\DescendingList\Properties.agda:27: (A : Type₀)
Data\DescendingList\Properties.agda:28: (_≥_ : A → A → Type₀)
Data\DescendingList\Properties.agda:42:data _≥ᴬ_ (x : A) : List A → Type₀ where
Data\DescendingList\Properties.agda:46:data descending : List A → Type₀ where
Data\DescendingList\Properties.agda:87:caseDL : ∀ {ℓ} → {X : Type ℓ} → (x y : X) → DL → X
Data\DescendingList\Properties.agda:110:   P : A → Type₀
Data\DescendingList\Properties.agda:115:     Q : (v : DL) → Type₀
Data\DescendingList\Properties.agda:149: -- The type DL is defined simultaneously with the relation _≥ᴴ_.
Data\DescendingList\Strict.agda:9: (A : Type₀)
Data\DescendingList\Strict.agda:10: (_>_ : A → A → Type₀)
Data\DescendingList\Strict\Properties.agda:5: (A : Type₀)
Data\DescendingList\Strict\Properties.agda:6: (_>_ : A → A → Type₀)
Data\DescendingList\Strict\Properties.agda:20:open import Cubical.Relation.Nullary using (Dec; Discrete) renaming (¬_ to Type¬_)
Data\DescendingList\Strict\Properties.agda:28:  data Tri (A B C : Type) : Type where
Data\DescendingList\Strict\Properties.agda:38:   (>-irreflexive : ∀ {x} → Type¬ x > x)
Data\DescendingList\Strict\Properties.agda:41:  Tri' : A → A → Type
Data\DescendingList\Strict\Properties.agda:64:  ≡ₚ-sym : ∀ {A : Type} {x y : A} → ⟨ x ≡ₚ y ⟩ → ⟨ y ≡ₚ x ⟩
Data\DescendingList\Strict\Properties.agda:115:    -- typechecking noticeably slower
Data\DescendingList\Strict\Properties.agda:127:       a≢x : Type¬ (a ≡ x)
Data\Empty\Base.agda:9:data ⊥ : Type₀ where
Data\Empty\Base.agda:11:⊥* : ∀ {ℓ} → Type ℓ
Data\Empty\Base.agda:14:rec : {A : Type ℓ} → ⊥ → A
Data\Empty\Base.agda:17:rec* : {A : Type ℓ} → ⊥* {ℓ'} → A
Data\Empty\Base.agda:20:elim : {A : ⊥ → Type ℓ} → (x : ⊥) → A x
Data\Empty\Base.agda:23:elim* : {A : ⊥* {ℓ'} → Type ℓ} → (x : ⊥*) → A x
Data\Empty\Properties.agda:15:isContr⊥→A : ∀ {ℓ} {A : Type ℓ} → isContr (⊥ → A)
Data\Empty\Properties.agda:19:isContrΠ⊥ : ∀ {ℓ} {A : ⊥ → Type ℓ} → isContr ((x : ⊥) → A x)
Data\Empty\Properties.agda:23:isContrΠ⊥* : ∀ {ℓ ℓ'} {A : ⊥* {ℓ} → Type ℓ'} → isContr ((x : ⊥*) → A x)
Data\Empty\Properties.agda:27:uninhabEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Data\Equality\Base.agda:1:{- Basic definitions for the inductively defined equality type
Data\Equality\Base.agda:15:  using (Type; Level; ℓ-zero; ℓ-suc; ℓ-max; Σ; Σ-syntax; _,_)
Data\Equality\Base.agda:18:-- Import the builtin equality type defined as an inductive family
Data\Equality\Base.agda:24:  A : Type a
Data\Equality\Base.agda:25:  B : Type b
Data\Equality\Base.agda:28:J : (M : (y : A) (p : x ≡ y) → Type ℓ) → M x refl → (p : x ≡ y) → M y p
Data\Equality\Base.agda:48:transport : ∀ (C : A → Type ℓ') {x y : A} → x ≡ y → C x → C y
Data\Equality\Base.agda:82:apd : {C : A → Type ℓ} (f : (x : A) → C x) {x y : A} (p : x ≡ y) → transport C p (f x) ≡ f y
Data\Equality\Base.agda:87:fiber : ∀ {A : Type ℓ} {B : Type ℓ'} (f : A → B) (y : B) → Type (ℓ-max ℓ ℓ')
Data\Equality\Base.agda:90:isContr : Type ℓ → Type ℓ
Data\Equality\Base.agda:93:isProp : Type ℓ → Type ℓ
Data\Equality\Base.agda:96:record isEquiv {A : Type ℓ} {B : Type ℓ'} (f : A → B) : Type (ℓ-max ℓ ℓ') where
Data\Equality\Base.agda:101:_≃_ : ∀ (A : Type ℓ) (B : Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Equality\Base.agda:119:HEq : {A0 A1 : Type ℓ}(Aeq : A0 ≡ A1) (a0 : A0)(a1 : A1) → Type _
Data\Equality\Base.agda:122:singlP : {A0 A1 : Type ℓ}(Aeq : A0 ≡ A1) (a : A0) → Type _
Data\Equality\Base.agda:125:singl : {A : Type ℓ}(a : A) → Type _
Data\Equality\Conversion.agda:1:{- Conversion between paths and the inductively defined equality type
Data\Equality\Conversion.agda:50:  A : Type a
Data\Equality\Conversion.agda:51:  B : Type b
Data\Equality\Conversion.agda:57:congPathd : {C : A → Type ℓ} (f : (x : A) → C x) {x y : A} (p : Path A x y) → Path (C y) (substPath C
p (f x)) (f y)
Data\Equality\Conversion.agda:87:happly : {B : A → Type ℓ} {f g : (x : A) → B x} → f ≡ g → (x : A) → f x ≡ g x
Data\Equality\Conversion.agda:91:funExt : {B : A → Type ℓ} {f g : (x : A) → B x} → ((x : A) → f x ≡ g x) → f ≡ g
Data\Equality\Conversion.agda:94:funExtRefl : {B : A → Type ℓ} {f : (x : A) → B x} → funExt (λ x → refl {x = f x}) ≡ refl
Data\Equality\Conversion.agda:97:Σ≡Prop : {P : A → Type ℓ} → ((x : A) → isProp (P x)) →  {u v : Σ A P} → u .pr₁ ≡ v .pr₁ → u ≡ v
Data\Equality\Conversion.agda:101:substPath≡transport' : (C : A → Type ℓ) {x y : A} (b : C x) (p : x ≡ y) → substPath C (eqToPath p) b
≡ transport C p b
Data\Equality\Conversion.agda:104:substPath≡transport : (C : A → Type ℓ) {x y : A} (b : C x) (p : Path _ x y) → substPath C p b ≡
transport C (pathToEq p) b
Data\Equality\Conversion.agda:153:  helper1 : {A B : Type ℓ} (f : A → B) (g : B → A) (h : ∀ y → Path _ (f (g y)) y)
Data\Equality\Conversion.agda:160:  helper2 : {A B : Type ℓ} (f : A → B) (g : B → A) (h : ∀ y → Path _ (g (f y)) y)
Data\Equality\Conversion.agda:180:isPropIsEquiv : {A B : Type ℓ} {f : A → B} (h1 h2 : isEquiv f) → Path _ h1 h2
Data\Equality\Conversion.agda:192:equivToEquiv : {A B : Type ℓ} (p : A ≃ B) → Path _ (equivPathToEquiv (equivToEquivPath p)) p
Data\Equality\Conversion.agda:197:equivPathToEquivPath : {A B : Type ℓ} (p : EquivPath A B) → Path _ (equivToEquivPath
(equivPathToEquiv p)) p
Data\Equality\Conversion.agda:201:equivPath≡Equiv : {A B : Type ℓ} → Path _ (EquivPath A B) (A ≃ B)
Data\Equality\Conversion.agda:204:path≡Eq : {A B : Type ℓ} → Path _ (Path _ A B) (A ≡ B)
Data\Equality\Conversion.agda:211:record Iso {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
Data\Equality\Conversion.agda:234:transportPathToEq→transportPath : (P : A → Type ℓ) (p : Path A x y) (u : P x) → transport P (pathToEq
p) u ≡ substPath P p u
Data\Equality\Conversion.agda:238:module _ (P : A → Type ℓ) {x y : A} {u : P x} {v : P y} where
Data\Equality\Conversion.agda:248:module _ (P : A → Type ℓ) {x : A} {u v : P x} where
Data\Equality\Conversion.agda:261:apd-pathToEq≡PathP→pathOver-cong : {P : A → Type ℓ} {x y : A} (f : (x : A) → P x) (p : Path _ x y) →
Data\Equality\Conversion.agda:282:module _ (P : A → Type ℓ) {x y : A} {u : P x} {v : P y} where
Data\Equality\Conversion.agda:307:cong-PathP→apd-pathOver : (P : A → Type ℓ) {x y : A} (f : (x : A) → P x)
Data\Equality\FunctionExtensionality.agda:3:- Function Extensionality stated in terms of the inductively defined equality type
Data\Equality\FunctionExtensionality.agda:33:    A : Type a
Data\Equality\FunctionExtensionality.agda:34:    P : A → Type ℓ
Data\Equality\PropositionalTruncation.agda:1:{- Propositional truncation for the inductively defined equality type ≡, using paths
internally -}
Data\Equality\PropositionalTruncation.agda:20:  A B : Type ℓ
Data\Equality\PropositionalTruncation.agda:26:∥∥-rec : {A : Type ℓ} {P : Type ℓ'} → isProp P → (A → P) → ∥ A ∥₁ → P
Data\Equality\PropositionalTruncation.agda:29:∥∥-elim : {A : Type ℓ} {P : ∥ A ∥₁ → Type ℓ'} → ((a : ∥ A ∥₁) → isProp (P a)) →
Data\Equality\S1.agda:34:  A : Type a
Data\Equality\S1.agda:39:S¹-rec : {A : Type ℓ} (b : A) (l : b ≡ b) → S¹ → A
Data\Equality\S1.agda:49:S¹-elimPath : (P : S¹ → Type ℓ) (b : P base) (l : PathP (λ i → P (loopPath i)) b b) → (x : S¹) → P x
Data\Equality\S1.agda:53:S¹-elim : (P : S¹ → Type ℓ) (b : P base) (l : transport P loop b ≡ b) → (x : S¹) → P x
Data\Equality\S1.agda:56:S¹-elim-base : (C : S¹ → Type ℓ) (b : C base) (l : transport C loop b ≡ b) → S¹-elim C b l base ≡ b
Data\Equality\S1.agda:59:S¹-elim-loop : (C : S¹ → Type ℓ) (b : C base) (l : transport C loop b ≡ b) → apd (S¹-elim C b l) loop ≡ l
Data\Equality\S1.agda:65:Cover : S¹ → Type₀
Data\Equality\S1.agda:68:ΩS¹ : Type₀
Data\Equality\Univalence.agda:3:- Univalence stated in terms of the inductively defined equality type
Data\Equality\Univalence.agda:35:  A : Type a
Data\Equality\Univalence.agda:36:  B : Type b
Data\Fast\Int\Divisibility.agda:47:_∣_ : ℤ → ℤ → Type
Data\Fast\Int\Divisibility.agda:55:_∣'_ : ℤ → ℤ → Type
Data\Fast\Int\Divisibility.agda:181:record Bézout (m n : ℤ) : Type where
Data\Fast\Int\Divisibility.agda:264:record QuotRem (m n : ℤ) : Type where
Data\Fast\Int\Divisibility.agda:352:  dec-helper : {ℓ ℓ' : Level}{A : Type ℓ}{B : Type ℓ'} → Dec A → B → A ⊎ ((¬ A) × B)
Data\Fast\Int\Order.agda:1:{- Order as an Indexed Data Type, as done in Agda stdlib and 1Lab -}
Data\Fast\Int\Order.agda:29:data _≤_ : ℤ → ℤ → Type where
Data\Fast\Int\Order.agda:34:data _<_ : ℤ → ℤ → Type where
Data\Fast\Int\Order.agda:39:_≥_ _>_ : ℤ → ℤ → Type
Data\Fast\Int\Order.agda:78:isProp≤ (pos≤pos p)       (pos≤pos q)       = cong pos≤pos (isPropBool→Type p q)
Data\Fast\Int\Order.agda:80:isProp≤ (negsuc≤negsuc p) (negsuc≤negsuc q) = cong negsuc≤negsuc (isPropBool→Type p q)
Data\Fast\Int\Order.agda:83:isProp< (pos<pos p)       (pos<pos q)       = cong pos<pos (isPropBool→Type p q)
Data\Fast\Int\Order.agda:85:isProp< (negsuc<negsuc p) (negsuc<negsuc q) = cong negsuc<negsuc (isPropBool→Type p q)
Data\Fast\Int\Order.agda:88:pos m    ≤? pos n    = mapDec pos≤pos ¬≤ℕ→¬pos≤pos DecBool→Type
Data\Fast\Int\Order.agda:91:negsuc m ≤? negsuc n = mapDec negsuc≤negsuc ¬≥ℕ→¬negsuc≤negsuc DecBool→Type
Data\Fast\Int\Order.agda:96:pos m    <? pos n    = mapDec pos<pos ¬<ℕ→¬pos<pos DecBool→Type
Data\Fast\Int\Order.agda:99:negsuc m <? negsuc n = mapDec negsuc<negsuc ¬>ℕ→¬negsuc<negsuc DecBool→Type
Data\Fast\Int\Order.agda:565:... | true  , p = <-weaken (pos<pos (subst Bool→Type (sym p) tt))
Data\Fast\Int\Order.agda:571:... | false , p = isAsym'< (¬>ℕ→¬negsuc<negsuc (subst Bool→Type p))
Data\Fast\Int\Order.agda:578:... | false , q = isAntisym≤ (pos≤pos p) (isAsym'< (¬<ℕ→¬pos<pos (subst Bool→Type q)) )
Data\Fast\Int\Order.agda:586:                             (<-weaken (negsuc<negsuc (subst Bool→Type (sym q) tt)))
Data\Fast\Int\Order.agda:592:... | false , p = isAsym'< (¬<ℕ→¬pos<pos (subst Bool→Type p))
Data\Fast\Int\Order.agda:600:... | true  , p = <-weaken (negsuc<negsuc (subst Bool→Type (sym p) tt))
Data\Fast\Int\Order.agda:606:... | false , q = isAntisym≤ (isAsym'< (¬<ℕ→¬pos<pos (subst Bool→Type q))) (pos≤pos p)
Data\Fast\Int\Order.agda:613:... | true  , q = isAntisym≤ (<-weaken (negsuc<negsuc (subst Bool→Type (sym q) tt)))
Data\Fast\Int\Order.agda:664:data Trichotomy m n : Type where
Data\Fast\Int\Order.agda:733:  {- This would take much longer to typecheck:
Data\Fast\Int\Properties.agda:66:subst-f : (A : (ℤ → ℤ → ℤ) → (ℤ → ℤ → ℤ) → Type) → A ℤ._+_ ℤ._·_ → A _+_ _·_
Data\Fin\Base.agda:18:-- Finite types.
Data\Fin\Base.agda:20:-- Currently it is most convenient to define these as a subtype of the
Data\Fin\Base.agda:25:Fin : ℕ → Type₀
Data\Fin\Base.agda:43:-- number as a number in the next largest finite type.
Data\Fin\Base.agda:96:-- The full inductive family eliminator for finite types.
Data\Fin\Base.agda:98:  : ∀(P : ∀(k : ℕ) → Fin k → Type ℓ)
Data\Fin\Base.agda:109:any? : ∀ {n} {P : Fin n → Type ℓ} → (∀ i → Dec (P i)) → Dec (Σ (Fin n) P)
Data\Fin\Base.agda:130:FinVec : (A : Type ℓ) (n : ℕ) → Type ℓ
Data\Fin\Base.agda:133:FinFamily : (n : ℕ) (ℓ : Level) → Type (ℓ-suc ℓ)
Data\Fin\Base.agda:134:FinFamily n ℓ = FinVec (Type ℓ) n
Data\Fin\Base.agda:136:FinFamily∙ : (n : ℕ) (ℓ : Level) → Type (ℓ-suc ℓ)
Data\Fin\Base.agda:146:prodFinFamily : (n : ℕ) → FinFamily (suc n) ℓ → Type ℓ
Data\Fin\Base.agda:157:sumFinGen : ∀ {ℓ} {A : Type ℓ} {n : ℕ}
Data\Fin\LehmerCode.agda:33:FinExcept : ∀ {n} → (i : Fin n) → Type₀
Data\Fin\LehmerCode.agda:113:data LehmerCode : (n : ℕ) → Type₀ where
Data\Fin\Properties.agda:37:   A : Type a
Data\Fin\Properties.agda:80:  subst-app : (B : A → Type b) (f : (x : A) → B x) {x y : A} (x≡y : x ≡ y) →
Data\Fin\Properties.agda:86:module _ (P  : (k : ℕ) → Fin k → Type ℓ)
Data\Fin\Properties.agda:147:-- A Residue is a family of types representing evidence that a
Data\Fin\Properties.agda:148:-- natural is congruent to a value of a finite type.
Data\Fin\Properties.agda:149:Residue : ℕ → ℕ → Type₀
Data\Fin\Properties.agda:157:-- A value of a finite type is its own residue.
Data\Fin\Properties.agda:260:    F : Fin (suc m) → Type₀
Data\Fin\Properties.agda:428:      : ∀ {A B : Type ℓ} {x y : A} {p : A ≡ B}
Data\Fin\Properties.agda:699:CharacΠFinIso : ∀ {ℓ} (n : ℕ) {B : Fin (suc n) → Type ℓ}
Data\Fin\Properties.agda:833:elimFin : ∀ {ℓ} {m : ℕ} {A : Fin (suc m) → Type ℓ}
Data\Fin\Properties.agda:843:elimFin-alt : ∀ {ℓ} {m : ℕ} {A : Fin (suc m) → Type ℓ}
Data\Fin\Properties.agda:851:elimFinβ : ∀ {ℓ} {m : ℕ} {A : Fin (suc m) → Type ℓ}
Data\Fin\Properties.agda:864:inhabitedFibres?Fin : ∀ {ℓ} {A : Type ℓ}
Data\Fin\Properties.agda:931:Iso-FinSuc→-Fin→× : ∀ {ℓ} (n : ℕ) {A : Fin (suc n) → Type ℓ}
Data\Fin\Properties.agda:1026:module _ {ℓ : Level} {n : ℕ} {A : Fin n → Type ℓ} (x₀ : Fin n)
Data\Fin\Recursive\Base.agda:9:data FinF (X : Type₀) : Type₀ where
Data\Fin\Recursive\Base.agda:13:Fin : ℕ → Type₀
Data\Fin\Recursive\Base.agda:21:    R : Type ℓ
Data\Fin\Recursive\Base.agda:28:  : ∀(P : ∀{k} → Fin k → Type ℓ)
Data\Fin\Recursive\Properties.agda:31:    A : Type ℓ
Data\Fin\Recursive\Properties.agda:56:  Cover : FinF A → FinF A → Type _
Data\Fin\Recursive\Properties.agda:124:any? : {P : Fin m → Type ℓ} → (∀ i → Dec (P i)) → Dec (Σ _ P)
Data\Fin\Recursive\Properties.agda:133:_#_ : Fin m → Fin m → Type₀
Data\FinData\Base.agda:14:    A B : Type ℓ
Data\FinData\Base.agda:16:data Fin : ℕ → Type₀ where
Data\FinData\Base.agda:61:  : ∀(P : ∀{k} → Fin k → Type ℓ)
Data\FinData\Base.agda:75:FinVec : (A : Type ℓ) (n : ℕ) → Type ℓ
Data\FinData\Base.agda:78:emptyFinVec : (A : Type ℓ) → FinVec A 0
Data\FinData\DepFinVec.agda:23:depFinVec : ((n : ℕ) → Type ℓ) → (m : ℕ) → Type ℓ
Data\FinData\FiniteChoice.agda:22:choice : {n : ℕ} (T : Fin n → Type ℓ) → ((x : Fin n) → ∥ T x ∥₁) → ∥ ((x : Fin n) → T x) ∥₁
Data\FinData\FinSet.agda:52:  (P : FinVec (Type ℓ) n) → (∀ k → Dec (P k)) → Dec (Σ (Fin n) P)
Data\FinData\Order.agda:23:_≤Fin_ : {n : ℕ} → Fin n → Fin n → Type
Data\FinData\Order.agda:26:_<Fin_ : {n : ℕ} → Fin n → Fin n → Type
Data\FinData\Order.agda:35:_≤'Fin_ : {n : ℕ} → Fin n → Fin n → Type
Data\FinData\Order.agda:38:_<'Fin_ : {n : ℕ} → Fin n → Fin n → Type
Data\FinData\Order.agda:46:data FinTrichotomy {n : ℕ} (i j : Fin n) : Type₀ where
Data\FinData\Properties.agda:32:   A : Type ℓ
Data\FinData\Properties.agda:148:data biEq {n : ℕ} (i j : Fin n) : Type where
Data\FinData\Properties.agda:152:data triEq {n : ℕ} (i j a : Fin n) : Type where
Data\FinData\Properties.agda:223:    (P : Fin n → Type ℓ)
Data\FinData\Properties.agda:234:    (P : Fin n → Type ℓ)
Data\FinData\Properties.agda:255:++FinElim : {P : A → Type ℓ'} {n m : ℕ} (U : FinVec A n) (V : FinVec A m)
Data\FinData\Properties.agda:365:    (P : Fin m → Type ℓ)
Data\FinData\Properties.agda:380:    (P : Fin m → Fin n → Type ℓ)
Data\FinSequence\Base.agda:11:record FinSequence (m : ℕ) (ℓ : Level) : Type (ℓ-suc ℓ) where
Data\FinSequence\Base.agda:14:    fobj : Fin (suc m) → Type ℓ
Data\FinSequence\Base.agda:18:  (C : FinSequence m ℓ) (D : FinSequence m ℓ') : Type (ℓ-max ℓ ℓ') where
Data\FinSet\Base.agda:28:    A : Type ℓ
Data\FinSet\Base.agda:33:isFinSet : Type ℓ → Type ℓ
Data\FinSet\Base.agda:36:isFinOrd : Type ℓ → Type ℓ
Data\FinSet\Base.agda:64:isFinSet' : Type ℓ → Type ℓ
Data\FinSet\Base.agda:76:-- the type of finite sets/propositions
Data\FinSet\Base.agda:78:FinSet : (ℓ : Level) → Type (ℓ-suc ℓ)
Data\FinSet\Base.agda:79:FinSet ℓ = TypeWithStr _ isFinSet
Data\FinSet\Base.agda:81:FinProp : (ℓ : Level) → Type (ℓ-suc ℓ)
Data\FinSet\Cardinality.agda:398:  ¬ΠQ→¬¬ΣP : (X : Type ℓ)
Data\FinSet\Cardinality.agda:399:      (P : X → Type ℓ' )
Data\FinSet\Cardinality.agda:400:      (Q : X → Type ℓ'')
Data\FinSet\Cardinality.agda:429:  Σ∥P∥→∥ΣP∥ : (X : Type ℓ)(P : X → Type ℓ')
Data\FinSet\Cardinality.agda:490:  (X : Type ℓ)
Data\FinSet\Cardinality.agda:496:    isMax : Type ℓ
Data\FinSet\Cardinality.agda:505:  ΣMax : Type ℓ
Data\FinSet\Cardinality.agda:508:  ∃Max : Type ℓ
Data\FinSet\Cardinality.agda:517:-- lemma about maximal value on sum type
Data\FinSet\Cardinality.agda:519:  (X : Type ℓ )
Data\FinSet\Cardinality.agda:520:  (Y : Type ℓ')
Data\FinSet\Cardinality.agda:618:-- a more computationally efficient version of equivalence type
Data\FinSet\Cardinality.agda:640:  isFinSetType≡Eff : isFinSet (X .fst ≡ Y .fst)
Data\FinSet\Cardinality.agda:641:  isFinSetType≡Eff = EquivPresIsFinSet (invEquiv univalence) (isFinSet≃Eff X Y)
Data\FinSet\Constructors.agda:40:  (X : Type ℓ)(p : isFinOrd X) where
Data\FinSet\Constructors.agda:49:  (X : Type ℓ )(p : isFinOrd X)
Data\FinSet\Constructors.agda:50:  (Y : Type ℓ')(q : isFinOrd Y) where
Data\FinSet\Constructors.agda:59:  (X : Type ℓ )(p : isFinOrd X)
Data\FinSet\Constructors.agda:60:  (Y : X → Type ℓ')(q : (x : X) → isFinOrd (Y x)) where
Data\FinSet\Constructors.agda:80:-- closedness under several type constructors
Data\FinSet\Constructors.agda:163:  isFinSetType≡ : isFinSet (X .fst ≡ Y .fst)
Data\FinSet\Constructors.agda:164:  isFinSetType≡ = EquivPresIsFinSet (invEquiv univalence) (isFinSet≃ X Y)
Data\FinSet\Constructors.agda:173:  isFinSetTypeAut : isFinSet (X .fst ≡ X .fst)
Data\FinSet\Constructors.agda:174:  isFinSetTypeAut = EquivPresIsFinSet (invEquiv univalence) isFinSetAut
Data\FinSet\Constructors.agda:215:  (X : Type ℓ)(Y : FinSet ℓ')
Data\FinSet\Constructors.agda:226:  (Y : Type ℓ')(h : Discrete Y)
Data\FinSet\DecidablePredicate.agda:37:  (X : Type ℓ)(p : isFinOrd X) where
Data\FinSet\DecidablePredicate.agda:46:  (X : Type ℓ )(p : isFinOrd X)
Data\FinSet\DecidablePredicate.agda:47:  (P : X → Type ℓ')
Data\FinSet\DecidablePredicate.agda:73:  (X : Type ℓ )(p : isFinOrd X)
Data\FinSet\DecidablePredicate.agda:130:  isDecProp× .snd = Σ-cong-equiv (P .snd .snd) (λ _ → Q .snd .snd) ⋆ Bool→Type×≃ _ _
Data\FinSet\FiniteChoice.agda:31:  {n : ℕ}(Y : Fin n → Type ℓ) → ((x : Fin n) → ∥ Y x ∥₁) ≃ ∥ ((x : Fin n) → Y x) ∥₁
Data\FinSet\FiniteChoice.agda:45:  (X : Type ℓ)(p : isFinOrd X)
Data\FinSet\FiniteChoice.agda:46:  (Y : X → Type ℓ') where
Data\FinSet\FiniteChoice.agda:59:  (Y : X .fst → Type ℓ') where
Data\FinSet\Induction.agda:106:  (P : FinSet ℓ → Type ℓ')
Data\FinSet\Properties.agda:33:    A : Type ℓ
Data\FinSet\Properties.agda:34:    B : Type ℓ'
Data\FinSet\Properties.agda:39:  {A : Type ℓ}{B : Type ℓ'}{C : Type ℓ''} where
Data\FinSet\Properties.agda:47:  {A : Type ℓ}{B : Type ℓ'} where
Data\FinSet\Properties.agda:96:    {A : Type ℓ}{B : A → Type ℓ'}
Data\FinSet\Properties.agda:100:isContr→isFinOrd : ∀ {ℓ} → {A : Type ℓ} →
Data\FinSet\Properties.agda:109:  {A : Type L} →
Data\FinSet\Properties.agda:119:EquivPresIsFinOrd : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → A ≃ B → isFinOrd A → isFinOrd B
Data\FinSet\Properties.agda:134:takeFirstFinOrd : ∀ {ℓ} → (A : Type ℓ) →
Data\FinSet\Quotients.agda:40:LiftDecProp : {ℓ ℓ' : Level}{P : Type ℓ} → (p : isDecProp P) → P ≃ Bool→Type* {ℓ'} (p .fst)
Data\FinSet\Quotients.agda:46:  (X : Type ℓ) where
Data\FinSet\Quotients.agda:48:  ℙEff : Type ℓ
Data\FinSet\Quotients.agda:55:  ℙEff→ℙDec f .fst x = Bool→Type* (f x) , isPropBool→Type*
Data\FinSet\Quotients.agda:56:  ℙEff→ℙDec f .snd x = DecBool→Type*
Data\FinSet\Quotients.agda:76:  (X : Type ℓ)(p : isFinOrd X) where
Data\FinSet\Quotients.agda:95:  (R : X .fst → X .fst → Type ℓ')
Data\FinSet\Quotients.agda:98:  isEqClassEff : ℙEff (X .fst) → Type ℓ
Data\FinSet\Quotients.agda:106:    → (a : X .fst) → Bool→Type* {ℓ = ℓ'} (f a) ≃ ∥ R a x ∥₁
Data\FinSet\Quotients.agda:108:      pathToEquiv (cong Bool→Type* (h a))
Data\FinSet\Quotients.agda:113:    → ((a : X .fst) → Bool→Type* {ℓ = ℓ'} (f a) ≃ ∥ R a x ∥₁)
Data\FinSet\Quotients.agda:116:    Bool→TypeInj* _ _
Data\FinSet\Quotients.agda:125:  _∥Eff_ : Type ℓ
Data\FinSet\Quotients.agda:138:  (R : X .fst → X .fst → Type ℓ')
Data\FinSet\Binary\Large.agda:23:isBinary : Type ℓ → Type ℓ
Data\FinSet\Binary\Large.agda:26:Binary : ∀ ℓ → Type _
Data\FinSet\Binary\Large.agda:27:Binary ℓ = Σ (Type ℓ) isBinary
Data\FinSet\Binary\Large.agda:29:isBinary→isSet : ∀{B : Type ℓ} → isBinary B → isSet B
Data\FinSet\Binary\Large.agda:34:    : ∀{ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'}
Data\FinSet\Binary\Large.agda:83:      (isOfHLevelTypeOfHLevel 2)
Data\FinSet\Binary\Large.agda:85:record BinStructure (B : Type ℓ) : Type ℓ where
Data\FinSet\Binary\Large.agda:98:module Parameterized (B : Type ℓ) where
Data\FinSet\Binary\Small\Base.agda:11:data Binary : Type₀
Data\FinSet\Binary\Small\Base.agda:12:El : Binary → Type₀
Data\FinSet\Binary\Small\Properties.agda:31:    B : Type ℓ
Data\FinSet\Binary\Small\Properties.agda:70:  lemma : ∀(B : Type₀) → ∥ Bool ≃ B ∥₁ → Σ[ b ∈ Binary ] El b ≃ B
Data\FinType\Base.agda:3:Finite Types
Data\FinType\Base.agda:5:This file formalize the notion of Rijke finite type,
Data\FinType\Base.agda:7:Basically, a type is (Rijke) n-finite if its i-th order
Data\FinType\Base.agda:15:module Cubical.Data.FinType.Base where
Data\FinType\Base.agda:31:    X : Type ℓ
Data\FinType\Base.agda:33:-- the (Rijke) finite type
Data\FinType\Base.agda:35:isFinType : (n : ℕ) → Type ℓ → Type ℓ
Data\FinType\Base.agda:36:isFinType 0 X = isFinSet ∥ X ∥₂
Data\FinType\Base.agda:37:isFinType (suc n) X = (isFinType 0 X) × ((a b : X) → isFinType n (a ≡ b))
Data\FinType\Base.agda:39:isPropIsFinType : isProp (isFinType n X)
Data\FinType\Base.agda:40:isPropIsFinType {n = 0} = isPropIsFinSet
Data\FinType\Base.agda:41:isPropIsFinType {n = suc n} = isProp× isPropIsFinSet (isPropΠ2 (λ _ _ → isPropIsFinType {n = n}))
Data\FinType\Base.agda:43:-- the type of finite types
Data\FinType\Base.agda:45:FinType : (ℓ : Level)(n : ℕ) → Type (ℓ-suc ℓ)
Data\FinType\Base.agda:46:FinType ℓ n = TypeWithStr ℓ (isFinType n)
Data\FinType\Base.agda:50:isFinTypeSuc→isFinType : isFinType (suc n) X → isFinType n X
Data\FinType\Base.agda:51:isFinTypeSuc→isFinType {n = 0} p = p .fst
Data\FinType\Base.agda:52:isFinTypeSuc→isFinType {n = suc n} p .fst = p .fst
Data\FinType\Base.agda:53:isFinTypeSuc→isFinType {n = suc n} p .snd a b = isFinTypeSuc→isFinType {n = n} (p .snd a b)
Data\FinType\Base.agda:55:isFinType→isFinType0 : isFinType n X → isFinType 0 X
Data\FinType\Base.agda:56:isFinType→isFinType0 {n = 0} p = p
Data\FinType\Base.agda:57:isFinType→isFinType0 {n = suc n} p = p .fst
Data\FinType\Base.agda:59:isFinTypeSuc→isFinType1 : isFinType (suc n) X → isFinType 1 X
Data\FinType\Base.agda:60:isFinTypeSuc→isFinType1 {n = 0} p = p
Data\FinType\Base.agda:61:isFinTypeSuc→isFinType1 {n = suc n} p .fst = p .fst
Data\FinType\Base.agda:62:isFinTypeSuc→isFinType1 {n = suc n} p .snd a b = isFinType→isFinType0 {n = suc n} (p .snd a b)
Data\FinType\FiniteStructure.agda:4:  In short, the type of structures should be finite set itself.
Data\FinType\FiniteStructure.agda:8:- The type of finitely-structured finite sets is Rijke finite,
Data\FinType\FiniteStructure.agda:13:module Cubical.Data.FinType.FiniteStructure where
Data\FinType\FiniteStructure.agda:28:open import Cubical.Data.FinType
Data\FinType\FiniteStructure.agda:29:open import Cubical.Data.FinType.Sigma
Data\FinType\FiniteStructure.agda:37:-- type of finite sets with finite structure
Data\FinType\FiniteStructure.agda:39:FinSetWithStr : (S : FinSet ℓ → FinSet ℓ') → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Data\FinType\FiniteStructure.agda:42:-- type of finite sets with a fixed cardinal
Data\FinType\FiniteStructure.agda:44:FinSetOfCard : (ℓ : Level) (n : ℕ) → Type (ℓ-suc ℓ)
Data\FinType\FiniteStructure.agda:47:FinSetWithStrOfCard : (S : FinSet ℓ → FinSet ℓ') (n : ℕ) → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Data\FinType\FiniteStructure.agda:64:isFinTypeFinSetOfCard : isFinType 1 (FinSetOfCard ℓ n)
Data\FinType\FiniteStructure.agda:65:isFinTypeFinSetOfCard .fst = isPathConnected→isFinType0 isPathConnectedFinSetOfCard
Data\FinType\FiniteStructure.agda:66:isFinTypeFinSetOfCard .snd X Y =
Data\FinType\FiniteStructure.agda:67:  isFinSet→isFinType 0 (EquivPresIsFinSet (FinSet≡ _ _ ⋆ FinSetOfCard≡ _ _) (isFinSetType≡Eff (X
.fst) (Y .fst)))
Data\FinType\FiniteStructure.agda:69:-- the type of finitely-structured finite sets is Rijke finite
Data\FinType\FiniteStructure.agda:72:isFinTypeFinSetWithStrOfCard :
Data\FinType\FiniteStructure.agda:74:  → isFinType 0 (FinSetWithStrOfCard S n)
Data\FinType\FiniteStructure.agda:75:isFinTypeFinSetWithStrOfCard S n =
Data\FinType\FiniteStructure.agda:76:  isFinTypeΣ {n = 0} (_ , isFinTypeFinSetOfCard) (λ X → _ , isFinSet→isFinType 0 (S (X .fst) .snd))
Data\FinType\Properties.agda:4:- Some basic properties of Rijke finite types.
Data\FinType\Properties.agda:8:module Cubical.Data.FinType.Properties where
Data\FinType\Properties.agda:20:open import Cubical.Data.FinType.Base
Data\FinType\Properties.agda:26:    X : Type ℓ
Data\FinType\Properties.agda:27:    Y : Type ℓ'
Data\FinType\Properties.agda:29:EquivPresIsFinType : (n : ℕ) → X ≃ Y → isFinType n X → isFinType n Y
Data\FinType\Properties.agda:30:EquivPresIsFinType 0 e = EquivPresIsFinSet (isoToEquiv (setTruncIso (equivToIso e)))
Data\FinType\Properties.agda:31:EquivPresIsFinType (suc n) e (p , q) .fst = EquivPresIsFinType 0 e p
Data\FinType\Properties.agda:32:EquivPresIsFinType (suc n) e (p , q) .snd a b =
Data\FinType\Properties.agda:33:  EquivPresIsFinType n (invEquiv (congEquiv (invEquiv e))) (q _ _)
Data\FinType\Properties.agda:35:isFinSet→isFinType : (n : ℕ) → isFinSet X → isFinType n X
Data\FinType\Properties.agda:36:isFinSet→isFinType 0 p = EquivPresIsFinSet (invEquiv (setTruncIdempotent≃ (isFinSet→isSet p))) p
Data\FinType\Properties.agda:37:isFinSet→isFinType (suc n) p .fst = isFinSet→isFinType 0 p
Data\FinType\Properties.agda:38:isFinSet→isFinType (suc n) p .snd a b = isFinSet→isFinType n (isFinSet≡ (_ , p) _ _)
Data\FinType\Properties.agda:40:isPathConnected→isFinType0 : isContr ∥ X ∥₂ → isFinType 0 X
Data\FinType\Properties.agda:41:isPathConnected→isFinType0 p = isContr→isFinSet p
Data\FinType\Sigma.agda:4:- Rijke finiteness is closed under forming Σ-type.
Data\FinType\Sigma.agda:8:module Cubical.Data.FinType.Sigma where
Data\FinType\Sigma.agda:23:open import Cubical.Data.FinType
Data\FinType\Sigma.agda:34:  (X : Type ℓ )
Data\FinType\Sigma.agda:35:  (Y : Type ℓ') (h : isFinType 1 Y)
Data\FinType\Sigma.agda:37:  (q : (y : Y) → isFinType 0 (fiber f y)) where
Data\FinType\Sigma.agda:58:  isFinType0Total : isFinType 0 X
Data\FinType\Sigma.agda:59:  isFinType0Total = isFinSetTotal ∥ X ∥₂ (∥ Y ∥₂ , h .fst) ∥f∥₂ isFinSetFiber∥∥₂
Data\FinType\Sigma.agda:62:  (X : FinType ℓ 1)
Data\FinType\Sigma.agda:63:  (Y : X .fst → FinType ℓ' 0) where
Data\FinType\Sigma.agda:65:  isFinType0Σ : isFinType 0 (Σ (X .fst) (λ x → Y x .fst))
Data\FinType\Sigma.agda:66:  isFinType0Σ =
Data\FinType\Sigma.agda:67:    isFinType0Total (Σ (X .fst) (λ x → Y x .fst)) (X .fst) (X .snd) fst
Data\FinType\Sigma.agda:68:      (λ x → EquivPresIsFinType 0 (fiberProjEquiv _ _ x) (Y x .snd))
Data\FinType\Sigma.agda:72:isFinTypeΣ : {n : ℕ}
Data\FinType\Sigma.agda:73:  (X : FinType ℓ (1 + n))
Data\FinType\Sigma.agda:74:  (Y : X .fst → FinType ℓ' n)
Data\FinType\Sigma.agda:75:  → isFinType n (Σ (X .fst) (λ x → Y x .fst))
Data\FinType\Sigma.agda:76:isFinTypeΣ {n = 0} = isFinType0Σ
Data\FinType\Sigma.agda:77:isFinTypeΣ {n = suc n} X Y .fst =
Data\FinType\Sigma.agda:78:  isFinType0Σ (_ , isFinTypeSuc→isFinType1 {n = suc n} (X .snd))
Data\FinType\Sigma.agda:79:    (λ x → _ , isFinType→isFinType0 {n = suc n} (Y x .snd))
Data\FinType\Sigma.agda:80:isFinTypeΣ {n = suc n} X Y .snd a b =
Data\FinType\Sigma.agda:81:  EquivPresIsFinType n (ΣPathTransport≃PathΣ a b)
Data\FinType\Sigma.agda:82:    (isFinTypeΣ {n = n} (_ , X .snd .snd _ _) (λ _ → _ , Y _ .snd .snd _ _))
Data\FinWeak\Base.agda:17:data FinPure : ℕ → Type where
Data\FinWeak\Base.agda:25:data Fin : ℕ → Type where
Data\Graph\Base.agda:8:-- The type of directed multigraphs (with loops)
Data\Graph\Base.agda:10:record Graph ℓv ℓe : Type (ℓ-suc (ℓ-max ℓv ℓe)) where
Data\Graph\Base.agda:12:    Node : Type ℓv
Data\Graph\Base.agda:13:    Edge : Node → Node → Type ℓe
Data\Graph\Base.agda:21:TypeGr : ∀ ℓ → Graph (ℓ-suc ℓ) ℓ
Data\Graph\Base.agda:22:Node (TypeGr ℓ) = Type ℓ
Data\Graph\Base.agda:23:Edge (TypeGr ℓ) A B = A → B
Data\Graph\Base.agda:28:                : Type (ℓ-suc (ℓ-max (ℓ-max ℓv ℓe) (ℓ-max ℓv' ℓe'))) where
Data\Graph\Base.agda:61:-- Diagrams are (graph) functors with codomain Type
Data\Graph\Base.agda:63:Diag : ∀ ℓd (G : Graph ℓv ℓe) → Type (ℓ-suc (ℓ-max (ℓ-max ℓv ℓe) (ℓ-suc ℓd)))
Data\Graph\Base.agda:64:Diag ℓd G = GraphHom G (TypeGr ℓd)
Data\Graph\Base.agda:67:               : Type (ℓ-suc (ℓ-max (ℓ-max ℓv ℓe) (ℓ-suc (ℓ-max ℓd ℓd')))) where
Data\Graph\Displayed.agda:16:  record Graphᴰ ℓgᴰ ℓgᴰ' : Type (ℓ-max (ℓ-max ℓg ℓg') (ℓ-suc (ℓ-max ℓgᴰ ℓgᴰ')))
Data\Graph\Displayed.agda:20:      Node[_] : G .Node → Type ℓgᴰ
Data\Graph\Displayed.agda:22:                   → Type ℓgᴰ'
Data\Graph\Displayed.agda:35:  record Section : Type (ℓ-max (ℓ-max ℓg ℓg')
Data\Graph\Examples.agda:42:data Adj : ℕ → ℕ → Type₀ where
Data\Graph\Examples.agda:60:record ωDiag ℓ : Type (ℓ-suc ℓ) where
Data\Graph\Examples.agda:62:    ωNode : ℕ → Type ℓ
Data\Graph\Examples.agda:73:data AdjFin : ∀ {k} → Fin k → Fin k → Type₀ where
Data\Graph\Examples.agda:97:record [_]Diag ℓ (k : ℕ) : Type (ℓ-suc ℓ) where
Data\Graph\Examples.agda:99:    []Node : Fin (suc k) → Type ℓ
Data\Graph\Examples.agda:119:               : Type (ℓ-max (ℓ-suc ℓ) (ℓ-max (ℓ-max ℓv ℓv') (ℓ-max ℓe ℓe'))) where
Data\Graph\Examples.agda:121:      ⊎Node : Node G ⊎ Node G' → Type ℓ
Data\Graph\Examples.agda:136:  DecGraph : ∀ ℓv ℓe → Type (ℓ-suc (ℓ-max ℓv ℓe))
Data\Graph\Examples.agda:148:               : Type (ℓ-max (ℓ-suc ℓ) (ℓ-max (ℓ-max ℓv ℓv') (ℓ-max ℓe ℓe'))) where
Data\Graph\Examples.agda:150:      ×Node : Node (fst G) × Node (fst G') → Type ℓ
Data\Graph\Path.agda:18:  data Path : (v w : Node G) → Type (ℓ-max ℓv ℓe) where
Data\Graph\Path.agda:59:    PathWithLen : ℕ → Node G → Node G → Type (ℓ-max ℓv ℓe)
Data\InfNat\Base.agda:9:data ℕ+∞ : Type₀ where
Data\InfNat\Base.agda:20:caseInfNat : ∀ {ℓ} → {A : Type ℓ} → (aF aI : A) → ℕ+∞ → A
Data\Int\Base.agda:15:data ℤ : Type₀ where
Data\Int\Divisibility.agda:62:_∣_ : ℤ → ℤ → Type
Data\Int\Divisibility.agda:70:_∣'_ : ℤ → ℤ → Type
Data\Int\Divisibility.agda:197:record Bézout (m n : ℤ) : Type where
Data\Int\Divisibility.agda:279:record QuotRem (m n : ℤ) : Type where
Data\Int\Divisibility.agda:361:  dec-helper : {ℓ ℓ' : Level}{A : Type ℓ}{B : Type ℓ'} → Dec A → B → A ⊎ ((¬ A) × B)
Data\Int\Order.agda:19:_≤_ : ℤ → ℤ → Type₀
Data\Int\Order.agda:22:_<_ : ℤ → ℤ → Type₀
Data\Int\Order.agda:25:_≥_ : ℤ → ℤ → Type₀
Data\Int\Order.agda:28:_>_ : ℤ → ℤ → Type₀
Data\Int\Order.agda:31:data Trichotomy (m n : ℤ) : Type₀ where
Data\Int\Properties.agda:387:  T : ℤ → Type₀
Data\Int\Properties.agda:394:  T : ℤ → Type₀
Data\Int\Properties.agda:401:  T : ℤ → Type₀
Data\Int\Properties.agda:408:  T : ℤ → Type₀
Data\Int\Properties.agda:518:ind-comm : {A : Type₀} (_∙_ : A → A → A) (f : ℕ → A) (g : A → A)
Data\Int\Properties.agda:535:ind-assoc : {A : Type₀} (_·_ : A → A → A) (f : ℕ → A)
Data\Int\MoreInts\BiInvInt\Base.agda:33:data BiInvℤ : Type₀ where
Data\Int\MoreInts\BiInvInt\Base.agda:119:  sym-filler : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y)
Data\Int\MoreInts\BiInvInt\Properties.agda:24:  ∀ {ℓ} {P : BiInvℤ → Type ℓ} → (∀ n → isProp (P n)) →
Data\Int\MoreInts\BiInvInt\Properties.agda:49:BiInvℤ-rec : ∀ {ℓ} {A : Type ℓ} → A → A ≃ A → BiInvℤ → A
Data\Int\MoreInts\DeltaInt\Base.agda:32:data DeltaInt : Type₀ where
Data\Int\MoreInts\DiffInt\Base.agda:12:rel : (ℕ × ℕ) → (ℕ × ℕ) → Type₀
Data\Int\MoreInts\QuoInt\Base.agda:21:Sign : Type₀
Data\Int\MoreInts\QuoInt\Base.agda:31:data ℤ : Type₀ where
Data\Int\MoreInts\QuoInt\Base.agda:65:rec : ∀ {A : Type l} → (pos' neg' : ℕ → A) → pos' 0 ≡ neg' 0 → ℤ → A
Data\Int\MoreInts\QuoInt\Base.agda:70:elim : ∀ (P : ℤ → Type l)
Data\List\Base.agda:10:module _ {ℓ} {A : Type ℓ} where
Data\List\Base.agda:33:  map : ∀ {ℓ'} {B : Type ℓ'} → (A → B) → List A → List B
Data\List\Base.agda:37:  map2 : ∀ {ℓ' ℓ''} {B : Type ℓ'} {C : Type ℓ''}
Data\List\Base.agda:43:  filterMap : ∀ {ℓ'} {B : Type ℓ'} → (A → Maybe B) → List A → List B
Data\List\Base.agda:47:  foldr : ∀ {ℓ'} {B : Type ℓ'} → (A → B → B) → B → List A → B
Data\List\Base.agda:51:  foldl : ∀ {ℓ'} {B : Type ℓ'} → (B → A → B) → B → List A → B
Data\List\Base.agda:65:  elim : ∀ {ℓ'} {B : List A → Type ℓ'}
Data\List\Base.agda:72:  rec : ∀ {ℓ'} {B : Type ℓ'}
Data\List\Dependent.agda:21:data ListP {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) : (as : List A) → Type (ℓ-max ℓA ℓB) where
Data\List\Dependent.agda:30:RepListP : ∀ {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) (as : List A) → Type (ℓ-max ℓA ℓB)
Data\List\Dependent.agda:34:isoRepListP : ∀ {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) (as : List A) → ListP B as ≅ RepListP B as
Data\List\Dependent.agda:44:equivRepListP : ∀ {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) (as : List A) → ListP B as ≃ RepListP B as
Data\List\Dependent.agda:47:pathRepListP : ∀ {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) (as : List A) → ListP B as ≡ RepListP B as
Data\List\Dependent.agda:52:    → {A : Type ℓA}
Data\List\Dependent.agda:53:    → {B : A → Type ℓB} → ((a : A) → isOfHLevel (suc (suc n)) (B a))
Data\List\Dependent.agda:60:  → {A : Type ℓA}
Data\List\Dependent.agda:61:  → {B : A → Type ℓB} → ((a : A) → isOfHLevel (suc (suc n)) (B a))
Data\List\Dependent.agda:69:lookupP : ∀ {ℓA ℓB} {A : Type ℓA} {B : A → Type ℓB} {as} (bs : ListP B as) → (p : Fin (length as)) → B
(lookup as p)
Data\List\Dependent.agda:73:{- It seems sensible to reserve the name tabulateP for a function that mentions tabulate (rather than
lookup) in its type.
Data\List\Dependent.agda:75:tabulateOverLookup : ∀ {ℓA ℓB} {A : Type ℓA} {B : A → Type ℓB} as (^b : (p : Fin (length as)) → B (lookup
as p))
Data\List\Dependent.agda:80:tabulateOverLookup-lookupP : ∀ {ℓA ℓB} {A : Type ℓA} {B : A → Type ℓB} {as} (bs : ListP B as) →
Data\List\Dependent.agda:85:lookupP-tabulateOverLookup : ∀ {ℓA ℓB} {A : Type ℓA} (B : A → Type ℓB) as (^b : (p : Fin (length as)) → B
(lookup as p))
Data\List\Dependent.agda:92:mapP : ∀ {ℓA ℓA' ℓB ℓB'} {A : Type ℓA} {A' : Type ℓA'} {B : A → Type ℓB} {B' : A' → Type ℓB'}
Data\List\Dependent.agda:97:mapOverIdfun : ∀ {ℓA ℓB ℓB'} {A : Type ℓA} {B : A → Type ℓB} {B' : A → Type ℓB'}
Data\List\Dependent.agda:102:mapOverIdfun-idfun : ∀ {ℓA ℓB} {A : Type ℓA} {B : A → Type ℓB} as → mapOverIdfun (λ a → idfun _) as ≡
(idfun (ListP B as))
Data\List\Dependent.agda:106:mapOverIdfun-∘ : ∀ {ℓA ℓB ℓB' ℓB''} {A : Type ℓA} {B : A → Type ℓB} {B' : A → Type ℓB'} {B'' : A → Type
ℓB''}
Data\List\Dependent.agda:112:mapOverSpan : ∀ {ℓI ℓA ℓA' ℓB ℓB'} {I : Type ℓI} {A : Type ℓA} {A' : Type ℓA'} {B : A → Type ℓB} {B' : A'
→ Type ℓB'}
Data\List\Dependent.agda:117:mapOverSpan-idfun : ∀ {ℓI ℓA ℓB} {I : Type ℓI} {A : Type ℓA} {B : A → Type ℓB}
Data\List\Dependent.agda:123:  {I : Type ℓI}
Data\List\Dependent.agda:124:  {A : Type ℓA} {A' : Type ℓA'} {A'' : Type ℓA''}
Data\List\Dependent.agda:125:  {B : A → Type ℓB} {B' : A' → Type ℓB'} {B'' : A'' → Type ℓB''}
Data\List\Dependent.agda:136:  {I : Type ℓI}
Data\List\Dependent.agda:137:  {A : Type ℓA} {A'' : Type ℓA''}
Data\List\Dependent.agda:138:  {B : A → Type ℓB} {B' : A → Type ℓB'} {B'' : A'' → Type ℓB''}
Data\List\FinData.agda:16:    A B : Type ℓ
Data\List\FinData.agda:42:lookup-tabulate-iso : (A : Type ℓ) → Iso (List A) (Σ[ n ∈ ℕ ] (Fin n → A))
Data\List\FinData.agda:49:lookup-tabulate-equiv : (A : Type ℓ) → List A ≃ (Σ[ n ∈ ℕ ] (Fin n → A))
Data\List\Properties.agda:18:module _ {ℓ} {A : Type ℓ} where
Data\List\Properties.agda:54:  data SnocView : List A → Type ℓ where
Data\List\Properties.agda:65:-- Path space of list type
Data\List\Properties.agda:66:module ListPath {ℓ} {A : Type ℓ} where
Data\List\Properties.agda:68:  Cover : List A → List A → Type ℓ
Data\List\Properties.agda:110:isOfHLevelList : ∀ {ℓ} (n : HLevel) {A : Type ℓ}
Data\List\Properties.agda:122:    A : Type ℓ
Data\List\Properties.agda:123:    B : Type ℓ'
Data\List\Properties.agda:127:caseList : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → (n c : B) → List A → B
Data\List\Properties.agda:241:map-∘ : ∀ {ℓA ℓB ℓC} {A : Type ℓA} {B : Type ℓB} {C : Type ℓC}
Data\List\Properties.agda:289:Split++ : (xs ys xs' ys' zs : List A) → Type _
Data\Maybe\Base.agda:8:    A : Type ℓA
Data\Maybe\Base.agda:9:    B : Type ℓB
Data\Maybe\Base.agda:11:data Maybe (A : Type ℓ) : Type ℓ where
Data\Maybe\Base.agda:27:elim : ∀ {A : Type ℓA} (B : Maybe A → Type ℓB) → B nothing → ((x : A) → B (just x)) → (mx : Maybe A) → B mx
Data\Maybe\Properties.agda:23:Maybe∙ : ∀ {ℓ} (A : Type ℓ) → Pointed ℓ
Data\Maybe\Properties.agda:29:module _ {ℓ} (A : Type ℓ) {ℓ'} (B : Pointed ℓ') where
Data\Maybe\Properties.agda:40:map-Maybe-id : ∀ {ℓ} {A : Type ℓ} → ∀ m → map-Maybe (idfun A) m ≡ m
Data\Maybe\Properties.agda:44:-- Path space of Maybe type
Data\Maybe\Properties.agda:45:module MaybePath {ℓ} {A : Type ℓ} where
Data\Maybe\Properties.agda:46:  Cover : Maybe A → Maybe A → Type ℓ
Data\Maybe\Properties.agda:96:isOfHLevelMaybe : ∀ {ℓ} (n : HLevel) {A : Type ℓ}
Data\Maybe\Properties.agda:109:   A : Type ℓ
Data\Maybe\Properties.agda:169:congMaybeEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Data\Nat\Algebra.agda:8:Proofing the latter is trivial, since the typechecker does the work for us.
Data\Nat\Algebra.agda:10:For details see the paper [Homotopy-initial algebras in type theory](https://arxiv.org/abs/1504.05531)
Data\Nat\Algebra.agda:35:record NatAlgebra ℓ : Type (ℓ-suc ℓ) where
Data\Nat\Algebra.agda:37:    Carrier  : Type ℓ
Data\Nat\Algebra.agda:41:record NatMorphism (A : NatAlgebra ℓ) (B : NatAlgebra ℓ') : Type (ℓ-max ℓ ℓ') where
Data\Nat\Algebra.agda:48:record NatFiber (N : NatAlgebra ℓ') ℓ : Type (ℓ-max ℓ' (ℓ-suc ℓ)) where
Data\Nat\Algebra.agda:51:    Fiber    : Carrier → Type ℓ
Data\Nat\Algebra.agda:55:record NatSection {N : NatAlgebra ℓ'} (F : NatFiber N ℓ) : Type (ℓ-max ℓ' ℓ) where
Data\Nat\Algebra.agda:63:isNatHInitial  : NatAlgebra ℓ' → (ℓ : Level) → Type (ℓ-max ℓ' (ℓ-suc ℓ))
Data\Nat\Algebra.agda:66:isNatInductive : NatAlgebra ℓ' → (ℓ : Level) → Type (ℓ-max ℓ' (ℓ-suc ℓ))
Data\Nat\Algebra.agda:74:  -- under the assumption that some shape is nat-inductive, the type of sections over any fiber
Data\Nat\Algebra.agda:88:    squeezeSquare : ∀{a}{A : Type a}{w x y z : A} (p : w ≡ x) {q : x ≡ y} (r : z ≡ y)
Data\Nat\Algebra.agda:234:-- this implies moreover that the carrier types are isomorphic
Data\Nat\Base.agda:19:caseNat : ∀ {ℓ} → {A : Type ℓ} → (a0 aS : A) → ℕ → A
Data\Nat\Base.agda:33:iter : ∀ {ℓ} {A : Type ℓ} → ℕ → (A → A) → A → A
Data\Nat\Base.agda:37:elim : ∀ {ℓ} {A : ℕ → Type ℓ}
Data\Nat\Base.agda:44:elim+2 : ∀ {ℓ} {A : ℕ → Type ℓ} → A 0 → A 1
Data\Nat\Base.agda:58:--Typed version
Data\Nat\Base.agda:60:  toType : Bool → Type
Data\Nat\Base.agda:61:  toType false = ⊥
Data\Nat\Base.agda:62:  toType true = Unit
Data\Nat\Base.agda:64:isEvenT : ℕ → Type
Data\Nat\Base.agda:65:isEvenT n = toType (isEven n)
Data\Nat\Base.agda:67:isOddT : ℕ → Type
Data\Nat\Base.agda:82:_ˣ_ : ∀ {ℓ} (A : ℕ → Type ℓ) (n : ℕ) → Type ℓ
Data\Nat\Base.agda:86:0ˣ : ∀ {ℓ} (A : ℕ → Type ℓ) (0A : (n : ℕ) → A n) → (n : ℕ) → A ˣ n
Data\Nat\Coprime.agda:16:areCoprime : ℕ × ℕ → Type₀
Data\Nat\Divisibility.agda:25:_∣_ : ℕ → ℕ → Type₀
Data\Nat\Divisibility.agda:31:prediv : ℕ → ℕ → Type₀
Data\Nat\Divisibility.agda:36:_∣'_ : ℕ → ℕ → Type₀
Data\Nat\GCD.agda:34:isCD : ℕ → ℕ → ℕ → Type₀
Data\Nat\GCD.agda:45:isGCD : ℕ → ℕ → ℕ → Type₀
Data\Nat\GCD.agda:48:GCD : ℕ → ℕ → Type₀
Data\Nat\Literals.agda:4:   and negative integer literals for any type (e.g. Int, ℕ₋₁, ℕ₋₂, ℕ₊₁).
Data\Nat\Lower.agda:23:isMonotone : (ℕ → Bool) → Type
Data\Nat\Lower.agda:32:Monotone : Type
Data\Nat\Lower.agda:79:data MView : (ℕ → Bool) → Type where
Data\Nat\Lower.agda:92:Detached : (ℕ → Bool) → Type
Data\Nat\Lower.agda:93:Detached p = Σ[ n ∈ ℕ ] Bool→Type (p n)
Data\Nat\Lower.agda:95:Lower : Monotone → Type
Data\Nat\Lower.agda:101:  = ΣPathP (s , isPropDep∘ p isPropDep-Bool→Type q r s)
Data\Nat\Lower.agda:112:  apart : ℕ → ℕ → Type
Data\Nat\Lower.agda:134:_#_ : ∀{P : ℕ → Type ℓ} → Σ ℕ P → Σ ℕ P → Type
Data\Nat\Lower.agda:137:_#?_ : ∀{P : ℕ → Type ℓ} → (u v : Σ ℕ P) → (u # v) ⊎ (fst u ≡ fst v)
Data\Nat\Lower.agda:145:#→≢ : ∀{P : ℕ → Type ℓ} (u v : Σ ℕ P) → u # v → ¬ u ≡ v
Data\Nat\Lower.agda:148:isProp# : ∀{P : ℕ → Type ℓ} (u v : Σ ℕ P) → isProp (u # v)
Data\Nat\Lower.agda:151:isProp#Depᵣ : ∀{P : ℕ → Type ℓ} (v : Σ ℕ P) → isPropDep (λ u → u # v)
Data\Nat\Mod.agda:22:record QuotRemℕ (m n : ℕ) : Type where
Data\Nat\Omniscience.agda:11:  renaming (Bool to 𝟚; Bool→Type to ⟨_⟩)
Data\Nat\Omniscience.agda:21:  A : Type ℓ
Data\Nat\Omniscience.agda:22:  F : A → Type ℓ
Data\Nat\Order.agda:28:_≤_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:31:_<_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:34:_≥_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:37:_>_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:40:data Trichotomy (m n : ℕ) : Type₀ where
Data\Nat\Order.agda:306:  ≤ᵇ-∸-+-cancel : ∀ m n → Bool→Type (m ≤ᵇ n) → (n ∸ m) + m ≡ n
Data\Nat\Order.agda:311:<ᵇ→< : Bool→Type (m <ᵇ n) → m < n
Data\Nat\Order.agda:318:<→<ᵇ : m < n → Bool→Type (m <ᵇ n)
Data\Nat\Order.agda:323:≤ᵇ→≤ : Bool→Type (m ≤ᵇ n) → m ≤ n
Data\Nat\Order.agda:327:≤→≤ᵇ : m ≤ n → Bool→Type (m ≤ᵇ n)
Data\Nat\Order.agda:353:  ∸→>ᵇ : ∀ m n → caseNat ⊥.⊥ Unit (m ∸ n) → Bool→Type (m >ᵇ n)
Data\Nat\Order.agda:392:≤CaseInduction : {P : ℕ → ℕ → Type ℓ} {n m : ℕ}
Data\Nat\Order.agda:456:    (P : ℕ → Type₀)
Data\Nat\Order.agda:569:≤-solver-type : (m n : ℕ) → Trichotomy m n → Type
Data\Nat\Order.agda:570:≤-solver-type m n (lt p) = m ≤ n
Data\Nat\Order.agda:571:≤-solver-type m n (eq p) = m ≤ n
Data\Nat\Order.agda:572:≤-solver-type m n (gt p) = n < m
Data\Nat\Order.agda:574:≤-solver-case : (m n : ℕ) → (p : Trichotomy m n) → ≤-solver-type m n p
Data\Nat\Order.agda:579:≤-solver : (m n : ℕ) → ≤-solver-type m n (m ≟ n)
Data\Nat\Order.agda:585:data _≤'_ : ℕ → ℕ → Type where
Data\Nat\Order.agda:589:_<'_ : ℕ → ℕ → Type
Data\Nat\Order.agda:635:isStrictlyIncreasing : (f : ℕ → ℕ) → Type
Data\Nat\Order.agda:638:isIncreasing : (f : ℕ → ℕ) → Type
Data\Nat\Properties.agda:79:codeℕ : (n m : ℕ) → Type ℓ-zero
Data\Nat\Properties.agda:149:≡ᵇ→≡ : Bool→Type (m ≡ᵇ n) → m ≡ n
Data\Nat\Properties.agda:153:≡→≡ᵇ : m ≡ n → Bool→Type (m ≡ᵇ n)
Data\Nat\Properties.agda:161:... | false , p = no  (subst Bool→Type p ∘ ≡→≡ᵇ)
Data\Nat\Properties.agda:162:... | true  , p = yes (≡ᵇ→≡ (subst Bool→Type (sym p) tt))
Data\Nat\Properties.agda:383:compSubstℕ : ∀ {ℓ} {A : ℕ → Type ℓ} {n m l : ℕ}
Data\Nat\Bijections\IncreasingFunction.agda:105:  partition : Type
Data\Nat\Order\Inductive.agda:21:_<ᵗ_ : (n m : ℕ) → Type
Data\Nat\Order\Inductive.agda:22:n <ᵗ m = Bool→Type (n <ᵇ m)
Data\Nat\Order\Inductive.agda:24:_≤ᵗ_ : (n m : ℕ) → Type
Data\Nat\Order\Inductive.agda:27:_>ᵗ_ : (n m : ℕ) → Type
Data\Nat\Order\Inductive.agda:30:_≥ᵗ_ : (n m : ℕ) → Type
Data\Nat\Order\Inductive.agda:46:  -- _<ᵗ_ : (n m : ℕ) → Type
Data\Nat\Order\Inductive.agda:51:data Trichotomyᵗ (m n : ℕ) : Type₀ where
Data\Nat\Order\Recursive.agda:22:_≤_ : ℕ → ℕ → Type₀
Data\Nat\Order\Recursive.agda:27:_<_ : ℕ → ℕ → Type₀
Data\Nat\Order\Recursive.agda:35:data Trichotomy (m n : ℕ) : Type₀ where
Data\Nat\Order\Recursive.agda:43:    R : Type ℓ
Data\Nat\Order\Recursive.agda:44:    P : ℕ → Type ℓ
Data\Nat\Order\Recursive.agda:144:  Least : ∀{ℓ} → (ℕ → Type ℓ) → (ℕ → Type ℓ)
Data\NatMinusOne\Base.agda:8:record ℕ₋₁ : Type₀ where
Data\NatPlusOne\Base.agda:8:record ℕ₊₁ : Type₀ where
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:12:data ℕ₊₁ : Type where
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:18:module Elim {ℓ'} {B : ℕ₊₁ → Type ℓ'}
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:33:module ElimProp {ℓ'} {B : ℕ₊₁ → Type ℓ'} (BProp : {n : ℕ₊₁} → isProp (B n))
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:43:module Rec {ℓ'} {B : Type ℓ'} (BType : isSet B)
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:48:  f = Elim.f one* (λ m n → m +₁* n) assoc* λ _ → BType
Data\NatPlusOne\MoreNats\AssocNat\Base.agda:51:  constraintNumber : ℕ → Type
Data\Ordinal\Base.agda:35:Ord : ∀ {ℓ} → Type _
Data\Ordinal\Properties.agda:36:propOrd : (P : Type ℓ) → isProp P → Ord {ℓ}
Data\Ordinal\Properties.agda:40:    _<_ : P → P → Type ℓ
Data\Prod\Base.agda:6:-- Here we define an inductive version of the product type, see below
Data\Prod\Base.agda:10:-- sigma types, which is the generally preferred one.
Data\Prod\Base.agda:15:-- implementation is done using a datatype which computes positively.
Data\Prod\Base.agda:22:data _×_ (A : Type ℓ) (B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
Data\Prod\Base.agda:27:proj₁ : {A : Type ℓ} {B : Type ℓ'} → A × B → A
Data\Prod\Base.agda:30:proj₂ : {A : Type ℓ} {B : Type ℓ'} → A × B → B
Data\Prod\Base.agda:36:    A    : Type ℓ
Data\Prod\Base.agda:37:    B C  : A → Type ℓ
Data\Prod\Base.agda:42:map : {B : Type ℓ} {D : B → Type ℓ'}
Data\Prod\Base.agda:47:×-η : {A : Type ℓ} {B : Type ℓ'} (x : A × B) → x ≡ ((proj₁ x) , (proj₂ x))
Data\Prod\Base.agda:51:-- The product type with one parameter in Typeω
Data\Prod\Base.agda:53:record _×ω_ {a} (A : Type a) (B : Typeω) : Typeω where
Data\Prod\Properties.agda:16:    A : Type ℓ
Data\Prod\Properties.agda:17:    B : Type ℓ'
Data\Prod\Properties.agda:30:isEquivSwap : (A : Type ℓ) (B : Type ℓ') → isEquiv (λ (xy : A × B) → swap xy)
Data\Prod\Properties.agda:33:swapEquiv : (A : Type ℓ) (B : Type ℓ') → A × B ≃ B × A
Data\Prod\Properties.agda:36:swapEq : (A : Type ℓ) (B : Type ℓ') → A × B ≡ B × A
Data\Prod\Properties.agda:42:  -- As × is defined as a datatype this computes as expected
Data\Prod\Properties.agda:69:×-≃ : ∀ {ℓ₁ ℓ₂ ℓ₃ ℓ₄} {A : Type ℓ₁} {B : Type ℓ₂} {C : Type ℓ₃} {D : Type ℓ₄}
Data\Prod\Properties.agda:88:prodIso : ∀ {ℓ ℓ' ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
Data\Prod\Properties.agda:97:toProdIso : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Data\Prod\Properties.agda:104:curryIso : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Data\Prod\Properties.agda:111:fiber-map-× : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Data\Queue\1List.agda:18:module 1List {ℓ} (A : Type ℓ) (Aset : isSet A) where
Data\Queue\Finite.agda:23:module _ (A : Type ℓ) (Aset : isSet A) where
Data\Queue\Truncated2List.agda:19:module Truncated2List {ℓ} (A : Type ℓ) (Aset : isSet A) where
Data\Queue\Truncated2List.agda:22: data Q : Type ℓ where
Data\Queue\Untruncated2List.agda:19:module Untruncated2List {ℓ} (A : Type ℓ) (Aset : isSet A) where
Data\Queue\Untruncated2List.agda:23: data Q : Type ℓ where
Data\Queue\Untruncated2List.agda:161: -- In particular, the untruncated queue type is a set
Data\Queue\Untruncated2ListInvariant.agda:12:module Untruncated2ListInvariant {ℓ} (A : Type ℓ) where
Data\Queue\Untruncated2ListInvariant.agda:15: Inv : List A → List A → Type ℓ
Data\Queue\Untruncated2ListInvariant.agda:38: data Q : Type ℓ where
Data\Quiver\Base.agda:1:-- A Quiver is an endo-span of types.
Data\Quiver\Base.agda:50:record QuiverOver (ob : Type ℓg) ℓg' : Type (ℓ-suc (ℓ-max ℓg ℓg')) where
Data\Quiver\Base.agda:52:    mor : Type ℓg'
Data\Quiver\Base.agda:57:Quiver : ∀ ℓg ℓg' → Type _
Data\Quiver\Base.agda:58:Quiver ℓg ℓg' = Σ[ ob ∈ Type ℓg ] QuiverOver ob ℓg'
Data\Quiver\Base.agda:62:       : Type (ℓ-max (ℓ-max ℓq ℓq') (ℓ-max ℓg ℓg')) where
Data\Quiver\Base.agda:106:  record HetSection : Type (ℓ-max (ℓ-max ℓq ℓq')
Data\Quiver\Reachability.agda:44:  data Walk (end : ⟨ ob ⟩) : ⟨ ob ⟩ → ℕ → Type (ℓ-max ℓ ℓ') where
Data\Quiver\Reachability.agda:48:  Walk' : (end start : ⟨ ob ⟩) → Type (ℓ-max ℓ ℓ')
Data\Quiver\Reachability.agda:147:  hasUniqueVertices : ∀ {end start : ⟨ ob ⟩} → Walk end start n → Type ℓ
Data\Quiver\Reachability.agda:158:  uniqueVerticesWalk : ∀ (end start : ⟨ ob ⟩) → Type (ℓ-max ℓ ℓ')
Data\Quiver\Reachability.agda:230:  UniqueWalk : ∀ (end start : ⟨ ob ⟩) → Type _
Data\Quiver\Reachability.agda:288:  Reachable PathReachable : ⟨ ob ⟩ → ⟨ ob ⟩ → Type _
Data\Rationals\Base.agda:25:_∼_ : ℤ × ℕ₊₁ → ℤ × ℕ₊₁ → Type₀
Data\Rationals\Base.agda:28:ℚ : Type₀
Data\Rationals\Order.agda:146:_≤_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:149:_<_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:152:_≥_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:155:_>_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:158:_#_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:161:data Trichotomy (m n : ℚ) : Type₀ where
Data\Rationals\Properties.agda:422:  where lem : ∀ {ℓ} {A : Type ℓ} (_·_ : A → A → A)
Data\Rationals\MoreRationals\HITQ\Base.agda:15:-- ℚ as a higher inductive type
Data\Rationals\MoreRationals\HITQ\Base.agda:17:data ℚ : Type₀ where
Data\Rationals\MoreRationals\HITQ\Base.agda:25:module Elim {ℓ} {B : ℚ → Type ℓ}
Data\Rationals\MoreRationals\HITQ\Base.agda:38:module ElimProp {ℓ} {B : ℚ → Type ℓ} {BProp : {q : ℚ} → isProp (B q)}
Data\Rationals\MoreRationals\HITQ\Base.agda:48:module Rec {ℓ} {B : Type ℓ} {BType : isSet B}
Data\Rationals\MoreRationals\HITQ\Base.agda:54:  f = Elim.f con* path* λ _ → BType
Data\Rationals\MoreRationals\HITQ\Base.agda:56:module Rec2 {ℓ} {B : Type ℓ} {BType : isSet B}
Data\Rationals\MoreRationals\HITQ\Base.agda:69:  f = Rec.f {BType = λ x y p q i j w → BType (x w) (y w) (λ k → p k w) (λ k → q k w) i j}
Data\Rationals\MoreRationals\HITQ\Base.agda:70:    (λ u a p → Rec.f {BType = BType} (con* u a p) (path*₂ u a {p}))
Data\Rationals\MoreRationals\HITQ\Base.agda:71:    λ u a v b eq → funExt (ElimProp.f {BProp = BType _ _}
Data\Rationals\MoreRationals\QuoQ\Base.agda:28:_∼_ : ℤ × ℕ₊₁ → ℤ × ℕ₊₁ → Type₀
Data\Rationals\MoreRationals\QuoQ\Base.agda:31:ℚ : Type₀
Data\Rationals\MoreRationals\QuoQ\Properties.agda:188:  where lem : ∀ {ℓ} {A : Type ℓ} (_·_ : A → A → A)
Data\Rationals\MoreRationals\SigmaQ\Base.agda:18:ℚ : Type₀
Data\Sequence\Base.agda:13:record Sequence (ℓ : Level) : Type (ℓ-suc ℓ) where
Data\Sequence\Base.agda:16:    obj : ℕ → Type ℓ
Data\Sequence\Base.agda:19:record SequenceMap (C : Sequence ℓ) (D : Sequence ℓ') : Type (ℓ-max ℓ ℓ') where
Data\Sequence\Base.agda:26:converges : ∀ {ℓ} → Sequence ℓ → (n : ℕ) → Type ℓ
Data\Sequence\Base.agda:29:finiteSequence : (ℓ : Level) (m : ℕ) → Type (ℓ-suc ℓ)
Data\Sequence\Base.agda:37:SequenceIso : (A : Sequence ℓ) (B : Sequence ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sequence\Base.agda:45:SequenceEquiv : (A : Sequence ℓ) (B : Sequence ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sequence\Properties.agda:163:  (P : (B : Sequence ℓ) → SequenceEquiv A B → Type ℓ')
Data\Sequence\Properties.agda:168:  P' : Σ[ B ∈ Sequence ℓ ] SequenceEquiv A B → Type _
Data\Sequence\Properties.agda:175:  {P : (B : Sequence ℓ) → SequenceEquiv A B → Type ℓ'}
Data\Sequence\Properties.agda:181:  (P : (B : Sequence ℓ) → SequenceEquiv A B → Type ℓ')
Data\Sequence\Properties.agda:190:  P' : Σ[ B ∈ Sequence ℓ ] SequenceEquiv A B → Type _
Data\Sigma\Base.agda:1:{- Basic definitions using Σ-types
Data\Sigma\Base.agda:3:Σ-types are defined in Core/Primitives as they are needed for Glue types.
Data\Sigma\Base.agda:7:- Non-dependent pair types: A × B
Data\Sigma\Base.agda:20:-- Non-dependent pair types
Data\Sigma\Base.agda:22:_×_ : ∀ {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sigma\Base.agda:30:∃ : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sigma\Base.agda:35:∃-syntax : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sigma\Base.agda:43:∃! : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sigma\Base.agda:48:∃!-syntax : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Data\Sigma\Properties.agda:3:Basic properties about Σ-types
Data\Sigma\Properties.agda:6:- Characterization of equality in Σ-types using dependent paths ([ΣPath{Iso,≃,≡}PathΣ], [Σ≡Prop])
Data\Sigma\Properties.agda:7:- Proof that discrete types are closed under Σ ([discreteΣ])
Data\Sigma\Properties.agda:11:- Characterization of equality in Σ-types using transport ([ΣPathTransport{≃,≡}PathΣ])
Data\Sigma\Properties.agda:40:    A A' : Type ℓ
Data\Sigma\Properties.agda:41:    B B' : (a : A) → Type ℓ
Data\Sigma\Properties.agda:42:    C : (a : A) (b : B a) → Type ℓ
Data\Sigma\Properties.agda:44:map-fst : {B : Type ℓ} → (f : A → A') → A × B → A' × B
Data\Sigma\Properties.agda:50:map-× : {B : Type ℓ} {B' : Type ℓ'} → (A → A') → (B → B') → A × B → A' × B'
Data\Sigma\Properties.agda:53:≡-× : {A : Type ℓ} {B : Type ℓ'} {x y : A × B} → fst x ≡ fst y → snd x ≡ snd y → x ≡ y
Data\Sigma\Properties.agda:59:module _ {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ'}
Data\Sigma\Properties.agda:103:module _ {A : I → Type ℓ} {B : (i : I) → (a : A i) → Type ℓ'}
Data\Sigma\Properties.agda:120:-- Σ of discrete types
Data\Sigma\Properties.agda:158:module _ {A : Type ℓ} {A' : Type ℓ'} where
Data\Sigma\Properties.agda:167:module _ {A : Type ℓ} {B : A → Type ℓ'} {C : ∀ a → B a → Type ℓ''} where
Data\Sigma\Properties.agda:184:module _ {A : Type ℓ} {B : A → Type ℓ'} {B' : ∀ a → Type ℓ''} where
Data\Sigma\Properties.agda:228:    PB : ∀ {x y} → x ≡ y → B x → B y → Type _
Data\Sigma\Properties.agda:282:Σ-cong' : (p : A ≡ A') → PathP (λ i → p i → Type ℓ') B B' → Σ A B ≡ Σ A' B'
Data\Sigma\Properties.agda:283:Σ-cong' p p' = cong₂ (λ (A : Type _) (B : A → Type _) → Σ A B) p p'
Data\Sigma\Properties.agda:295:-- Alternative version for path in Σ-types, as in the HoTT book
Data\Sigma\Properties.agda:297:ΣPathTransport : (a b : Σ A B) → Type _
Data\Sigma\Properties.agda:330:module _ (A : Unit → Type ℓ) where
Data\Sigma\Properties.agda:371:ΣPathPProp : ∀ {ℓ ℓ'} {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ'}
Data\Sigma\Properties.agda:386:≃-× : ∀ {ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''} → A ≃ C → B ≃ D → A × B ≃ C
× D
Data\Sigma\Properties.agda:405:prodIso : ∀ {ℓ ℓ' ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
Data\Sigma\Properties.agda:414:prodEquivToIso : ∀ {ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
Data\Sigma\Properties.agda:422:toProdIso : {B C : A → Type ℓ}
Data\Sigma\Properties.agda:429:module _ {A : Type ℓ} {B : A → Type ℓ'} {C : ∀ a → B a → Type ℓ''} where
Data\Sigma\Properties.agda:438:-- Sigma type with empty base
Data\Sigma\Properties.agda:440:module _ (A : ⊥ → Type ℓ) where
Data\Sigma\Properties.agda:450:module _ {ℓ : Level} (A : ⊥* {ℓ} → Type ℓ) where
Data\Sigma\Properties.agda:460:  (A : Type ℓ)
Data\Sigma\Properties.agda:461:  (B : A → Type ℓ') where
Data\Sum\Base.agda:10:    A B C D : Type ℓ
Data\Sum\Base.agda:12:data _⊎_ (A : Type ℓ)(B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
Data\Sum\Base.agda:16:rec : {C : Type ℓ} → (A → C) → (B → C) → A ⊎ B → C
Data\Sum\Base.agda:20:elim : {C : A ⊎ B → Type ℓ} →  ((a : A) → C (inl a)) → ((b : B) → C (inr b))
Data\Sum\Base.agda:29:_⊎?_ : {P Q : Type ℓ} → Dec P → Dec Q → Dec (P ⊎ Q)
Data\Sum\Properties.agda:24:    A : Type ℓa
Data\Sum\Properties.agda:25:    B : Type ℓb
Data\Sum\Properties.agda:26:    C : Type ℓc
Data\Sum\Properties.agda:27:    D : Type ℓd
Data\Sum\Properties.agda:28:    E : A ⊎ B → Type ℓe
Data\Sum\Properties.agda:31:-- Path space of sum type
Data\Sum\Properties.agda:32:module ⊎Path {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} where
Data\Sum\Properties.agda:34:  Cover : A ⊎ B → A ⊎ B → Type (ℓ-max ℓ ℓ')
Data\Sum\Properties.agda:302:  ⊥-fib : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → A ⊎ B → Type
Data\Sum\Properties.agda:306:  module _ {A : Type ℓa} {B : Type ℓb} {C : Type ℓc} {D : Type ℓd}
Data\Sum\Properties.agda:310:    T : (b : B) → Type _
Data\Sum\Properties.agda:313:    T-elim : ∀ {ℓ} (b : B) {P : (x : T b) → Type ℓ}
Data\SumFin\Base.agda:18:Fin : ℕ → Type₀
Data\SumFin\Base.agda:26:  : (P : ∀ {k} → Fin k → Type ℓ)
Data\SumFin\Properties.agda:66:enumElim : (P : Fin k → Type ℓ) → ((n : ℕ)(p : n <ᵗ k) → P (enum _ p)) → (i : Fin k) → P i
Data\SumFin\Properties.agda:69:-- Closure properties of SumFin under type constructors
Data\SumFin\Properties.agda:106:SumFin∥∥DecProp : (n : ℕ) → ∥ Fin n ∥₁ ≃ Bool→Type (ℕ→Bool n)
Data\SumFin\Properties.agda:112:SumFin¬ : (n : ℕ) → (¬ Fin n) ≃ Bool→Type (isZero n)
Data\SumFin\Properties.agda:135:  ⋆ Σ-cong-equiv (UnitToType≃ Bool ⋆ invEquiv SumFin2≃Bool) (λ _ → SumFinℙ≃ n)
Data\SumFin\Properties.agda:148:SumFinDec⊎≃ : (n : ℕ)(t : Bool) → (Bool→Type t ⊎ Fin n) ≃ (Fin (Bool→ℕ t + n))
Data\SumFin\Properties.agda:152:SumFinSub≃ : (n : ℕ)(f : Fin n → Bool) → Σ _ (Bool→Type ∘ f) ≃ Fin (trueCount f)
Data\SumFin\Properties.agda:156:  ⋆ ⊎-equiv (ΣUnit (Bool→Type ∘ f ∘ inl)) (SumFinSub≃ n (f ∘ inr))
Data\SumFin\Properties.agda:169:SumFin∃→ : (n : ℕ)(f : Fin n → Bool) → Σ _ (Bool→Type ∘ f) → Bool→Type (trueForSome n f)
Data\SumFin\Properties.agda:172:    Bool→Type⊎' _ _
Data\SumFin\Properties.agda:173:  ∘ ⊎.map (ΣUnit (Bool→Type ∘ f ∘ inl) .fst) (SumFin∃→ n (f ∘ inr))
Data\SumFin\Properties.agda:176:SumFin∃← : (n : ℕ)(f : Fin n → Bool) → Bool→Type (trueForSome n f) → Σ _ (Bool→Type ∘ f)
Data\SumFin\Properties.agda:180:  ∘ ⊎.map (invEq (ΣUnit (Bool→Type ∘ f ∘ inl))) (SumFin∃← n (f ∘ inr))
Data\SumFin\Properties.agda:181:  ∘ Bool→Type⊎ _ _
Data\SumFin\Properties.agda:183:SumFin∃≃ : (n : ℕ)(f : Fin n → Bool) → ∥ Σ (Fin n) (Bool→Type ∘ f) ∥₁ ≃ Bool→Type (trueForSome n f)
Data\SumFin\Properties.agda:185:  propBiimpl→Equiv isPropPropTrunc isPropBool→Type
Data\SumFin\Properties.agda:186:    (Prop.rec isPropBool→Type (SumFin∃→ n f))
Data\SumFin\Properties.agda:189:SumFin∀≃ : (n : ℕ)(f : Fin n → Bool) → ((x : Fin n) → Bool→Type (f x)) ≃ Bool→Type (trueForAll n f)
Data\SumFin\Properties.agda:193:  ⋆ Σ-cong-equiv (ΠUnit (Bool→Type ∘ f ∘ inl)) (λ _ → SumFin∀≃ n (f ∘ inr))
Data\SumFin\Properties.agda:194:  ⋆ Bool→Type×≃ _ _
Data\SumFin\Properties.agda:209:SumFin≡≃ : (n : ℕ) → (a b : Fin n) → (a ≡ b) ≃ Bool→Type (SumFin≡ n a b)
Data\SumFin\Properties.agda:299:  (P : Fin n → Type ℓ) →
Data\Unit\Base.agda:10:Unit* : ∀ {ℓ} → Type ℓ
Data\Unit\Base.agda:16:Unit*∙ : ∀ {ℓ} → Σ[ X ∈ Type ℓ ] X
Data\Unit\Base.agda:22:data lockUnit {ℓ} : Type ℓ where
Data\Unit\Properties.agda:23:terminal : (A : Type ℓ) → A → Unit
Data\Unit\Properties.agda:38:module _ (A : Type ℓ) where
Data\Unit\Properties.agda:39:  UnitToType≃ : (Unit → A) ≃ A
Data\Unit\Properties.agda:40:  unquoteDef UnitToType≃ = defStrictEquiv UnitToType≃ (λ f → f _) const
Data\Unit\Properties.agda:42:UnitToTypePath : ∀ {ℓ} (A : Type ℓ) → (Unit → A) ≡ A
Data\Unit\Properties.agda:43:UnitToTypePath A = ua (UnitToType≃ A)
Data\Unit\Properties.agda:45:module _ (A : Unit → Type ℓ) where
Data\Unit\Properties.agda:58:module _ (A : Unit* {ℓ} → Type ℓ') where
Data\Unit\Properties.agda:71:fiberUnitIso : {A : Type ℓ} → Iso (fiber (λ (a : A) → tt) tt) A
Data\Unit\Properties.agda:77:isContr→Iso2 : {A : Type ℓ} {B : Type ℓ'} → isContr A → Iso (A → B) B
Data\Unit\Properties.agda:86:fibId : (A : Type ℓ) → (fiber (λ (x : A) → tt) tt) ≡ A
Data\Unit\Properties.agda:91:isContr→≃Unit : {A : Type ℓ} → isContr A → A ≃ Unit
Data\Unit\Properties.agda:94:isContr→≡Unit : {A : Type₀} → isContr A → A ≡ Unit
Data\Unit\Properties.agda:115:isContr→≃Unit* : {A : Type ℓ} → isContr A → A ≃ Unit* {ℓ'}
Data\Unit\Properties.agda:118:isContr→≡Unit* : {A : Type ℓ} → isContr A → A ≡ Unit*
Data\Unit\Properties.agda:122:JPointedProp : ∀ {ℓ ℓ'} {B : (A : Type ℓ') (a : A) (isPr : isProp A) → Type ℓ}
Data\Unit\Properties.agda:124:  → (A : Type ℓ') (a : A) (isPr : isProp A) → B A a isPr
Data\Unit\Properties.agda:128:  A* : TypeOfHLevel ℓ' 1
Data\Vec\Base.agda:13:    A : Type ℓ
Data\Vec\Base.agda:14:    B : Type ℓ'
Data\Vec\Base.agda:18:data Vec (A : Type ℓ) : ℕ → Type ℓ where
Data\Vec\Base.agda:34:map : ∀ {A : Type ℓ} {B : Type ℓ'} {n} → (A → B) → Vec A n → Vec B n
Data\Vec\Base.agda:38:replicate : ∀ {n} {A : Type ℓ} → A → Vec A n
Data\Vec\Base.agda:42:zipWith : ∀ {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {n : ℕ}
Data\Vec\Base.agda:63:lookup : ∀ {n} {A : Type ℓ} → Fin n → Vec A n → A
Data\Vec\DepVec.agda:21:data depVec (G : (n : ℕ) → Type ℓ) : ℕ → Type ℓ where
Data\Vec\DepVec.agda:26:module depVecPath (G : (n : ℕ) → Type ℓ)
Data\Vec\DepVec.agda:29:  code : {n : ℕ} → (v v' : depVec G n) → Type ℓ
Data\Vec\NAry.agda:14:    A : Type ℓ
Data\Vec\NAry.agda:15:    B : Type ℓ'
Data\Vec\NAry.agda:21:nAryOp : (n : ℕ) → Type ℓ → Type ℓ' → Type (nAryLevel ℓ ℓ' n)
Data\Vec\OperationsNat.agda:23:genδℕ-Vec : {A : Type ℓ} → (m k : ℕ) → (a b : A) → Vec A m
Data\Vec\OperationsNat.agda:120:rep-concat : (k l : ℕ) → {B : Type ℓ} → (b : B) →
Data\Vec\Properties.agda:23:    A : Type ℓ
Data\Vec\Properties.agda:68:module VecPath {A : Type ℓ}
Data\Vec\Properties.agda:71:  code : {n : ℕ} → (v v' : Vec A n) → Type ℓ
Data\W\Indexed.agda:22:module Types {X : Type ℓX} (S : X → Type ℓS) (P : ∀ x → S x → Type ℓP) (inX : ∀ x (s : S x) → P x s → X) where
Data\W\Indexed.agda:23:  data IW (x : X) : Type (ℓ-max ℓX (ℓ-max ℓS ℓP)) where
Data\W\Indexed.agda:26:  Subtree : ∀ {x} → (s : S x) → Type (ℓ-max (ℓ-max ℓX ℓS) ℓP)
Data\W\Indexed.agda:29:  RepIW : (x : X) → Type (ℓ-max (ℓ-max ℓX ℓS) ℓP)
Data\W\Indexed.agda:32:open Types public
Data\W\Indexed.agda:34:module _ {X : Type ℓX} {S : X → Type ℓS} {P : ∀ x → S x → Type ℓP} {inX : ∀ x (s : S x) → P x s → X} where
Data\W\Indexed.agda:64:module IWPathTypes {X : Type ℓX} (S : X → Type ℓS) (P : ∀ x → S x → Type ℓP) (inX : ∀ x (s : S x) → P x s → X)
where
Data\W\Indexed.agda:66:  --somewhat inspired by https://github.com/jashug/IWTypes , but different.
Data\W\Indexed.agda:68:  IndexCover : Type (ℓ-max (ℓ-max ℓX ℓS) ℓP)
Data\W\Indexed.agda:71:  ShapeCover : IndexCover → Type ℓS
Data\W\Indexed.agda:74:  ArityCover : ∀ xww' → ShapeCover xww' → Type ℓP
Data\W\Indexed.agda:80:  Cover : ∀ {x : X} → (w w' : IW S P inX x) → Type (ℓ-max (ℓ-max ℓX ℓS) ℓP)
Data\W\Indexed.agda:83:module IWPath {X : Type ℓX} {S : X → Type ℓS} {P : ∀ x → S x → Type ℓP} {inX : ∀ x (s : S x) → P x s → X} where
Data\W\Indexed.agda:84:  open IWPathTypes S P inX
Data\W\Indexed.agda:138:open IWPathTypes
Data\W\Indexed.agda:141:isOfHLevelSuc-IW : {X : Type ℓX} {S : X → Type ℓS} {P : ∀ x → S x → Type ℓP} {inX : ∀ x (s : S x) → P x s → X} →
Data\W\W.agda:10:data W (S : Type ℓ) (P : S → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Data\W\W.agda:13:WInd : (S : Type ℓ) (P : S → Type ℓ') (M : W S P → Type ℓ'') →
Displayed\Auto.agda:37:  data UARelDesc : ∀ {ℓA ℓ≅A} {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) → Typeω where
Displayed\Auto.agda:39:    generic : ∀ {ℓA} {A : Type ℓA} → UARelDesc (𝒮-generic A)
Displayed\Auto.agda:46:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} (dA : UARelDesc 𝒮-A)
Displayed\Auto.agda:47:      {B : Type ℓB} {𝒮-B : UARel B ℓ≅B} (dB : UARelDesc 𝒮-B)
Displayed\Auto.agda:51:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} (dA : UARelDesc 𝒮-A)
Displayed\Auto.agda:52:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B} (dB : DUARelDesc 𝒮-A 𝒮ᴰ-B)
Displayed\Auto.agda:55:    param : ∀ {ℓA ℓB ℓ≅B} (A : Type ℓA)
Displayed\Auto.agda:56:      {B : Type ℓB} {𝒮-B : UARel B ℓ≅B} (dB : UARelDesc 𝒮-B)
Displayed\Auto.agda:60:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} (dA : UARelDesc 𝒮-A)
Displayed\Auto.agda:61:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B} (dB : DUARelDesc 𝒮-A 𝒮ᴰ-B)
Displayed\Auto.agda:68:    {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:69:    {C : Type ℓC} {𝒮-C : UARel C ℓ≅C}
Displayed\Auto.agda:71:    → Typeω
Displayed\Auto.agda:74:    id : ∀ {ℓA ℓ≅A} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:78:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:79:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B}
Displayed\Auto.agda:80:      {C : Type ℓC} {𝒮-C : UARel C ℓ≅C}
Displayed\Auto.agda:86:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:87:      {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Auto.agda:88:      {C : Type ℓC} {𝒮-C : UARel C ℓ≅C}
Displayed\Auto.agda:94:      {A : Type ℓA}
Displayed\Auto.agda:95:      {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Auto.agda:96:      {C : Type ℓC} {𝒮-C : UARel C ℓ≅C}
Displayed\Auto.agda:102:    {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Auto.agda:103:    {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B) → Typeω
Displayed\Auto.agda:106:    generic : ∀ {ℓA ℓ≅A ℓB} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : A → Type ℓB}
Displayed\Auto.agda:110:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : Type ℓB}
Displayed\Auto.agda:115:    el : ∀ {ℓA ℓ≅A ℓU} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:121:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:122:      {B : A → Type ℓB} {𝒮ˢ-B : SubstRel 𝒮-A B} (dB : SubstRelDesc 𝒮-A 𝒮ˢ-B)
Displayed\Auto.agda:123:      {C : A → Type ℓC} {𝒮ˢ-C : SubstRel 𝒮-A C} (dC : SubstRelDesc 𝒮-A 𝒮ˢ-C)
Displayed\Auto.agda:127:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:128:      {B : A → Type ℓB} {𝒮ˢ-B : SubstRel 𝒮-A B} (dB : SubstRelDesc 𝒮-A 𝒮ˢ-B)
Displayed\Auto.agda:129:      {C : Σ A B → Type ℓC} {𝒮ˢ-C : SubstRel (∫ˢ 𝒮ˢ-B) C} (dC : SubstRelDesc (∫ˢ 𝒮ˢ-B) 𝒮ˢ-C)
Displayed\Auto.agda:133:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:134:      {B : A → Type ℓB} {𝒮ˢ-B : SubstRel 𝒮-A B} (dB : SubstRelDesc 𝒮-A 𝒮ˢ-B)
Displayed\Auto.agda:135:      {C : Σ A B → Type ℓC} {𝒮ˢ-C : SubstRel (∫ˢ 𝒮ˢ-B) C} (dC : SubstRelDesc (∫ˢ 𝒮ˢ-B) 𝒮ˢ-C)
Displayed\Auto.agda:139:    {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Auto.agda:140:    {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B) → Typeω
Displayed\Auto.agda:143:    generic : ∀ {ℓA ℓ≅A ℓB} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : A → Type ℓB}
Displayed\Auto.agda:147:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:148:      {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Auto.agda:152:    el : ∀ {ℓA ℓ≅A ℓU} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:158:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:159:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B} (dB : DUARelDesc 𝒮-A 𝒮ᴰ-B)
Displayed\Auto.agda:160:      {C : A → Type ℓC} {𝒮ᴰ-C : DUARel 𝒮-A C ℓ≅C} (dC : DUARelDesc 𝒮-A 𝒮ᴰ-C)
Displayed\Auto.agda:164:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:165:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B} (dB : DUARelDesc 𝒮-A 𝒮ᴰ-B)
Displayed\Auto.agda:166:      {C : Σ A B → Type ℓC} {𝒮ᴰ-C : DUARel (∫ 𝒮ᴰ-B) C ℓ≅C} (dC : DUARelDesc (∫ 𝒮ᴰ-B) 𝒮ᴰ-C)
Displayed\Auto.agda:170:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:171:      {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B} (dB : DUARelDesc 𝒮-A 𝒮ᴰ-B)
Displayed\Auto.agda:172:      {C : Σ A B → Type ℓC} {𝒮ᴰ-C : DUARel (∫ 𝒮ᴰ-B) C ℓ≅C} (dC : DUARelDesc (∫ 𝒮ᴰ-B) 𝒮ᴰ-C)
Displayed\Auto.agda:176:      {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:177:      {B : A → Type ℓB} {𝒮ˢ-B : SubstRel 𝒮-A B} (dB : SubstRelDesc 𝒮-A 𝒮ˢ-B)
Displayed\Auto.agda:178:      {C : Σ A B → Type ℓC} {𝒮ᴰ-C : DUARel (∫ˢ 𝒮ˢ-B) C ℓ≅C} (dC : DUARelDesc (∫ˢ 𝒮ˢ-B) 𝒮ᴰ-C)
Displayed\Auto.agda:182:  getUARel : ∀ {ℓA ℓ≅A} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:187:    {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Auto.agda:188:    {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B}
Displayed\Auto.agda:198:  autoUARelDesc zero hole = R.typeError [ R.strErr "Out of fuel" ]
Displayed\Auto.agda:231:  autoUARelReindex zero hole = R.typeError [ R.strErr "Out of fuel" ]
Displayed\Auto.agda:255:  autoSubstRelDesc zero hole = R.typeError [ R.strErr "Out of fuel" ]
Displayed\Auto.agda:285:  autoDUARelDesc zero hole = R.typeError [ R.strErr "Out of fuel" ]
Displayed\Auto.agda:325:  autoUARel : ∀ {ℓA} (A : Type ℓA) → ℕ → R.Term → R.TC Unit
Displayed\Auto.agda:336:  autoDUARel : ∀ {ℓA ℓ≅A ℓB} {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (B : A → Type ℓB)
Displayed\Auto.agda:350:  autoUARel : ∀ {ℓA} (A : Type ℓA) → R.Term → R.TC Unit
Displayed\Auto.agda:353:  autoDUARel : ∀ {ℓA ℓ≅A ℓB} {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (B : A → Type ℓB)
Displayed\Auto.agda:358:  module Example (A : Type) (a₀ : A) where
Displayed\Auto.agda:360:    example0 : DUARel (autoUARel Type) (λ X → X → A × X) ℓ-zero
Displayed\Auto.agda:363:    example0' : {X Y : Type} (e : X ≃ Y)
Displayed\Auto.agda:369:    -- An example where a DUARel is parameterized over a pair of types
Displayed\Auto.agda:371:    example1 : DUARel (autoUARel (Type × Type)) (λ (X , Z) → X → Z) ℓ-zero
Displayed\Auto.agda:374:    example1' : {X Y : Type} (e : X ≃ Y) {Z W : Type} (h : Z ≃ W)
Displayed\Auto.agda:380:    -- An example where a DUARel is parameterized over a family of types
Displayed\Auto.agda:382:    example2 : DUARel (autoUARel (A → Type)) (λ B → B a₀) ℓ-zero
Displayed\Auto.agda:385:    example2' : {B C : A → Type} (e : (a : A) → B a ≃ C a)
Displayed\Base.agda:7:    “Higher Groups via Displayed Univalent Reflexive Graphs in Cubical Type Theory”
Displayed\Base.agda:28:record UARel (A : Type ℓA) (ℓ≅A : Level) : Type (ℓ-max ℓA (ℓ-suc ℓ≅A)) where
Displayed\Base.agda:32:    _≅_ : A → A → Type ℓ≅A
Displayed\Base.agda:49:make-𝒮 : {A : Type ℓA} {_≅_ : A → A → Type ℓ≅A}
Displayed\Base.agda:54:record DUARel {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Base.agda:55:              (B : A → Type ℓB) (ℓ≅B : Level) : Type (ℓ-max (ℓ-max ℓA ℓB) (ℓ-max ℓ≅A (ℓ-suc ℓ≅B))) where
Displayed\Base.agda:61:    _≅ᴰ⟨_⟩_ : {a a' : A} → B a → a ≅ a' → B a' → Type ℓ≅B
Displayed\Base.agda:79:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Base.agda:80:  {B : A → Type ℓB} {ℓ≅B : Level}
Displayed\Constant.agda:20:module _ {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Constant.agda:21:  {B : Type ℓB} (𝒮-B : UARel B ℓ≅B)  where
Displayed\Constant.agda:32:module _ {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (B : Type ℓB) where
Displayed\Function.agda:3:  Functions building UARels and DUARels on function types
Displayed\Function.agda:28:-- UARel on dependent function type
Displayed\Function.agda:31:module _ {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B) where
Displayed\Function.agda:43:-- Parameterize UARel by type
Displayed\Function.agda:45:_→𝒮_ : (A : Type ℓA) {B : Type ℓB} (𝒮-B : UARel B ℓ≅B) → UARel (A → B) (ℓ-max ℓA ℓ≅B)
Displayed\Function.agda:52:𝒮-app : {A : Type ℓA} {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Function.agda:58:-- DUARel on dependent function type
Displayed\Function.agda:61:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Function.agda:62:  {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Function.agda:63:  {C : (a : A) → B a → Type ℓC} (𝒮ᴰ-C : DUARel (∫ 𝒮ᴰ-B) (uncurry C) ℓ≅C)
Displayed\Function.agda:81:_→𝒮ᴰ_ : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Function.agda:82:  {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Function.agda:83:  {C : A → Type ℓC} (𝒮ᴰ-C : DUARel 𝒮-A C ℓ≅C)
Displayed\Function.agda:88:-- DUARel on dependent function type
Displayed\Function.agda:91:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Function.agda:92:  {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B)
Displayed\Function.agda:93:  {C : (a : A) → B a → Type ℓC} (𝒮ᴰ-C : DUARel (∫ˢ 𝒮ˢ-B) (uncurry C) ℓ≅C)
Displayed\Function.agda:110:-- SubstRel on a dependent function type
Displayed\Function.agda:113:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Function.agda:114:  {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B)
Displayed\Function.agda:115:  {C : Σ A B → Type ℓC} (𝒮ˢ-C : SubstRel (∫ˢ 𝒮ˢ-B) C)
Displayed\Generic.agda:19:-- UARel for an arbitrary type
Displayed\Generic.agda:21:𝒮-generic : (A : Type ℓA) → UARel A ℓA
Displayed\Generic.agda:27:𝒮ᴰ-generic : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (B : A → Type ℓB) → DUARel 𝒮-A B ℓB
Displayed\Generic.agda:33:𝒮ˢ-generic : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (B : A → Type ℓB) → SubstRel 𝒮-A B
Displayed\Morphism.agda:22:record UARelHom {A : Type ℓA} {B : Type ℓB} (𝒮-A : UARel A ℓ≅A) (𝒮-B : UARel B ℓ≅B)
Displayed\Morphism.agda:23:  : Type (ℓ-max (ℓ-max ℓA ℓ≅A) (ℓ-max ℓB ℓ≅B)) where
Displayed\Morphism.agda:34:𝒮-id : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) → UARelHom 𝒮-A 𝒮-A
Displayed\Morphism.agda:39:𝒮-∘ : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Morphism.agda:40:  {C : Type ℓC} {𝒮-C : UARel C ℓ≅C}
Displayed\Morphism.agda:49:𝒮ᴰ-reindex : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : Type ℓB} {𝒮-B : UARel B ℓ≅B} {C : B → Type ℓC}
Displayed\Morphism.agda:59:𝒮ˢ-reindex : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : Type ℓB} {𝒮-B : UARel B ℓ≅B} {C : B → Type ℓC}
Displayed\Prop.agda:28:𝒮ᴰ-prop : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) (P : A → hProp ℓP)
Displayed\Prop.agda:34:𝒮-subtype : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) {P : A → Type ℓP}
Displayed\Prop.agda:37:𝒮-subtype 𝒮-A propP .UARel._≅_ (a , _) (a' , _) = 𝒮-A .UARel._≅_ a a'
Displayed\Prop.agda:38:𝒮-subtype 𝒮-A propP .UARel.ua (a , _) (a' , _) =
Displayed\Prop.agda:41:𝒮ᴰ-subtype : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Prop.agda:42:  {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Prop.agda:43:  {P : (a : A) → B a → Type ℓP}
Displayed\Prop.agda:46:𝒮ᴰ-subtype 𝒮ᴰ-B propP .DUARel._≅ᴰ⟨_⟩_ (b , _) p (b' , _) = 𝒮ᴰ-B .DUARel._≅ᴰ⟨_⟩_ b p b'
Displayed\Prop.agda:47:𝒮ᴰ-subtype 𝒮ᴰ-B propP .DUARel.uaᴰ (b , _) p (b' , _) =
Displayed\Properties.agda:24:module _ {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) where
Displayed\Properties.agda:38:    (P : (a' : A) → (p : a ≅ a') → Type ℓ)
Displayed\Properties.agda:47:    (P : (a' : A) → (p : a ≅ a') → Type ℓ)
Displayed\Properties.agda:56:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Properties.agda:57:  {B : A → Type ℓB}
Displayed\Properties.agda:58:  (_≅ᴰ⟨_⟩_ : {a a' : A} → B a → UARel._≅_ 𝒮-A a a' → B a' → Type ℓ≅B)
Displayed\Properties.agda:94:𝒮-iso→iso : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Properties.agda:95:               {B : Type ℓB} (𝒮-B : UARel B ℓ≅B)
Displayed\Properties.agda:107:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Properties.agda:108:  {A' : Type ℓA'} {𝒮-A' : UARel A' ℓ≅A'}
Displayed\Properties.agda:110:  {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Properties.agda:111:  {B' : A' → Type ℓB'} (𝒮ᴰ-B' : DUARel 𝒮-A' B' ℓ≅B') where
Displayed\Record.agda:3:Generate univalent reflexive graph characterizations for record types from
Displayed\Record.agda:4:characterizations of the field types using reflection.
Displayed\Record.agda:41:  - from a structure `R : A → Type _` and notion of structured equivalence `_≅R⟨_⟩_`,
Displayed\Record.agda:42:    which are meant to be defined as parameterized record types,
Displayed\Record.agda:44:    the underlying structure of which will be an iterated Σ-type,
Displayed\Record.agda:48:  the user builds up the Σ-type representation of the record using the DUAFields constructors.
Displayed\Record.agda:53:  When `R`, and `_≅R⟨_⟩_` are defined by record types, we can use reflection to automatically generate proofs
Displayed\Record.agda:57:data DUAFields {ℓA ℓ≅A ℓR ℓ≅R} {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Record.agda:58:  (R : A → Type ℓR) (_≅R⟨_⟩_ : {a a' : A} → R a → UARel._≅_ 𝒮-A a a' → R a' → Type ℓ≅R)
Displayed\Record.agda:59:  : ∀ {ℓS ℓ≅S} {S : A → Type ℓS}
Displayed\Record.agda:62:    → Typeω
Displayed\Record.agda:72:  -- field's type over `𝒮-A`. Data fields that depend on previous fields of the record are not currently
Displayed\Record.agda:74:  _data[_∣_∣_] : ∀ {ℓS ℓ≅S} {S : A → Type ℓS}
Displayed\Record.agda:78:    → ∀ {ℓF ℓ≅F} {F : A → Type ℓF}
Displayed\Record.agda:87:  _prop[_∣_] : ∀ {ℓS ℓ≅S} {S : A → Type ℓS}
Displayed\Record.agda:91:    → ∀ {ℓF} {F : (a : A) → S a → Type ℓF}
Displayed\Record.agda:94:    → DUAFields 𝒮-A R _≅R⟨_⟩_ (λ r → πS r , πF r) (𝒮ᴰ-subtype 𝒮ᴰ-S propF) (λ p → πS≅ p)
Displayed\Record.agda:96:module _ {ℓA ℓ≅A} {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Record.agda:97:  {ℓR ℓ≅R} {R : A → Type ℓR} (_≅R⟨_⟩_ : {a a' : A} → R a → UARel._≅_ 𝒮-A a a' → R a' → Type ℓ≅R)
Displayed\Record.agda:98:  {ℓS ℓ≅S} {S : A → Type ℓS}
Displayed\Record.agda:126:      (R.typeError (R.strErr "Not a name: " ∷ R.termErr t ∷ []))
Displayed\Record.agda:158:  parseFields t = R.typeError (R.strErr "Malformed specification: " ∷ R.termErr t ∷ [])
Displayed\Record.agda:163:    iterated Σ-type
Displayed\Record.agda:169:  module _ {ℓA ℓ≅A} {A : Type ℓA} (𝒮-A : UARel A ℓ≅A)
Displayed\Record.agda:170:    {ℓR ℓ≅R} {R : A → Type ℓR} (≅R : {a a' : A} → R a → UARel._≅_ 𝒮-A a a' → R a' → Type ℓ≅R)
Displayed\Record.agda:171:    {ℓS ℓ≅S} {S : A → Type ℓS}
Displayed\Record.agda:184:      R.quoteTC (DUARel 𝒮-A R ℓ≅R) >>= R.checkType hole >>= λ hole →
Displayed\Record.agda:190:      R.quoteTC {A = {a a' : A} → R a → UARel._≅_ 𝒮-A a a' → R a' → Type ℓ≅R} ≅R >>= R.normalise >>= λ `≅R` →
Displayed\Record.agda:208:    record Example (A : Type) : Type where
Displayed\Record.agda:217:    record ExampleEquiv {A B : Type} (x : Example A) (e : A ≃ B) (y : Example B) : Type where
Displayed\Sigma.agda:3:  Functions building UARels and DUARels on Σ-types
Displayed\Sigma.agda:22:-- UARel on a Σ-type
Displayed\Sigma.agda:24:∫ˢ : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B)
Displayed\Sigma.agda:28:_×𝒮_ : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) {B : Type ℓB} (𝒮-B : UARel B ℓ≅B)
Displayed\Sigma.agda:34:𝒮-fst : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : A → Type ℓB} {𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B}
Displayed\Sigma.agda:40:𝒮-snd : {A : Type ℓA} {𝒮-A : UARel A ℓ≅A} {B : Type ℓB} {𝒮-B : UARel B ℓ≅B}
Displayed\Sigma.agda:46:-- Lift a DUARel to live over a Σ-type
Displayed\Sigma.agda:48:𝒮ᴰ-Lift : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) {B : A → Type ℓB} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Sigma.agda:49:  {C : A → Type ℓC} (𝒮ᴰ-C : DUARel 𝒮-A C ℓ≅C)
Displayed\Sigma.agda:53:-- DUARel on a Σ-type
Displayed\Sigma.agda:55:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Sigma.agda:56:  {B : A → Type ℓB} {ℓ≅B : Level} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Sigma.agda:57:  {C : Σ A B → Type ℓC} {ℓ≅C : Level} (𝒮ᴰ-C : DUARel (∫ 𝒮ᴰ-B) C ℓ≅C)
Displayed\Sigma.agda:73:-- DUARel on a non-dependent Σ-type
Displayed\Sigma.agda:75:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Sigma.agda:76:  {B : A → Type ℓB} {ℓ≅B : Level} (𝒮ᴰ-B : DUARel 𝒮-A B ℓ≅B)
Displayed\Sigma.agda:77:  {C : A → Type ℓC} {ℓ≅C : Level} (𝒮ᴰ-C : DUARel 𝒮-A C ℓ≅C)
Displayed\Sigma.agda:83:-- SubstRel on a Σ-type
Displayed\Sigma.agda:85:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Sigma.agda:86:  {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B)
Displayed\Sigma.agda:87:  {C : Σ A B → Type ℓC} (𝒮ˢ-C : SubstRel (∫ˢ 𝒮ˢ-B) C)
Displayed\Sigma.agda:104:module _ {A : Type ℓA} {𝒮-A : UARel A ℓ≅A}
Displayed\Sigma.agda:105:  {B : A → Type ℓB} (𝒮ˢ-B : SubstRel 𝒮-A B)
Displayed\Sigma.agda:106:  {C : A → Type ℓC} (𝒮ˢ-C : SubstRel 𝒮-A C)
Displayed\Subst.agda:2:  Given a type A with a UARel and a family B over A,
Displayed\Subst.agda:24:record SubstRel {A : Type ℓA} {ℓ≅A : Level} (𝒮-A : UARel A ℓ≅A) (B : A → Type ℓB)
Displayed\Subst.agda:25:  : Type (ℓ-max (ℓ-max ℓA ℓB) ℓ≅A)
Displayed\Subst.agda:47:Subst→DUA : {A : Type ℓA} {ℓ≅A : Level} {𝒮-A : UARel A ℓ≅A} {B : A → Type ℓB}
Displayed\Unit.agda:26:𝒮ᴰ-Unit : {A : Type ℓA} (𝒮-A : UARel A ℓ≅A) → DUARel 𝒮-A (λ _ → Unit) ℓ-zero
Displayed\Universe.agda:22:𝒮-Univ : ∀ ℓ → UARel (Type ℓ) ℓ
Experiments\Combinatorics.agda:90:R : {n : ℕ} → Fin n .fst → Fin n .fst → Type
Experiments\CountingFiniteStructure.agda:21:open import Cubical.Data.FinType
Experiments\CountingFiniteStructure.agda:22:open import Cubical.Data.FinType.FiniteStructure
Experiments\CountingFiniteStructure.agda:30:isFinStrCard : (S : FinSet ℓ-zero → FinSet ℓ) (n : ℕ) → isFinType 0 (FinSetWithStrOfCard S
n)
Experiments\CountingFiniteStructure.agda:31:isFinStrCard S n = isFinTypeFinSetWithStrOfCard S n
Experiments\EscardoSIP.agda:24:    S : Type ℓ → Type ℓ'
Experiments\EscardoSIP.agda:26:-- We prove several useful equalities and equivalences between Σ-types all the proofs are taken from
Experiments\EscardoSIP.agda:31:Σ-≡-≃ : {X : Type ℓ} {A : X → Type ℓ'}
Experiments\EscardoSIP.agda:38:Σ-cong : {X : Type ℓ} {A B : X → Type ℓ'} →
Experiments\EscardoSIP.agda:43:NatΣ : {X : Type ℓ} {A : X → Type ℓ'} {B : X → Type ℓ''}
Experiments\EscardoSIP.agda:47:Σ-to-PathP : {X : Type ℓ} {A : X → Type ℓ'} {x : X} {a b : A x}
Experiments\EscardoSIP.agda:52:Σ-cong-≃ :  {X : Type ℓ} {A : X → Type ℓ'} {B : X → Type ℓ''} →
Experiments\EscardoSIP.agda:79:Σ-change-of-variable-Iso :  {X : Type ℓ} {Y : Type ℓ'} {A : Y → Type ℓ''} (f : X → Y)
Experiments\EscardoSIP.agda:120:Σ-change-of-variable-≃ : {X : Type ℓ} {Y : Type ℓ'} {A : Y → Type ℓ''} (f : X → Y)
Experiments\EscardoSIP.agda:126:-- A structure is a type-family S : Type ℓ → Type ℓ', i.e. for X : Type ℓ and s : S X, the pair (X , s)
Experiments\EscardoSIP.agda:130:-- that gives us for any two types with S-structure (X , s) and (Y , t) a family:
Experiments\EscardoSIP.agda:131:--    ι (X , s) (Y , t) : (X ≃ Y) → Type ℓ''
Experiments\EscardoSIP.agda:132:-- Note that for any equivalence (f , e) : X ≃ Y the type  ι (X , s) (Y , t) (f , e) need not to be
Experiments\EscardoSIP.agda:133:-- a proposition. Indeed this type should correspond to the ways s and t can be identified
Experiments\EscardoSIP.agda:137:SNS : (S : Type ℓ → Type ℓ') (ι : StrEquiv S ℓ'') → Type (ℓ-max (ℓ-max (ℓ-suc ℓ) ℓ') ℓ'')
Experiments\EscardoSIP.agda:138:SNS  {ℓ = ℓ} S ι = ∀ {X : (Type ℓ)} (s t : S X) → ((s ≡ t) ≃ ι (X , s) (X , t) (idEquiv X))
Experiments\EscardoSIP.agda:142:ρ :  {ι : StrEquiv S ℓ''} (θ : SNS S ι) (A : TypeWithStr ℓ S) → (ι A A (idEquiv (typ A)))
Experiments\EscardoSIP.agda:146:_≃[_]_ : (A : TypeWithStr ℓ S) (ι : StrEquiv S ℓ'') (B : TypeWithStr ℓ S) → (Type (ℓ-max ℓ ℓ''))
Experiments\EscardoSIP.agda:151:Id→homEq : (S : Type ℓ → Type ℓ') (ι : StrEquiv S ℓ'')
Experiments\EscardoSIP.agda:152:          → (ρ : (A : TypeWithStr ℓ S) → ι A A (idEquiv (typ A)))
Experiments\EscardoSIP.agda:153:          → (A B : TypeWithStr ℓ S) → A ≡ B → (A ≃[ ι ] B)
Experiments\EscardoSIP.agda:158:hom-lemma-dep : (S : Type ℓ → Type ℓ') (ι : StrEquiv S ℓ'') (θ : SNS S ι)
Experiments\EscardoSIP.agda:159:               → (A B : TypeWithStr ℓ S)
Experiments\EscardoSIP.agda:171:ua-lemma : (A B : Type ℓ) (e : A ≃ B) → (pathToEquiv (ua e)) ≡ e
Experiments\EscardoSIP.agda:177:homEq→Id : (S : Type ℓ → Type ℓ') (ι : StrEquiv S ℓ'') (θ : SNS S ι)
Experiments\EscardoSIP.agda:178:          → (A B : TypeWithStr ℓ S) → (A ≃[ ι ] B) → A ≡ B
Experiments\EscardoSIP.agda:191:SIP : (S : Type ℓ → Type ℓ') (ι : StrEquiv S ℓ'') (θ : SNS S ι)
Experiments\EscardoSIP.agda:192:     → (A B : TypeWithStr ℓ S) → ((A ≡ B) ≃ (A ≃[ ι ] B))
Experiments\EscardoSIP.agda:208:-- A simple example: pointed types
Experiments\EscardoSIP.agda:209:pointed-structure : Type ℓ → Type ℓ
Experiments\EscardoSIP.agda:212:Pointed-Type : Type (ℓ-suc ℓ)
Experiments\EscardoSIP.agda:213:Pointed-Type {ℓ = ℓ} = Σ (Type ℓ) pointed-structure
Experiments\EscardoSIP.agda:215:pointed-ι : (A B : Pointed-Type) → (A .fst) ≃ (B. fst) → Type ℓ
Experiments\EscardoSIP.agda:221:pointed-type-sip : (X Y : Type ℓ) (x : X) (y : Y)
Experiments\EscardoSIP.agda:223:pointed-type-sip X Y x y = invEquiv (SIP pointed-structure pointed-ι pointed-is-sns (X , x) (Y , y))
Experiments\FunExtFromUA.agda:14:_∼_ : {X : Type ℓ} {A : X → Type ℓ'} → (f g : (x : X) → A x) → Type (ℓ-max ℓ ℓ')
Experiments\FunExtFromUA.agda:17:funext : ∀ ℓ ℓ' → Type (ℓ-suc(ℓ-max ℓ ℓ'))
Experiments\FunExtFromUA.agda:18:funext ℓ ℓ' = {X : Type ℓ} {Y : Type ℓ'} {f g : X → Y} → f ∼ g → f ≡ g
Experiments\FunExtFromUA.agda:21:pre-comp-is-equiv : (X Y : Type ℓ) (f : X → Y) (Z : Type ℓ)
Experiments\FunExtFromUA.agda:26:  P : (X : Type ℓ) → (X → Y) → Type ℓ
Experiments\FunExtFromUA.agda:31:leftCancellable : {X : Type ℓ} {Y : Type ℓ'} → (X → Y) → Type (ℓ-max ℓ ℓ')
Experiments\FunExtFromUA.agda:34:equivLC : {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) → isEquiv f → leftCancellable f
Experiments\FunExtFromUA.agda:89:  data ℕ : Type₀ where
Experiments\Generic.agda:21:There : Type₀ → Type₀
Experiments\Generic.agda:24:Database : Type₀
Experiments\Generic.agda:55:Address : Type₀
Experiments\Generic.agda:58:Name : Type₀
Experiments\Generic.agda:61:data Person : Type₀ where
Experiments\Generic.agda:64:data Salary (A : Type₀) : Type₀ where
Experiments\Generic.agda:67:data Employee (A : Type₀) : Type₀ where
Experiments\Generic.agda:70:Manager : Type₀ → Type₀
Experiments\Generic.agda:75:  data Dept (A : Type₀) : Type₀ where
Experiments\Generic.agda:78:  data SubUnit (A : Type₀) : Type₀ where
Experiments\Generic.agda:82:data Company (A : Type₀) : Type₀ where
Experiments\HInt.agda:29:data ℤ : Type₀ where
Experiments\HoTT-UF.agda:3:This is a HoTT-UF core library based on cubical type theory, where the
Experiments\HoTT-UF.agda:21:     using ( _≡_            -- The identity type.
Experiments\HoTT-UF.agda:35:           ; Σ              -- Sum type. Needed to define contractible types, equivalences
Experiments\HoTT-UF.agda:40:           ; isProp         -- The usual notions of proposition, contractible type, set.
Experiments\HoTT-UF.agda:45:           ; _≃_            -- The type of equivalences between two given types.
Experiments\HoTT-UF.agda:51:           ; squash₁         -- A truncated type is a proposition.
Experiments\HoTT-UF.agda:65:  data ℕ : Type₀ where
Experiments\HoTT-UF.agda:98:type check. Moreover, the term pr₁ b would not evaluate to five, as it
Experiments\HoTT-UF.agda:99:does with the cubical type theory implementation of funext.
Experiments\List.agda:25:data List (A : Type) : Type where
Experiments\List.agda:30:data List' (A : Type) : Type where
Experiments\List.agda:35:  A : Type
Experiments\List.agda:63:-- an isomorphism of the types.
Experiments\List.agda:88:ListPath : (A : Type) → List A ≡ List' A
Experiments\List.agda:96:  -- First make a suitable Σ-type packaging what we need for the
Experiments\List.agda:97:  -- transport (note that _++_ and rev here are part of the Σ-type).
Experiments\List.agda:99:  T : Type → Type
Experiments\List.agda:155:module manualSIP (A : Type) where
Experiments\List.agda:159:  RawStruct : Type → Type
Experiments\List.agda:184:  P : (X : Type) → RawStruct X → Type
Experiments\List.agda:188:  List-Struct : Σ[ X ∈ Type ] (Σ[ s ∈ RawStruct X ] (P X s))
Experiments\List.agda:202:  List'-RawStruct : Σ[ X ∈ Type ] (RawStruct X)
Experiments\List.agda:230:module SIP-auto (A : Type) where
Experiments\List.agda:234:  RawStruct : Type → Type
Experiments\List.agda:245:  P : (X : Type) → RawStruct X → Type
Experiments\List.agda:249:  List-Struct : Σ[ X ∈ Type ] (Σ[ s ∈ RawStruct X ] (P X s))
Experiments\List.agda:263:  List'-RawStruct : Σ[ X ∈ Type ] (RawStruct X)
Experiments\NatMinusTwo.agda:2:  This type ℕ₋₂ was originally used as the index to n-truncation in order to
Experiments\NatMinusTwo.agda:7:   the hassle of having to use this type everywhere where truncation levels
Experiments\NatMinusTwo.agda:8:   were needed. So for this library, use the type `HLevel = ℕ` instead.
Experiments\Poset.agda:28:Order : (ℓ₁ : Level) → Type ℓ₀ → Type (ℓ-max ℓ₀ (ℓ-suc ℓ₁))
Experiments\Poset.agda:31:isSetOrder : (ℓ₁ : Level) (A : Type ℓ₀) → isSet (Order ℓ₁ A)
Experiments\Poset.agda:37:isOrderPreserving : (M : TypeWithStr ℓ₀ (Order ℓ₁)) (N : TypeWithStr ℓ₀′ (Order ℓ₁′))
Experiments\Poset.agda:38:                  → (fst M → fst N) → Type _
Experiments\Poset.agda:42:isPropIsOrderPreserving : (M : TypeWithStr ℓ₀  (Order ℓ₁))
Experiments\Poset.agda:43:                          (N : TypeWithStr ℓ₀′ (Order ℓ₁′))
Experiments\Poset.agda:52:isAnOrderPreservingEqv : (M : TypeWithStr ℓ₀  (Order ℓ₁))
Experiments\Poset.agda:53:                         (N : TypeWithStr ℓ₀′ (Order ℓ₁′))
Experiments\Poset.agda:54:                       → fst M ≃ fst N → Type _
Experiments\Poset.agda:104:isReflexive : {A : Type ℓ₀} → Order ℓ₁ A → hProp (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:107:isTransitive : {A : Type ℓ₀} → Order ℓ₁ A → hProp (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:110:    φ      : Type (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:115:isAntisym : {A : Type ℓ₀} → isSet A → Order ℓ₁ A → hProp (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:118:    φ      : Type (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:125:satPosetAx : (ℓ₁ : Level) (A : Type ℓ₀) → Order ℓ₁ A → hProp (ℓ-max ℓ₀ ℓ₁)
Experiments\Poset.agda:135:PosetStructure : (ℓ₁ : Level) → Type ℓ₀ → Type (ℓ-max ℓ₀ (ℓ-suc ℓ₁))
Experiments\Poset.agda:138:isSetPosetStructure : (ℓ₁ : Level) (A : Type ℓ₀) → isSet (PosetStructure ℓ₁ A)
Experiments\Poset.agda:144:Poset : (ℓ₀ ℓ₁ : Level) → Type (ℓ-max (ℓ-suc ℓ₀) (ℓ-suc ℓ₁))
Experiments\Poset.agda:145:Poset ℓ₀ ℓ₁ = TypeWithStr ℓ₀ (PosetStructure ℓ₁)
Experiments\Poset.agda:150:∣_∣ₚ : Poset ℓ₀ ℓ₁ → Type ℓ₀
Experiments\Poset.agda:176:isMonotonic : (P : Poset ℓ₀ ℓ₁) (Q : Poset ℓ₀′ ℓ₁′) → (∣ P ∣ₚ → ∣ Q ∣ₚ) → Type _
Experiments\Poset.agda:186:-- We collect the type of monotonic maps between two posets in the following
Experiments\Poset.agda:187:-- type.
Experiments\Poset.agda:189:_─m→_ : Poset ℓ₀ ℓ₁ → Poset ℓ₀′ ℓ₁′ → Type _
Experiments\Poset.agda:223:                → ∣ P ∣ₚ ≃ ∣ Q ∣ₚ → Type _
Experiments\Poset.agda:235:-- We denote by `_≃ₚ_` the type of monotonic poset equivalences.
Experiments\Poset.agda:237:_≃ₚ_ : Poset ℓ₀ ℓ₁ → Poset ℓ₀ ℓ₁ → Type _
Experiments\Poset.agda:250:    NTS : (A : Type ℓ) (_⊑_ : Order ℓ₁ A) → isProp ⟨ satPosetAx ℓ₁ A _⊑_ ⟩
Experiments\Poset.agda:257:-- _isomorphisms_ rather than equivalences. In the case when types `A` and `B`
Experiments\Poset.agda:258:-- are sets, the type of isomorphisms between `A` and `B` is equivalent to the
Experiments\Poset.agda:259:-- type of equivalences betwee them.
Experiments\Poset.agda:263:isPosetIso : (P Q : Poset ℓ₀ ℓ₁) → (P ─m→ Q) → Type _
Experiments\Poset.agda:283:-- We will denote by `P ≅ₚ Q` the type of isomorphisms between posets `P` and
Experiments\Poset.agda:286:_≅ₚ_ : Poset ℓ₀ ℓ₁ → Poset ℓ₀ ℓ₁ → Type _
Experiments\Poset.agda:320:-- Once we have this equivalence, the main result is then: the type of poset
Experiments\Poset.agda:321:-- isomorphisms between `P` and `Q` is equivalent to the type of identity proofs
Experiments\Problem.agda:16:ptType : Type _
Experiments\Problem.agda:17:ptType = Σ Type₀ \ A → A
Experiments\Problem.agda:19:pt : (A : ptType) → A .fst
Experiments\Problem.agda:22:S¹pt : ptType
Experiments\Problem.agda:24:S²pt : ptType
Experiments\Problem.agda:26:S³pt : ptType
Experiments\Problem.agda:28:joinpt : ptType
Experiments\Problem.agda:31:Ω : (A : ptType) → ptType
Experiments\Problem.agda:33:Ω² : (A : ptType) → ptType
Experiments\Problem.agda:35:Ω³ : (A : ptType) → ptType
Experiments\ZariskiLatticeBasicOpens.agda:73: _≼_ : A → A → Type ℓ
Experiments\ZariskiLatticeBasicOpens.agda:97: R : A → A → Type ℓ
Experiments\HAEquivInt\Base.agda:7:data HAEquivInt : Type₀ where
Experiments\IsoInt\Base.agda:22:data IsoInt : Type₀ where
Experiments\NatMinusTwo\Base.agda:8:record ℕ₋₂ : Type₀ where
Experiments\ZCohomology\Benchmarks.agda:357:    ind : (B : TotalHopf → Type) → ((x : _) → isOfHLevel 3 (B x)) → B (north , base) → (x :
_) → B x
Experiments\ZCohomology\Benchmarks.agda:359:      transport (λ i → (B : isoToPath IsoS³TotalHopf i → Type)
Experiments\ZCohomologyOld\Base.agda:19:    A : Type ℓ
Experiments\ZCohomologyOld\Base.agda:24:coHomK : (n : ℕ) → Type₀
Experiments\ZCohomologyOld\Base.agda:29:coHom : (n : ℕ) → Type ℓ → Type ℓ
Experiments\ZCohomologyOld\Base.agda:44:coHomRed : (n : ℕ) → (A : Pointed ℓ) → Type ℓ
Experiments\ZCohomologyOld\KcompPrelims.agda:41:    A : Type ℓ
Experiments\ZCohomologyOld\KcompPrelims.agda:55:    P : (a b : S₊ (2 + n)) → Type₀
Experiments\ZCohomologyOld\KcompPrelims.agda:100:  Code : (y : Susp S2+n) → north ≡ y → Type₀
Experiments\ZCohomologyOld\KcompPrelims.agda:121:    gluePath : I → Type _
Experiments\ZCohomologyOld\KcompPrelims.agda:124:    lem : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : z ≡ y) → (p ∙ q ⁻¹) ∙ q ≡ p
Experiments\ZCohomologyOld\Properties.agda:48:    A : Type ℓ
Experiments\ZCohomologyOld\Properties.agda:49:    B : Type ℓ'
Experiments\ZCohomologyOld\Properties.agda:72:coHomPointedElim : {A : Type ℓ} (n : ℕ) (a : A) {B : coHom (suc n) A → Type ℓ'}
Experiments\ZCohomologyOld\Properties.agda:80:  helper :  (n : ℕ) {B : coHom (suc n) A → Type ℓ'}
Experiments\ZCohomologyOld\Properties.agda:100:coHomPointedElim2 : {A : Type ℓ} (n : ℕ) (a : A) {B : coHom (suc n) A → coHom (suc n) A
→ Type ℓ'}
Experiments\ZCohomologyOld\Properties.agda:107:  helper : (n : ℕ) (a : A) {B : coHom (suc n) A → coHom (suc n) A → Type ℓ'}
Experiments\ZCohomologyOld\Properties.agda:130:                  (A : Type ℓ) →
Experiments\ZCohomologyOld\Properties.agda:395:  rUnitlUnitGen : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {b : B} (e : Iso A (b ≡ b))
Experiments\ZCohomologyOld\Properties.agda:450:coHomGr : ∀ {ℓ} (n : ℕ) (A : Type ℓ) → Group ℓ
Experiments\ZCohomologyOld\Properties.agda:463:×coHomGr : (n : ℕ) (A : Type ℓ) (B : Type ℓ') → Group _
Experiments\ZCohomologyOld\Properties.agda:466:coHomFun : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (n : ℕ) (f : A → B) → coHom n B → coHom n
A
Experiments\ZCohomologyOld\Properties.agda:469:-distrLemma : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (n m : ℕ) (f : GroupHom (coHomGr n A)
(coHomGr m B))
Experiments\ZCohomologyOld\Properties.agda:506:Unit' : Type₀
Experiments\ZCohomologyOld\Properties.agda:509:lock : ∀ {ℓ} {A : Type ℓ} → Unit' → A → A
Foundations\CartesianKanOps.agda:9:coe0→1 : ∀ {ℓ} (A : I → Type ℓ) → A i0 → A i1
Foundations\CartesianKanOps.agda:13:coe0→i : ∀ {ℓ} (A : I → Type ℓ) (i : I) → A i0 → A i
Foundations\CartesianKanOps.agda:17:coe0→i1 : ∀ {ℓ} (A : I → Type ℓ) (a : A i0) → coe0→i A i1 a ≡ coe0→1 A a
Foundations\CartesianKanOps.agda:20:coe0→i0 : ∀ {ℓ} (A : I → Type ℓ) (a : A i0) → coe0→i A i0 a ≡ a
Foundations\CartesianKanOps.agda:24:coe1→0 : ∀ {ℓ} (A : I → Type ℓ) → A i1 → A i0
Foundations\CartesianKanOps.agda:28:coe1→i : ∀ {ℓ} (A : I → Type ℓ) (i : I) → A i1 → A i
Foundations\CartesianKanOps.agda:32:coe1→i0 : ∀ {ℓ} (A : I → Type ℓ) (a : A i1) → coe1→i A i0 a ≡ coe1→0 A a
Foundations\CartesianKanOps.agda:35:coe1→i1 : ∀ {ℓ} (A : I → Type ℓ) (a : A i1) → coe1→i A i1 a ≡ a
Foundations\CartesianKanOps.agda:39:coei→0 : ∀ {ℓ} (A : I → Type ℓ) (i : I) → A i → A i0
Foundations\CartesianKanOps.agda:42:coei0→0 : ∀ {ℓ} (A : I → Type ℓ) (a : A i0) → coei→0 A i0 a ≡ a
Foundations\CartesianKanOps.agda:45:coei1→0 : ∀ {ℓ} (A : I → Type ℓ) (a : A i1) → coei→0 A i1 a ≡ coe1→0 A a
Foundations\CartesianKanOps.agda:57:coei→j : ∀ {ℓ} (A : I → Type ℓ) (i j : I) → A i → A j
Foundations\CartesianKanOps.agda:62:coei→1 : ∀ {ℓ} (A : I → Type ℓ) (i : I) → A i → A i1
Foundations\CartesianKanOps.agda:65:coei0→1 : ∀ {ℓ} (A : I → Type ℓ) (a : A i0) → coei→1 A i0 a ≡ coe0→1 A a
Foundations\CartesianKanOps.agda:68:coei1→1 : ∀ {ℓ} (A : I → Type ℓ) (a : A i1) → coei→1 A i1 a ≡ a
Foundations\CartesianKanOps.agda:72:coei→i0 : ∀ {ℓ} (A : I → Type ℓ) (i : I) (a : A i) → coei→j A i i0 a ≡ coei→0 A i a
Foundations\CartesianKanOps.agda:75:coei0→i : ∀ {ℓ} (A : I → Type ℓ) (i : I) (a : A i0) → coei→j A i0 i a ≡ coe0→i A i a
Foundations\CartesianKanOps.agda:78:coei→i1 : ∀ {ℓ} (A : I → Type ℓ) (i : I) (a : A i) → coei→j A i i1 a ≡ coei→1 A i a
Foundations\CartesianKanOps.agda:81:coei1→i : ∀ {ℓ} (A : I → Type ℓ) (i : I) (a : A i1) → coei→j A i1 i a ≡ coe1→i A i a
Foundations\CartesianKanOps.agda:85:coei→i : ∀ {ℓ} (A : I → Type ℓ) (i : I) (a : A i) → coei→j A i i a ≡ a
Foundations\CartesianKanOps.agda:95:coe0→0 : ∀ {ℓ} (A : I → Type ℓ) (a : A i0) → coei→i A i0 a ≡ refl
Foundations\CartesianKanOps.agda:98:coe1→1 : ∀ {ℓ} (A : I → Type ℓ) (a : A i1) → coei→i A i1 a ≡ refl
Foundations\CartesianKanOps.agda:102:coePath : ∀ {ℓ} (A : I → Type ℓ) (p : (i : I) → A i) → (i j : I) → coei→j A i j (p i) ≡ p j
Foundations\CartesianKanOps.agda:106:coePathi0 : ∀ {ℓ} (A : I → Type ℓ) (p : (i : I) → A i) → coePath A p i0 i0 ≡ refl
Foundations\CartesianKanOps.agda:109:coePathi1 : ∀ {ℓ} (A : I → Type ℓ) (p : (i : I) → A i) → coePath A p i1 i1 ≡ refl
Foundations\CartesianKanOps.agda:114:fill1→i : ∀ {ℓ} (A : ∀ i → Type ℓ)
Foundations\CartesianKanOps.agda:126:filli→0 : ∀ {ℓ} (A : ∀ i → Type ℓ)
Foundations\CartesianKanOps.agda:139:filli→j : ∀ {ℓ} (A : ∀ i → Type ℓ)
Foundations\CartesianKanOps.agda:157:fill' : ∀ {ℓ} (A : I → Type ℓ)
Foundations\CartesianKanOps.agda:169:fill'-cap :  ∀ {ℓ} (A : I → Type ℓ)
Foundations\Cubes.agda:16:    A : Type ℓ
Foundations\Cubes.agda:21:By mutual recursion, one can define the type of
Foundations\Cubes.agda:24:  Cube    : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes.agda:27:  ∂Cube   : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes.agda:30:  CubeRel : (n : ℕ) (A : Type ℓ) → ∂Cube n A → Type ℓ
Foundations\Cubes.agda:38:CubeDep    : {A : Type ℓ} (B : A → Type ℓ') →  Cube n A → Type ℓ'
Foundations\Cubes.agda:39:∂CubeDep   : {A : Type ℓ} (B : A → Type ℓ') → ∂Cube n A → Type ℓ'
Foundations\Cubes.agda:40:CubeDepRel : {A : Type ℓ} {B : A → Type ℓ'} (a₋ : Cube n A) → ∂CubeDep {n = n} B (∂ a₋) → Type ℓ'
Foundations\Cubes.agda:157:  ret-Cube2 : {A : Type ℓ} (a : Cube 2 A) → toCube2 (fromCube2 a) ≡ a
Foundations\Cubes.agda:163:  ret-∂Cube2 : {A : Type ℓ} (a : ∂Cube 2 A) → to∂Cube2 (from∂Cube2 a) ≡ a
Foundations\Cubes.agda:185:isCubeFilled : ℕ → Type ℓ → Type ℓ
Foundations\Cubes.agda:189:isCubeFilledDep : (n : ℕ) {A : Type ℓ} (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Cubes.agda:196:isOfHLevelDep→isCubeFilledDep : (n : HLevel) {B : A → Type ℓ'} → isOfHLevelDep n B → isCubeFilledDep n B
Foundations\Cubes.agda:199:isCubeFilledDep→isOfHLevelDep : (n : HLevel) {B : A → Type ℓ'} → isCubeFilledDep n B → isOfHLevelDep n B
Foundations\Equiv.agda:29:    A B C D : Type ℓ
Foundations\Equiv.agda:65:equivPathP : {A : I → Type ℓ} {B : I → Type ℓ'} {e : A i0 ≃ B i0} {f : A i1 ≃ B i1}
Foundations\Equiv.agda:112:equivToIso : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → A ≃ B → Iso A B
Foundations\Equiv.agda:122:invEquivIdEquiv : (A : Type ℓ) → invEquiv (idEquiv A) ≡ idEquiv A
Foundations\Equiv.agda:211:equivΠCod : ∀ {F : A → Type ℓ} {G : A → Type ℓ'}
Foundations\Equiv.agda:221:equivImplicitΠCod : ∀ {F : A → Type ℓ} {G : A → Type ℓ'}
Foundations\Equiv.agda:241:equivΠ' : ∀ {ℓA ℓA' ℓB ℓB'} {A : Type ℓA} {A' : Type ℓA'}
Foundations\Equiv.agda:242:  {B : A → Type ℓB} {B' : A' → Type ℓB'}
Foundations\Equiv.agda:269:equivΠ : ∀ {ℓA ℓA' ℓB ℓB'} {A : Type ℓA} {A' : Type ℓA'}
Foundations\Equiv.agda:270:  {B : A → Type ℓB} {B' : A' → Type ℓB'}
Foundations\Equiv.agda:287:_≃⟨_⟩_ : (X : Type ℓ) → (X ≃ B) → (B ≃ C) → (X ≃ C)
Foundations\Equiv.agda:290:_■ : (X : Type ℓ) → (X ≃ X)
Foundations\Function.agda:11:    A A' A'' : Type ℓ
Foundations\Function.agda:12:    B : A → Type ℓ
Foundations\Function.agda:13:    C : (a : A) → B a → Type ℓ
Foundations\Function.agda:14:    D : (a : A) (b : B a) → C a b → Type ℓ
Foundations\Function.agda:15:    E : (x : A) → (y : B x) → (z : C x y) → (w : D x y z) → Type ℓ
Foundations\Function.agda:16:    F : (x : A) → (y : B x) → (z : C x y) → (w : D x y z) → (u : E x y z w) → Type ℓ
Foundations\Function.agda:19:idfun : (A : Type ℓ) → A → A
Foundations\Function.agda:22:-- The membership relation (used to clarify the type of a term to Agda when inside a definition, like ::
in Haskell)
Foundations\Function.agda:24:hasType : (A : Type ℓ) → A → A
Foundations\Function.agda:25:hasType _ x = x
Foundations\Function.agda:27:infixr -8 hasType
Foundations\Function.agda:29:syntax hasType A x = x :> A
Foundations\Function.agda:33:_$_ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'} → ((a : A) → B a) → (a : A) → B a
Foundations\Function.agda:59:flip : {B : Type ℓ'} {C : A → B → Type ℓ''} →
Foundations\Function.agda:64:const : {B : Type ℓ} → A → B → A
Foundations\Function.agda:68:case_of_ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'} → (x : A) → (∀ x → B x) → B x
Foundations\Function.agda:72:case_return_of_ : ∀ {ℓ ℓ'} {A : Type ℓ} (x : A) (B : A → Type ℓ') → (∀ x → B x) → B x
Foundations\Function.agda:97:∘diag : {B : (x y : A) → Type ℓ} → (∀ x y → B x y) → ∀ x → B x x
Foundations\Function.agda:100:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} where
Foundations\Function.agda:106:  2-Constant : (A → B) → Type _
Foundations\Function.agda:114:  record 3-Constant (f : A → B) : Type (ℓ-max ℓ ℓ') where
Foundations\Function.agda:159:homotopyNatural : {B : Type ℓ'} {f g : A → B} (H : ∀ a → f a ≡ g a) {x y : A} (p : x ≡ y) →
Foundations\GroupoidLaws.agda:3:This file proves the higher groupoid structure of types
Foundations\GroupoidLaws.agda:14:    A : Type ℓ
Foundations\GroupoidLaws.agda:66:rCancel-filler' : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) → (i j k : I) → A
Foundations\GroupoidLaws.agda:77:rCancel' : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) → p ∙ p ⁻¹ ≡ refl
Foundations\GroupoidLaws.agda:90:symInvoP : {A : I → Type ℓ} → {x : A i0} → {y : A i1} → (p : PathP A x y) →
Foundations\GroupoidLaws.agda:94:rUnitP : {A : I → Type ℓ} → {x : A i0} → {y : A i1} → (p : PathP A x y) →
Foundations\GroupoidLaws.agda:98:rUnitP' : ∀ {ℓ'} {A : Type ℓ} (B : A → Type ℓ')
Foundations\GroupoidLaws.agda:104:lUnitP : {A : I → Type ℓ} → {x : A i0} → {y : A i1} → (p : PathP A x y) →
Foundations\GroupoidLaws.agda:113:lUnitP' : ∀ {ℓ'} {A : Type ℓ} (B : A → Type ℓ')
Foundations\GroupoidLaws.agda:124:rCancelP : {A : I → Type ℓ} → {x : A i0} → {y : A i1} → (p : PathP A x y) →
Foundations\GroupoidLaws.agda:133:lCancelP : {A : I → Type ℓ} → {x : A i0} → {y : A i1} → (p : PathP A x y) →
Foundations\GroupoidLaws.agda:139:assocP : {A : I → Type ℓ} {x : A i0} {y : A i1} {B_i1 : Type ℓ} {B : (A i1) ≡ B_i1} {z : B i1}
Foundations\GroupoidLaws.agda:140:  {C_i1 : Type ℓ} {C : (B i1) ≡ C_i1} {w : C i1} (p : PathP A x y) (q : PathP (λ i → B i) y z) (r :
PathP (λ i → C i) z w) →
Foundations\GroupoidLaws.agda:178:leftright : {ℓ : Level} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : y ≡ z) →
Foundations\GroupoidLaws.agda:187:split-leftright : {ℓ : Level} {A : Type ℓ} {w x y z : A} (p : w ≡ x) (q : x ≡ y) (r : y ≡ z) →
Foundations\GroupoidLaws.agda:194:split-leftright' : {ℓ : Level} {A : Type ℓ} {w x y z : A} (p : w ≡ x) (q : x ≡ y) (r : y ≡ z) →
Foundations\GroupoidLaws.agda:201:doubleCompPath-elim : {ℓ : Level} {A : Type ℓ} {w x y z : A} (p : w ≡ x) (q : x ≡ y)
Foundations\GroupoidLaws.agda:205:doubleCompPath-elim' : {ℓ : Level} {A : Type ℓ} {w x y z : A} (p : w ≡ x) (q : x ≡ y)
Foundations\GroupoidLaws.agda:209:cong-∙∙-filler : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {x y z w : A}
Foundations\GroupoidLaws.agda:220:cong-∙∙ : ∀ {B : Type ℓ} (f : A → B) (p : w ≡ x) (q : x ≡ y) (r : y ≡ z)
Foundations\GroupoidLaws.agda:224:cong-∙ : ∀ {B : Type ℓ} (f : A → B) (p : x ≡ y) (q : y ≡ z)
Foundations\GroupoidLaws.agda:228:hcomp-unique : ∀ {ℓ} {A : Type ℓ} {φ}
Foundations\GroupoidLaws.agda:237:hlid-unique : ∀ {ℓ} {A : Type ℓ} {φ}
Foundations\GroupoidLaws.agda:246:comp-unique : ∀ {ℓ} {A : I → Type ℓ} {φ}
Foundations\GroupoidLaws.agda:254:lid-unique : ∀ {ℓ} {A : I → Type ℓ} {φ}
Foundations\GroupoidLaws.agda:263:transp-hcomp : ∀ {ℓ} (φ : I) {A' : Type ℓ}
Foundations\GroupoidLaws.agda:264:                     (A : (i : I) → Type ℓ [ φ ↦ (λ _ → A') ]) (let B = \ (i : I) → outS (A i))
Foundations\GroupoidLaws.agda:275:hcomp-cong : ∀ {ℓ} {A : Type ℓ} {φ} → (u : I → Partial φ A) → (u0 : A [ φ ↦ u i0 ]) →
Foundations\GroupoidLaws.agda:282:congFunct-filler : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {x y z : A} (f : A → B) (p : x ≡ y) (q : y ≡ z)
Foundations\GroupoidLaws.agda:291:congFunct : ∀ {ℓ} {B : Type ℓ} (f : A → B) (p : x ≡ y) (q : y ≡ z) → cong f (p ∙ q) ≡ cong f p ∙ cong
f q
Foundations\GroupoidLaws.agda:295:-- congFunct for dependent types
Foundations\GroupoidLaws.agda:296:congFunct-dep : ∀ {ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'} {x y z : A} (f : (a : A) → B a) (p : x ≡ y)
(q : y ≡ z)
Foundations\GroupoidLaws.agda:300:cong₂Funct : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} {B : Type ℓ'} (f : A → A → B) →
Foundations\GroupoidLaws.agda:310:symDistr-filler : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : y ≡ z) → I → I → I → A
Foundations\GroupoidLaws.agda:317:symDistr : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : y ≡ z) → sym (p ∙ q) ≡ sym q ∙ sym p
Foundations\GroupoidLaws.agda:519:∙∙lCancel-fill : ∀ {ℓ} {A : Type ℓ} {x y : A}
Foundations\GroupoidLaws.agda:528:∙∙lCancel : ∀ {ℓ} {A : Type ℓ} {x y : A}
Foundations\HLevels.agda:3:Basic theory about h-levels/n-types:
Foundations\HLevels.agda:29:HLevel : Type₀
Foundations\HLevels.agda:35:    A A' : Type ℓ
Foundations\HLevels.agda:36:    B : A → Type ℓ
Foundations\HLevels.agda:37:    C : (x : A) → B x → Type ℓ
Foundations\HLevels.agda:38:    D : (x : A) (y : B x) → C x y → Type ℓ
Foundations\HLevels.agda:39:    E : (x : A) (y : B x) → (z : C x y) → D x y z → Type ℓ
Foundations\HLevels.agda:40:    F : (x : A) (y : B x) (z : C x y) (w : D x y z) (v : E x y z w) → Type ℓ
Foundations\HLevels.agda:41:    G : (x : A) (y : B x) (z : C x y) (w : D x y z) (v : E x y z w) (u : F x y z w v) → Type ℓ
Foundations\HLevels.agda:45:isOfHLevel : HLevel → Type ℓ → Type ℓ
Foundations\HLevels.agda:50:isOfHLevelFun : (n : HLevel) {A : Type ℓ} {B : Type ℓ'} (f : A → B) → Type (ℓ-max ℓ ℓ')
Foundations\HLevels.agda:54:  ∀ {ℓ} {A : Type ℓ} (n : ℕ)
Foundations\HLevels.agda:61:TypeOfHLevel : ∀ ℓ → HLevel → Type (ℓ-suc ℓ)
Foundations\HLevels.agda:62:TypeOfHLevel ℓ n = TypeWithStr ℓ (isOfHLevel n)
Foundations\HLevels.agda:64:hProp hSet hGroupoid h2Groupoid : ∀ ℓ → Type (ℓ-suc ℓ)
Foundations\HLevels.agda:65:hProp      ℓ = TypeOfHLevel ℓ 1
Foundations\HLevels.agda:66:hSet       ℓ = TypeOfHLevel ℓ 2
Foundations\HLevels.agda:67:hGroupoid  ℓ = TypeOfHLevel ℓ 3
Foundations\HLevels.agda:68:h2Groupoid ℓ = TypeOfHLevel ℓ 4
Foundations\HLevels.agda:100:-- When proving a type has h-level n+1, we can assume it is inhabited.
Foundations\HLevels.agda:101:-- To prove a type is a proposition, it suffices to prove it is contractible if inhabited
Foundations\HLevels.agda:112:-- hlevel of path types
Foundations\HLevels.agda:149:TypeOfHLevel≡ : (n : HLevel) {X Y : TypeOfHLevel ℓ n} → ⟨ X ⟩ ≡ ⟨ Y ⟩ → X ≡ Y
Foundations\HLevels.agda:150:TypeOfHLevel≡ n = Σ≡Prop (λ _ → isPropIsOfHLevel n)
Foundations\HLevels.agda:155:  : ∀ {B : Type ℓ}
Foundations\HLevels.agda:163:  : {B : Type ℓ}
Foundations\HLevels.agda:175:  : {B : Type ℓ}
Foundations\HLevels.agda:188:  : {B : Type ℓ}
Foundations\HLevels.agda:203:  : {B : Type ℓ}
Foundations\HLevels.agda:221:  : (n : HLevel) {B : Type ℓ}
Foundations\HLevels.agda:258:isOfHLevelRetractFromIso : {A : Type ℓ} {B : Type ℓ'} (n : HLevel) → Iso A B → isOfHLevel n B → isOfHLevel
n A
Foundations\HLevels.agda:261:isOfHLevelRespectEquiv : {A : Type ℓ} {B : Type ℓ'} → (n : HLevel) → A ≃ B → isOfHLevel n A → isOfHLevel n
B
Foundations\HLevels.agda:264:isContrRetractOfConstFun : {A : Type ℓ} {B : Type ℓ'} (b₀ : B)
Foundations\HLevels.agda:270:-- h-level of dependent path types
Foundations\HLevels.agda:272:isOfHLevelPathP' : {A : I → Type ℓ} (n : HLevel)
Foundations\HLevels.agda:278:isOfHLevelPathP : {A : I → Type ℓ} (n : HLevel)
Foundations\HLevels.agda:287:  {A : I → I → Type ℓ}
Foundations\HLevels.agda:311:-- h-level of Σ-types
Foundations\HLevels.agda:368:isProp× : {A : Type ℓ} {B : Type ℓ'} → isProp A → isProp B → isProp (A × B)
Foundations\HLevels.agda:371:isProp×2 : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Foundations\HLevels.agda:375:isProp×3 : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
Foundations\HLevels.agda:379:isProp×4 : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''} {E : Type ℓ''''}
Foundations\HLevels.agda:383:isProp×5 : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''} {E : Type ℓ''''} {F : Type ℓ'''''}
Foundations\HLevels.agda:389:isOfHLevel× : ∀ {A : Type ℓ} {B : Type ℓ'} n → isOfHLevel n A → isOfHLevel n B
Foundations\HLevels.agda:393:isSet× : ∀ {A : Type ℓ} {B : Type ℓ'} → isSet A → isSet B → isSet (A × B)
Foundations\HLevels.agda:396:isGroupoid× : ∀ {A : Type ℓ} {B : Type ℓ'} → isGroupoid A → isGroupoid B
Foundations\HLevels.agda:400:is2Groupoid× : ∀ {A : Type ℓ} {B : Type ℓ'} → is2Groupoid A → is2Groupoid B
Foundations\HLevels.agda:404:-- h-level of Π-types
Foundations\HLevels.agda:472:isProp→ : {A : Type ℓ} {B : Type ℓ'} → isProp B → isProp (A → B)
Foundations\HLevels.agda:516:isOfHLevelΠ⁻ : ∀ {A : Type ℓ} {B : Type ℓ'} n
Foundations\HLevels.agda:532:  : ∀ n {A : Type ℓ} {B : Type ℓ'}
Foundations\HLevels.agda:543:isOfHLevel≡ : ∀ n → {A B : Type ℓ} (hA : isOfHLevel n A) (hB : isOfHLevel n B) →
Foundations\HLevels.agda:548:  : ∀ n {A : Type ℓ} {B : Type ℓ'}
Foundations\HLevels.agda:556:  : ∀ n {A : Type ℓ} {B : Type ℓ'}
Foundations\HLevels.agda:566:  : ∀ n → {A B : Type ℓ}
Foundations\HLevels.agda:575:  : ∀ n → {A B : Type ℓ}
Foundations\HLevels.agda:583:-- h-level of TypeOfHLevel
Foundations\HLevels.agda:585:isPropHContr : isProp (TypeOfHLevel ℓ 0)
Foundations\HLevels.agda:588:isOfHLevelTypeOfHLevel : ∀ n → isOfHLevel (suc n) (TypeOfHLevel ℓ n)
Foundations\HLevels.agda:589:isOfHLevelTypeOfHLevel zero = isPropHContr
Foundations\HLevels.agda:590:isOfHLevelTypeOfHLevel (suc n) (X , a) (Y , b) =
Foundations\HLevels.agda:596:isSetHProp = isOfHLevelTypeOfHLevel 1
Foundations\HLevels.agda:599:isGroupoidHSet = isOfHLevelTypeOfHLevel 2
Foundations\HLevels.agda:602:-- h-level of lifted type
Foundations\HLevels.agda:604:isOfHLevelLift : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} → isOfHLevel n A → isOfHLevel n (Lift ℓ' A)
Foundations\HLevels.agda:607:isOfHLevelLower : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} → isOfHLevel n (Lift ℓ' A) → isOfHLevel n A
Foundations\HLevels.agda:620:isContrPartial→isContr : ∀ {ℓ} {A : Type ℓ}
Foundations\HLevels.agda:633:-- Dependent h-level over a type
Foundations\HLevels.agda:635:isOfHLevelDep : HLevel → {A : Type ℓ} (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\HLevels.agda:640:isContrDep : {A : Type ℓ} (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\HLevels.agda:643:isPropDep : {A : Type ℓ} (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\HLevels.agda:647:  : {A' : Type ℓ} (f : A' → A) → isContrDep B → isContrDep (B ∘ f)
Foundations\HLevels.agda:652:isPropDep∘ : {A' : Type ℓ} (f : A' → A) → isPropDep B → isPropDep (B ∘ f)
Foundations\HLevels.agda:656:  → {A : Type ℓ} {B : A → Type ℓ'} → isOfHLevelDep n {A = A} B → (a : A) → isOfHLevel n (B a)
Foundations\HLevels.agda:662:  → {A : Type ℓ} {B : A → Type ℓ'} (h : (a : A) → isOfHLevel n (B a)) → isOfHLevelDep n {A = A} B
Foundations\HLevels.agda:830:module _ (B : (i j k : I) → Type ℓ)
Foundations\HLevels.agda:846:  CubeP : Type ℓ
Foundations\Interpolate.agda:16:  {A : Type} {p : I → A} {i j k l m : I}
Foundations\Isomorphism.agda:22:    A B C : Type ℓ
Foundations\Isomorphism.agda:25:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} where
Foundations\Isomorphism.agda:26:  section : (f : A → B) → (g : B → A) → Type ℓ'
Foundations\Isomorphism.agda:30:  retract : (f : A → B) → (g : B → A) → Type ℓ
Foundations\Isomorphism.agda:33:record Iso {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
Foundations\Isomorphism.agda:42:isIso : (A → B) → Type _
Foundations\Isomorphism.agda:188:domIso : ∀ {ℓ} {C : Type ℓ} → Iso A B → Iso (A → C) (B → C)
Foundations\Isomorphism.agda:195:_Iso⟨_⟩_ : ∀ {ℓ ℓ' ℓ''} {B : Type ℓ'} {C : Type ℓ''} (X : Type ℓ) → Iso X B → Iso B C → Iso X C
Foundations\Isomorphism.agda:198:_∎Iso : ∀ {ℓ} (A : Type ℓ) → Iso A A
Foundations\Isomorphism.agda:204:codomainIsoDep : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : A → Type ℓ'} {C : A → Type ℓ''}
Foundations\Isomorphism.agda:212:codomainIso : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Foundations\Path.agda:16:    A : Type ℓ
Foundations\Path.agda:18:module _ {A : I → Type ℓ} {x : A i0} {y : A i1} where
Foundations\Path.agda:25:PathP≡Path : ∀ (P : I → Type ℓ) (p : P i0) (q : P i1) →
Foundations\Path.agda:29:PathP≡Path⁻ : ∀ (P : I → Type ℓ) (p : P i0) (q : P i1) →
Foundations\Path.agda:33:PathPIsoPath : ∀ (A : I → Type ℓ) (x : A i0) (y : A i1) → Iso (PathP A x y) (transport (λ i → A i) x ≡ y)
Foundations\Path.agda:81:PathP≃Path : (A : I → Type ℓ) (x : A i0) (y : A i1) →
Foundations\Path.agda:85:PathP≡compPath : ∀ {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : y ≡ z) (r : x ≡ z)
Foundations\Path.agda:90:3-ConstantCompChar : {A : Type ℓ} {B : Type ℓ'} (f : A → B) (link : 2-Constant f)
Foundations\Path.agda:97:PathP≡doubleCompPathˡ : ∀ {A : Type ℓ} {w x y z : A} (p : w ≡ y) (q : w ≡ x) (r : y ≡ z) (s : x ≡ z)
Foundations\Path.agda:102:PathP≡doubleCompPathʳ : ∀ {A : Type ℓ} {w x y z : A} (p : w ≡ y) (q : w ≡ x) (r : y ≡ z) (s : x ≡ z)
Foundations\Path.agda:107:compPathl-cancel : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : x ≡ z) → p ∙ (sym p ∙ q) ≡ q
Foundations\Path.agda:113:compPathr-cancel : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : z ≡ y) (q : x ≡ y) → (q ∙ sym p) ∙ p ≡ q
Foundations\Path.agda:130:isProp→SquareP : ∀ {B : I → I → Type ℓ} → ((i j : I) → isProp (B i j))
Foundations\Path.agda:144:isProp→isPropPathP : ∀ {ℓ} {B : I → Type ℓ} → ((i : I) → isProp (B i))
Foundations\Path.agda:149:isProp→isContrPathP : {A : I → Type ℓ} → (∀ i → isProp (A i))
Foundations\Path.agda:193:-- The type of fillers of a square is equivalent to the double composition identites
Foundations\Path.agda:205:  B : (q : x ≡ x) → I → Type _
Foundations\Path.agda:216:  B : (q : x ≡ x) → I → Type _
Foundations\Path.agda:223:flipSquare≡cong-sym : ∀ {ℓ} {A : Type ℓ} {x : A} (P : Square (refl {x = x}) refl refl refl)
Foundations\Path.agda:228:sym≡cong-sym : ∀ {ℓ} {A : Type ℓ} {x : A} (P : Square (refl {x = x}) refl refl refl)
Foundations\Path.agda:232:-- sym induces an equivalence on path types
Foundations\Path.agda:239:module _ {ℓ : Level} {A : Type ℓ}
Foundations\Path.agda:275:module _ {A : Type ℓ} {B : A -> Type ℓ'} where
Foundations\Path.agda:277:  record Reveal_·_is_ (f : (x : A) → B x) (x : A) (y : B x) : Type (ℓ-max ℓ ℓ') where
Foundations\Path.agda:285:Jequiv : {x : A} (P : ∀ y → x ≡ y → Type ℓ') → P x refl ≃ (∀ {y} (p : x ≡ y) → P y p)
Foundations\Path.agda:299:congPathIso : ∀ {ℓ ℓ'} {A : I → Type ℓ} {B : I → Type ℓ'}
Foundations\Path.agda:337:congPathEquiv : ∀ {ℓ ℓ'} {A : I → Type ℓ} {B : I → Type ℓ'}
Foundations\Path.agda:342:-- Characterizations of dependent paths in path types
Foundations\Path.agda:450:pathFiber : {B : Type ℓ} (f : A → B)
Foundations\Powerset.agda:3:This file introduces the "powerset" of a type in the style of
Foundations\Powerset.agda:24:    X : Type ℓ
Foundations\Powerset.agda:26:ℙ : Type ℓ → Type (ℓ-suc ℓ)
Foundations\Powerset.agda:34:_∈_ : {X : Type ℓ} → X → ℙ X → Type ℓ
Foundations\Powerset.agda:37:_⊆_ : {X : Type ℓ} → ℙ X → ℙ X → Type ℓ
Foundations\Powerset.agda:58:  funExt (λ x → TypeOfHLevel≡ 1 (hPropExt (A x .snd) (B x .snd) (φ x) (ψ x)))
Foundations\Prelude.agda:12:- Σ-types and contractibility of singletons
Foundations\Prelude.agda:41:    A : Type ℓ
Foundations\Prelude.agda:42:    B : A → Type ℓ
Foundations\Prelude.agda:53:-- symP infers the type of its argument from the type of its output
Foundations\Prelude.agda:54:symP : {A : I → Type ℓ} → {x : A i1} → {y : A i0} →
Foundations\Prelude.agda:58:-- symP infers the type of its output from the type of its argument
Foundations\Prelude.agda:59:symP-fromGoal : {A : I → Type ℓ} → {x : A i0} → {y : A i1} →
Foundations\Prelude.agda:68:{- `S` stands for simply typed. Using `congS` instead of `cong`
Foundations\Prelude.agda:71:congS : ∀ {B : Type ℓ} → (f : A → B) (p : x ≡ y) → f x ≡ f y
Foundations\Prelude.agda:75:congP : {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ'}
Foundations\Prelude.agda:81:cong₂ : {C : (a : A) → (b : B a) → Type ℓ} →
Foundations\Prelude.agda:89:cong₃ : {C : (a : A) → (b : B a) → Type ℓ}
Foundations\Prelude.agda:90:        {D : (a : A) (b : B a) → C a b → Type ℓ'}
Foundations\Prelude.agda:99:congP₂ : {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ'}
Foundations\Prelude.agda:100:  {C : (i : I) (a : A i) → B i a → Type ℓ''}
Foundations\Prelude.agda:108:congL : {C : Type ℓ} (f : (a : A) → C → B a) (p : x ≡ y)
Foundations\Prelude.agda:113:congR : {C : Type ℓ} (f : C → (a : A) → B a) (p : x ≡ y)
Foundations\Prelude.agda:226:compPathP : {A : I → Type ℓ} {x : A i0} {y : A i1} {B_i1 : Type ℓ} {B : (A i1) ≡ B_i1} {z : B i1}
Foundations\Prelude.agda:234:-- Composition in a family indexed by a type
Foundations\Prelude.agda:235:compPathP' : {B : A → Type ℓ'} {x' : B x} {y' : B y} {z' : B z} {p : x ≡ y} {q : y ≡ z}
Foundations\Prelude.agda:244:compPathP-filler : {A : I → Type ℓ} {x : A i0} {y : A i1} {B_i1 : Type ℓ} {B : A i1 ≡ B_i1} {z : B i1}
Foundations\Prelude.agda:253:compPathP'-filler : {B : A → Type ℓ'} {x' : B x} {y' : B y} {z' : B z} {p : x ≡ y} {q : y ≡ z}
Foundations\Prelude.agda:293:transport : {A B : Type ℓ} → A ≡ B → A → B
Foundations\Prelude.agda:301:transport-filler : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B) (x : A)
Foundations\Prelude.agda:306:subst : (B : A → Type ℓ') (p : x ≡ y) → B x → B y
Foundations\Prelude.agda:309:subst2 : ∀ {ℓ' ℓ''} {B : Type ℓ'} {z w : B} (C : A → B → Type ℓ'')
Foundations\Prelude.agda:313:substRefl : ∀ {B : A → Type ℓ} {x} → (px : B x) → subst B refl px ≡ px
Foundations\Prelude.agda:316:subst-filler : (B : A → Type ℓ') (p : x ≡ y) (b : B x)
Foundations\Prelude.agda:320:subst2-filler : {B : Type ℓ'} {z w : B} (C : A → B → Type ℓ'')
Foundations\Prelude.agda:327:funExt : {B : A → I → Type ℓ'}
Foundations\Prelude.agda:333:implicitFunExt : {B : A → I → Type ℓ'}
Foundations\Prelude.agda:343:funExt⁻ : {B : A → I → Type ℓ'}
Foundations\Prelude.agda:349:congP₂$ : {A : I → Type ℓ} {B : ∀ i → A i → Type ℓ'}
Foundations\Prelude.agda:355:implicitFunExt⁻ : {B : A → I → Type ℓ'}
Foundations\Prelude.agda:363:{- `S` stands for simply typed. Using `funExtS⁻` instead of `funExt⁻`
Foundations\Prelude.agda:366:funExtS⁻ : {B : I → Type ℓ'}
Foundations\Prelude.agda:376:module _ (P : ∀ y → x ≡ y → Type ℓ') (d : P x refl) where
Foundations\Prelude.agda:395:  (P : (y : A) (p : x ≡ y) (z : B y) (q : PathP (λ i → B (p i)) b z) → Type ℓ'')
Foundations\Prelude.agda:405:  {P : (y : A) → x ≡ y → Type ℓ'} {d : (y : A) (p : x ≡ y) → P y p}
Foundations\Prelude.agda:406:  (Q : (y : A) (p : x ≡ y) (z : P y p) → d y p ≡ z → Type ℓ'')
Foundations\Prelude.agda:421:module _ {P : ∀ y → x ≡ y → Type ℓ'} (d : P x refl) where
Foundations\Prelude.agda:430:module _ {A : I → Type ℓ} {x : A i0} {y : A i1} where
Foundations\Prelude.agda:441:_◁_▷_ : ∀ {ℓ} {A : I → Type ℓ} {a₀ a₀' : A i0} {a₁ a₁' : A i1}
Foundations\Prelude.agda:448:  ∀ {ℓ} {A : I → Type ℓ} {a₀ a₀' : A i0} {a₁ a₁' : A i1}
Foundations\Prelude.agda:458:_◁_ : ∀ {ℓ} {A : I → Type ℓ} {a₀ a₀' : A i0} {a₁ : A i1}
Foundations\Prelude.agda:462:_▷_ : ∀ {ℓ} {A : I → Type ℓ} {a₀ : A i0} {a₁ a₁' : A i1}
Foundations\Prelude.agda:468:isContr : Type ℓ → Type ℓ
Foundations\Prelude.agda:471:isProp : Type ℓ → Type ℓ
Foundations\Prelude.agda:474:isSet : Type ℓ → Type ℓ
Foundations\Prelude.agda:477:isGroupoid : Type ℓ → Type ℓ
Foundations\Prelude.agda:480:is2Groupoid : Type ℓ → Type ℓ
Foundations\Prelude.agda:485:singlP : (A : I → Type ℓ) (a : A i0) → Type _
Foundations\Prelude.agda:488:singl : (a : A) → Type _
Foundations\Prelude.agda:496:isContrSinglP : (A : I → Type ℓ) (a : A i0) → isContr (singlP A a)
Foundations\Prelude.agda:515:_i0:>_UsingEqP : (A : I → Type ℓ) (a : A i0) → singlP A a
Foundations\Prelude.agda:518:-- Higher cube types
Foundations\Prelude.agda:521:  (A : I → I → Type ℓ)
Foundations\Prelude.agda:525:  → Type ℓ
Foundations\Prelude.agda:532:  → Type _
Foundations\Prelude.agda:550:  → Type _
Foundations\Prelude.agda:569:isSet' : Type ℓ → Type ℓ
Foundations\Prelude.agda:582:isGroupoid' : Type ℓ → Type ℓ
Foundations\Prelude.agda:602:isProp→PathP : ∀ {B : I → Type ℓ} → ((i : I) → isProp (B i))
Foundations\Prelude.agda:639:isPropSinglP : {A : I → Type ℓ} {a : A i0} → isProp (singlP A a)
Foundations\Prelude.agda:644:record Lift ℓ' (A : Type ℓ) : Type (ℓ-max ℓ ℓ') where
Foundations\Prelude.agda:651:liftExt : ∀ {A : Type ℓ} {a b : Lift ℓ' A} → lower a ≡ lower b → a ≡ b
Foundations\Prelude.agda:654:liftFun : ∀ {ℓ ℓ' ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'}
Foundations\RelationalStructure.agda:31:StrRel : (S : Type ℓ → Type ℓ') (ℓ'' : Level) → Type (ℓ-max (ℓ-suc (ℓ-max ℓ ℓ'')) ℓ')
Foundations\RelationalStructure.agda:34:-- Given a type A and relation R, a quotient structure is a structure on the set quotient A/R
such that
Foundations\RelationalStructure.agda:36:InducedQuotientStr : (S : Type ℓ → Type ℓ') (ρ : StrRel S ℓ'')
Foundations\RelationalStructure.agda:37:  (A : TypeWithStr ℓ S) (R : Rel (typ A) (typ A) ℓ)
Foundations\RelationalStructure.agda:38:  → Type (ℓ-max ℓ' ℓ'')
Foundations\RelationalStructure.agda:42:-- A structured equivalence relation R on a structured type A should induce a structure on A/R
Foundations\RelationalStructure.agda:43:InducesQuotientStr : (S : Type ℓ → Type ℓ') (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:45:  (A : TypeWithStr ℓ S) (R : EquivPropRel (typ A) ℓ)
Foundations\RelationalStructure.agda:50:isReflexiveStrRel : {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:52:  {X : Type ℓ} → (s : S X) → ρ (idPropRel X .fst) s s
Foundations\RelationalStructure.agda:55:isSymmetricStrRel : {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:57:  {X Y : Type ℓ} (R : PropRel X Y ℓ)
Foundations\RelationalStructure.agda:63:isTransitiveStrRel : {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:65:  {X Y Z : Type ℓ}
Foundations\RelationalStructure.agda:72:-- The type of structures on a set should be a set
Foundations\RelationalStructure.agda:73:preservesSetsStr : (S : Type ℓ → Type ℓ') → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Foundations\RelationalStructure.agda:76:-- The type of structures on a prop-valued relation should be a prop
Foundations\RelationalStructure.agda:77:preservesPropsStrRel : {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:79:  {X Y : Type ℓ} {R : Rel X Y ℓ}
Foundations\RelationalStructure.agda:84:record SuitableStrRel (S : Type ℓ → Type ℓ') (ρ : StrRel S ℓ'') : Type (ℓ-max (ℓ-max (ℓ-suc ℓ)
ℓ') ℓ'')
Foundations\RelationalStructure.agda:95:quotientPropRel : ∀ {ℓ} {A : Type ℓ} (R : Rel A A ℓ) → PropRel A (A / R) ℓ
Foundations\RelationalStructure.agda:101:StrRelMatchesEquiv : {S : Type ℓ → Type ℓ'}
Foundations\RelationalStructure.agda:102:  → StrRel S ℓ'' → StrEquiv S ℓ''' → Type _
Foundations\RelationalStructure.agda:104:  (A B : TypeWithStr _ S) (e : typ A ≃ typ B) →
Foundations\RelationalStructure.agda:109:isDetransitiveStrRel : {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'') → Type _
Foundations\RelationalStructure.agda:111:  {X Y Z : Type ℓ}
Foundations\RelationalStructure.agda:117:record StrRelAction {S : Type ℓ → Type ℓ'} (ρ : StrRel S ℓ'')
Foundations\RelationalStructure.agda:118:  : Type (ℓ-max (ℓ-suc ℓ) (ℓ-max ℓ' ℓ''))
Foundations\RelationalStructure.agda:124:      {R₀ : X₀ → Y₀ → Type ℓ} {R₁ : X₁ → Y₁ → Type ℓ}
Foundations\RelationalStructure.agda:130:strRelQuotientComparison : {S : Type ℓ → Type ℓ'} {ρ : StrRel S ℓ''}
Foundations\RelationalStructure.agda:132:  {X : Type ℓ} (R : EquivPropRel X ℓ)
Foundations\RelationalStructure.agda:175:record PositiveStrRel {S : Type ℓ → Type ℓ'} {ρ : StrRel S ℓ''} (θ : SuitableStrRel S ρ)
Foundations\RelationalStructure.agda:176:  : Type (ℓ-max (ℓ-suc ℓ) (ℓ-max ℓ' ℓ''))
Foundations\RelationalStructure.agda:182:    quo : {X : Type ℓ} (R : EquivPropRel X ℓ) → isEquiv (strRelQuotientComparison θ act R)
Foundations\RelationalStructure.agda:186:posRelReflexive : {S : Type ℓ → Type ℓ'} {ρ : StrRel S ℓ''} {θ : SuitableStrRel S ρ}
Foundations\RelationalStructure.agda:188:  → {X : Type ℓ} (R : EquivPropRel X ℓ)
Foundations\RelationalStructure.agda:202:-- between structured types A and B, we get induced structures on the quotients A/(R ∙ R⁻¹)
and B/(R⁻¹ ∙ R),
Foundations\RelationalStructure.agda:206:record QERDescends (S : Type ℓ → Type ℓ') (ρ : StrRel S ℓ'')
Foundations\RelationalStructure.agda:207:  (A B : TypeWithStr ℓ S) (R : QuasiEquivRel (typ A) (typ B) ℓ) : Type (ℓ-max ℓ' ℓ'')
Foundations\RelationalStructure.agda:219:structuredQER→structuredEquiv : {S : Type ℓ → Type ℓ'} {ρ : StrRel S ℓ''}
Foundations\RelationalStructure.agda:221:  (A B : TypeWithStr ℓ S) (R : QuasiEquivRel (typ A) (typ B) ℓ)
Foundations\SIP.agda:25:    S : Type ℓ₁ → Type ℓ₂
Foundations\SIP.agda:27:-- Note that for any equivalence (f , e) : X ≃ Y the type  ι (X , s) (Y , t) (f , e) need not to be
Foundations\SIP.agda:28:-- a proposition. Indeed this type should correspond to the ways s and t can be identified
Foundations\SIP.agda:31:SNS : (S : Type ℓ₁ → Type ℓ₂) (ι : StrEquiv S ℓ₃) → Type (ℓ-max (ℓ-max (ℓ-suc ℓ₁) ℓ₂) ℓ₃)
Foundations\SIP.agda:32:SNS {ℓ₁} S ι = ∀ {X : Type ℓ₁} (s t : S X) → ι (X , s) (X , t) (idEquiv X) ≃ (s ≡ t)
Foundations\SIP.agda:37:_≃[_]_ : (A : TypeWithStr ℓ₁ S) (ι : StrEquiv S ℓ₂) (B : TypeWithStr ℓ₁ S) → Type (ℓ-max ℓ₁ ℓ₂)
Foundations\SIP.agda:44:UnivalentStr : (S : Type ℓ₁ → Type ℓ₂) (ι : StrEquiv S ℓ₃) → Type (ℓ-max (ℓ-max (ℓ-suc ℓ₁) ℓ₂) ℓ₃)
Foundations\SIP.agda:46:  {A B : TypeWithStr ℓ₁ S} (e : typ A ≃ typ B)
Foundations\SIP.agda:52:UnivalentStr→SNS : (S : Type ℓ₁ → Type ℓ₂) (ι : StrEquiv S ℓ₃)
Foundations\SIP.agda:68:  P : (X : Type _) → X ≃ Y → Type _
Foundations\SIP.agda:80:TransportStr : {S : Type ℓ → Type ℓ₁} (α : EquivAction S) → Type (ℓ-max (ℓ-suc ℓ) ℓ₁)
Foundations\SIP.agda:82:  {X Y : Type ℓ} (e : X ≃ Y) (s : S X) → equivFun (α e) s ≡ subst S (ua e) s
Foundations\SIP.agda:84:TransportStr→UnivalentStr : {S : Type ℓ → Type ℓ₁} (α : EquivAction S)
Foundations\SIP.agda:94:UnivalentStr→TransportStr : {S : Type ℓ → Type ℓ₁} (α : EquivAction S)
Foundations\SIP.agda:99:invTransportStr : {S : Type ℓ → Type ℓ₂} (α : EquivAction S) (τ : TransportStr α)
Foundations\SIP.agda:100:  {X Y : Type ℓ} (e : X ≃ Y) (t : S Y) → invEq (α e) t ≡ subst⁻ S (ua e) t
Foundations\SIP.agda:111:module _ {S : Type ℓ₁ → Type ℓ₂} {ι : StrEquiv S ℓ₃}
Foundations\SIP.agda:112:  (θ : UnivalentStr S ι) (A B : TypeWithStr ℓ₁ S)
Foundations\Structure.agda:9:    S : Type ℓ → Type ℓ'
Foundations\Structure.agda:11:-- A structure is a type-family S : Type ℓ → Type ℓ', i.e. for X : Type ℓ and s : S X,
Foundations\Structure.agda:12:-- the pair (X , s) : TypeWithStr ℓ S means that X is equipped with an S-structure, witnessed by s.
Foundations\Structure.agda:14:TypeWithStr : (ℓ : Level) (S : Type ℓ → Type ℓ') → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Foundations\Structure.agda:15:TypeWithStr ℓ S = Σ[ X ∈ Type ℓ ] S X
Foundations\Structure.agda:18: A helper to make a definition or the second component of a type with structure
Foundations\Structure.agda:23:makeOpaque : {A : Type ℓ'} → A → A
Foundations\Structure.agda:30:withOpaqueStr : {A : Type ℓ'} {B : A → Type ℓ''}
Foundations\Structure.agda:36:typ : TypeWithStr ℓ S → Type ℓ
Foundations\Structure.agda:39:str : (A : TypeWithStr ℓ S) → S (typ A)
Foundations\Structure.agda:43:⟨_⟩ : TypeWithStr ℓ S → Type ℓ
Foundations\Structure.agda:47:  mkTypeWithStr : ∀ {ℓ} {S : Type ℓ → Type ℓ'} {X} → {{S X}} → TypeWithStr ℓ S
Foundations\Structure.agda:48:  mkTypeWithStr {{i}} = _ , i
Foundations\Structure.agda:52:-- that gives us for any two types with S-structure (X , s) and (Y , t) a family:
Foundations\Structure.agda:53:--    ι (X , s) (Y , t) : (X ≃ Y) → Type ℓ''
Foundations\Structure.agda:54:StrEquiv : (S : Type ℓ → Type ℓ'') (ℓ' : Level) → Type (ℓ-max (ℓ-suc (ℓ-max ℓ ℓ')) ℓ'')
Foundations\Structure.agda:55:StrEquiv {ℓ} S ℓ' = (A B : TypeWithStr ℓ S) → typ A ≃ typ B → Type ℓ'
Foundations\Structure.agda:60:EquivAction : (S : Type ℓ → Type ℓ'') → Type (ℓ-max (ℓ-suc ℓ) ℓ'')
Foundations\Structure.agda:61:EquivAction {ℓ} S = {X Y : Type ℓ} → X ≃ Y → S X ≃ S Y
Foundations\Structure.agda:63:EquivAction→StrEquiv : {S : Type ℓ → Type ℓ''}
Foundations\Transport.agda:17:-- explicitly tell Agda that the type is constant (like in CHM)
Foundations\Transport.agda:18:transpFill : ∀ {ℓ} {A : Type ℓ}
Foundations\Transport.agda:20:             (A : (i : I) → Type ℓ [ φ ↦ (λ _ → A) ])
Foundations\Transport.agda:26:transport⁻ : ∀ {ℓ} {A B : Type ℓ} → A ≡ B → B → A
Foundations\Transport.agda:29:subst⁻ : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} (B : A → Type ℓ') (p : x ≡ y) → B y → B x
Foundations\Transport.agda:32:subst⁻-filler : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} (B : A → Type ℓ') (p : x ≡ y) (b : B y)
Foundations\Transport.agda:36:transport-fillerExt : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B)
Foundations\Transport.agda:40:transport⁻-fillerExt : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B)
Foundations\Transport.agda:44:transport-fillerExt⁻ : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B)
Foundations\Transport.agda:48:transport⁻-fillerExt⁻ : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B)
Foundations\Transport.agda:53:transport⁻-filler : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B) (x : B)
Foundations\Transport.agda:57:transport⁻Transport : ∀ {ℓ} {A B : Type ℓ} → (p : A ≡ B) → (a : A) →
Foundations\Transport.agda:61:transportTransport⁻ : ∀ {ℓ} {A B : Type ℓ} → (p : A ≡ B) → (b : B) →
Foundations\Transport.agda:65:subst⁻Subst : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} (B : A → Type ℓ') (p : x ≡ y)
Foundations\Transport.agda:69:substSubst⁻ : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} (B : A → Type ℓ') (p : x ≡ y)
Foundations\Transport.agda:73:substEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {a a' : A} (P : A → Type ℓ') (p : a ≡ a') → P a ≃ P a'
Foundations\Transport.agda:76:subst2Equiv : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {a a' : A} {b b' : B} (P : A → B → Type ℓ'')
Foundations\Transport.agda:80:liftEquiv : ∀ {ℓ ℓ'} {A B : Type ℓ} (P : Type ℓ → Type ℓ') (e : A ≃ B) → P A ≃ P B
Foundations\Transport.agda:83:transpEquiv : ∀ {ℓ} {A B : Type ℓ} (p : A ≡ B) → ∀ i → p i ≃ B
Foundations\Transport.agda:87:uaTransportη : ∀ {ℓ} {A B : Type ℓ} (P : A ≡ B) → ua (pathToEquiv P) ≡ P
Foundations\Transport.agda:91:pathToIso : ∀ {ℓ} {A B : Type ℓ} → A ≡ B → Iso A B
Foundations\Transport.agda:97:substIso : ∀ {ℓ ℓ'} {A : Type ℓ} (B : A → Type ℓ') {x y : A} (p : x ≡ y) → Iso (B x) (B y)
Foundations\Transport.agda:101:substEquiv' : ∀ {ℓ ℓ'} {A : Type ℓ} (B : A → Type ℓ') {x y : A} (p : x ≡ y) → B x ≃ B y
Foundations\Transport.agda:104:isInjectiveTransport : ∀ {ℓ : Level} {A B : Type ℓ} {p q : A ≡ B}
Foundations\Transport.agda:117:transportUaInv : ∀ {ℓ} {A B : Type ℓ} (e : A ≃ B) → transport (ua (invEquiv e)) ≡ transport (sym (ua e))
Foundations\Transport.agda:123:isSet-subst : ∀ {ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'}
Foundations\Transport.agda:130:substComposite : ∀ {ℓ ℓ'} {A : Type ℓ} → (B : A → Type ℓ')
Foundations\Transport.agda:137:transportComposite : ∀ {ℓ} {A B C : Type ℓ} (p : A ≡ B) (q : B ≡ C) (x : A)
Foundations\Transport.agda:142:substCommSlice : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ}
Foundations\Transport.agda:143:                   → (B : A → Type ℓ') (C : A → Type ℓ'')
Foundations\Transport.agda:150:constSubstCommSlice : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ}
Foundations\Transport.agda:151:                   → (B : A → Type ℓ')
Foundations\Transport.agda:152:                   → (C : Type ℓ'')
Foundations\Transport.agda:160:funTypeTransp : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} (B : A → Type ℓ') (C : A → Type ℓ'') {x y : A} (p : x ≡ y) (f
: B x → C x)
Foundations\Transport.agda:162:funTypeTransp B C {x = x} p f i b =
Foundations\Transport.agda:166:overPathFunct : ∀ {ℓ} {A : Type ℓ} {x y : A} (p q : x ≡ x) (P : x ≡ y)
Foundations\Transport.agda:175:substInPaths : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}  {a a' : A}
Foundations\Transport.agda:188:flipTransport : ∀ {ℓ} {A : I → Type ℓ} {x : A i0} {y : A i1}
Foundations\Transport.agda:195:module _ {ℓ : Level} {A : Type ℓ} {a x1 x2 : A} (p : x1 ≡ x2) where
Foundations\Transport.agda:212:transport-filler-ua : ∀ {ℓ} {A B : Type ℓ} (e : A ≃ B) (a : A)
Foundations\Univalence.agda:6:- Re-exports Glue types from Cubical.Core.Glue
Foundations\Univalence.agda:35:ua : ∀ {A B : Type ℓ} → A ≃ B → A ≡ B
Foundations\Univalence.agda:39:uaIdEquiv : {A : Type ℓ} → ua (idEquiv A) ≡ refl
Foundations\Univalence.agda:43:hPropExt : {A B : Type ℓ} → isProp A → isProp B → (A → B) → (B → A) → A ≡ B
Foundations\Univalence.agda:48:ua-unglue : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : ua e i)
Foundations\Univalence.agda:52:ua-glue : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : Partial (~ i) A)
Foundations\Univalence.agda:57:module _ {A B : Type ℓ} (e : A ≃ B) {x : A} {y : B} where
Foundations\Univalence.agda:71:ua-ungluePathExt : {A B : Type ℓ} (e : A ≃ B) → PathP (λ i → ua e i → B) (fst e) (idfun B)
Foundations\Univalence.agda:74:ua-gluePathExt : {A B : Type ℓ} (e : A ≃ B) → PathP (λ i → A → ua e i) (idfun _) (fst e)
Foundations\Univalence.agda:79:-- strengthening the types of ua-unglue and ua-glue gives a nicer formulation of this, see below
Foundations\Univalence.agda:81:ua-unglue-glue : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : Partial (~ i) A) (y : B [ _ ↦ _ ])
Foundations\Univalence.agda:85:ua-glue-unglue : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : ua e i)
Foundations\Univalence.agda:89:-- mainly for documentation purposes, ua-unglue and ua-glue wrapped in cubical subtypes
Foundations\Univalence.agda:91:ua-unglueS : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : A) (y : B)
Foundations\Univalence.agda:96:ua-glueS : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : A) (y : B)
Foundations\Univalence.agda:101:ua-unglueS-glueS : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : A) (y : B)
Foundations\Univalence.agda:106:ua-glueS-unglueS : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : A) (y : B)
Foundations\Univalence.agda:113:ua-gluePt : ∀ {A B : Type ℓ} (e : A ≃ B) (i : I) (x : A)
Foundations\Univalence.agda:121:unglueIsEquiv : ∀ (A : Type ℓ) (φ : I)
Foundations\Univalence.agda:122:                (f : PartialP φ (λ o → Σ[ T ∈ Type ℓ ] T ≃ A)) →
Foundations\Univalence.agda:141:unglueEquiv : ∀ (A : Type ℓ) (φ : I)
Foundations\Univalence.agda:142:              (f : PartialP φ (λ o → Σ[ T ∈ Type ℓ ] T ≃ A)) →
Foundations\Univalence.agda:146:ua-unglueEquiv : ∀ {A B : Type ℓ} (e : A ≃ B) →
Foundations\Univalence.agda:156:-- https://groups.google.com/forum/#!msg/homotopytypetheory/HfCB_b-PNEU/Ibb48LvUMeUJ
Foundations\Univalence.agda:164:EquivContr : ∀ (A : Type ℓ) → ∃![ T ∈ Type ℓ ] (T ≃ A)
Foundations\Univalence.agda:169:  idEquiv≡ : (y : Σ (Type ℓ) (λ T → T ≃ A)) → (A , idEquiv A) ≡ y
Foundations\Univalence.agda:175:      f : ∀ i → PartialP (~ i ∨ i) (λ x → Σ[ T ∈ Type ℓ ] T ≃ A)
Foundations\Univalence.agda:178:contrSinglEquiv : {A B : Type ℓ} (e : A ≃ B) → (B , idEquiv B) ≡ (A , e)
Foundations\Univalence.agda:183:EquivJ : {A B : Type ℓ} (P : (A : Type ℓ) → (e : A ≃ B) → Type ℓ')
Foundations\Univalence.agda:188:-- The proof is a special case of isEquivTransp where the line of types is
Foundations\Univalence.agda:190:isEquivTransport : {A B : Type ℓ} (p : A ≡ B) → isEquiv (transport p)
Foundations\Univalence.agda:192:  A : I → Type _
Foundations\Univalence.agda:198:pathToEquiv : {A B : Type ℓ} → A ≡ B → A ≃ B
Foundations\Univalence.agda:202:pathToEquivRefl : {A : Type ℓ} → pathToEquiv refl ≡ idEquiv A
Foundations\Univalence.agda:208:uaβ : {A B : Type ℓ} (e : A ≃ B) (x : A) → transport (ua e) x ≡ equivFun e x
Foundations\Univalence.agda:211:~uaβ : {A B : Type ℓ} (e : A ≃ B) (x : B) → transport (sym (ua e)) x ≡ invEq e x
Foundations\Univalence.agda:214:uaη : ∀ {A B : Type ℓ} → (P : A ≡ B) → ua (pathToEquiv P) ≡ P
Foundations\Univalence.agda:219:  sides : Partial φ (Σ[ T ∈ Type _ ] T ≃ B)
Foundations\Univalence.agda:224:pathToEquiv-ua : {A B : Type ℓ} (e : A ≃ B) → pathToEquiv (ua e) ≡ e
Foundations\Univalence.agda:227:ua-pathToEquiv : {A B : Type ℓ} (p : A ≡ B) → ua (pathToEquiv p) ≡ p
Foundations\Univalence.agda:231:univalenceIso : {A B : Type ℓ} → Iso (A ≡ B) (A ≃ B)
Foundations\Univalence.agda:237:isEquivPathToEquiv : {A B : Type ℓ} → isEquiv (pathToEquiv {A = A} {B = B})
Foundations\Univalence.agda:240:univalence : {A B : Type ℓ} → (A ≡ B) ≃ (A ≃ B)
Foundations\Univalence.agda:245:module Univalence (au : ∀ {ℓ} {A B : Type ℓ} → A ≡ B → A ≃ B)
Foundations\Univalence.agda:246:                  (aurefl : ∀ {ℓ} {A : Type ℓ} → au refl ≡ idEquiv A) where
Foundations\Univalence.agda:248:  ua-au : {A B : Type ℓ} (p : A ≡ B) → ua (au p) ≡ p
Foundations\Univalence.agda:252:  au-ua : {A B : Type ℓ} (e : A ≃ B) → au (ua e) ≡ e
Foundations\Univalence.agda:256:  isoThm : ∀ {ℓ} {A B : Type ℓ} → Iso (A ≡ B) (A ≃ B)
Foundations\Univalence.agda:262:  thm : ∀ {ℓ} {A B : Type ℓ} → isEquiv au
Foundations\Univalence.agda:266:eqweqmap : {A B : Type ℓ} → A ≡ B → A ≃ B
Foundations\Univalence.agda:269:eqweqmapid : {A : Type ℓ} → eqweqmap refl ≡ idEquiv A
Foundations\Univalence.agda:272:univalenceStatement : {A B : Type ℓ} → isEquiv (eqweqmap {ℓ} {A} {B})
Foundations\Univalence.agda:275:univalenceUAH : {A B : Type ℓ} → (A ≡ B) ≃ (A ≃ B)
Foundations\Univalence.agda:278:univalencePath : {A B : Type ℓ} → (A ≡ B) ≡ Lift _ (A ≃ B)
Foundations\Univalence.agda:281:-- Lemmas for constructing and destructing dependent paths in a function type where the domain is ua.
Foundations\Univalence.agda:282:ua→ : ∀ {ℓ ℓ'} {A₀ A₁ : Type ℓ} {e : A₀ ≃ A₁} {B : (i : I) → Type ℓ'}
Foundations\Univalence.agda:297:ua→⁻ : ∀ {ℓ ℓ'} {A₀ A₁ : Type ℓ} {e : A₀ ≃ A₁} {B : (i : I) → Type ℓ'}
Foundations\Univalence.agda:309:ua→2 : ∀ {ℓ ℓ' ℓ''} {A₀ A₁ : Type ℓ} {e₁ : A₀ ≃ A₁}
Foundations\Univalence.agda:310:  {B₀ B₁ : Type ℓ'} {e₂ : B₀ ≃ B₁}
Foundations\Univalence.agda:311:  {C : (i : I) → Type ℓ''}
Foundations\Univalence.agda:319:transportUAop₁ : ∀ {A B : Type ℓ} → (e : A ≃ B) (f : A → A) (x : B)
Foundations\Univalence.agda:324:transportUAop₂ : ∀ {ℓ} {A B : Type ℓ} → (e : A ≃ B) (f : A → A → A) (x y : B)
Foundations\Univalence.agda:332:elimEquivFun : {A B : Type ℓ} (P : (A : Type ℓ) → (A → B) → Type ℓ')
Foundations\Univalence.agda:337:elimIso : {B : Type ℓ} → (Q : {A : Type ℓ} → (A → B) → (B → A) → Type ℓ') →
Foundations\Univalence.agda:338:          (h : Q (idfun B) (idfun B)) → {A : Type ℓ} →
Foundations\Univalence.agda:342:  P : (A : Type ℓ) → (f : A → B) → Type (ℓ-max ℓ' ℓ)
Foundations\Univalence.agda:348:  rem1 : {A : Type ℓ} → (f : A → B) → P A f
Foundations\Univalence.agda:352:uaInvEquiv : ∀ {A B : Type ℓ} → (e : A ≃ B) → ua (invEquiv e) ≡ sym (ua e)
Foundations\Univalence.agda:356:uaCompEquiv : ∀ {A B C : Type ℓ} → (e : A ≃ B) (f : B ≃ C) → ua (compEquiv e f) ≡ ua e ∙ ua f
Foundations\Cubes\Base.agda:5:- The definition of the type of n-cubes;
Foundations\Cubes\Base.agda:22:    A : Type ℓ
Foundations\Cubes\Base.agda:25:-- The Type of n-Cubes
Foundations\Cubes\Base.agda:33:  Cube    : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes\Base.agda:34:  ∂Cube₀₁ : (n : ℕ) (A : Type ℓ) (a₀ a₁ : Cube n A) → Type ℓ
Foundations\Cubes\Base.agda:35:  ∂Cube   : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes\Base.agda:36:  CubeRel : (n : ℕ) (A : Type ℓ) → ∂Cube n A → Type ℓ
Foundations\Cubes\Base.agda:55:∂_ : {n : ℕ}{A : Type ℓ} → Cube n A → ∂Cube n A
Foundations\Cubes\Base.agda:59:∂₀ : {n : ℕ}{A : Type ℓ} → Cube (suc n) A → Cube n A
Foundations\Cubes\Base.agda:63:∂₁ : {n : ℕ}{A : Type ℓ} → Cube (suc n) A → Cube n A
Foundations\Cubes\Base.agda:67:∂ᵇ₀ : {n : ℕ}{A : Type ℓ} → ∂Cube (suc n) A → Cube n A
Foundations\Cubes\Base.agda:71:∂ᵇ₁ : {n : ℕ}{A : Type ℓ} → ∂Cube (suc n) A → Cube n A
Foundations\Cubes\Base.agda:76:make∂ : {n : ℕ}{A : Type ℓ}{∂₀ ∂₁ : ∂Cube n A} → ∂₀ ≡ ∂₁ → CubeRel n A ∂₀ → CubeRel n A ∂₁ → ∂Cube (suc
n) A
Foundations\Cubes\Base.agda:80:makeCube : {n : ℕ}{A : Type ℓ}{a₀ a₁ : Cube n A} → a₀ ≡ a₁ → Cube (suc n) A
Foundations\Cubes\Base.agda:86:-- because Agda doesn't support pattern matching on ℕ towards pre-types.
Foundations\Cubes\Base.agda:92:∂Cube₀₁→∂Cube : {n : ℕ}{A : Type ℓ}{a₀ a₁ : Cube n A} → ∂Cube₀₁ n A a₀ a₁ → ∂Cube (suc n) A
Foundations\Cubes\Base.agda:96:CubeRel→Cube : {n : ℕ}{A : Type ℓ}{∂ : ∂Cube n A} → CubeRel n A ∂ → Cube n A
Foundations\Cubes\Base.agda:104:  {n : ℕ} {A : Type ℓ}
Foundations\Cubes\Base.agda:111:  {n : ℕ} {A : Type ℓ}
Foundations\Cubes\Base.agda:121:constCube : {n : ℕ}{A : Type ℓ} → Cube n A → Cube (suc n) A
Foundations\Cubes\Base.agda:125:retConst : {n : ℕ}{A : Type ℓ} → (cube : Cube n A) → ∂₀ (constCube {n = n} cube) ≡ cube
Foundations\Cubes\Base.agda:129:secConst : {n : ℕ}{A : Type ℓ} → (cube : Cube (suc n) A) → constCube (∂₀ cube) ≡ cube
Foundations\Cubes\Base.agda:133:isEquivConstCube : {n : ℕ}{A : Type ℓ} → isEquiv (constCube {n = n} {A = A})
Foundations\Cubes\Base.agda:139:const : (n : ℕ){A : Type ℓ} → A → Cube n A
Foundations\Cubes\Base.agda:143:isEquivConst : {n : ℕ}{A : Type ℓ} → isEquiv (const n {A = A})
Foundations\Cubes\Base.agda:147:cubeEquiv : {n : ℕ}{A : Type ℓ} → A ≃ Cube n A
Foundations\Cubes\Base.agda:150:makeConst : {n : ℕ}{A : Type ℓ} → (cube : Cube n A) → Σ[ a ∈ A ] cube ≡ const n a
Foundations\Cubes\Base.agda:153:makeConstUniq : {n : ℕ}{A : Type ℓ} → (a : A) → makeConst (const n a) ≡ (a , refl)
Foundations\Cubes\Base.agda:160:const∂ : (n : ℕ){A : Type ℓ} → A → ∂Cube n A
Foundations\Cubes\Base.agda:168:module _ {n : ℕ} {A : Type ℓ}
Foundations\Cubes\Base.agda:169:  (P : Cube n A → Type ℓ') (d : (a : A) → P (const _ a)) where
Foundations\Cubes\Dependent.agda:7:- The definition of the type of dependent n-cubes;
Foundations\Cubes\Dependent.agda:31:    A : Type ℓ
Foundations\Cubes\Dependent.agda:34:-- The Type of Dependent n-Cubes
Foundations\Cubes\Dependent.agda:38:  CubeDep    : {A : Type ℓ} (B : A → Type ℓ') →  Cube n A → Type ℓ'
Foundations\Cubes\Dependent.agda:39:  ∂CubeDep   : {A : Type ℓ} (B : A → Type ℓ') → ∂Cube n A → Type ℓ'
Foundations\Cubes\Dependent.agda:40:  CubeDepRel : {A : Type ℓ} {B : A → Type ℓ'} (a₋ : Cube n A) → ∂CubeDep {n = n} B (∂ a₋) → Type ℓ'
Foundations\Cubes\Dependent.agda:58:∂CubeDepConst : (n : ℕ) (B : A → Type ℓ') (a : A) → Type ℓ'
Foundations\Cubes\Dependent.agda:61:CubeDepConstRel : {n : ℕ} {B : A → Type ℓ'} {a : A} → ∂CubeDepConst n B a → Type ℓ'
Foundations\Cubes\Dependent.agda:69:  ∂CubeDepConst→∂Cube : (n : ℕ) (B : A → Type ℓ') (a : A) → ∂CubeDepConst n B a → ∂Cube n (B a)
Foundations\Cubes\Dependent.agda:71:  CubeDepConstRel→CubeRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:89:  ∂Cube→∂CubeDepConst : (n : ℕ) (B : A → Type ℓ') (a : A) → ∂Cube n (B a) → ∂CubeDepConst n B a
Foundations\Cubes\Dependent.agda:91:  CubeRel→CubeDepConstRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:109:  ∂CubeDepConst→∂Cube→∂CubeDepConst : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:112:  CubeDepConstRel→CubeRel→CubeDepConstRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:132:  ∂Cube→∂CubeDepConst→∂Cube : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:135:  CubeRel→CubeDepConstRel→CubeDepConstRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:155:Iso-∂CubeDepConst-∂Cube : (n : ℕ) (B : A → Type ℓ') (a : A) → Iso (∂CubeDepConst n B a) (∂Cube n
(B a))
Foundations\Cubes\Dependent.agda:163:HAEquiv-∂CubeDepConst-∂Cube : (n : ℕ) (B : A → Type ℓ') (a : A) → HAEquiv (∂CubeDepConst n B a)
(∂Cube n (B a))
Foundations\Cubes\Dependent.agda:166:IsoOver-CubeDepConstRel-CubeRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:172:∂CubeDepConst≡∂Cube : (n : ℕ) (B : A → Type ℓ') (a : A) → ∂CubeDepConst n B a ≡ ∂Cube n (B a)
Foundations\Cubes\Dependent.agda:175:CubeDepConstRel≡CubeRel : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\Dependent.agda:176:  → PathP (λ i → ∂CubeDepConst≡∂Cube n B a i → Type ℓ') CubeDepConstRel (CubeRel n (B a))
Foundations\Cubes\HLevels.agda:12:open import Cubical.Foundations.Cubes.Subtypes
Foundations\Cubes\HLevels.agda:21:    A : Type ℓ
Foundations\Cubes\HLevels.agda:22:    B : A → Type ℓ'
Foundations\Cubes\HLevels.agda:36:isCubeFilled : ℕ → Type ℓ → Type ℓ
Foundations\Cubes\HLevels.agda:43:isCubeFilledPath : ℕ → Type ℓ → Type ℓ
Foundations\Cubes\HLevels.agda:46:isCubeFilledPath≡Suc : (n : ℕ) (A : Type ℓ)
Foundations\Cubes\HLevels.agda:56:isCubeFilledPath→Suc : (n : ℕ) (A : Type ℓ)
Foundations\Cubes\HLevels.agda:61:isCubeFilledSuc→Path : (n : ℕ) (A : Type ℓ)
Foundations\Cubes\HLevels.agda:89:isCubeFilledDep : (n : ℕ) {A : Type ℓ} (B : A → Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Cubes\HLevels.agda:96:isCubeFilledDepConst : (n : ℕ) (B : A → Type ℓ') (a : A) → Type ℓ'
Foundations\Cubes\HLevels.agda:101:isCubeFilledDepConst≡Fiber : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\HLevels.agda:107:isCubeFilledDepConst→Fiber : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\HLevels.agda:112:isCubeFilledFiber→DepConst : (n : ℕ) (B : A → Type ℓ') (a : A)
Foundations\Cubes\HLevels.agda:120:isOfHLevelDep→isCubeFilledDep : (n : HLevel) {B : A → Type ℓ'} → isOfHLevelDep n B → isCubeFilledDep
n B
Foundations\Cubes\HLevels.agda:129:isCubeFilledDep→isOfHLevelDep : (n : HLevel) {B : A → Type ℓ'} → isCubeFilledDep n B → isOfHLevelDep
n B
Foundations\Cubes\Subtypes.agda:5:- Some cases of internal cubical subtypes (extension types);
Foundations\Cubes\Subtypes.agda:7:- Cubes with a pair of fixed constant opposite faces is equivalent to cubes in the path type;
Foundations\Cubes\Subtypes.agda:13:module Cubical.Foundations.Cubes.Subtypes where
Foundations\Cubes\Subtypes.agda:30:    A : Type ℓ
Foundations\Cubes\Subtypes.agda:35:  Cubical Subtypes
Foundations\Cubes\Subtypes.agda:42:∂CubeConst₀₁ : (n : ℕ) (A : Type ℓ) → (a₀ a₁ : A) → Type ℓ
Foundations\Cubes\Subtypes.agda:45:CubeRelConst₀₁ : (n : ℕ) (A : Type ℓ) {a₀ a₁ : A} → ∂CubeConst₀₁ n A a₀ a₁ → Type ℓ
Foundations\Cubes\Subtypes.agda:48:CubeConst₀₁ : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes\Subtypes.agda:54:  The equivalence of cubes with fixed constant opposite faces and cubes in the path type
Foundations\Cubes\Subtypes.agda:62:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:66:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}{∂₀₁ : ∂CubeConst₀₁ n A a₀ a₁}
Foundations\Cubes\Subtypes.agda:85:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:89:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}{∂ : ∂Cube n (a₀ ≡ a₁)}
Foundations\Cubes\Subtypes.agda:107:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:112:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}{∂₀₁ : ∂CubeConst₀₁ n A a₀ a₁}
Foundations\Cubes\Subtypes.agda:133:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:138:    {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}{∂ : ∂Cube n (a₀ ≡ a₁)}
Foundations\Cubes\Subtypes.agda:158:Iso-∂CubeConst₀₁-Path : {n : ℕ}{A : Type ℓ}{a₀ a₁ : A} → Iso (∂CubeConst₀₁ n A a₀ a₁) (∂Cube n (a₀
≡ a₁))
Foundations\Cubes\Subtypes.agda:165:HAEquiv-∂CubeConst₀₁-Path : {n : ℕ}{A : Type ℓ}{a₀ a₁ : A} → HAEquiv (∂CubeConst₀₁ n A a₀ a₁)
(∂Cube n (a₀ ≡ a₁))
Foundations\Cubes\Subtypes.agda:168:IsoOver-CubeRelConst₀₁-Path : {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:174:∂CubeConst₀₁≡∂CubePath : {n : ℕ}{A : Type ℓ}{a₀ a₁ : A} → ∂CubeConst₀₁ n A a₀ a₁ ≡ ∂Cube n (a₀ ≡ a₁)
Foundations\Cubes\Subtypes.agda:177:CubeRelConst₀₁≡CubeRelPath : {n : ℕ}{A : Type ℓ}{a₀ a₁ : A}
Foundations\Cubes\Subtypes.agda:178:  → PathP (λ i → ∂CubeConst₀₁≡∂CubePath {n = n} {A} {a₀} {a₁} i → Type ℓ) (CubeRelConst₀₁ n A)
(CubeRel n (a₀ ≡ a₁))
Foundations\Cubes\Subtypes.agda:191:Σ∂CubeConst₀₁ : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes\Subtypes.agda:194:ΣCubeRelConst₀₁ : (n : ℕ) (A : Type ℓ) → Σ∂CubeConst₀₁ n A → Type ℓ
Foundations\Cubes\Subtypes.agda:197:ΣCubeConst₀₁ : (n : ℕ) (A : Type ℓ) → Type ℓ
Foundations\Cubes\Subtypes.agda:203:∂CubeConst₀₁≃∂CubeSuc : {n : ℕ} {A : Type ℓ} → Σ∂CubeConst₀₁ (suc n) A ≃ ∂Cube (suc (suc n)) A
Foundations\Cubes\Subtypes.agda:206:HAEquiv-∂CubeConst₀₁-∂CubeSuc : {n : ℕ}{A : Type ℓ} → HAEquiv (Σ∂CubeConst₀₁ (suc n) A) (∂Cube (suc
(suc n)) A)
Foundations\Cubes\Subtypes.agda:209:IsoOver-CubeRelConst₀₁-CubeRelSuc : {n : ℕ} {A : Type ℓ}
Foundations\Cubes\Subtypes.agda:213:∂CubeConst₀₁≡∂CubeSuc : {n : ℕ} {A : Type ℓ} → Σ∂CubeConst₀₁ (suc n) A ≡ ∂Cube (suc (suc n)) A
Foundations\Cubes\Subtypes.agda:216:CubeRelConst₀₁≡CubeRelSuc : {n : ℕ}{A : Type ℓ}
Foundations\Cubes\Subtypes.agda:217:  → PathP (λ i → ∂CubeConst₀₁≡∂CubeSuc {n = n} {A} i → Type ℓ) (ΣCubeRelConst₀₁ (suc n) A) (CubeRel
(suc (suc n)) A)
Foundations\Equiv\Base.agda:9:fiber : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) (y : B) → Type (ℓ-max ℓ ℓ')
Foundations\Equiv\Base.agda:13:-- equality. For such (f,g), the result type simplifies to isContr (fiber f b).
Foundations\Equiv\Base.agda:14:strictContrFibers : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {f : A → B} (g : B → A) (b : B)
Foundations\Equiv\Base.agda:21:idIsEquiv : ∀ {ℓ} (A : Type ℓ) → isEquiv (idfun A)
Foundations\Equiv\Base.agda:24:idEquiv : ∀ {ℓ} (A : Type ℓ) → A ≃ A
Foundations\Equiv\Base.agda:28:-- the definition using Π-type
Foundations\Equiv\Base.agda:29:isEquiv' : ∀ {ℓ}{ℓ'}{A : Type ℓ}{B : Type ℓ'} → (A → B) → Type (ℓ-max ℓ ℓ')
Foundations\Equiv\Base.agda:32:-- Transport along a line of types A, constant on some extent φ, is an equivalence.
Foundations\Equiv\Base.agda:33:isEquivTransp : ∀ {ℓ : I → Level} (A : (i : I) → Type (ℓ i)) → ∀ (φ : I) → isEquiv (transp (λ j → A (φ ∨
j)) φ)
Foundations\Equiv\Base.agda:41:  -- A line of types, interpolating between propositions:
Foundations\Equiv\Base.agda:44:  γ : (k : I) → Type _
Foundations\Equiv\Base.agda:62:transpEquiv : ∀ {ℓ : I → Level} (A : (i : I) → Type (ℓ i)) → ∀ φ → A φ ≃ A i1
Foundations\Equiv\BiInvertible.agda:26:    A : Type ℓ
Foundations\Equiv\BiInvertible.agda:27:    B : Type ℓ'
Foundations\Equiv\BiInvertible.agda:28:    C : Type ℓ''
Foundations\Equiv\BiInvertible.agda:29:    P : A → Type ℓ''
Foundations\Equiv\BiInvertible.agda:30:    Q : B → Type ℓ'''
Foundations\Equiv\BiInvertible.agda:33:record BiInvEquiv {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
Foundations\Equiv\BiInvertible.agda:60:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (e : BiInvEquiv A B) where
Foundations\Equiv\BiInvertible.agda:85:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (i : Iso A B) where
Foundations\Equiv\BiInvertible.agda:121:  {A : Type ℓ} {B : Type ℓ'}
Foundations\Equiv\BiInvertible.agda:123:  (P : A → Type ℓ'') (Q : B → Type ℓ''')
Foundations\Equiv\BiInvertible.agda:124:    : Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-max ℓ'' ℓ''')) where
Foundations\Equiv\BiInvertible.agda:135:  {A : Type ℓ} {B : Type ℓ'}
Foundations\Equiv\BiInvertible.agda:137:  (P : A → Type ℓ'') (Q : B → Type ℓ''')
Foundations\Equiv\BiInvertible.agda:139:    : Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-max ℓ'' ℓ''')) where
Foundations\Equiv\BiInvertible.agda:176:  {A : Type ℓA} {B : Type ℓB} {C : Type ℓC}
Foundations\Equiv\BiInvertible.agda:177:  {P : A → Type ℓP} {Q : B → Type ℓQ} {R : C → Type ℓR}
Foundations\Equiv\BiInvertible.agda:207:  {A : Type ℓA}
Foundations\Equiv\BiInvertible.agda:208:  {P : A → Type ℓP} {Q : A → Type ℓQ}
Foundations\Equiv\BiInvertible.agda:219:  {A : Type ℓA}{B : Type ℓB}
Foundations\Equiv\BiInvertible.agda:220:  {P : B → Type ℓP}
Foundations\Equiv\Dependent.agda:5:Extremely useful if one wants to construct explicit isomorphisms between record types
Foundations\Equiv\Dependent.agda:25:    A : Type ℓ
Foundations\Equiv\Dependent.agda:26:    B : Type ℓ'
Foundations\Equiv\Dependent.agda:27:    P : A → Type ℓ''
Foundations\Equiv\Dependent.agda:28:    Q : B → Type ℓ'''
Foundations\Equiv\Dependent.agda:35:  (P : A → Type ℓ'')(Q : B → Type ℓ''')
Foundations\Equiv\Dependent.agda:36:  → Type _
Foundations\Equiv\Dependent.agda:41:  {A : Type ℓA}{B : Type ℓB}{C : Type ℓC}
Foundations\Equiv\Dependent.agda:42:  {P : A → Type ℓP}{Q : B → Type ℓQ}{R : C → Type ℓR}
Foundations\Equiv\Dependent.agda:54:  → Type _
Foundations\Equiv\Dependent.agda:69:  → Type _
Foundations\Equiv\Dependent.agda:77:  → Type _
Foundations\Equiv\Dependent.agda:86:record IsoOver {ℓ ℓ'} {A : Type ℓ}{B : Type ℓ'}
Foundations\Equiv\Dependent.agda:87:  (isom : Iso A B)(P : A → Type ℓ'')(Q : B → Type ℓ''')
Foundations\Equiv\Dependent.agda:88:  : Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-max ℓ'' ℓ''')) where
Foundations\Equiv\Dependent.agda:97:record isIsoOver {ℓ ℓ'} {A : Type ℓ}{B : Type ℓ'}
Foundations\Equiv\Dependent.agda:98:  (isom : Iso A B)(P : A → Type ℓ'')(Q : B → Type ℓ''')
Foundations\Equiv\Dependent.agda:100:  : Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-max ℓ'' ℓ''')) where
Foundations\Equiv\Dependent.agda:138:  {A : Type ℓA}{B : Type ℓB}{C : Type ℓC}
Foundations\Equiv\Dependent.agda:139:  {P : A → Type ℓP}{Q : B → Type ℓQ}{R : C → Type ℓR}
Foundations\Equiv\Dependent.agda:168:  {A : Type ℓA}
Foundations\Equiv\Dependent.agda:169:  {P : A → Type ℓP}{Q : A → Type ℓQ}
Foundations\Equiv\Dependent.agda:184:  {A : Type ℓA}{B : Type ℓB}
Foundations\Equiv\Dependent.agda:185:  {P : B → Type ℓP}
Foundations\Equiv\Dependent.agda:241:  {A : Type ℓ } {P : A → Type ℓ'' }
Foundations\Equiv\Dependent.agda:242:  {B : Type ℓ'} {Q : B → Type ℓ'''}
Foundations\Equiv\Dependent.agda:263:record isHAEquivOver {ℓ ℓ'} {A : Type ℓ}{B : Type ℓ'}
Foundations\Equiv\Dependent.agda:264:  (hae : HAEquiv A B)(P : A → Type ℓ'')(Q : B → Type ℓ''')
Foundations\Equiv\Dependent.agda:266:  : Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-max ℓ'' ℓ''')) where
Foundations\Equiv\Dependent.agda:277:HAEquivOver : (P : A → Type ℓ'')(Q : B → Type ℓ''')(hae : HAEquiv A B) → Type _
Foundations\Equiv\Fiberwise.agda:15:module _ {A : Type ℓ} (P : A → Type ℓ') (Q : A → Type ℓ'')
Foundations\Equiv\Fiberwise.agda:48:module _ {U : Type ℓ} (_~_ : U → U → Type ℓ')
Foundations\Equiv\Fiberwise.agda:64:  The following is called fundamental theorem of identity types in Egbert Rijke's
Foundations\Equiv\Fiberwise.agda:65:  introduction to homotopy type theory.
Foundations\Equiv\Fiberwise.agda:67:recognizeId : {A : Type ℓ} {a : A} (Eq : A → Type ℓ')
Foundations\Equiv\Fiberwise.agda:85:fundamentalTheoremOfId : {A : Type ℓ} (Eq : A → A → Type ℓ')
Foundations\Equiv\Fiberwise.agda:92:  {A : Type ℓ} (Eq : A → A → Type ℓ')
Foundations\Equiv\HalfAdjoint.agda:20:    A : Type ℓ
Foundations\Equiv\HalfAdjoint.agda:21:    B : Type ℓ'
Foundations\Equiv\HalfAdjoint.agda:23:record isHAEquiv {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) : Type (ℓ-max ℓ ℓ') where
Foundations\Equiv\HalfAdjoint.agda:65:HAEquiv : (A : Type ℓ) (B : Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Equiv\PathSplit.agda:30:record isPathSplitEquiv {ℓ ℓ'} {A : Type  ℓ} {B : Type ℓ'} (f : A → B) : Type (ℓ-max ℓ ℓ') where
Foundations\Equiv\PathSplit.agda:35:PathSplitEquiv : ∀ {ℓ ℓ'} (A : Type  ℓ) (B : Type ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Equiv\PathSplit.agda:40:idIsPathSplitEquiv : ∀ {ℓ} {A : Type ℓ} → isPathSplitEquiv (λ (x : A) → x)
Foundations\Equiv\PathSplit.agda:44:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} where
Foundations\Equiv\PathSplit.agda:66:module _ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} where
Foundations\Equiv\PathSplit.agda:92:  PathSplitEquiv is a proposition and the type
Foundations\Equiv\PathSplit.agda:93:  of path split equivs is equivalent to the type of equivalences
Foundations\Equiv\PathSplit.agda:95:isPropIsPathSplitEquiv : ∀ {ℓ} {ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) → isProp
(isPathSplitEquiv f)
Foundations\Equiv\PathSplit.agda:116:module _ {ℓ} {A B : Type ℓ} where
Foundations\Equiv\PathSplit.agda:133:secCongDep : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : A → Type ℓ'} {C : A → Type ℓ''}
Foundations\Equiv\Properties.agda:30:    A B C : Type ℓ
Foundations\Equiv\Properties.agda:70:hasSection : (A → B) → Type _
Foundations\Equiv\Properties.agda:73:hasRetract : (A → B) → Type _
Foundations\Equiv\Properties.agda:155:cong≃ : (F : Type ℓ → Type ℓ') → (A ≃ B) → F A ≃ F B
Foundations\Equiv\Properties.agda:158:cong≃-char : (F : Type ℓ → Type ℓ') {A B : Type ℓ} (e : A ≃ B) → ua (cong≃ F e) ≡ cong F (ua e)
Foundations\Equiv\Properties.agda:161:cong≃-idEquiv : (F : Type ℓ → Type ℓ') (A : Type ℓ) → cong≃ F (idEquiv A) ≡ idEquiv (F A)
Foundations\Equiv\Properties.agda:171:  rCoh1 : (sec : hasSection f) → Type _
Foundations\Equiv\Properties.agda:174:  rCoh2 : (sec : hasSection f) → Type _
Foundations\Equiv\Properties.agda:177:  rCoh3 : (sec : hasSection f) → Type _
Foundations\Equiv\Properties.agda:180:  rCoh4 : (sec : hasSection f) → Type _
Foundations\Equiv\Properties.agda:210:conjugatePathEquiv : {A : Type ℓ} {a b : A} (p : a ≡ b) → (a ≡ a) ≃ (b ≡ b)
Foundations\Equiv\Properties.agda:213:-- composition on the right induces an equivalence of path types
Foundations\Equiv\Properties.agda:214:compr≡Equiv : {A : Type ℓ} {a b c : A} (p q : a ≡ b) (r : b ≡ c) → (p ≡ q) ≃ (p ∙ r ≡ q ∙ r)
Foundations\Equiv\Properties.agda:217:-- composition on the left induces an equivalence of path types
Foundations\Equiv\Properties.agda:218:compl≡Equiv : {A : Type ℓ} {a b c : A} (p : a ≡ b) (q r : b ≡ c) → (q ≡ r) ≃ (p ∙ q ≡ p ∙ r)
Foundations\Equiv\Properties.agda:221:isEquivFromIsContr : {A : Type ℓ} {B : Type ℓ'}
Foundations\Equiv\Properties.agda:228:isEquiv[f∘equivFunA≃B]→isEquiv[f] : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Foundations\Equiv\Properties.agda:241:isEquiv[equivFunA≃B∘f]→isEquiv[f] : {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Foundations\Equiv\Properties.agda:254:isPointedTarget→isEquiv→isEquiv : {A B : Type ℓ} (f : A → B)
Foundations\Equiv\Properties.agda:259:module _ {ℓ ℓ' ℓ''} {A : Type ℓ} {A' : Type ℓ'} {C : A → Type ℓ''} (is : Iso A' A) where
Foundations\HLevels\Extend.agda:3:Kan Operations for n-Truncated Types
Foundations\HLevels\Extend.agda:5:It provides an efficient way to construct cubes in truncated types.
Foundations\HLevels\Extend.agda:29:  {X : Type ℓ}
Foundations\HLevels\Extend.agda:40:  {X : I → Type ℓ}
Foundations\HLevels\Extend.agda:58:  {X : I → I → Type}
Foundations\HLevels\Extend.agda:83:  (X : I → I → I → Type)
Foundations\HLevels\Extend.agda:111:  -- It can help when one wants to pattern match certain HITs towards some n-types.
Foundations\HLevels\Extend.agda:114:    {X : Type ℓ} (h : isProp X)
Foundations\Pointed\Base.agda:17:Pointed : (ℓ : Level) → Type (ℓ-suc ℓ)
Foundations\Pointed\Base.agda:18:Pointed ℓ = TypeWithStr ℓ (λ x → x)
Foundations\Pointed\Base.agda:29:_→∙_ : (A : Pointed ℓ) (B : Pointed ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Base.agda:43:_≃∙_ : (A : Pointed ℓ) (B : Pointed ℓ') → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Base.agda:65:Equiv∙J : {B : Pointed ℓ} (C : (A : Pointed ℓ) → A ≃∙ B → Type ℓ')
Foundations\Pointed\Base.agda:71:  help : ∀ {A : Type ℓ} (e : A ≃ typ B) (a : A) (b : typ B)
Foundations\Pointed\Base.agda:73:       → (C : (A : Pointed ℓ) → A ≃∙ (fst B , b) → Type ℓ')
Foundations\Pointed\Base.agda:78:       → (C : (A : Pointed ℓ) → A ≃∙ (fst B , b) → Type ℓ')
Foundations\Pointed\Base.agda:82:          → (C : (A : Pointed ℓ) → A ≃∙ (fst B , b) → Type ℓ')
Foundations\Pointed\Base.agda:93:{- J for pointed function types -}
Foundations\Pointed\Base.agda:94:→∙J : ∀ {ℓ ℓ' ℓ''} {A : Pointed ℓ} {B : Type ℓ'}
Foundations\Pointed\Base.agda:95:    → (P : (b₀ : B) (f : A →∙ (B , b₀)) → Type ℓ'')
Foundations\Pointed\Base.agda:101:{- HIT allowing for pattern matching on pointed types -}
Foundations\Pointed\Base.agda:102:data Pointer {ℓ} (A : Pointed ℓ) : Type ℓ where
Foundations\Pointed\FunExt.agda:15:module _ {A : Pointed ℓ} {B : typ A → Type ℓ'} {ptB : B (pt A)} where
Foundations\Pointed\Homogeneous.agda:3:Definition of a homogeneous pointed type, and proofs that pi, product, path, and discrete types
are homogeneous
Foundations\Pointed\Homogeneous.agda:26:  We might say that a type is homogeneous if its automorphism group acts transitively;
Foundations\Pointed\Homogeneous.agda:32:  any homogeneous type in our sense gives rise to such, as shown in:
Foundations\Pointed\Homogeneous.agda:36:isHomogeneous : ∀ {ℓ} → Pointed ℓ → Type (ℓ-suc ℓ)
Foundations\Pointed\Homogeneous.agda:39:-- Pointed functions into a homogeneous type are equal as soon as they are equal
Foundations\Pointed\Homogeneous.agda:123:isHomogeneousPi : ∀ {ℓ ℓ'} {A : Type ℓ} {B∙ : A → Pointed ℓ'}
Foundations\Pointed\Homogeneous.agda:128:isHomogeneousΠ∙ : ∀ {ℓ ℓ'} (A : Pointed ℓ) (B : typ A → Type ℓ')
Foundations\Pointed\Homogeneous.agda:169:isHomogeneousPath : ∀ {ℓ} (A : Type ℓ) {x y : A} (p : x ≡ y) → isHomogeneous ((x ≡ y) , p)
Foundations\Pointed\Homotopy.agda:26:module _ {A : Pointed ℓ} {B : typ A → Type ℓ'} {ptB : B (pt A)} where
Foundations\Pointed\Homotopy.agda:30:  -- pointed homotopy as pointed Π. This is just a Σ-type, see ∙∼Σ
Foundations\Pointed\Homotopy.agda:31:  _∙∼_ : (f g : Π∙ A B ptB) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Homotopy.agda:34:  -- pointed homotopy with PathP. Also a Σ-type, see ∙∼PΣ
Foundations\Pointed\Homotopy.agda:35:  _∙∼P_ : (f g : Π∙ A B ptB) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Homotopy.agda:49:      P : Type ℓ'
Foundations\Pointed\Homotopy.agda:53:      Q : Type ℓ'
Foundations\Pointed\Homotopy.agda:107:  -- to their Σ-type versions
Foundations\Pointed\Homotopy.agda:108:  _∙∼Σ_ : (f g : Π∙ A B ptB) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Homotopy.agda:111:  _∙∼PΣ_ : (f g : Π∙ A B ptB) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Properties.agda:19:-- the default pointed Π-type: A is pointed, and B has a base point in the chosen fiber
Foundations\Pointed\Properties.agda:20:Π∙ : (A : Pointed ℓ) (B : typ A → Type ℓ') (ptB : B (pt A)) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Properties.agda:23:-- the unpointed Π-type becomes a pointed type if the fibers are all pointed
Foundations\Pointed\Properties.agda:24:Πᵘ∙ : (A : Type ℓ) (B : A → Pointed ℓ') → Pointed (ℓ-max ℓ ℓ')
Foundations\Pointed\Properties.agda:28:-- if the base and all fibers are pointed, we have the pointed pointed Π-type
Foundations\Pointed\Properties.agda:34:-- the default pointed Σ-type is just the Σ-type, but as a pointed type
Foundations\Pointed\Properties.agda:35:Σ∙ : (A : Pointed ℓ) (B : typ A → Type ℓ') (ptB : B (pt A)) → Pointed (ℓ-max ℓ ℓ')
Foundations\Pointed\Properties.agda:40:-- version if B is a family of pointed types
Foundations\Pointed\Properties.agda:98:  isInIm∙ : (x : typ B) → Type (ℓ-max ℓ ℓ')
Foundations\Pointed\Properties.agda:101:  isInKer∙ : (x : fst A) → Type ℓ'
Foundations\Pointed\Properties.agda:140:  lem : ∀ {ℓ} {A : Type ℓ} {x y z w : A}
Foundations\Pointed\Properties.agda:237:compPathrEquiv∙ : {A : Type ℓ} {a b c : A} {q : a ≡ b} (p : b ≡ c)
Foundations\Pointed\Properties.agda:242:compPathlEquiv∙ : {A : Type ℓ} {a b c : A} {q : b ≡ c} (p : a ≡ b)
Foundations\Pointed\Properties.agda:248:Σ-cong-equiv-snd∙ : ∀ {ℓ ℓ'} {A : Type ℓ} {B₁ B₂ : A → Type ℓ'}
Foundations\Univalence\Dependent.agda:24:-- Given families `P` and `Q` over base types `A` and `B`
Foundations\Univalence\Dependent.agda:26:--  * an equivalence of base types `e : A ≃ B`,
Foundations\Univalence\Dependent.agda:30:  {A B : Type ℓ} {P : A → Type ℓ'} {Q : B → Type ℓ'}
Foundations\Univalence\Dependent.agda:41:    _ : PathP (λ i → ua e i → Type ℓ') P Q
Foundations\Univalence\Dependent.agda:44:  uaOver : PathP (λ i → ua e i → Type ℓ') P Q
Foundations\Univalence\Dependent.agda:47:    -- Glue-types, except that they are glued
Foundations\Univalence\Dependent.agda:63:    -- i.e. term of type `B`:
Foundations\Univalence\Dependent.agda:68:    -- This gives us a line `(i : I) ⊢ Base` in the universe of types,
Foundations\Univalence\Dependent.agda:77:    Base : Type ℓ'
Foundations\Univalence\Dependent.agda:80:    equiv-boundary : Partial φ (Σ[ T ∈ Type ℓ' ] T ≃ Base)
Foundations\Univalence\Dependent.agda:85:    -- thus `P x` and `Q x` are well-typed.
Foundations\Univalence\Dependent.agda:97:  {A B : Type ℓ} {P : A → Type ℓ'} {Q : B → Type ℓ'}
Foundations\Univalence\Dependent.agda:100:  → PathP (λ i → ua (_ , isHAEquiv→isEquiv hae) i → Type ℓ') P Q
Foundations\Univalence\Universe.agda:16:--  U is the type of codes
Foundations\Univalence\Universe.agda:24:-- space of the code type is equivalent to the path space of the actual
Foundations\Univalence\Universe.agda:33:    (U : Type ℓ)
Foundations\Univalence\Universe.agda:34:    (El : U → Type ℓ')
Foundations\Univalence\Universe.agda:40:    A : Type ℓ'
Functions\Bundle.agda:9:open import Cubical.Structures.TypeEqvTo
Functions\Bundle.agda:14:module _ {ℓb ℓf} {B : Type ℓb} {F : Type ℓf} {ℓ} where
Functions\Bundle.agda:17:    A fiber bundle with base space B and fibers F is a map `p⁻¹ : B → TypeEqvTo F`
Functions\Bundle.agda:20:    e.g. a double cover is a map `B → TypeEqvTo Bool`
Functions\Bundle.agda:23:  Total : (p⁻¹ : B → TypeEqvTo ℓ F) → Type (ℓ-max ℓb ℓ)
Functions\Bundle.agda:26:  pr : (p⁻¹ : B → TypeEqvTo ℓ F) → Total p⁻¹ → B
Functions\Bundle.agda:29:  inc : (p⁻¹ : B → TypeEqvTo ℓ F) (x : B) → p⁻¹ x .fst → Total p⁻¹
Functions\Bundle.agda:32:  fibPrEquiv : (p⁻¹ : B → TypeEqvTo ℓ F) (x : B) → fiber (pr p⁻¹) x ≃ p⁻¹ x .fst
Functions\Bundle.agda:35:module _ {ℓb ℓf} (B : Type ℓb) (ℓ : Level) (F : Type ℓf) where
Functions\Bundle.agda:40:    Equivalently, a fiber bundle with base space B and fibers F is a type E and
Functions\Bundle.agda:44:  bundleEquiv : (B → TypeEqvTo ℓ' F) ≃ (Σ[ E ∈ Type ℓ' ] Σ[ p ∈ (E → B) ] ∀ x → ∥ fiber p x ≃ F ∥₁)
Functions\Bundle.agda:47:          p :   (Σ[ p⁻¹ ∈ (B → Type ℓ') ]            ∀ x → ∥ p⁻¹ x ≃ F ∥₁)
Functions\Bundle.agda:48:              ≡ (Σ[ p ∈ (Σ[ E ∈ Type ℓ' ] (E → B)) ] ∀ x → ∥ fiber (snd p) x ≃ F ∥₁ )
Functions\Embedding.agda:33:    A B C : Type ℓ
Functions\Embedding.agda:45:isEmbedding : (A → B) → Type _
Functions\Embedding.agda:63:hasPropFibers : (A → B) → Type _
Functions\Embedding.agda:67:hasPropFibersOfImage : (A → B) → Type _
Functions\Embedding.agda:71:_↪_ : Type ℓ' → Type ℓ'' → Type (ℓ-max ℓ' ℓ'')
Functions\Embedding.agda:184:id↪ : ∀ {ℓ} → (A : Type ℓ) → A ↪ A
Functions\Embedding.agda:187:iso→isEmbedding : ∀ {ℓ} {A B : Type ℓ}
Functions\Embedding.agda:193:Iso→Embedding : ∀ {ℓ} {A B : Type ℓ}
Functions\Embedding.agda:198:  ∀ {ℓ} {A B C : Type ℓ}
Functions\Embedding.agda:226:-- We now show that the powerset is the subtype classifier
Functions\Embedding.agda:227:-- i.e. ℙ X ≃ Σ[A ∈ Type ℓ] (A ↪ X)
Functions\Embedding.agda:228:Embedding→Subset : {X : Type ℓ} → Σ[ A ∈ Type ℓ ] (A ↪ X) → ℙ X
Functions\Embedding.agda:231:Subset→Embedding : {X : Type ℓ} → ℙ X → Σ[ A ∈ Type ℓ ] (A ↪ X)
Functions\Embedding.agda:239:Subset→Embedding→Subset : {X : Type ℓ} → section (Embedding→Subset {ℓ} {X}) (Subset→Embedding {ℓ} {X})
Functions\Embedding.agda:242:Embedding→Subset→Embedding : {X : Type ℓ} → retract (Embedding→Subset {ℓ} {X}) (Subset→Embedding {ℓ} {X})
Functions\Embedding.agda:246:Subset≃Embedding : {X : Type ℓ} → ℙ X ≃ (Σ[ A ∈ Type ℓ ] (A ↪ X))
Functions\Embedding.agda:250:Subset≡Embedding : {X : Type ℓ} → ℙ X ≡ (Σ[ A ∈ Type ℓ ] (A ↪ X))
Functions\Embedding.agda:271:    Dom′ : ∀ u v → Type _
Functions\Embedding.agda:273:    Cod′ : ∀ u v → Type _
Functions\Embedding.agda:302:-- Inspired by https://martinescardo.github.io/TypeTopology/UF.UniverseEmbedding.html
Functions\Embedding.agda:305:  → (F : Type ℓ → Type ℓ')
Functions\Embedding.agda:321:              → isEmbedding (Lift ℓ' :> (Type ℓ → Type (ℓ-max ℓ ℓ')))
Functions\Embedding.agda:324:module FibrationIdentityPrinciple {B : Type ℓ} {ℓ'} where
Functions\Embedding.agda:332:    f≃g′ : Type (ℓ-max ℓ ℓ')
Functions\Embedding.agda:346:  -- Then embed into the above case by lifting the type
Functions\Embedding.agda:347:  L : Type ℓ' → Type _ -- local synonym fixing the levels of Lift
Functions\Embedding.agda:379:    f≃g : Type (ℓ-max ℓ ℓ')
Functions\Embedding.agda:390:_≃Fib_ : {B : Type ℓ} (f g : Fibration B ℓ') → Type (ℓ-max ℓ ℓ')
Functions\Embedding.agda:393:FibrationIP : {B : Type ℓ} (f g : Fibration B ℓ') → f ≃Fib g ≃ (f ≡ g)
Functions\Embedding.agda:396:Embedding : (B : Type ℓ') → (ℓ : Level) → Type (ℓ-max ℓ' (ℓ-suc ℓ))
Functions\Embedding.agda:397:Embedding B ℓ = Σ[ A ∈ Type ℓ ] A ↪ B
Functions\Embedding.agda:399:module EmbeddingIdentityPrinciple {B : Type ℓ} {ℓ'} (f g : Embedding B ℓ') where
Functions\Embedding.agda:404:  f≃g : Type _
Functions\Embedding.agda:430:_≃Emb_ : {B : Type ℓ} (f g : Embedding B ℓ') → Type _
Functions\Embedding.agda:433:EmbeddingIP : {B : Type ℓ} (f g : Embedding B ℓ') → f ≃Emb g ≃ (f ≡ g)
Functions\Embedding.agda:437:isSetEmbedding : {B : Type ℓ} {ℓ' : Level} → isSet (Embedding B ℓ')
Functions\Embedding.agda:445:Set-Embedding-into-Powerset : {A : Type ℓ} → isSet A → A ↪ ℙ A
Functions\Embedding.agda:458:                {A : Type ℓa} {B : Type ℓb} {C : Type ℓc} {D : Type ℓd}
Functions\Embedding.agda:474:EmbeddingΣProp : {A : Type ℓ} → {B : A → Type ℓ'} → (∀ a → isProp (B a)) → Σ A B ↪ A
Functions\Embedding.agda:478:_∈ₑ_ : {A : Type ℓ} → A → Embedding A ℓ' → Type (ℓ-max ℓ ℓ')
Functions\Embedding.agda:481:isProp∈ₑ : {A : Type ℓ} (x : A) (S : Embedding A ℓ') → isProp (x ∈ₑ S)
Functions\Embedding.agda:484:_⊆ₑ_ : {A : Type ℓ} → Embedding A ℓ' → Embedding A ℓ'' → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Functions\Embedding.agda:487:isProp⊆ₑ : {A : Type ℓ} (X : Embedding A ℓ') (Y : Embedding A ℓ'')
Functions\Embedding.agda:491:isRefl⊆ₑ : {A : Type ℓ} → (S : Embedding A ℓ') → S ⊆ₑ S
Functions\Embedding.agda:494:isAntisym⊆ₑ : {A : Type ℓ}
Functions\Embedding.agda:501:isTrans⊆ₑ : {A : Type ℓ}
Functions\Embedding.agda:510:_∩ₑ_ : {A : Type ℓ}
Functions\Embedding.agda:518:_∪ₑ_ : {A : Type ℓ}
Functions\Embedding.agda:525:⋂ₑ_ : {A : Type ℓ}
Functions\Embedding.agda:526:      {I : Type ℓ'}
Functions\Embedding.agda:532:⋃ₑ_ : {A : Type ℓ}
Functions\Embedding.agda:533:      {I : Type ℓ'}
Functions\Fibration.agda:18:    B : Type ℓb
Functions\Fibration.agda:20:module FiberIso {ℓ} (p⁻¹ : B → Type ℓ) (x : B) where
Functions\Fibration.agda:50:module _ {ℓ} {E : Type ℓ} (p : E → B) where
Functions\Fibration.agda:61:module _ (B : Type ℓb) (ℓ : Level) where
Functions\Fibration.agda:66:  fibrationEquiv : (Σ[ E ∈ Type ℓ' ] (E → B)) ≃ (B → Type ℓ')
Functions\Fibration.agda:68:    where isom : Iso (Σ[ E ∈ Type ℓ' ] (E → B)) (B → Type ℓ')
Functions\Fibration.agda:76:module ForSets {E : Type ℓ} {isSetB : isSet B} (f : E → B) where
Functions\Fibration.agda:86:-- The path type in a fiber of f is equivalent to a fiber of (cong f)
Functions\Fibration.agda:89:fiberPath : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {f : A → B} {b : B} (h h' : fiber f b) →
Functions\Fibration.agda:94:fiber≡ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {f : A → B} {b : B} (h h' : fiber f b)
Functions\Fibration.agda:100:fiberCong : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) {a₀ a₁ : A} (q : f a₀ ≡ f a₁)
Functions\Fibration.agda:106:FibrationStr : (B : Type ℓb) → Type ℓ → Type (ℓ-max ℓ ℓb)
Functions\Fibration.agda:109:Fibration : (B : Type ℓb) → (ℓ : Level) → Type (ℓ-max ℓb (ℓ-suc ℓ))
Functions\Fibration.agda:110:Fibration {ℓb = ℓb} B ℓ = Σ[ A ∈ Type ℓ ] FibrationStr B A
Functions\Fixpoint.agda:13:    A : Type ℓ
Functions\Fixpoint.agda:15:Fixpoint : (A → A) → Type _
Functions\FunExtEquiv.agda:21:module _ {A : Type ℓ} {B : A → I → Type ℓ₁}
Functions\FunExtEquiv.agda:34:funExt₂ : {A : Type ℓ} {B : A → Type ℓ₁} {C : (x : A) → B x → I → Type ℓ₂}
Functions\FunExtEquiv.agda:42:module _ {A : Type ℓ} {B : A → Type ℓ₁} {C : (x : A) → B x → I → Type ℓ₂}
Functions\FunExtEquiv.agda:57:funExt₃ : {A : Type ℓ} {B : A → Type ℓ₁} {C : (x : A) → B x → Type ℓ₂}
Functions\FunExtEquiv.agda:58:          {D : (x : A) → (y : B x) → C x y → I → Type ℓ₃}
Functions\FunExtEquiv.agda:66:module _ {A : Type ℓ} {B : A → Type ℓ₁} {C : (x : A) → B x → Type ℓ₂}
Functions\FunExtEquiv.agda:67:         {D : (x : A) → (y : B x) → C x y → I → Type ℓ₃}
Functions\FunExtEquiv.agda:82:nAryFunExt : {X : Type ℓ} {Y : I → Type ℓ₁} (n : ℕ) (fX : nAryOp n X (Y i0)) (fY : nAryOp n X (Y i1))
Functions\FunExtEquiv.agda:89:nAryFunExt⁻ : (n : ℕ) {X : Type ℓ} {Y : I → Type ℓ₁} (fX : nAryOp n X (Y i0)) (fY : nAryOp n X (Y i1))
Functions\FunExtEquiv.agda:95:nAryFunExtEquiv : (n : ℕ) {X : Type ℓ} {Y : I → Type ℓ₁} (fX : nAryOp n X (Y i0)) (fY : nAryOp n X (Y i1))
Functions\FunExtEquiv.agda:114:funExtDep : {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ₁}
Functions\FunExtEquiv.agda:121:funExtDep⁻ : {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ₁}
Functions\FunExtEquiv.agda:127:funExtDepEquiv : {A : I → Type ℓ} {B : (i : I) → A i → Type ℓ₁}
Functions\FunExtEquiv.agda:158:funExtNonDep : {A : I → Type ℓ} {B : I → Type ℓ₁}
Functions\FunExtEquiv.agda:164:funExtNonDep⁻ : {A : I → Type ℓ} {B : I → Type ℓ₁}
Functions\FunExtEquiv.agda:170:funExtNonDepEquiv : {A : I → Type ℓ} {B : I → Type ℓ₁}
Functions\FunExtEquiv.agda:186:heteroHomotopy≃Homotopy : {A : I → Type ℓ} {B : (i : I) → Type ℓ₁}
Functions\Image.agda:19:  A B : Type ℓ
Functions\Image.agda:22:  isInImage : B → Type _
Functions\Image.agda:28:  Image : Type _
Functions\Image.agda:53:  {Im₀ : Type ℓ₀} (e₀ : A ↠ Im₀) (m₀ : Im₀ ↪ B)
Functions\Image.agda:54:  {Im₁ : Type ℓ₁} (e₁ : A ↠ Im₁) (m₁ : Im₁ ↪ B)
Functions\Image.agda:77:  {Im₀ : Type ℓ₀} (e₀ : A ↠ Im₀) (m₀ : Im₀ ↪ B)
Functions\Image.agda:78:  {Im₁ : Type ℓ₁} (e₁ : A ↠ Im₁) (m₁ : Im₁ ↪ B)
Functions\Image.agda:98:  the notion of powerset ℙ - so subsets of a type A : Type ℓ, are
Functions\Image.agda:101:module _ {A B : Type ℓ} (f : A → B) where
Functions\Image.agda:102:  isInSubsetImage : ℙ A → B → Type _
Functions\Implicit.agda:7:implicit≃Explicit : ∀ {ℓ ℓ'} {A : Type ℓ} {B : A → Type ℓ'}
Functions\Involution.agda:9:isInvolution : ∀{ℓ} {A : Type ℓ} → (A → A) → Type _
Functions\Involution.agda:12:module _ {ℓ} {A : Type ℓ} {f : A → A} (invol : isInvolution f) where
Functions\Logic.agda:9:-- of having them bundled up with the type.
Functions\Logic.agda:32:-- The type hProp of mere propositions
Functions\Logic.agda:34:-- hProp ℓ = Σ (Type ℓ) isProp
Functions\Logic.agda:40:    A B C : Type ℓ
Functions\Logic.agda:61:∥_∥ₚ : Type ℓ → hProp ℓ
Functions\Logic.agda:68:hProp≡ = TypeOfHLevel≡ 1
Functions\Logic.agda:121:_⊔′_ : Type ℓ → Type ℓ' → Type _
Functions\Logic.agda:139:_⊓′_ : Type ℓ → Type ℓ' → Type _
Functions\Logic.agda:192:∥¬A∥≡¬∥A∥ : (A : Type ℓ) → ∥ (A → ⊥.⊥) ∥ₚ ≡ (¬ ∥ A ∥ₚ)
Functions\Morphism.agda:10:module ax {ℓ : Level} (A : Type ℓ) (_+A_ : A → A → A) (a₀ : A) where
Functions\Morphism.agda:14:  rCancel : (-A_ : A → A) → Type ℓ
Functions\Morphism.agda:17:  lCancel : (-A_ : A → A) → Type ℓ
Functions\Morphism.agda:24:module morphLemmas {ℓ ℓ' : Level} {A : Type ℓ} {B : Type ℓ'}
Functions\Preimage.agda:22:    A B : Type ℓ
Functions\Preimage.agda:27:           isInPreimage : A → Type _
Functions\Preimage.agda:33:           Preimage : Type _
Functions\Preimage.agda:49:PreimageOfImage : {A B : Type ℓ}
Functions\Surjection.agda:22:  A B C : Type ℓ
Functions\Surjection.agda:25:isSurjection : (A → B) → Type _
Functions\Surjection.agda:28:_↠_ : Type ℓ → Type ℓ' → Type (ℓ-max ℓ ℓ')
Functions\Surjection.agda:66:rightCancellable : (f : A → B) → Type _
Functions\Surjection.agda:67:rightCancellable {ℓ} {A} {ℓ'} {B} f = ∀ {C : Type (ℓ-suc (ℓ-max ℓ ℓ'))}
Functions\Surjection.agda:100:↠Fixpoint : ∀ {A : Type ℓ} {B : Type ℓ'}
Functions\Surjection.agda:109:-- Cantor's theorem, that no type surjects into its power set
Functions\Surjection.agda:110:¬Surjection-into-Powerset : ∀ {A : Type ℓ} → ¬ (A ↠ ℙ A)
Functions\Surjection.agda:113:  where _∉_ : ∀ {A} → A → ℙ A → Type ℓ
HITs\TypeQuotients.agda:1:module Cubical.HITs.TypeQuotients where
HITs\TypeQuotients.agda:3:open import Cubical.HITs.TypeQuotients.Base public
HITs\TypeQuotients.agda:4:open import Cubical.HITs.TypeQuotients.Properties public
HITs\2GroupoidTruncation\Base.agda:12:-- 2-groupoid truncation as a higher inductive type:
HITs\2GroupoidTruncation\Base.agda:14:data ∥_∥₄ {ℓ} (A : Type ℓ) : Type ℓ where
HITs\2GroupoidTruncation\Properties.agda:22:    A : Type ℓ
HITs\2GroupoidTruncation\Properties.agda:24:rec : ∀ {B : Type ℓ} → is2Groupoid B → (A → B) → ∥ A ∥₄ → B
HITs\2GroupoidTruncation\Properties.agda:30:elim : {B : ∥ A ∥₄ → Type ℓ}
HITs\2GroupoidTruncation\Properties.agda:40:elim2 : {B : ∥ A ∥₄ → ∥ A ∥₄ → Type ℓ}
HITs\2GroupoidTruncation\Properties.agda:47:elim3 : {B : (x y z : ∥ A ∥₄) → Type ℓ}
HITs\AbPath\Base.agda:6:-- 'Abelianised' path types (useful for encode-decode computations of π₁ᵃᵇ)
HITs\AbPath\Base.agda:7:data _≡ᵃᵇ_ {ℓ} {A : Type ℓ} (x y : A) : Type ℓ
HITs\AbPath\Base.agda:12:Pathᵃᵇ : ∀ {ℓ} (A : Type ℓ) (x y : A) → Type ℓ
HITs\AbPath\Base.agda:15:Ωᵃᵇ : ∀ {ℓ} (A : Pointed ℓ) → Type ℓ
HITs\AbPath\Properties.agda:32:elimProp≡ᵃᵇ : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} {B : x ≡ᵃᵇ y → Type ℓ'}
HITs\AbPath\Properties.agda:45:  pathsᵃᵇLemmaL : ∀ {ℓ} {A : Type ℓ} {x y : A} (z : _)
HITs\AbPath\Properties.agda:53:  pathsᵃᵇLemmaR : ∀ {ℓ} {A : Type ℓ} {x y : A} (z : _)
HITs\AbPath\Properties.agda:62:act≡ᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ x) → x ≡ᵃᵇ y → x ≡ᵃᵇ y
HITs\AbPath\Properties.agda:66:actL·πᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) → y ≡ᵃᵇ z → x ≡ᵃᵇ z
HITs\AbPath\Properties.agda:70:·πᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x y z : A}
HITs\AbPath\Properties.agda:83:symᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x y : A} → x ≡ᵃᵇ y → y ≡ᵃᵇ x
HITs\AbPath\Properties.agda:95:-πᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x y : A} → ∥ x ≡ᵃᵇ y ∥₂ → ∥ y ≡ᵃᵇ x ∥₂
HITs\AbPath\Properties.agda:98:reflᵃᵇ : ∀ {ℓ} {A : Type ℓ} {x : A} → x ≡ᵃᵇ x
HITs\AbPath\Properties.agda:102:·πᵃᵇrUnit : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : ∥ x ≡ᵃᵇ y ∥₂)
HITs\AbPath\Properties.agda:107:·πᵃᵇlUnit : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : ∥ x ≡ᵃᵇ y ∥₂)
HITs\AbPath\Properties.agda:112:·πᵃᵇrCancel : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : ∥ x ≡ᵃᵇ y ∥₂)
HITs\AbPath\Properties.agda:117:·πᵃᵇlCancel : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : ∥ x ≡ᵃᵇ y ∥₂)
HITs\AbPath\Properties.agda:122:·πᵃᵇassoc : ∀ {ℓ} {A : Type ℓ} {x : A} (p q r : ∥ x ≡ᵃᵇ x ∥₂)
HITs\AbPath\Properties.agda:130:·πᵃᵇcomm : ∀ {ℓ} {A : Type ℓ} {x : A} (p q : ∥ x ≡ᵃᵇ x ∥₂) → ·πᵃᵇ p q ≡ ·πᵃᵇ q p
HITs\AbPath\Properties.agda:180:-- Below definition is verbose to speed up type checking
HITs\AssocList\Base.agda:11:    A : Type ℓ
HITs\AssocList\Base.agda:15:data AssocList (A : Type ℓ) : Type ℓ where
HITs\AssocList\Base.agda:29:module Elim {ℓ'} {B : AssocList A → Type ℓ'}
HITs\AssocList\Base.agda:49:module ElimProp {ℓ'} {B : AssocList A → Type ℓ'} (BProp : {xs : AssocList A} → isProp (B xs))
HITs\AssocList\Base.agda:61:module Rec {ℓ'} {B : Type ℓ'} (BType : isSet B)
HITs\AssocList\Base.agda:68: f = Elim.f ⟨⟩* (λ x n b → ⟨ x , n ⟩∷* b) (λ x y b → per* x y b) (λ x m n b → agg* x m n b) (λ x b → del* x
b) (λ _ → BType)
HITs\AssocList\Properties.agda:25:    A : Type ℓ
HITs\Bouquet\Base.agda:5:- Definition of the Bouquet of circles of a type aka wedge of A circles
HITs\Bouquet\Base.agda:18:data Bouquet (A : Type ℓ) : Type ℓ where
HITs\Bouquet\Base.agda:22:Bouquet∙ : Type ℓ → Pointed ℓ
HITs\Bouquet\Discrete.agda:4:This module, uses normalization and decidable equality from `Cubical.Algebra.Group.Free` to demonstrate
that Bouquet over discrete type is hGroupoid by establishing a coding between loops in the bouquet and elements of the FreeGroup
represented by normalised words.
HITs\Bouquet\Discrete.agda:34:module _ {A : Type ℓ} (_≟_ : Discrete A) where
HITs\Bouquet\Discrete.agda:41:  CodeBouquet : Bouquet A → Type ℓ
HITs\Bouquet\FundamentalGroupProof.agda:48:    A : Type ℓ
HITs\Bouquet\FundamentalGroupProof.agda:50:-- Pointed versions of the non truncated types
HITs\Bouquet\FundamentalGroupProof.agda:52:ΩBouquet : {A : Type ℓ} → Pointed ℓ
HITs\Bouquet\FundamentalGroupProof.agda:55:FreeGroupoid∙ : {A : Type ℓ} → Pointed ℓ
HITs\Bouquet\FundamentalGroupProof.agda:58:-- Functions without using the truncated forms of types
HITs\Bouquet\FundamentalGroupProof.agda:74:code : {A : Type ℓ} → (Bouquet A) → Type ℓ
HITs\Bouquet\FundamentalGroupProof.agda:84:-- Functions using the truncated forms of types
HITs\Bouquet\FundamentalGroupProof.agda:86:π₁Bouquet : {A : Type ℓ} → Type ℓ
HITs\Bouquet\FundamentalGroupProof.agda:97:substPathsR : {C : Type ℓ}{y z : C} → (x : C) → (p : y ≡ z) → subst (λ y → x ≡ y) p ≡ λ q →
q ∙ p
HITs\Bouquet\FundamentalGroupProof.agda:101:    P : ∀ z' → y ≡ z' → Type _
HITs\Bouquet\FundamentalGroupProof.agda:111:substFunctions : {B C : A → Type ℓ}{x y : A}
HITs\Bouquet\FundamentalGroupProof.agda:120:  P : ∀ y' → x ≡ y' → Type _
HITs\Bouquet\FundamentalGroupProof.agda:132:-- Definition of the encode - decode functions over the family of types Π(x : W A) → code x
HITs\Bouquet\FundamentalGroupProof.agda:137:decode : {A : Type ℓ}(x : Bouquet A) → code x → base ≡ x
HITs\Bouquet\FundamentalGroupProof.agda:183:  P : (x' : Bouquet A) → base ≡ x' → Type _
HITs\Bouquet\FundamentalGroupProof.agda:203:  B : ∀ g → Type _
HITs\Bouquet\FundamentalGroupProof.agda:261:-- Encode Decode over the truncated versions of the types
HITs\Bouquet\FundamentalGroupProof.agda:300:π₁Bouquet≡FreeGroup : {A : Type ℓ} → π₁Bouquet ≡ FreeGroup A
HITs\Bouquet\Properties.agda:5:- Definition of the Bouquet of circles of a type aka wedge of A circles
HITs\Bouquet\Properties.agda:27:elimPropBouquet : ∀ {ℓ ℓ'} {A : Type ℓ}
HITs\Bouquet\Properties.agda:28:  {B : Bouquet A → Type ℓ'}
HITs\Bouquet\Properties.agda:36:module _ {ℓ} {A : Type ℓ} where
HITs\Bouquet\Properties.agda:65:module _ {ℓ ℓ'} {A : Type ℓ} (B : Pointed ℓ') where
HITs\Colimit\Base.agda:18:record Cocone ℓ {ℓd ℓv ℓe} {I : Graph ℓv ℓe} (F : Diag ℓd I) (X : Type ℓ)
HITs\Colimit\Base.agda:19:              : Type (ℓ-suc (ℓ-max ℓ (ℓ-max (ℓ-max ℓv ℓe) (ℓ-suc ℓd)))) where
HITs\Colimit\Base.agda:24:  postcomp : ∀ {ℓ'} {Y : Type ℓ'} → (X → Y) → Cocone ℓ' F Y
HITs\Colimit\Base.agda:31:-- Σ (Type ℓ) (Cocone ℓ F) forms a category:
HITs\Colimit\Base.agda:37:    _* : ∀ {ℓ ℓ'} {X : Type ℓ} {Y : Type ℓ'} → (X → Y) → Cocone _ F X → Cocone _ F Y
HITs\Colimit\Base.agda:40:  CoconeMor : ∀ {ℓ ℓ'} → Σ (Type ℓ) (Cocone ℓ F) → Σ (Type ℓ') (Cocone ℓ' F) → Type _
HITs\Colimit\Base.agda:43:  idCoconeMor : ∀ {ℓ} (Cp : Σ (Type ℓ) (Cocone ℓ F)) → CoconeMor Cp Cp
HITs\Colimit\Base.agda:46:  compCoconeMor : ∀ {ℓ ℓ' ℓ''} {C : Σ (Type ℓ) (Cocone ℓ F)} {D : Σ (Type ℓ') (Cocone ℓ' F)}
HITs\Colimit\Base.agda:47:                    {E : Σ (Type ℓ'') (Cocone ℓ'' F)}
HITs\Colimit\Base.agda:52:-- Universal cocones are initial objects in the category Σ (Type ℓ) (Cocone ℓ F)
HITs\Colimit\Base.agda:54:module _ {ℓ ℓd ℓv ℓe} {I : Graph ℓv ℓe} {F : Diag ℓd I} {X : Type ℓ} where
HITs\Colimit\Base.agda:56:  isUniversalAt : ∀ ℓq → Cocone ℓ F X → Type (ℓ-max ℓ (ℓ-suc (ℓ-max ℓq (ℓ-max (ℓ-max ℓv ℓe) (ℓ-suc ℓd)))))
HITs\Colimit\Base.agda:57:  isUniversalAt ℓq C = ∀ (Y : Type ℓq) → isEquiv {A = (X → Y)} {B = Cocone ℓq F Y} (postcomp C)
HITs\Colimit\Base.agda:59:                  -- ∀ (Y : Type ℓ) (D : Cocone ℓ F Y) → ∃![ h ∈ (X → Y) ] (h *) C ≡ D
HITs\Colimit\Base.agda:65:  isUniversal : Cocone ℓ F X → Typeω
HITs\Colimit\Base.agda:71:record isColimit {ℓ ℓd ℓv ℓe} {I : Graph ℓv ℓe} (F : Diag ℓd I) (X : Type ℓ) : Typeω where
HITs\Colimit\Base.agda:77:module _ {ℓ ℓ' ℓd ℓv ℓe} {I : Graph ℓv ℓe} {F : Diag ℓd I} {X : Type ℓ} {Y : Type ℓ'} where
HITs\Colimit\Base.agda:90:module _ {ℓ ℓ' ℓd ℓv ℓe} {I : Graph ℓv ℓe} {F : Diag ℓd I} {X : Type ℓ} {Y : Type ℓ'} where
HITs\Colimit\Base.agda:108:data colim {ℓd ℓe ℓv} {I : Graph ℓv ℓe} (F : Diag ℓd I) : Type (ℓ-suc (ℓ-max (ℓ-max ℓv ℓe) (ℓ-suc ℓd))) where
HITs\Colimit\Base.agda:118:  rec : ∀ {ℓ} {X : Type ℓ} → Cocone ℓ F X → (colim F → X)
HITs\Colimit\Examples.agda:17:module _ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} where
HITs\Colimit\Examples.agda:26:module _ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {f : A → B} {g : A → C} where
HITs\Colimit\Examples.agda:36:    module _ ℓq (Y : Type ℓq) where
HITs\Cost\Base.agda:12:    A B C : Type ℓ
HITs\Cost\Base.agda:14:Cost : (A : Type ℓ) → Type ℓ
HITs\CumulativeHierarchy\Base.agda:6:Jérémy Ledent, Modeling set theory in homotopy type theory, code of which can be found online at
HITs\CumulativeHierarchy\Base.agda:29:-- set up the basic hierarchy definition and _∈_ as recursive, higher inductive types
HITs\CumulativeHierarchy\Base.agda:30:data V (ℓ : Level) : Type (ℓ-suc ℓ)
HITs\CumulativeHierarchy\Base.agda:33:eqImage : {X Y : Type ℓ} (ix : X → V ℓ) (iy : Y → V ℓ) → Type (ℓ-suc ℓ)
HITs\CumulativeHierarchy\Base.agda:38:  sett : (X : Type ℓ) → (X → V ℓ) → V ℓ
HITs\CumulativeHierarchy\Base.agda:39:  seteq : (X Y : Type ℓ) (ix : X → V ℓ) (iy : Y → V ℓ) (eq : eqImage ix iy) → sett X ix ≡ sett Y
iy
HITs\CumulativeHierarchy\Base.agda:51:record ElimSet {Z : (s : V ℓ) → Type ℓ'}
HITs\CumulativeHierarchy\Base.agda:52:               (isSetZ : ∀ s → isSet (Z s)) : Type (ℓ-max ℓ' (ℓ-suc ℓ)) where
HITs\CumulativeHierarchy\Base.agda:55:      ∀ (X : Type ℓ) (ix : X → V ℓ)
HITs\CumulativeHierarchy\Base.agda:61:      ∀ (X₁ X₂ : Type ℓ) (ix₁ : X₁ → V ℓ) (ix₂ : X₂ → V ℓ) (eq : eqImage ix₁ ix₂)
HITs\CumulativeHierarchy\Base.agda:70:module _ {Z : (s : V ℓ) → Type ℓ'} {isSetZ : ∀ s → isSet (Z s)} (E : ElimSet isSetZ) where
HITs\CumulativeHierarchy\Base.agda:101:elimProp : {Z : (s : V ℓ) → Type ℓ'} (isPropZ : ∀ s → isProp (Z s))
HITs\CumulativeHierarchy\Base.agda:102:         → ((X : Type ℓ) → (ix : X → V ℓ) → (∀ x → Z (ix x)) → Z (sett X ix))
HITs\CumulativeHierarchy\Base.agda:117:record Elim2Set {Z : (s t : V ℓ) → Type ℓ'}
HITs\CumulativeHierarchy\Base.agda:118:                (isSetZ : ∀ s t → isSet (Z s t)) : Type (ℓ-max ℓ' (ℓ-suc ℓ)) where
HITs\CumulativeHierarchy\Base.agda:121:      ∀ (X : Type ℓ) (ix : X → V ℓ) (Y : Type ℓ) (iy : Y → V ℓ)
HITs\CumulativeHierarchy\Base.agda:128:      ∀ (X₁ X₂ : Type ℓ) (ix₁ : X₁ → V ℓ) (ix₂ : X₂ → V ℓ) (eq : eqImage ix₁ ix₂)
HITs\CumulativeHierarchy\Base.agda:130:      → (Y : Type ℓ) (iy : Y → V ℓ)
HITs\CumulativeHierarchy\Base.agda:146:      ∀ (X : Type ℓ) (ix : X → V ℓ)
HITs\CumulativeHierarchy\Base.agda:148:      → (Y₁ Y₂ : Type ℓ) (iy₁ : Y₁ → V ℓ) (iy₂ : Y₂ → V ℓ) → (eq : eqImage iy₁ iy₂)
HITs\CumulativeHierarchy\Base.agda:163:module _ {Z : (s t : V ℓ) → Type ℓ'} {isSetZ : ∀ s t → isSet (Z s t)} (E : Elim2Set isSetZ) where
HITs\CumulativeHierarchy\Base.agda:174:    eliminatorImplX : (X : Type ℓ) (ix : X → V ℓ)
HITs\CumulativeHierarchy\Base.agda:194:      ∀ (X : Type ℓ) (ix : X → V ℓ)
HITs\CumulativeHierarchy\Base.agda:200:      ∀ (X₁ X₂ : Type ℓ) (ix₁ : X₁ → V ℓ) (ix₂ : X₂ → V ℓ) → (eq : eqImage ix₁ ix₂)
HITs\CumulativeHierarchy\Base.agda:219:      elimImplSExtT : (Y : Type ℓ) (iy : Y → V ℓ) → _ {- the appropriate path type -}
HITs\CumulativeHierarchy\Constructions.agda:40:record SetStructure ℓ : Type (ℓ-suc ℓ) where
HITs\CumulativeHierarchy\Constructions.agda:42:    X : Type ℓ
HITs\CumulativeHierarchy\Constructions.agda:47:record SetPackage ℓ ℓ' : Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ')) where
HITs\CumulativeHierarchy\Properties.agda:29:    X Y : Type ℓ
HITs\CumulativeHierarchy\Properties.agda:40:-- implementing the map : V ℓ → Σ[ X : Type ℓ ] (X → V ℓ)
HITs\CumulativeHierarchy\Properties.agda:41:-- Quotienting by Path (V ℓ) or via eqImage would lead to X : Type (ℓ-suc ℓ)
HITs\CumulativeHierarchy\Properties.agda:45:  goalProp : (X : Type ℓ) (ix : X → V ℓ)
HITs\CumulativeHierarchy\Properties.agda:46:           → (Y : Type ℓ) (iy : Y → V ℓ)
HITs\CumulativeHierarchy\Properties.agda:55:  lemma : {X₁ X₂ Y : Type ℓ} {ix₁ : X₁ → V ℓ} {ix₂ : X₂ → V ℓ} (iy : Y → V ℓ)
HITs\CumulativeHierarchy\Properties.agda:80:_≊_ : (s t : V ℓ) → Type ℓ
HITs\CumulativeHierarchy\Properties.agda:94:  eqImageXY : {X Y : Type ℓ} {ix : X → V ℓ} {iy : Y → V ℓ} → (∀ x y → ⟨ ix x ∼ iy y ⟩ → ix
x ≡ iy y)
HITs\CumulativeHierarchy\Properties.agda:106:      ∀ (X : Type _) (ix : X → V _)
HITs\CumulativeHierarchy\Properties.agda:120:repFiber : (f : X → V ℓ) (b : V ℓ) → Type _
HITs\CumulativeHierarchy\Properties.agda:126:-- projecting out a representing type together with the embedding
HITs\CumulativeHierarchy\Properties.agda:127:MonicPresentation : (a : V ℓ) → Type (ℓ-suc ℓ)
HITs\CumulativeHierarchy\Properties.agda:146:sett-repr : (X : Type ℓ) (ix : X → V ℓ) → MonicPresentation (sett X ix)
HITs\CumulativeHierarchy\Properties.agda:148:  Kernel : X → X → Type ℓ
HITs\CumulativeHierarchy\Properties.agda:150:  Rep : Type ℓ
HITs\CumulativeHierarchy\Properties.agda:172:data DeepMonicPresentation (a : V ℓ) : Type (ℓ-suc ℓ) where
HITs\CumulativeHierarchy\Properties.agda:188:-- "Cannot eliminate fibrant type DeepMonicPresentation a
HITs\CumulativeHierarchy\Properties.agda:189:--  unless target type is also fibrant"
HITs\CumulativeHierarchy\Properties.agda:194:  MonicDataF : Type (ℓ-suc ℓ) → Type (ℓ-suc ℓ)
HITs\CumulativeHierarchy\Properties.agda:210:  -- note the problem of making this a datatype directly: MonicDataF is *not* strictly
positive!
HITs\CumulativeHierarchy\Properties.agda:213:elim : (B : V ℓ → Type ℓ')
HITs\CumulativeHierarchy\Properties.agda:214:     → ((X : Type ℓ) (ix : X → V ℓ) (emb : isEmbedding ix) (rec : ∀ x → B (ix x)) → B
(sett X ix))
HITs\CumulativeHierarchy\Properties.agda:220:⟪_⟫ : (s : V ℓ) → Type ℓ
HITs\CumulativeHierarchy\Properties.agda:260:ix∈ₛ : {X : Type ℓ} {ix : X → V ℓ}
HITs\Cylinder\Base.agda:17:-- Cylinder A is a cylinder object in the category of cubical types.
HITs\Cylinder\Base.agda:20:data Cylinder {ℓ} (A : Type ℓ) : Type ℓ where
HITs\Cylinder\Base.agda:28:Cocylinder : ∀ {ℓ} → Type ℓ → Type ℓ
HITs\Cylinder\Base.agda:31:module _ {ℓ} {A : Type ℓ} where
HITs\Cylinder\Base.agda:33:  -- of type A ⊎ A → A into a pair of mappings:
HITs\Cylinder\Base.agda:53:    : ∀{ℓ'} {B : Cylinder A → Type ℓ'}
HITs\Cylinder\Base.agda:105:-- Since we can construct cylinders for every type, Cylinder actually
HITs\Cylinder\Base.agda:117:      A : Type ℓa
HITs\Cylinder\Base.agda:118:      B : Type ℓb
HITs\Cylinder\Base.agda:119:      C : Type ℓc
HITs\Cylinder\Base.agda:164:  -- cylinder over the unit type.
HITs\Cylinder\Base.agda:193:  -- over any type A and the product of A and the interval.
HITs\Cylinder\Base.agda:194:  module _ {ℓ} {A : Type ℓ} where
HITs\Cylinder\Base.agda:196:      Cyl : Type ℓ
HITs\Cylinder\Base.agda:230:module Push {ℓ} {A : Type ℓ} where
HITs\Cylinder\Base.agda:234:    Push : Type ℓ
HITs\Cylinder\Base.agda:237:    Cyl : Type ℓ
HITs\Delooping\Two\Base.agda:8:data Bℤ₂ : Type₀ where
HITs\Delooping\Two\Base.agda:17:    A : Type ℓ
HITs\Delooping\Two\Base.agda:38:  elim : (P : Bℤ₂ → Type ℓ)
HITs\Delooping\Two\Properties.agda:48:    (isOfHLevelTypeOfHLevel 2)
HITs\Delooping\Two\Properties.agda:50:  El : Bℤ₂ → Type₀
HITs\Delooping\Two\Properties.agda:63:  Loop²-coh : (a b c : Bool) → Type₀
HITs\Delooping\Two\Properties.agda:131:  module _ (B : Type₀) where
HITs\DunceCap\Base.agda:14:data Dunce : Type₀ where
HITs\DunceCap\Base.agda:25:DunceCone : Type₀
HITs\DunceCap\Properties.agda:19:Disk : Type₀
HITs\EilenbergMacLane1\Base.agda:5:- The first Eilenberg–Mac Lane type as a HIT
HITs\EilenbergMacLane1\Base.agda:7:Remark: The proof that there is an isomorphism of types
HITs\EilenbergMacLane1\Base.agda:27:  data EM₁ : Type ℓ where
HITs\EilenbergMacLane1\Base.agda:68:  data EM₁-raw : Type ℓ where
HITs\EilenbergMacLane1\Properties.agda:3:Eilenberg–Mac Lane type K(G, 1)
HITs\EilenbergMacLane1\Properties.agda:37:   {B : EM₁ (G , str) → Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:59:  elimSet : {B : EM₁ (G , str) → Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:79:  elimProp : {B : EM₁ (G , str) → Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:91:  elimProp2 : {C : EM₁ (G , str) → EM₁ (G , str) → Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:101:  elim : {B : EM₁ (G , str) → Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:118:  rec : {B : Type ℓ}
HITs\EilenbergMacLane1\Properties.agda:127:  rec' : {B : Type ℓ}
HITs\FiniteMultiset\Base.agda:10:    A : Type ℓ
HITs\FiniteMultiset\Base.agda:14:data FMSet (A : Type ℓ) : Type ℓ where
HITs\FiniteMultiset\Base.agda:22:module Elim {ℓ'} {B : FMSet A → Type ℓ'}
HITs\FiniteMultiset\Base.agda:35:module ElimProp {ℓ'} {B : FMSet A → Type ℓ'} (BProp : {xs : FMSet A} → isProp (B xs))
HITs\FiniteMultiset\Base.agda:44:module Rec {ℓ'} {B : Type ℓ'} (BType : isSet B)
HITs\FiniteMultiset\Base.agda:49:  f = Elim.f []* (λ x b → x ∷* b) (λ x y b → comm* x y b) (λ _ → BType)
HITs\FiniteMultiset\CountExtensionality.agda:25:module _{A : Type ℓ} (discA : Discrete A) where
HITs\FiniteMultiset\CountExtensionality.agda:26: _≼_ : FMSet A → FMSet A → Type ℓ
HITs\FiniteMultiset\CountExtensionality.agda:80: module ≼-ElimProp {ℓ'} {B : FMSet A → Type ℓ'}
HITs\FiniteMultiset\CountExtensionality.agda:84:  C : FMSet A → Type (ℓ-max ℓ ℓ')
HITs\FiniteMultiset\CountExtensionality.agda:109: ≼-ElimPropBin :  ∀ {ℓ'} {B : FMSet A → FMSet A → Type ℓ'}
HITs\FiniteMultiset\CountExtensionality.agda:132: ≼-ElimPropBinSym :  ∀ {ℓ'} {B : FMSet A → FMSet A → Type ℓ'}
HITs\FiniteMultiset\CountExtensionality.agda:147:  B : FMSet A → FMSet A → Type ℓ
HITs\FiniteMultiset\Properties.agda:14:    A : Type ℓ
HITs\FiniteMultiset\Properties.agda:48:module FMSetUniversal {ℓ} {M : Type ℓ} (MSet : isSet M)
HITs\FreeAbGroup\Base.agda:17:  A : Type ℓ
HITs\FreeAbGroup\Base.agda:19:data FreeAbGroup (A : Type ℓ) : Type ℓ where
HITs\FreeAbGroup\Base.agda:30:module Elim {B : FreeAbGroup A → Type ℓ'}
HITs\FreeAbGroup\Base.agda:57:module ElimProp {B : FreeAbGroup A → Type ℓ'}
HITs\FreeAbGroup\Base.agda:72:module Rec {B : Type ℓ'} (BType : isSet B)
HITs\FreeAbGroup\Base.agda:84:  f = Elim.f ⟦_⟧* ε* _·*_ _⁻¹* assoc* comm* identityᵣ* invᵣ* (const BType)
HITs\FreeComMonoids\Base.agda:10:  A : Type ℓ
HITs\FreeComMonoids\Base.agda:12:data FreeComMonoid (A : Type ℓ) : Type ℓ where
HITs\FreeComMonoids\Base.agda:22:module Elim {ℓ'} {B : FreeComMonoid A → Type ℓ'}
HITs\FreeComMonoids\Base.agda:47:module ElimProp {ℓ'} {B : FreeComMonoid A → Type ℓ'}
HITs\FreeComMonoids\Base.agda:61:module Rec {ℓ'} {B : Type ℓ'} (BType : isSet B)
HITs\FreeComMonoids\Base.agda:72:  f = Elim.f ⟦_⟧* ε* _·*_ comm* identityᵣ* identityₗ* assoc* (const BType)
HITs\FreeComMonoids\Properties.agda:19:  A : Type ℓ
HITs\FreeGroup\Base.agda:5:- An implementation of the free group of a type of generators as a HIT
HITs\FreeGroup\Base.agda:17:data FreeGroup (A : Type ℓ) : Type ℓ where
HITs\FreeGroup\NormalForm.agda:4:For an arbitrary type of generators:
HITs\FreeGroup\NormalForm.agda:7:The following properties are defined with the assumption that the type of the generators is an hSet.
Without this assumption, they can be adapted to be stated "modulo set truncation":
HITs\FreeGroup\NormalForm.agda:11: - `NF⇔DiscreteA` indicates that computing the normal form is feasible if and only if the type of
generators is discrete.
HITs\FreeGroup\NormalForm.agda:49:module _ {A : Type ℓ} where
HITs\FreeGroup\Properties.agda:10:- Equivalence of the types (A → Group .fst) (GroupHom (freeGroupGroup A) Group)
HITs\FreeGroup\Properties.agda:42:    A : Type ℓ
HITs\FreeGroup\Properties.agda:60:freeGroupGroup : Type ℓ → Group ℓ
HITs\FreeGroup\Properties.agda:85:elimProp : {B : FreeGroup A → Type ℓ'}
HITs\FreeGroup\Properties.agda:164:  B : ∀ x → Type _
HITs\FreeGroup\Properties.agda:200:-- The type of Group Homomorphisms from the FreeGroup A into G
HITs\FreeGroup\Properties.agda:201:-- is equivalent to the type of functions from A into G .fst
HITs\FreeGroupoid\Base.agda:19:data FreeGroupoid (A : Type ℓ) : Type ℓ where
HITs\FreeGroupoid\GroupoidActions.agda:25:    A : Type ℓ
HITs\FreeGroupoid\GroupoidActions.agda:122:pathsInU : {A : Type ℓ} → FreeGroupoid A → (FreeGroupoid A) ≡ (FreeGroupoid A)
HITs\FreeGroupoid\Properties.agda:32:    A : Type ℓ
HITs\FreeGroupoid\Properties.agda:35:elimProp : ∀ {B : FreeGroupoid A → Type ℓ'}
HITs\FreeGroupoid\Properties.agda:101:∥freeGroupoid∥₂IsSemiGroup : ∀ {ℓ}{A : Type ℓ} → IsSemigroup _∣·∣₂_
HITs\FreeGroupoid\Properties.agda:129:∥freeGroupoid∥₂Group : Type ℓ → Group ℓ
HITs\GroupoidQuotients\Base.agda:14:-- Groupoid quotients as a higher inductive type:
HITs\GroupoidQuotients\Base.agda:16:data _//_ {ℓ ℓ'} (A : Type ℓ) {R : A → A → Type ℓ'}
HITs\GroupoidQuotients\Base.agda:17:          (Rt : BinaryRelation.isTrans R) : Type (ℓ-max ℓ ℓ') where
HITs\GroupoidQuotients\Base.agda:37:comp'// : {ℓ ℓ' : Level} (A : Type ℓ) {R : A → A → Type ℓ'}
HITs\GroupoidQuotients\Properties.agda:27:-- Type quotients
HITs\GroupoidQuotients\Properties.agda:32:    A : Type ℓA
HITs\GroupoidQuotients\Properties.agda:33:    R : A → A → Type ℓR
HITs\GroupoidQuotients\Properties.agda:36:     → {B : A // Rt → Type ℓ}
HITs\GroupoidQuotients\Properties.agda:55:         → {B : A // Rt → Type ℓ}
HITs\GroupoidQuotients\Properties.agda:64:          → {C : A // Rt → A // Rt → Type ℓ}
HITs\GroupoidQuotients\Properties.agda:77:     → {B : A // Rt → Type ℓ}
HITs\GroupoidQuotients\Properties.agda:96:    → {B : Type ℓ}
HITs\GroupoidTruncation\Base.agda:12:-- groupoid truncation as a higher inductive type:
HITs\GroupoidTruncation\Base.agda:14:data ∥_∥₃ {ℓ} (A : Type ℓ) : Type ℓ where
HITs\GroupoidTruncation\Properties.agda:22:    A : Type ℓ
HITs\GroupoidTruncation\Properties.agda:24:rec : ∀ {B : Type ℓ} → isGroupoid B → (A → B) → ∥ A ∥₃ → B
HITs\GroupoidTruncation\Properties.agda:29:elim : {B : ∥ A ∥₃ → Type ℓ}
HITs\GroupoidTruncation\Properties.agda:39:elim2 : {B : ∥ A ∥₃ → ∥ A ∥₃ → Type ℓ}
HITs\GroupoidTruncation\Properties.agda:46:elim3 : {B : (x y z : ∥ A ∥₃) → Type ℓ}
HITs\InfNat\Base.agda:11:data ℕ+∞ : Type₀ where
HITs\Interval\Base.agda:5:data Interval : Type₀ where
HITs\Interval\Base.agda:18:funExtInterval : ∀ {ℓ} (A B : Type ℓ) (f g : A → B) → ((x : A) → f x ≡ g x) → f ≡ g
HITs\Interval\Base.agda:26:elim : (A : Interval → Type₀) (x : A zero) (y : A one)
HITs\Interval\Base.agda:33:intervalEta : ∀ {A : Type₀} (f : Interval → A) → elim _ (f zero) (f one) (λ i → f (seg i)) ≡ f
HITs\James\Base.agda:7:It can be seen as the free A∞-monoid constructed out of a given type,
HITs\James\Base.agda:8:namely the "correct higher version" of free monoid that is meaningful for all types,
HITs\James\Base.agda:13:  "The James construction and π₄(𝕊³) in homotopy type theory"
HITs\James\Base.agda:33:  data James : Type ℓ where
HITs\James\Inductive.agda:51:  𝕁 : ℕ → Type ℓ
HITs\James\Inductive.agda:62:  𝕁∞ : Type ℓ
HITs\James\Inductive.agda:83:  𝕁Push : ℕ → Type ℓ
HITs\James\LoopSuspEquiv.agda:4:  - The equivalence "James X ≃ Ω Σ X" for any connected pointed type X.
HITs\James\LoopSuspEquiv.agda:41:  Total : Type ℓ
HITs\James\LoopSuspEquiv.agda:103:      ∣isEquiv∣ : hLevelTrunc 2 X → Type ℓ
HITs\James\LoopSuspEquiv.agda:109:    Code : Susp X → Type ℓ
HITs\James\Properties.agda:7:  - The type James X has h-monoid structure, namely being a monoid in "homotopy category".
HITs\James\Properties.agda:9:  - The equivalence "James X₊ ≃ List X" for type X,
HITs\James\Properties.agda:10:    where X₊ denotes the type formed by freely adjoining a base point to X.
HITs\James\Properties.agda:51:  (X : Type ℓ) where
HITs\James\Stable.agda:31:  Code : Pushout (terminal X) (terminal X) → Type ℓ
HITs\James\Inductive\Base.agda:27:  data 𝕁ames : ℕ → Type ℓ where
HITs\James\Inductive\Base.agda:45:  𝕁ames∞ : Type ℓ
HITs\James\Inductive\Coherence.agda:28:    {A : Type ℓ}(a : A) where
HITs\James\Inductive\Coherence.agda:58:      {B : Type ℓ'}(f : A → B) where
HITs\James\Inductive\Coherence.agda:122:  {A : Type ℓ}{a : A} where
HITs\James\Inductive\Coherence.agda:159:  {A : Type ℓ}{B : Type ℓ'}{a b c d : A} where
HITs\James\Inductive\Coherence.agda:188:  {A : Type ℓ}{a b c : A} where
HITs\James\Inductive\Coherence.agda:203:    {B : Type ℓ'} where
HITs\James\Inductive\Coherence.agda:217:  {A : Type ℓ}{B : Type ℓ'}{a b c : A}
HITs\James\Inductive\Coherence.agda:237:  {A : Type ℓ}{a : A} where
HITs\James\Inductive\Coherence.agda:273:  {A : Type ℓ}{B : Type ℓ'}{a : A}(f : A → B) where
HITs\James\Inductive\Coherence.agda:275:  push-helper-cong-Type : {b c : A}
HITs\James\Inductive\Coherence.agda:278:    → Type _
HITs\James\Inductive\Coherence.agda:279:  push-helper-cong-Type p q q' sqr =
HITs\James\Inductive\Coherence.agda:287:  push-helper-cong-refl : push-helper-cong-Type refl refl refl refl
HITs\James\Inductive\Coherence.agda:302:    → push-helper-cong-Type p q q' sqr
HITs\James\Inductive\Coherence.agda:305:  push-helper-cong : ∀ {b c} p q q' sqr → push-helper-cong-Type {b = b} {c = c} p q q' sqr
HITs\James\Inductive\Coherence.agda:310:  {A : Type ℓ}{a : A} where
HITs\James\Inductive\Coherence.agda:312:  push-coh-helper-Type : {b c : A}
HITs\James\Inductive\Coherence.agda:315:    → Type _
HITs\James\Inductive\Coherence.agda:316:  push-coh-helper-Type p q q' sqr =
HITs\James\Inductive\Coherence.agda:340:  push-coh-helper-refl : push-coh-helper-Type refl refl refl refl
HITs\James\Inductive\Coherence.agda:353:    → push-coh-helper-Type p q q' sqr
HITs\James\Inductive\Coherence.agda:356:  push-coh-helper : ∀ {b c} p q q' sqr → push-coh-helper-Type {b = b} {c = c} p q q' sqr
HITs\James\Inductive\Coherence.agda:361:  {A : Type ℓ}{a : A} where
HITs\James\Inductive\Coherence.agda:389:  {A : Type ℓ}{a : A} where
HITs\James\Inductive\Coherence.agda:391:  coh-cube-helper-Type :
HITs\James\Inductive\Coherence.agda:394:    → Type _
HITs\James\Inductive\Coherence.agda:395:  coh-cube-helper-Type {c = c} p q q' sqr =
HITs\James\Inductive\Coherence.agda:418:  coh-cube-helper-refl : coh-cube-helper-Type refl refl refl refl
HITs\James\Inductive\Coherence.agda:431:    → coh-cube-helper-Type p q q' sqr
HITs\James\Inductive\Coherence.agda:434:  coh-cube-helper : ∀ {b c} p q q' sqr → coh-cube-helper-Type {b = b} {c = c} p q q' sqr
HITs\James\Inductive\Coherence.agda:439:  {A : Type ℓ}{B : Type ℓ'}{a : A}(f : A → B) where
HITs\James\Inductive\Coherence.agda:441:  coh-helper-cong-Type : {b c : A}{a' b' c' : B}
HITs\James\Inductive\Coherence.agda:450:    → Type _
HITs\James\Inductive\Coherence.agda:451:  coh-helper-cong-Type pa pb pc q r h h' h'' sqr sqr' =
HITs\James\Inductive\Coherence.agda:458:  coh-helper-cong-refl : coh-helper-cong-Type refl refl refl refl refl refl refl refl refl refl
HITs\James\Inductive\Coherence.agda:480:    → coh-helper-cong-Type pa pb pc q r h h' h'' sqr sqr'
HITs\James\Inductive\Coherence.agda:487:    → coh-helper-cong-Type {b = b} {c = c} {a' = a'} {b' = b'} {c' = c'}
HITs\James\Inductive\ColimitEquivalence.agda:4:  - The reduced version gives the same type as James.
HITs\James\Inductive\PushoutFormula.agda:45:  𝕁amesPush : (n : ℕ) → Type ℓ
HITs\James\Inductive\PushoutFormula.agda:143:  -- The type family 𝕁ames can be constructed by iteratively using pushouts
HITs\James\Inductive\PushoutFormula.agda:180:    Unit×-≃ : {A : Type ℓ} → A ≃ Unit × A
HITs\James\Inductive\PushoutFormula.agda:186:  𝕁amesPush' : (n : ℕ) → Type ℓ
HITs\James\Inductive\Reduced.agda:35:  data 𝕁Red : Type ℓ where
HITs\James\Inductive\Reduced.agda:41:  data 𝕁Red∞ : Type ℓ where
HITs\James\Inductive\Reduced.agda:47:  -- The following square of types is defined as HIT over I × I.
HITs\James\Inductive\Reduced.agda:51:  data 𝕁Square (i j : I) : Type ℓ where
HITs\James\Inductive\Reduced.agda:62:  𝕁Path : I → Type ℓ
HITs\James\Inductive\Reduced.agda:72:  data 𝕁Path∞ (i : I) : Type ℓ where
HITs\Join\Base.agda:13:data join {ℓ ℓ'} (A : Type ℓ) (B : Type ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\Join\Properties.agda:48:join-inr-null : {X : Pointed ℓ} {Y : Type ℓ'} (y : Y)
HITs\Join\Properties.agda:54:-- Characterisation of function type join A B → C
HITs\Join\Properties.agda:55:IsoFunSpaceJoin : ∀ {ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Join\Properties.agda:68:joinPushout : (A : Type ℓ) → (B : Type ℓ') → Type (ℓ-max ℓ ℓ')
HITs\Join\Properties.agda:72:joinPushout-iso-join : (A : Type ℓ) → (B : Type ℓ') → Iso (joinPushout A B) (join A B)
HITs\Join\Properties.agda:96:joinPushout≃join : (A : Type ℓ) → (B : Type ℓ') → joinPushout A B ≃ join A B
HITs\Join\Properties.agda:99:joinPushout≡join : (A : Type ℓ) → (B : Type ℓ') → joinPushout A B ≡ join A B
HITs\Join\Properties.agda:106:join-assoc : (A B C : Type₀) → join (join A B) C ≡ join A (join B C)
HITs\Join\Properties.agda:170:        A×join : Type₀
HITs\Join\Properties.agda:252:        join×C : Type₀
HITs\Join\Properties.agda:311:joinSwitch : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Join\Properties.agda:315:  switch : ∀ {ℓ ℓ' ℓ''}  {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Join\Properties.agda:333:  invol : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Join\Properties.agda:364:joinAssocDirect : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Join\Properties.agda:458:join-commFun : ∀ {ℓ'} {A : Type ℓ} {B : Type ℓ'} → join A B → join B A
HITs\Join\Properties.agda:463:join-commFun² : ∀ {ℓ'} {A : Type ℓ} {B : Type ℓ'} (x : join A B)
HITs\Join\Properties.agda:469:join-comm : ∀ {ℓ'} {A : Type ℓ} {B : Type ℓ'}
HITs\Join\Properties.agda:477:     {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
HITs\Join\Properties.agda:485:     {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
HITs\Join\Properties.agda:499:joinAnnihilL : {A : Type ℓ} → isContr (join (Unit* {ℓ'}) A)
HITs\Join\Properties.agda:509:private module _ {ℓ : Level} {B : Type ℓ} where
HITs\Join\Properties.agda:536:  ganea-fill₃ : ∀ {ℓ} {A : Type ℓ} (f : A → B) (b : B)
HITs\Join\Properties.agda:548:  fib-cofib : Type _
HITs\Join\Properties.agda:556:  GaneaFib : Type _
HITs\Join\Properties.agda:613:      J-lem : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A) (q : x ≡ y)
HITs\Join\Properties.agda:625:        J-lem-refl : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A)
HITs\Join\Properties.agda:631:      J-lem₂ : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A) (q : x ≡ y) (z : A) (p : x ≡ z)
HITs\Join\Properties.agda:640:        J-lem₂-refl : ∀ {ℓ} {A : Type ℓ} {x : A} (q : x ≡ x) (r : refl ≡ q)
HITs\Join\Properties.agda:684:       btm : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A) (q : x ≡ y)
HITs\Join\Properties.agda:695:       side : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A) (p : x ≡ y)
HITs\Join\Properties.agda:721:module _ {A : Type ℓ}{B : Type ℓ'} where
HITs\Join\Properties.agda:722:  elim : {C : join A B → Type ℓ''}
HITs\Join\Properties.agda:731:  elimProp : {C : join A B → Type ℓ''} (isPropC : ∀ j → isProp (C j))
HITs\KleinBottle\Base.agda:10:data KleinBottle : Type where
HITs\KleinBottle\Properties.agda:23:rec : ∀ {ℓ} {A : Type ℓ} (x : A)
HITs\KleinBottle\Properties.agda:32:elimSet : ∀ {ℓ} {A : KleinBottle → Type ℓ}
HITs\KleinBottle\Properties.agda:46:elimProp : ∀ {ℓ} {A : KleinBottle → Type ℓ}
HITs\KleinBottle\Properties.agda:56:K²FunCharacIso : ∀ {ℓ} {A : KleinBottle → Type ℓ}
HITs\KleinBottle\Properties.agda:78:invS¹Loop : S¹ → Type
HITs\ListedFiniteSet\Base.agda:13:    A B : Type ℓ
HITs\ListedFiniteSet\Base.agda:19:data LFSet (A : Type ℓ) : Type ℓ where
HITs\ListedFiniteSet\Base.agda:31:_∈_ : {A : Type ℓ} → A → LFSet A → hProp ℓ
HITs\ListedFiniteSet\Base.agda:50:  {B : LFSet A → Type ℓ}
HITs\ListedFiniteSet\Base.agda:70:module Rec {ℓ} {B : Type ℓ}
HITs\ListedFiniteSet\Base.agda:85:  {B : LFSet A → Type ℓ}
HITs\ListedFiniteSet\Properties.agda:11:    A B : Type ℓ
HITs\Localization\Base.agda:8:module _ {ℓα ℓs ℓt} {A : Type ℓα} {S : A → Type ℓs} {T : A → Type ℓt} where
HITs\Localization\Base.agda:10:  isLocal : ∀ (F : ∀ α → S α → T α) {ℓ} (X : Type ℓ) → Type _
HITs\Localization\Base.agda:13:  data Localize (F : ∀ α → S α → T α) {ℓ} (X : Type ℓ) : Type (ℓ-max ℓ (ℓ-max ℓα (ℓ-max ℓs ℓt))) where
HITs\Localization\Base.agda:21:  isLocal-Localize : ∀ (F : ∀ α → S α → T α) {ℓ} (X : Type ℓ) → isLocal F (Localize F X)
HITs\Localization\Properties.agda:12:module _ {ℓα ℓs ℓt} {A : Type ℓα} {S : A → Type ℓs} {T : A → Type ℓt} where
HITs\Localization\Properties.agda:14:  rec : ∀ {F : ∀ α → S α → T α} {ℓ ℓ'} {X : Type ℓ} {Y : Type ℓ'}
HITs\MappingCones\Base.agda:15:data Cone {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) : Type (ℓ-max ℓ ℓ') where
HITs\MappingCones\Base.agda:22:data Cones {X : Type ℓ} {Y : Type ℓ'} (A : Type ℓ'') (f : A → X → Y) : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
where
HITs\MappingCones\Properties.agda:18:PushoutUnit-iso-Cone : ∀ {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) → Iso (Pushout (const tt) f) (Cone
f)
HITs\MappingCones\Properties.agda:32:PushoutUnit≡Cone : ∀ {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) → Pushout (const tt) f ≡ Cone f
HITs\MappingCones\Properties.agda:35:ConesUnit-iso-Cone : ∀ {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) → Iso (Cones Unit (λ { tt → f }))
(Cone f)
HITs\MappingCones\Properties.agda:49:ConesUnit≡Cone : ∀ {X : Type ℓ} {Y : Type ℓ'} (f : X → Y) → (Cones Unit (λ { tt → f })) ≡ (Cone f)
HITs\Modulo\Base.agda:15:NonZero : ℕ → Type₀
HITs\Modulo\Base.agda:24:-- The Modulo type is similar to the Fin type, but instead of being
HITs\Modulo\Base.agda:39:data Modulo (k : ℕ) : Type₀ where
HITs\Modulo\Base.agda:54:  : (P : ∀ k → Modulo k → Type ℓ)
HITs\Modulo\FinEquiv.agda:17:-- residue modulo `k`, given by a value of type `Fin k`. This
HITs\Modulo\FinEquiv.agda:26:  ResiduePath : ℕ → Type₀
HITs\Nullification\Base.agda:8:module _ {ℓα ℓs} {A : Type ℓα} (S : A → Type ℓs) where
HITs\Nullification\Base.agda:9:  isNull : ∀ {ℓ} (X : Type ℓ) → Type (ℓ-max (ℓ-max ℓα ℓs) ℓ)
HITs\Nullification\Base.agda:12:  data Null {ℓ} (X : Type ℓ) : Type (ℓ-max (ℓ-max ℓα ℓs) ℓ) where
HITs\Nullification\Base.agda:21:  isNull-Null : ∀ {ℓ} {X : Type ℓ} → isNull (Null X)
HITs\Nullification\Properties.agda:31:    A : Type ℓα
HITs\Nullification\Properties.agda:32:    S : A → Type ℓs
HITs\Nullification\Properties.agda:33:    X : Type ℓ
HITs\Nullification\Properties.agda:40:isNullΠ : {Y : X → Type ℓ'} → ((x : X) → isNull S (Y x)) → isNull S ((x : X) → Y x)
HITs\Nullification\Properties.agda:58:isNullΣ : {Y : X → Type ℓ'} → (isNull S X) → ((x : X) → isNull S (Y x)) →
HITs\Nullification\Properties.agda:73:equivPreservesIsNull : {Y : Type ℓ'} → (e : X ≃ Y) → (isNull S X) → isNull S Y
HITs\Nullification\Properties.agda:80:rec : {Y : Type ℓ'} → (nB : isNull S Y) → (X → Y) → Null S X → Y
HITs\Nullification\Properties.agda:87:toPathP⁻ : (A : I → Type ℓ) {x : A i0} {y : A i1} → x ≡ transport⁻ (λ i → A i) y → PathP A x y
HITs\Nullification\Properties.agda:90:toPathP⁻-sq : ∀ {ℓ} {A : Type ℓ} (x : A) → Square (toPathP⁻ (λ _ → A) (λ _ → transport refl x))
refl
HITs\Nullification\Properties.agda:96:module _ {Y : Null S X → Type ℓ'} where
HITs\Nullification\Properties.agda:140:NullRecIsPathSplitEquiv : {Y : Type ℓ'} → (isNull S Y) → isPathSplitEquiv {A = (Null S X) → Y}
(λ f → f ∘ ∣_∣)
HITs\Nullification\Properties.agda:144:NullRecIsEquiv : {Y : Type ℓ'} → (isNull S Y) → isEquiv {A = (Null S X) → Y} (λ f → f ∘ ∣_∣)
HITs\Nullification\Properties.agda:147:NullRecEquiv : {Y : Type ℓ'} → (isNull S Y) → ((Null S X) → Y) ≃ (X → Y)
HITs\Nullification\Properties.agda:162:  We check that a few common definitions in type theory are null,
HITs\Nullification\Properties.agda:163:  assuming they are given null types as input.
HITs\Nullification\Properties.agda:169:  {Y : Type ℓ'} (nullX : isNull S X)
HITs\Nullification\Properties.agda:176:  ∀ {ℓα ℓs ℓ} {A : Type ℓα} {S : A → Type ℓs}
HITs\Nullification\Properties.agda:177:  {X : Type ℓ} {Y : Type ℓ'} → isNull S X → isNull S Y → isNull S (X ≃ Y)
HITs\Nullification\Properties.agda:188:NullModality : {A : Type ℓα} (S : A → Type ℓs) → Modality (ℓ-max ℓ (ℓ-max ℓα ℓs))
HITs\Nullification\Properties.agda:202:idemNull : ∀ {ℓa ℓs ℓ} {A : Type ℓa} (S : A → Type ℓs) (X : Type (ℓ-max ℓ (ℓ-max ℓa ℓs))) →
isNull S X → X ≃ Null S X
HITs\Nullification\Properties.agda:207:module Null-iso-Localize (S : A → Type ℓs) (X : Type ℓ) where
HITs\Nullification\Properties.agda:240:Null≃Localize : (S : A → Type ℓs) (X : Type ℓ) → Null S X ≃ Localize (λ α → const {B = S α} tt) X
HITs\Nullification\Properties.agda:244:  (X : Type ℓ) (sep : (x y : X) → isNull S (x ≡ y))
HITs\Nullification\Properties.agda:253:generatorsConnected : {A : Type ℓα} (S : A → Type ℓ) →
HITs\Nullification\Properties.agda:258:nullMap : {A : Type ℓα} (S : A → Type ℓ) →
HITs\Nullification\Properties.agda:259:  {X : Type ℓ'} {Y : Type ℓ''} → (X → Y) → Null S X → Null S Y
HITs\Nullification\Properties.agda:266:nullPreservesIso : {A : Type ℓα} (S : A → Type ℓ) → {X : Type ℓ'} →
HITs\Nullification\Properties.agda:267:  {Y : Type ℓ''} → Iso X Y → Iso (Null S X) (Null S Y)
HITs\Nullification\Properties.agda:275:nullPreservesEquiv : {A : Type ℓα} (S : A → Type ℓ) → {X : Type ℓ'} →
HITs\Nullification\Properties.agda:276:  {Y : Type ℓ''} → X ≃ Y → Null S X ≃ Null S Y
HITs\Nullification\Topological.agda:5:  from Rijke, Shulman, Spitters, Modalities in homotopy type theory.
HITs\Nullification\Topological.agda:25:  {A : Type ℓα}
HITs\Nullification\Topological.agda:26:  (S : A → Type ℓs)
HITs\Nullification\Topological.agda:33:  We use the formulation of lexness that the universe of null types is
HITs\Nullification\Topological.agda:36:  We choose the level of the universe of null types to be as low as
HITs\Nullification\Topological.agda:39:NullType : Type (ℓ-max (ℓ-suc (ℓ-max ℓ ℓs)) ℓα )
HITs\Nullification\Topological.agda:40:NullType {ℓ} = Σ[ X ∈ Type (ℓ-max ℓ ℓs) ] isNull S X
HITs\Nullification\Topological.agda:45:NullType≡isNull : (X Y : NullType {ℓ = ℓ}) → isNull S (X ≡ Y)
HITs\Nullification\Topological.agda:46:NullType≡isNull {ℓ = ℓ} X Y =
HITs\Nullification\Topological.agda:56:  {- Recall that a type Z is injective when we can extend any map S α → Z to
HITs\Nullification\Topological.agda:57:     an element of Z. We show this is the case for Z = NullType.
HITs\Nullification\Topological.agda:59:  NullTypeIsInj : (α : A) → hasSection (const {A = NullType {ℓ = ℓ}} {B = S α})
HITs\Nullification\Topological.agda:60:  fst (NullTypeIsInj α) f = ((z : S α) → fst (f z)) , isNullΠ (λ z → snd (f z))
HITs\Nullification\Topological.agda:61:  snd (NullTypeIsInj α) f = funExt (λ z → Σ≡Prop (λ _ → isPropIsNull) (ua (e z)))
HITs\Nullification\Topological.agda:76:  isNullNullTypes : isNull S (NullType {ℓ = ℓ})
HITs\Nullification\Topological.agda:77:  isNullNullTypes {ℓ} =
HITs\Nullification\Topological.agda:78:    SeparatedAndInjective→Null (NullType {ℓ = ℓ})
HITs\Nullification\Topological.agda:79:      (NullType≡isNull {ℓ = ℓ}) (NullTypeIsInj {ℓ = ℓ})
HITs\Nullification\Topological.agda:81:  topUnitWeaklyEmb : {X : Type ℓ} (x y : X) → Path (Null S X) ∣ x ∣ ∣ y ∣ ≃ Null S (x ≡ y)
HITs\Nullification\Topological.agda:84:      E : (Null S X) → NullType {ℓ = ℓ-max ℓ ℓα}
HITs\Nullification\Topological.agda:85:      E = rec (isNullNullTypes {ℓ = ℓ-max ℓ ℓα}) (λ y' → (Null S (x ≡ y')) , isNull-Null S)
HITs\Nullification\Topological.agda:99:  topUnitWeaklyInj : {X : Type ℓ} (x y : X) → Path (Null S X) ∣ x ∣ ∣ y ∣ → Null S (x ≡ y)
HITs\Nullification\Topological.agda:102:  topPreservesHLevel : {X : Type ℓ} (n : HLevel) → (isOfHLevel n X) → isOfHLevel n (Null S X)
HITs\PropositionalTruncation\Base.agda:12:-- Propositional truncation as a higher inductive type:
HITs\PropositionalTruncation\Base.agda:14:data ∥_∥₁ {ℓ} (A : Type ℓ) : Type ℓ where
HITs\PropositionalTruncation\MagicTrick.agda:5:
https://homotopytypetheory.org/2013/10/28/the-truncation-map-_-ℕ-‖ℕ‖-is-nearly-invertible/
HITs\PropositionalTruncation\MagicTrick.agda:7:Defines [recover], which definitionally satisfies `recover ∣ x ∣ ≡ x` ([recover∣∣]) for
homogeneous types
HITs\PropositionalTruncation\MagicTrick.agda:11:
https://homotopytypetheory.org/2014/02/24/composition-is-not-what-you-think-it-is-why-nearly-invertible-isnt/
HITs\PropositionalTruncation\MagicTrick.agda:42:  -- thus any truncated element (of a homogeneous type) can be recovered by agda's
normalizer!
HITs\PropositionalTruncation\MagicTrick.agda:51:    -- notice that the following typechecks because typ (B∙ ∣ x ∣₁) is definitionally
equal to to A, but
HITs\PropositionalTruncation\MagicTrick.agda:57:    -- one might wonder if (cong recover (squash₁ ∣ x ∣₁ ∣ y ∣₁)) therefore has type x
≡ y, but thankfully
HITs\PropositionalTruncation\Monad.agda:16:    P Q : Type ℓ
HITs\PropositionalTruncation\Properties.agda:27:    A B C : Type ℓ
HITs\PropositionalTruncation\Properties.agda:28:    A′ : Type ℓ'
HITs\PropositionalTruncation\Properties.agda:30:∥∥-isPropDep : (P : A → Type ℓ) → isOfHLevelDep 1 (λ x → ∥ P x ∥₁)
HITs\PropositionalTruncation\Properties.agda:33:rec : {P : Type ℓ} → isProp P → (A → P) → ∥ A ∥₁ → P
HITs\PropositionalTruncation\Properties.agda:37:rec2 : {P : Type ℓ} → isProp P → (A → B → P) → ∥ A ∥₁ → ∥ B ∥₁ → P
HITs\PropositionalTruncation\Properties.agda:42:rec3 : {P : Type ℓ} → isProp P → (A → B → C → P) → ∥ A ∥₁ → ∥ B ∥₁ → ∥ C ∥₁ → P
HITs\PropositionalTruncation\Properties.agda:48:∃-rec : {B : A → Type ℓ'} {P : Type ℓ} → isProp P → (∀ x → B x → P) → ∃[ x ∈ A ] B x → P
HITs\PropositionalTruncation\Properties.agda:52:-- rec2 : ∀ {P : Type ℓ} → isProp P → (A → A → P) → ∥ A ∥ → ∥ A ∥ → P
HITs\PropositionalTruncation\Properties.agda:56:recFin : {m : ℕ} {P : Fin m → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:57:         {B : Type ℓ'} (isPropB : isProp B)
HITs\PropositionalTruncation\Properties.agda:72:recFin2 : {m1 m2 : ℕ} {P : Fin m1 → Fin m2 → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:73:          {B : Type ℓ'} (isPropB : isProp B)
HITs\PropositionalTruncation\Properties.agda:91:elim : {P : ∥ A ∥₁ → Type ℓ} → ((a : ∥ A ∥₁) → isProp (P a))
HITs\PropositionalTruncation\Properties.agda:98:elim2 : {P : ∥ A ∥₁ → ∥ B ∥₁ → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:106:elim3 : {P : ∥ A ∥₁ → ∥ B ∥₁ → ∥ C ∥₁ → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:114:elimFin : {m : ℕ} {P : Fin m → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:115:          {B : (∀ i → ∥ P i ∥₁) → Type ℓ'}
HITs\PropositionalTruncation\Properties.agda:138:∃-elim : {B : A → Type ℓ'} {P : ∃[ x ∈ A ] B x → Type ℓ} (Pprop : ∀ s → isProp (P s))
HITs\PropositionalTruncation\Properties.agda:165:elim' : {P : ∥ A ∥₁ → Type ℓ} → ((a : ∥ A ∥₁) → isProp (P a)) →
HITs\PropositionalTruncation\Properties.agda:177:-- types as long as the function used in the eliminator is 'coherently
HITs\PropositionalTruncation\Properties.agda:270:elim→Set : ∀ {ℓ'} {A : Type ℓ'} {P : ∥ A ∥₁ → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:292:    {P : ∥ A ∥₁ → ∥ B ∥₁ → Type ℓ}
HITs\PropositionalTruncation\Properties.agda:318:module _ (B : ∥ A ∥₁ → Type ℓ)
HITs\PropositionalTruncation\Properties.agda:480:RecHSet : (P : A → TypeOfHLevel ℓ 2) → 3-Constant P → ∥ A ∥₁ → TypeOfHLevel ℓ 2
HITs\PropositionalTruncation\Properties.agda:481:RecHSet P 3kP = rec→Gpd (isOfHLevelTypeOfHLevel 2) P 3kP
HITs\PropositionalTruncation\Properties.agda:517:∥∥-Idempotent-⊎ : {A : Type ℓ} {A′ : Type ℓ'} → ∥ ∥ A ∥₁ ⊎ ∥ A′ ∥₁ ∥₁ ≡ ∥ A ⊎ A′ ∥₁
HITs\PropositionalTruncation\Properties.agda:552:∥∥-Idempotent-× : {A : Type ℓ} {A′ : Type ℓ'} → ∥ ∥ A ∥₁ × ∥ A′ ∥₁ ∥₁ ≡ ∥ A × A′ ∥₁
HITs\PropositionalTruncation\Properties.agda:557:∥∥-Idempotent-×-≃ : {A : Type ℓ} {A′ : Type ℓ'} → ∥ ∥ A ∥₁ × ∥ A′ ∥₁ ∥₁ ≃ ∥ A × A′ ∥₁
HITs\PropositionalTruncation\Properties.agda:560:∥∥-×-≃ : {A : Type ℓ} {A′ : Type ℓ'} → ∥ A ∥₁ × ∥ A′ ∥₁ ≃ ∥ A × A′ ∥₁
HITs\PropositionalTruncation\Properties.agda:563:∥∥-× : {A : Type ℓ} {A′ : Type ℓ'} → ∥ A ∥₁ × ∥ A′ ∥₁ ≡ ∥ A × A′ ∥₁
HITs\PropositionalTruncation\Properties.agda:567:rec2→Set : {A B C : Type ℓ} (Cset : isSet C)
HITs\Pushout\Base.agda:18:    X₀ X₁ X₂ Y₀ Y₁ Y₂ : Type ℓ
HITs\Pushout\Base.agda:20:data Pushout {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Pushout\Base.agda:21:             (f : A → B) (g : A → C) : Type (ℓ-max ℓ (ℓ-max ℓ' ℓ'')) where
HITs\Pushout\Base.agda:37:cofib : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) → Type _
HITs\Pushout\Base.agda:40:cofib∙ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) → Pointed _
HITs\Pushout\Base.agda:44:cfcod : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) → B → cofib f
HITs\Pushout\Base.agda:49:symPushout : {ℓ ℓ' ℓ'' : Level} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Pushout\Base.agda:59:PushoutSusp : ∀ {ℓ} (A : Type ℓ) → Type ℓ
HITs\Pushout\Base.agda:62:PushoutSusp→Susp : ∀ {ℓ} {A : Type ℓ} → PushoutSusp A → Susp A
HITs\Pushout\Base.agda:67:Susp→PushoutSusp : ∀ {ℓ} {A : Type ℓ} → Susp A → PushoutSusp A
HITs\Pushout\Base.agda:72:Susp→PushoutSusp→Susp : ∀ {ℓ} {A : Type ℓ} (x : Susp A) →
HITs\Pushout\Base.agda:78:PushoutSusp→Susp→PushoutSusp : ∀ {ℓ} {A : Type ℓ} (x : PushoutSusp A) →
HITs\Pushout\Base.agda:84:PushoutSuspIsoSusp : ∀ {ℓ} {A : Type ℓ} → Iso (PushoutSusp A) (Susp A)
HITs\Pushout\Base.agda:91:PushoutSusp≃Susp : ∀ {ℓ} {A : Type ℓ} → PushoutSusp A ≃ Susp A
HITs\Pushout\Base.agda:94:PushoutSusp≡Susp : ∀ {ℓ} {A : Type ℓ} → PushoutSusp A ≡ Susp A
HITs\Pushout\Base.agda:98:data PushoutGen {ℓ₁ ℓ₂ ℓ₃ : Level} {X : Type ℓ₁} {Y : Type ℓ₂}
HITs\Pushout\Base.agda:99:                (Q : X → Y → Type ℓ₃) : Type (ℓ-max (ℓ-max ℓ₁ ℓ₂) ℓ₃)
HITs\Pushout\Base.agda:106:module _ {ℓ₁ ℓ₂ ℓ₃ : Level} {A : Type ℓ₁} {B : Type ℓ₂} {C : Type ℓ₃}
HITs\Pushout\Base.agda:110:  doubleFib : B → C → Type _
HITs\Pushout\Base.agda:152:  {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
HITs\Pushout\Flattening.agda:22:module FlatteningLemma {ℓa ℓb ℓc} {A : Type ℓa} {B : Type ℓb} {C : Type ℓc} (f : A → B) (g : A → C)
HITs\Pushout\Flattening.agda:23:                       {ℓ} (F : B → Type ℓ) (G : C → Type ℓ) (e : ∀ a → F (f a) ≃ G (g a)) where
HITs\Pushout\Flattening.agda:25:  E : Pushout f g → Type ℓ
HITs\Pushout\Flattening.agda:58:      -- Note: the (j = i1) case typechecks because of the definitional equalities:
HITs\Pushout\Flattening.agda:63:    sq : ∀ {ℓ} {A B : Type ℓ} (e : A ≃ B)
HITs\Pushout\Flattening.agda:71:      -- Note: this typechecks because of the definitional equalities:
HITs\Pushout\KrausVonRaumer.agda:4:Kraus and von Raumer, "Path Spaces of Higher Inductive Types in Homotopy Type Theory"
HITs\Pushout\KrausVonRaumer.agda:32:    A : Type ℓ
HITs\Pushout\KrausVonRaumer.agda:33:    B : Type ℓ'
HITs\Pushout\KrausVonRaumer.agda:34:    C : Type ℓ''
HITs\Pushout\KrausVonRaumer.agda:56:  (P : ∀ b → Path (Pushout f g) (inl b₀) (inl b) → Type ℓ''')
HITs\Pushout\KrausVonRaumer.agda:57:  (Q : ∀ c → Path (Pushout f g) (inl b₀) (inr c) → Type ℓ''')
HITs\Pushout\KrausVonRaumer.agda:62:  Codes : (d : Pushout f g) (q : inl b₀ ≡ d) → Type ℓ'''
HITs\Pushout\KrausVonRaumer.agda:94:  (P : ∀ b → Path (Pushout f g) (inr c₀) (inl b) → Type ℓ''')
HITs\Pushout\KrausVonRaumer.agda:95:  (Q : ∀ c → Path (Pushout f g) (inr c₀) (inr c) → Type ℓ''')
HITs\Pushout\KrausVonRaumer.agda:100:  Codes : (d : Pushout f g) (q : inr c₀ ≡ d) → Type ℓ'''
HITs\Pushout\KrausVonRaumer.agda:138:  Q : ∀ c → ⊔.inr c₀ ≡ ⊔.inr c → Type _
HITs\Pushout\KrausVonRaumer.agda:141:  P : ∀ b → ⊔.inr c₀ ≡ ⊔.inl b → Type _
HITs\Pushout\KrausVonRaumer.agda:159:-- Further Application: Pushouts of emedding-spans of n-Types are n-Types, for n≥0
HITs\Pushout\Properties.agda:49:    A : Type ℓ
HITs\Pushout\Properties.agda:50:    B : Type ℓ'
HITs\Pushout\Properties.agda:51:    C : Type ℓ''
HITs\Pushout\Properties.agda:57:  → (P : Pushout f g → Type ℓ''')
HITs\Pushout\Properties.agda:83:pushoutIdfunEquiv : ∀ {ℓ ℓ'} {X : Type ℓ} {Y : Type ℓ'} (f : X → Y)
HITs\Pushout\Properties.agda:97:pushoutIdfunEquiv' : ∀ {ℓ ℓ'} {X : Type ℓ} {Y : Type ℓ'} (f : X → Y)
HITs\Pushout\Properties.agda:107:  record  3-span : Type (ℓ-suc ℓ*) where
HITs\Pushout\Properties.agda:109:      A0 : Type ℓ₀
HITs\Pushout\Properties.agda:110:      A2 : Type ℓ₂
HITs\Pushout\Properties.agda:111:      A4 : Type ℓ₄
HITs\Pushout\Properties.agda:115:  3span : {A0 : Type ℓ₀} {A2 : Type ℓ₂} {A4 : Type ℓ₄}
HITs\Pushout\Properties.agda:119:  spanPushout : (s : 3-span) → Type ℓ*
HITs\Pushout\Properties.agda:131:                    : Type (ℓ-suc ℓ*) where
HITs\Pushout\Properties.agda:191:Let Aᵢⱼ denote a type, fᵢⱼ a map and Hᵢⱼ a homotopy. Given a diagram of the following shape:
HITs\Pushout\Properties.agda:213:  Type (ℓ-suc (ℓ-maxList (ℓ₀₀ ∷ ℓ₀₂ ∷ ℓ₀₄ ∷ ℓ₂₀ ∷ ℓ₂₂ ∷ ℓ₂₄ ∷ ℓ₄₀ ∷ ℓ₄₂ ∷ ℓ₄₄ ∷ []))) where
HITs\Pushout\Properties.agda:215:    A00 : Type ℓ₀₀
HITs\Pushout\Properties.agda:216:    A02 : Type ℓ₀₂
HITs\Pushout\Properties.agda:217:    A04 : Type ℓ₀₄
HITs\Pushout\Properties.agda:218:    A20 : Type ℓ₂₀
HITs\Pushout\Properties.agda:219:    A22 : Type ℓ₂₂
HITs\Pushout\Properties.agda:220:    A24 : Type ℓ₂₄
HITs\Pushout\Properties.agda:221:    A40 : Type ℓ₄₀
HITs\Pushout\Properties.agda:222:    A42 : Type ℓ₄₂
HITs\Pushout\Properties.agda:223:    A44 : Type ℓ₄₄
HITs\Pushout\Properties.agda:247:  A□0 : Type _
HITs\Pushout\Properties.agda:250:  A□2 : Type _
HITs\Pushout\Properties.agda:253:  A□4 : Type _
HITs\Pushout\Properties.agda:272:  A□○ : Type _
HITs\Pushout\Properties.agda:276:  A0□ : Type _
HITs\Pushout\Properties.agda:279:  A2□ : Type _
HITs\Pushout\Properties.agda:282:  A4□ : Type _
HITs\Pushout\Properties.agda:301:  A○□ : Type _
HITs\Pushout\Properties.agda:420:  module PushoutIso {ℓ : Level} {A₁ B₁ C₁ A₂ B₂ C₂ : Type ℓ}
HITs\Pushout\Properties.agda:448:  abbrType₁ : {ℓ : Level} {A₁ B₁ C₁ A₂ B₂ C₂ : Type ℓ}
HITs\Pushout\Properties.agda:454:    → Type _
HITs\Pushout\Properties.agda:455:  abbrType₁ A≃ B≃ C≃ f₁ g₁ f₂ g₂ id1 id2 =
HITs\Pushout\Properties.agda:461:  abbrType : {ℓ : Level} {A₁ B₁ C₁ A₂ B₂ C₂ : Type ℓ}
HITs\Pushout\Properties.agda:463:          → Type _
HITs\Pushout\Properties.agda:464:  abbrType {A₁ = A₁} {B₁ = B₁} {C₁ = C₁} {A₂ = A₂} {B₂ = B₂} {C₂ = C₂}
HITs\Pushout\Properties.agda:470:    → abbrType₁ A≃ B≃ C≃ f₁ g₁ f₂ g₂ id1 id2
HITs\Pushout\Properties.agda:472:  F-G-cancel : {ℓ : Level} {A₁ B₁ C₁ A₂ B₂ C₂ : Type ℓ}
HITs\Pushout\Properties.agda:474:             → abbrType A≃ B≃ C≃
HITs\Pushout\Properties.agda:477:      abbrType A≃ B≃ C≃)
HITs\Pushout\Properties.agda:479:      abbrType (idEquiv A₂) B≃ C≃)
HITs\Pushout\Properties.agda:480:        (EquivJ (λ C₁ C≃ → abbrType (idEquiv A₂) (idEquiv B₂) C≃)
HITs\Pushout\Properties.agda:483:                          → abbrType₁ (idEquiv A₂) (idEquiv B₂) (idEquiv C₂)
HITs\Pushout\Properties.agda:485:                 (J (λ g₂ id2 → abbrType₁ (idEquiv A₂) (idEquiv B₂) (idEquiv C₂)
HITs\Pushout\Properties.agda:491:      → abbrType₁ (idEquiv A₂) (idEquiv B₂) (idEquiv C₂)
HITs\Pushout\Properties.agda:495:      refl-lem : ∀ {ℓ} {A : Type ℓ} (x : A)
HITs\Pushout\Properties.agda:533:module _ {ℓ : Level} {A₁ B₁ C₁ A₂ B₂ C₂ : Type ℓ}
HITs\Pushout\Properties.agda:555:  {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} (f : A → B) (g : A → C) where
HITs\Pushout\Properties.agda:559:  PushoutLift : Type PushoutLevel
HITs\Pushout\Properties.agda:582:      {A₁ : Type ℓA₁} {B₁ : Type ℓB₁} {C₁ : Type ℓC₁}
HITs\Pushout\Properties.agda:583:      {A₂ : Type ℓA₂} {B₂ : Type ℓB₂} {C₂ : Type ℓC₂}
HITs\Pushout\Properties.agda:630:module _ {ℓ ℓ' ℓ'' ℓ'''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
HITs\Pushout\Properties.agda:631:  (f : A → B) (g : A → C) (X : Pushout f g → Type ℓ''') where
HITs\Pushout\Properties.agda:640:  PushoutΣ : Type _
HITs\Pushout\Properties.agda:657:module _ {C : Type ℓ} {B : Type ℓ'} where
HITs\Pushout\Properties.agda:658:  PushoutAlongEquiv→ : {A : Type ℓ}
HITs\Pushout\Properties.agda:665:    PushoutAlongEquiv→Cancel : {A : Type ℓ} (e : A ≃ C) (f : A → B)
HITs\Pushout\Properties.agda:674:  PushoutAlongEquiv : {A : Type ℓ} (e : A ≃ C) (f : A → B)
HITs\Pushout\Properties.agda:682:  {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} {D : Type ℓ'''}
HITs\Pushout\Properties.agda:727:PushoutEmptyDomainIso : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
HITs\Pushout\Properties.agda:739:  {A : Type ℓA} {A' : Type ℓA'} {B : Type ℓB} {B' : Type ℓB'}
HITs\Pushout\Properties.agda:740:  {C : Type ℓC}
HITs\Pushout\Properties.agda:753:  liftEq : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (ℓ* : Level)
HITs\Pushout\Properties.agda:757:  PushoutCompEquivIso' : ∀ {ℓ ℓ' ℓ''} {A A' : Type ℓ} {B B' : Type ℓ'} {C : Type ℓ''}
HITs\Pushout\Properties.agda:852:  record  commSquare : Type (ℓ-suc ℓ*) where
HITs\Pushout\Properties.agda:856:      P : Type ℓP
HITs\Pushout\Properties.agda:868:  isPushoutSquare : commSquare → Type _
HITs\Pushout\Properties.agda:871:  PushoutSquare : Type (ℓ-suc ℓ*)
HITs\Pushout\Properties.agda:875:  {P' : Type ℓP'} where
HITs\Pushout\Properties.agda:965:  {A : Type ℓA} {B : Type ℓB}
HITs\Pushout\Properties.agda:1002:    P' : Type _
HITs\Pushout\Properties.agda:1045:    B'tot : Type _
HITs\Pushout\Properties.agda:1134:  {A : Type ℓA} {B : Type ℓB}
HITs\Pushout\PushoutProduct.agda:28:    A : Type ℓ
HITs\Pushout\PushoutProduct.agda:29:    B : Type ℓ'
HITs\Pushout\PushoutProduct.agda:30:    X : Type ℓ''
HITs\Pushout\PushoutProduct.agda:31:    Y : Type ℓ'''
HITs\Pushout\PushoutProduct.agda:36:PushProd : (f : X → A)(g : Y → B) → Type _
HITs\Pushout\PushoutProduct.agda:51:  (P : A × B → TypeOfHLevel ℓ (m + n)) where
HITs\Pushout\PushoutProduct.agda:57:      fam : A → Type _
HITs\Replacement\Base.agda:3:Type-theoretic replacement: a construction taking a map F : A → B where
HITs\Replacement\Base.agda:4:  - A : Type ℓA
HITs\Replacement\Base.agda:5:  - B : Type ℓB,
HITs\Replacement\Base.agda:6:  - the identity types of B essentially have universe level ℓ≅B,
HITs\Replacement\Base.agda:15:for a definition of type-theoretic replacement.
HITs\Replacement\Base.agda:29:The datatype defined in this module originally included a third constructor
HITs\Replacement\Base.agda:48:module _ {ℓA ℓB ℓ≅B} {A : Type ℓA} {B : Type ℓB} (𝒮-B : UARel B ℓ≅B) (f : A → B)  where
HITs\Replacement\Base.agda:52:  data Replacement : Type (ℓ-max ℓA ℓ≅B)
HITs\Replacement\Base.agda:67:  elimProp : ∀ {ℓ} {P : Replacement → Type ℓ}
HITs\RPn\Base.agda:5:   [BR17] U. Buchholtz, E. Rijke, The real projective spaces in homotopy type theory.
HITs\RPn\Base.agda:22:open import Cubical.Structures.TypeEqvTo
HITs\RPn\Base.agda:42:    A : Type ℓ
HITs\RPn\Base.agda:45:data RP² : Type₀ where
HITs\RPn\Base.agda:52:2-EltType₀    = TypeEqvTo    ℓ-zero Bool -- Σ[ X ∈ Type₀ ] ∥ X ≃ Bool ∥
HITs\RPn\Base.agda:53:2-EltPointed₀ = PointedEqvTo ℓ-zero Bool -- Σ[ X ∈ Type₀ ] X × ∥ X ≃ Bool ∥
HITs\RPn\Base.agda:55:Bool* : 2-EltType₀
HITs\RPn\Base.agda:60:--  for any 2-element type (A, ∣e∣).
HITs\RPn\Base.agda:81:--  2-element pointed type (X , x, ∣e∣).
HITs\RPn\Base.agda:93:module ⊕* (X : 2-EltType₀) where
HITs\RPn\Base.agda:108:  elim : ∀ {ℓ'} (P : (A : Type₀) (_⊕'_ : A → A → Bool) → Type ℓ') (propP : ∀ A _⊕'_ → isProp (P A _⊕'_))
HITs\RPn\Base.agda:115:          R₂ : (B : Type₀) → B ≃ Bool → B → B → Bool
HITs\RPn\Base.agda:145:RP  : ℕ₋₁ → Type₀
HITs\RPn\Base.agda:146:cov⁻¹ : (n : ℕ₋₁) → RP n → 2-EltType₀ -- (see Cubical.Functions.Bundle)
HITs\RPn\Base.agda:175:        RP (n-1) - - - - - - > Type
HITs\RPn\Base.agda:197:       A — — — — > C                 Define:   E : Pushout f g → Type
HITs\RPn\Base.agda:201:       B — — — — > Type
HITs\RPn\Base.agda:330:elimSetRP² : {A : RP² → Type ℓ} → ((x : RP²) → isSet (A x))
HITs\RPn\Base.agda:339:elimPropRP² : {A : RP² → Type ℓ} → ((x : RP²) → isProp (A x))
HITs\RPn\Base.agda:346:characRP²Fun : ∀ {ℓ} {A : Type ℓ} (f : RP² → A)
HITs\RPn\Base.agda:351:RP²FunCharacIso : {A : RP² → Type ℓ}
HITs\S1\Base.agda:22:data S¹ : Type₀ where
HITs\S1\Base.agda:36:helix : S¹ → Type₀
HITs\S1\Base.agda:40:ΩS¹ : Type₀
HITs\S1\Base.agda:149:basedΩS¹ : (x : S¹) → Type₀
HITs\S1\Base.agda:265:toPropElim : ∀ {ℓ} {B : S¹ → Type ℓ}
HITs\S1\Base.agda:273:toPropElim2 : ∀ {ℓ} {B : S¹ → S¹ → Type ℓ}
HITs\S1\Base.agda:289:toSetElim2 : ∀ {ℓ} {B : S¹ → S¹ → Type ℓ}
HITs\S1\Base.agda:410:isPropFamS¹ : ∀ {ℓ} (P : S¹ → Type ℓ) (pP : (x : S¹) → isProp (P x)) (b0 : P base) →
HITs\S1\Properties.agda:13:rec : ∀ {ℓ} {A : Type ℓ} (b : A) (l : b ≡ b) → S¹ → A
HITs\S1\Properties.agda:17:elim : ∀ {ℓ} (C : S¹ → Type ℓ) (b : C base) (l : PathP (λ i → C (loop i)) b b) → (x : S¹) → C x
HITs\S1\Properties.agda:36:IsoFunSpaceS¹ : ∀ {ℓ} {A : Type ℓ} → Iso (S¹ → A) (Σ[ x ∈ A ] x ≡ x)
HITs\S2\Base.agda:6:data S² : Type₀ where
HITs\S2\Properties.agda:17:S²ToSetElim : ∀ {ℓ} {A : S² → Type ℓ}
HITs\S2\Properties.agda:26:wedgeconFunS² : ∀ {ℓ} {P : S² → S² → Type ℓ}
HITs\S2\Properties.agda:46:wedgeconFunS²Id : ∀ {ℓ} {P : S² → S² → Type ℓ}
HITs\S2\Properties.agda:121:  sym≡cong-sym-refl : ∀ {ℓ} {A : Type ℓ} {x : A} → sym≡cong-sym (λ _ _ → x) ≡ refl
HITs\S3\Base.agda:7:data S³ : Type₀ where
HITs\SequentialColimit\Base.agda:19:data SeqColim (X : Sequence ℓ) : Type ℓ where
HITs\SequentialColimit\Base.agda:23:data FinSeqColim (m : ℕ) (X : Sequence ℓ) : Type ℓ where
HITs\SequentialColimit\Properties.agda:43:  record ElimData (P : SeqColim X → Type ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\SequentialColimit\Properties.agda:49:  record ElimDataShifted (n : ℕ)(P : SeqColim X → Type ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\SequentialColimit\Properties.agda:58:  ElimData→ElimDataShifted : (n : ℕ)(P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:71:    (P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:99:    (n : ℕ)(P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:147:      (P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:154:    → (P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:161:    → (P : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:182:      (n : ℕ)(Y : SeqColim X → Type ℓ')
HITs\SequentialColimit\Properties.agda:190:      (Y : SeqColim X → TypeOfHLevel ℓ' d) where
HITs\SequentialColimit\Properties.agda:225:        (Y : SeqColim X → TypeOfHLevel ℓ' d) where
HITs\SequentialColimit\Properties.agda:272:  module _ {P : (k : ℕ) → seq .obj (k + n) → Type ℓ}
HITs\SequentialColimit\Properties.agda:289:      lem : ∀ {ℓ ℓ'} {A B : Type ℓ} (e : A ≃ B) (x : A)
HITs\SequentialColimit\Properties.agda:290:            (P : B → Type ℓ') (πP : (x : A) → P (fst e x))
HITs\SequentialColimit\Properties.agda:293:        EquivJ (λ A e → (x : A) (P : B → Type ℓ') (πP : (x : A) → P (fst e x))
HITs\SequentialColimit\Properties.agda:383:SeqColim→Prop : ∀ {ℓ ℓ'} {C : Sequence ℓ} {B : SeqColim C → Type ℓ'}
HITs\SequentialColimit\Properties.agda:537:  {X : Sequence ℓ} {m : ℕ} {B : FinSeqColim m X → Type ℓ'}
HITs\SequentialColimit\Properties.agda:620:  PushoutSequenceFam : ℕ → Type _
HITs\SequentialColimit\Properties.agda:635:  PushoutColim : Type _
HITs\SetCoequalizer\Base.agda:15:    A : Type ℓ
HITs\SetCoequalizer\Base.agda:16:    B : Type ℓ'
HITs\SetCoequalizer\Base.agda:18:-- Set coequalizers as a higher inductive type
HITs\SetCoequalizer\Base.agda:19:data SetCoequalizer {A : Type ℓ} {B : Type ℓ'} (f g : A → B) : Type (ℓ-max ℓ ℓ') where
HITs\SetCoequalizer\Properties.agda:20:    A : Type ℓ
HITs\SetCoequalizer\Properties.agda:21:    B : Type ℓ'
HITs\SetCoequalizer\Properties.agda:24:elimProp : {f g : A → B} {C : SetCoequalizer f g → Type ℓ}
HITs\SetCoequalizer\Properties.agda:37:elimProp2 : {A' : Type ℓ} {B' : Type ℓ'} {f g : A → B} {f' g' : A' → B'}
HITs\SetCoequalizer\Properties.agda:38:            {C : SetCoequalizer f g → SetCoequalizer f' g' → Type (ℓ-max ℓ ℓ')}
HITs\SetCoequalizer\Properties.agda:45:elimProp3 : {A' A'' : Type ℓ} {B' B'' : Type ℓ'} {f g : A → B} {f' g' : A' → B'}
HITs\SetCoequalizer\Properties.agda:48:               → Type (ℓ-max ℓ ℓ')}
HITs\SetCoequalizer\Properties.agda:59:rec : {C : Type ℓ''} {f g : A → B}
HITs\SetCoequalizer\Properties.agda:70:rec2 : {A' : Type ℓ} {B' : Type ℓ'} {C : Type ℓ''} {f g : A → B} {f' g' : A' → B'}
HITs\SetCoequalizer\Properties.agda:94:  inducedHom : {C : Type ℓ''} {f g : A → B}
HITs\SetCoequalizer\Properties.agda:101:  commutativity : {C : Type ℓ''} {f g : A → B}
HITs\SetCoequalizer\Properties.agda:108:  uniqueness : {C : Type ℓ''}
HITs\SetQuotients\Base.agda:12:-- Set quotients as a higher inductive type:
HITs\SetQuotients\Base.agda:13:data _/_ {ℓ ℓ'} (A : Type ℓ) (R : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\SetQuotients\EqClass.agda:32:  (X : Type ℓ) where
HITs\SetQuotients\EqClass.agda:34:  ℙ : Type (ℓ-max ℓ (ℓ-suc ℓ'))
HITs\SetQuotients\EqClass.agda:37:  ℙDec : Type (ℓ-max ℓ (ℓ-suc ℓ'))
HITs\SetQuotients\EqClass.agda:47:    (R : X → X → Type ℓ'') where
HITs\SetQuotients\EqClass.agda:49:    isEqClass : ℙ → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
HITs\SetQuotients\EqClass.agda:55:    _∥_ : Type (ℓ-max (ℓ-max ℓ (ℓ-suc ℓ')) ℓ'')
HITs\SetQuotients\EqClass.agda:64:      _∥Dec_ : Type (ℓ-max (ℓ-max ℓ (ℓ-suc ℓ')) ℓ'')
HITs\SetQuotients\EqClass.agda:87:  (X : Type ℓ)
HITs\SetQuotients\EqClass.agda:88:  (R : X → X → Type ℓ'')
HITs\SetQuotients\Properties.agda:27:open import Cubical.HITs.TypeQuotients as TypeQuot using (_/ₜ_ ; [_] ; eq/)
HITs\SetQuotients\Properties.agda:38:    A B C Q : Type ℓ
HITs\SetQuotients\Properties.agda:39:    R S T W : A → A → Type ℓ
HITs\SetQuotients\Properties.agda:41:elimProp : {P : A / R → Type ℓ}
HITs\SetQuotients\Properties.agda:54:elimProp2 : {P : A / R → B / S → Type ℓ}
HITs\SetQuotients\Properties.agda:62:elimProp3 : {P : A / R → B / S → C / T → Type ℓ}
HITs\SetQuotients\Properties.agda:70:elimProp4 : {P : A / R → B / S → C / T → Q / W → Type ℓ}
HITs\SetQuotients\Properties.agda:79:elimContr : {P : A / R → Type ℓ}
HITs\SetQuotients\Properties.agda:86:elimContr2 : {P : A / R → B / S → Type ℓ}
HITs\SetQuotients\Properties.agda:97:elim : {P : A / R → Type ℓ}
HITs\SetQuotients\Properties.agda:149:-- i.e. for any type A with a binary relation R and groupoid B,
HITs\SetQuotients\Properties.agda:155:-- by set-truncating the (non-truncated type quotient)
HITs\SetQuotients\Properties.agda:156:typeQuotSetTruncIso : Iso (A / R) ∥ A /ₜ R ∥₂
HITs\SetQuotients\Properties.agda:157:Iso.fun typeQuotSetTruncIso = rec isSetSetTrunc (λ a → ∣ [ a ] ∣₂)
HITs\SetQuotients\Properties.agda:159:Iso.inv typeQuotSetTruncIso = SetTrunc.rec squash/ (TypeQuot.rec [_] eq/)
HITs\SetQuotients\Properties.agda:160:Iso.sec typeQuotSetTruncIso = SetTrunc.elim (λ _ → isProp→isSet (squash₂ _ _))
HITs\SetQuotients\Properties.agda:161:                                  (TypeQuot.elimProp (λ _ → squash₂ _ _) λ _ → refl)
HITs\SetQuotients\Properties.agda:162:Iso.ret typeQuotSetTruncIso = elimProp (λ _ → squash/ _ _) λ _ → refl
HITs\SetQuotients\Properties.agda:164:module rec→Gpd {B : Type ℓ''} (Bgpd : isGroupoid B)
HITs\SetQuotients\Properties.agda:177:      f/ = TypeQuot.rec f feq
HITs\SetQuotients\Properties.agda:181:        TypeQuot.elimProp2
HITs\SetQuotients\Properties.agda:186:    f₂ = Iso.fun typeQuotSetTruncIso
HITs\SetQuotients\Properties.agda:309:-- path-types for equivalence relations (not prop-valued)
HITs\SetQuotients\Properties.agda:342:descendMapPath : {M : Type ℓ} (f g : A / R → M) (isSetM : isSet M)
HITs\SetQuotients\Properties.agda:357:module _  {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ} (ER : isEquivRel R) where
HITs\SetQuotients\Properties.agda:359:  retract/R : (f : A → B) → (g : B → A) → Type ℓ
HITs\SetQuotients\Properties.agda:362:record Iso/R  (A : Type ℓ) (B : Type ℓ') {R : A → A → Type ℓ} (ER : isEquivRel R) : Type (ℓ-max ℓ
ℓ') where
HITs\SetQuotients\Properties.agda:373:R* : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} {iso/r : Iso/R A B {R}
ER} → B → B → Type ℓ
HITs\SetQuotients\Properties.agda:376:section/R : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} {iso/r : Iso/R A B
{R} ER} → Type (ℓ-max ℓ ℓ')
HITs\SetQuotients\Properties.agda:379:retract/R→section/R : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} {iso/r :
Iso/R A B {R} ER} →
HITs\SetQuotients\Properties.agda:384:Iso/R→RelIso : {A : Type ℓ} {A' : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} → (iso/r :
Iso/R A A' {R} ER) → RelIso {A = A} R {A' = A'} (R* {iso/r = iso/r})
HITs\SetQuotients\Properties.agda:388:iso/R-A≡B : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R} → (AB : A ≡ B) →
Iso/R A B ER
HITs\SetQuotients\Properties.agda:398:ER≡ : (A : Type ℓ) → isEquivRel ((_≡_) {ℓ = ℓ} {A})
HITs\SetQuotients\Properties.agda:401:R→R* : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} → {iso/r : Iso/R A B
{R} ER}{a a' : A}
HITs\SetQuotients\Properties.agda:408:R*→R : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} → {iso/r : Iso/R A B
{R} ER}{b b' : B} →
HITs\SetQuotients\Properties.agda:415:iso/R→≡→Iso : {A : Type ℓ} {B : Type ℓ'} →
HITs\SetQuotients\Properties.agda:433:isEquivRelR* : (A : Type ℓ) (B : Type ℓ') {R : A → A → Type ℓ} {ER : isEquivRel R} → (iso/r :
Iso/R A B ER) → isEquivRel (R* {iso/r = iso/r})
HITs\SetQuotients\Properties.agda:440:iso/R→Iso/R* : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R} →
HITs\SetQuotients\Properties.agda:446:isPropR→IsPropR* : {A : Type ℓ} {B : Type ℓ'} {R : A → A → Type ℓ}{ER : isEquivRel R} → (iso/r :
Iso/R {ℓ} A B {R} ER)
HITs\SetQuotients\Properties.agda:451:isPropR→IsPropR** : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R} → (iso/r :
Iso/R {ℓ} A B {R} ER)
HITs\SetQuotients\Properties.agda:456:R**→R :  {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER}
HITs\SetQuotients\Properties.agda:463:R→R** :  {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER}
HITs\SetQuotients\Properties.agda:470:R*-IsProp-Def1 : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel
R}{iso/r : Iso/R {ℓ} A B {R} ER}
HITs\SetQuotients\Properties.agda:478:R**≡R : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER}
HITs\SetQuotients\Properties.agda:489:R*≡Rinv :  {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r : Iso/R A B
{R} ER} →
HITs\SetQuotients\Properties.agda:493:R*≡λttHlp :  {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{AB : A ≡ B} →
HITs\SetQuotients\Properties.agda:501:R*≡λR :  {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r : Iso/R A B {R}
ER} →
HITs\SetQuotients\Properties.agda:505:R*≡λtt :  {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{AB : A ≡ B} →
HITs\SetQuotients\Properties.agda:510:A/R→B/R* : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER} →
HITs\SetQuotients\Properties.agda:517:B/R*→A/R : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER} →
HITs\SetQuotients\Properties.agda:525:raa'→[a]≡[a'] : {ℓ : Level} {A : Type ℓ} {R : A → A → Type ℓ} {a a' : A} → R a a' → (_≡_) {ℓ} {A
/ R} (_/_.[ a ]) (_/_.[ a' ])
HITs\SetQuotients\Properties.agda:528:∥f∥₁-map : {A : Type ℓ} {B : Type ℓ'} → (f : A → B) → ∥ A ∥₁ → ∥ B ∥₁
HITs\SetQuotients\Properties.agda:531:extrapolate[] : {ℓ : Level} {A : Type ℓ} {R : A → A → Type ℓ} →
HITs\SetQuotients\Properties.agda:548:isoA/R-B/R'Hlp3 : {ℓ : Level} {A : Type ℓ} {R : A → A → Type ℓ} →
HITs\SetQuotients\Properties.agda:552:isoA/R-B/R'Hlp1 : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}
HITs\SetQuotients\Properties.agda:565:isoA/R-B/R'Hlp2 : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}
HITs\SetQuotients\Properties.agda:582:isoA/R-B/R' : {ℓ : Level} {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r
: Iso/R {ℓ} A B {R} ER} →
HITs\SetQuotients\Properties.agda:588:quotientEqualityLemma : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{ER : isEquivRel R}{iso/r :
Iso/R {ℓ} A B {R} ER}
HITs\SetQuotients\Properties.agda:593:A/R≡A/R'Hlp : {A : Type ℓ} → {R R' : A → A → Type ℓ} →
HITs\SetQuotients\Properties.agda:606:quotientRule : {A : Type ℓ} → {R R' : A → A → Type ℓ} → (RR' : R ≡ R') → A / R ≡ A / R'
HITs\SetQuotients\Properties.agda:609:A/R≡A/R'Hlp2 : {A : Type ℓ} → {R R' : A → A → Type ℓ} →
HITs\SetQuotients\Properties.agda:615:truncRel≡ : {A : Type ℓ}{R : A → A → Type ℓ} → (A / R) ≡ (A / (λ a b → ∥ R a b ∥₁))
HITs\SetQuotients\Properties.agda:619:A/R≡A/R' : {A : Type ℓ} → {R R' : A → A → Type ℓ} →
HITs\SetQuotients\Properties.agda:624:quotientEqualityLemma2 : {A B : Type ℓ}{R : A → A → Type ℓ}{ER : isEquivRel R} →
HITs\SetQuotients\Properties.agda:631:quotientEqualityLemma3 : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{R' : B → B → Type ℓ}
HITs\SetQuotients\Properties.agda:642:quotientEqualityLemma4 : {A : Type ℓ} {B : Type ℓ} {R : A → A → Type ℓ}{R' : B → B → Type ℓ}
HITs\SetTruncation\Base.agda:13:-- set truncation as a higher inductive type:
HITs\SetTruncation\Base.agda:15:data ∥_∥₂ {ℓ} (A : Type ℓ) : Type ℓ where
HITs\SetTruncation\Fibers.agda:34:  {X : Type ℓ }
HITs\SetTruncation\Fibers.agda:35:  {Y : Type ℓ'}
HITs\SetTruncation\Fibers.agda:49:    fiberRel : ∥ fiber f y ∥₂ → ∥ fiber f y ∥₂ → Type ℓ
HITs\SetTruncation\Fibers.agda:133:    fiberRel2 : (x x' : ∥ fiber f y ∥₂) → Type (ℓ-max ℓ ℓ')
HITs\SetTruncation\Properties.agda:27:    A : Type ℓa
HITs\SetTruncation\Properties.agda:28:    B : Type ℓb
HITs\SetTruncation\Properties.agda:29:    C : Type ℓc
HITs\SetTruncation\Properties.agda:30:    D : Type ℓd
HITs\SetTruncation\Properties.agda:51:elim : {B : ∥ A ∥₂ → Type ℓ}
HITs\SetTruncation\Properties.agda:60:elim2 : {C : ∥ A ∥₂ → ∥ B ∥₂ → Type ℓ}
HITs\SetTruncation\Properties.agda:77:elim3 : {D : ∥ A ∥₂ → ∥ B ∥₂ → ∥ C ∥₂ → Type ℓ}
HITs\SetTruncation\Properties.agda:84:elim4 : {E : ∥ A ∥₂ → ∥ B ∥₂ → ∥ C ∥₂ → ∥ D ∥₂ → Type ℓ}
HITs\SetTruncation\Properties.agda:95:-- i.e. for any type A and groupoid B we can construct a map ∥ A ∥₂ → B
HITs\SetTruncation\Properties.agda:99:module rec→Gpd {A : Type ℓ} {B : Type ℓ'} (Bgpd : isGroupoid B) (f : A → B)
HITs\SetTruncation\Properties.agda:102: data H : Type ℓ where
HITs\SetTruncation\Properties.agda:109: module Helim {P : H → Type ℓ''} (Pgpd : ∀ h → isGroupoid (P h))
HITs\SetTruncation\Properties.agda:127: module Hrec {C : Type ℓ''} (Cgpd : isGroupoid C)
HITs\SetTruncation\Properties.agda:139: module HelimProp {P : H → Type ℓ''} (Pprop : ∀ h → isProp (P h))
HITs\SetTruncation\Properties.agda:151: module HelimSet {P : H → Type ℓ''} (Pset : ∀ h → isSet (P h))
HITs\SetTruncation\Properties.agda:168: localHedbergLemma : {X : Type ℓ''} (P : X → Type ℓ'')
HITs\SetTruncation\Properties.agda:262:sigmaElim : {B : ∥ A ∥₂ → Type ℓ} {C : Σ ∥ A ∥₂ B  → Type ℓ'}
HITs\SetTruncation\Properties.agda:269:sigmaProdElim : {C : ∥ A ∥₂ × ∥ B ∥₂ → Type ℓ} {D : Σ (∥ A ∥₂ × ∥ B ∥₂) C  → Type ℓ'}
HITs\SetTruncation\Properties.agda:279:prodElim : {C : ∥ A ∥₂ × ∥ B ∥₂ → Type ℓ}
HITs\SetTruncation\Properties.agda:285:prodRec : {C : Type ℓ} → isSet C → (A → B → C) → ∥ A ∥₂ × ∥ B ∥₂ → C
HITs\SetTruncation\Properties.agda:288:prodElim2 : {E : (∥ A ∥₂ × ∥ B ∥₂) → (∥ C ∥₂ × ∥ D ∥₂) → Type ℓ}
HITs\SetTruncation\Properties.agda:304:IsoSetTruncateSndΣ : {A : Type ℓ} {B : A → Type ℓ'} → Iso ∥ Σ A B ∥₂ ∥ Σ A (λ x → ∥ B x ∥₂) ∥₂
HITs\SetTruncation\Properties.agda:311:setSigmaIso : {B : A → Type ℓ} → Iso ∥ Σ A B ∥₂ ∥ Σ A (λ x → ∥ B x ∥₂) ∥₂
HITs\SetTruncation\Properties.agda:316:  transport (λ i → rec {B = TypeOfHLevel _ 1} (isOfHLevelTypeOfHLevel 1)
HITs\SetTruncation\Properties.agda:323:mapFunctorial : {A B C : Type ℓ} (f : A → B) (g : B → C)
HITs\SmashProduct\Base.agda:25:data Smash {ℓ ℓ'} (A : Pointed ℓ) (B : Pointed ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\SmashProduct\Base.agda:69:_⋀_ : Pointed ℓ → Pointed ℓ' → Type (ℓ-max ℓ ℓ')
HITs\SmashProduct\Base.agda:165:  isContrIso : ∀ {ℓ ℓ'} {A : Type ℓ} (a : A) (B : singl a → Type ℓ')
HITs\SmashProduct\Base.agda:176:-- induction priciples for maps into pointed types
HITs\SmashProduct\Base.agda:197:⋀→Homogeneous≡ : {A B : Pointed ℓ} {D : Type ℓ'}
HITs\SmashProduct\Base.agda:213:⋀^→Homogeneous≡ : (n : ℕ) (A : Fin (suc n) → Pointed ℓ) {B : Type ℓ'}
HITs\SmashProduct\Base.agda:264:_⋀→refl_ : ∀ {ℓ ℓ'} {C : Type ℓ} {D : Type ℓ'}
HITs\SmashProduct\Base.agda:274:_⋀∙→refl_ : ∀ {ℓ ℓ'} {C : Type ℓ} {D : Type ℓ'}
HITs\SmashProduct\Base.agda:332:  data ⋀×2 : Type (ℓ-max ℓ (ℓ-max ℓ' ℓ'')) where
HITs\SmashProduct\Base.agda:851:module _ {C : Type ℓ} (f g : A ⋀ B → C)
HITs\SmashProduct\Base.agda:901:module ⋀-fun≡' {C : Type ℓ} (f g : A ⋀ B → C)
HITs\SmashProduct\Base.agda:952:   sm-fillᵣ : ∀ {ℓ} {A : Type ℓ} {x* : A} (y* : A) (p* : x* ≡ y*)
HITs\SmashProduct\Base.agda:963:   sm-fillₗ : ∀ {ℓ} {A : Type ℓ} {x* : A} (y* : A) (p* : x* ≡ y*)
HITs\SmashProduct\Base.agda:974:   sm-fillₗᵣ≡ : ∀ {ℓ} {A : Type ℓ} {x* : A} (y* : A) (p* : x* ≡ y*)
HITs\SmashProduct\Induction.agda:42:FS : (n : ℕ) → FinFamily (suc n) ℓ → Type ℓ
HITs\SmashProduct\Induction.agda:56:⋀̃ : (n : ℕ) (A : FinFamily∙ (suc n) ℓ) → Type ℓ
HITs\SmashProduct\Induction.agda:109:⋀̃→⋀-ind : (n : ℕ) (A : FinFamily∙ (suc n) ℓ) {B : Type ℓ'}
HITs\SmashProduct\Induction.agda:116:⋀̃→⋀-ind-coh : (n : ℕ) (A : FinFamily∙ (suc n) ℓ) {B : Type ℓ'}
HITs\SmashProduct\SymmetricMonoidalCat.agda:4:of pointed types into a symmetric monoidal wild category. The pentagon
HITs\Sn\Base.agda:12:S : ℕ₋₁ → Type₀
HITs\Sn\Base.agda:16:S₊ : ℕ → Type₀
HITs\Sn\Base.agda:22:S⁻ : ℕ → Type
HITs\Sn\Multiplication.agda:545:sym^ : ∀ {ℓ} {A : Type ℓ} {x : A} (n : ℕ) → x ≡ x → x ≡ x
HITs\Sn\Multiplication.agda:609:  master-lem : ∀ {ℓ} {A : Type ℓ} {x : A} (p : x ≡ x) (coh : refl ≡ p)
HITs\Sn\Properties.agda:82:sphereElim : (n : ℕ) {A : (S₊ (suc n)) → Type ℓ} → ((x : S₊ (suc n)) → isOfHLevel (suc n) (A x))
HITs\Sn\Properties.agda:94:sphereElim2 : ∀ {ℓ} (n : ℕ) {A : (S₊ (suc n)) → (S₊ (suc n)) → Type ℓ}
HITs\Sn\Properties.agda:102:  compPath-lem : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : z ≡ y)
HITs\Sn\Properties.agda:110:sphereElim' : (n : ℕ) {A : S₊ n → Type ℓ} →
HITs\Sn\Properties.agda:116:sphereToPropElim : (n : ℕ) {A : (S₊ (suc n)) → Type ℓ} → ((x : S₊ (suc n)) → isProp (A x))
HITs\Sn\Properties.agda:134:wedgeconFun : (n m : ℕ) {A : (S₊ (suc n)) → (S₊ (suc m)) → Type ℓ}
HITs\Sn\Properties.agda:140:wedgeconLeft : (n m : ℕ) {A : (S₊ (suc n)) → (S₊ (suc m)) → Type ℓ}
HITs\Sn\Properties.agda:146:wedgeconRight : (n m : ℕ) {A : (S₊ (suc n)) → (S₊ (suc m)) → Type ℓ}
HITs\Sn\Properties.agda:337:sphereToTrunc : (n : ℕ) {A : S⁻ n → Type ℓ}
HITs\Sn\Properties.agda:360:  lem : ({A : S₊ (suc n) → Type _} →
HITs\Sn\Properties.agda:455:  l : ∀ {ℓ} {A : Type ℓ} {x : A} (p : x ≡ x) (P : refl ≡ p)
HITs\SphereBouquet\Base.agda:13:SphereBouquet : ∀ {ℓ} (n : ℕ) (A : Type ℓ) → Type ℓ
HITs\SphereBouquet\Base.agda:16:SphereBouquet∙ : ∀ {ℓ} (n : ℕ) (A : Type ℓ) → Pointed ℓ
HITs\SphereBouquet\Base.agda:19:FinSphereBouquetMap : (c1 c2 : ℕ) (n : ℕ) → Type
HITs\SphereBouquet\Base.agda:23:FinSphereBouquetMap∙ : (c1 c2 : ℕ) (n : ℕ) → Type
HITs\SphereBouquet\Degree.agda:80:  ⋁gen→∙Kn≡ : {A : Type ℓ} {B : A → Pointed ℓ'} (m : ℕ)
HITs\SphereBouquet\Degree.agda:131:  ⋁gen→∙Kn≡∙ : {A : Type ℓ} {B : A → Pointed ℓ'} (m : ℕ)
HITs\SphereBouquet\Properties.agda:35:SphereBouquet→Prop : (n : ℕ) {A : Type ℓ} (a : A)
HITs\SphereBouquet\Properties.agda:36:  → {B : SphereBouquet n A → Type ℓ'}
HITs\SphereBouquet\Properties.agda:53:isConnectedSphereBouquet : {n : ℕ} {A : Type ℓ}
HITs\SphereBouquet\Properties.agda:60:isConnectedSphereBouquet' : {n : ℕ} {A : Type ℓ}
HITs\SphereBouquet\Properties.agda:78:sphereBouquetSuspIso₀ : {A : Type ℓ}
HITs\SphereBouquet\Properties.agda:115:sphereBouquetSuspIso : {A : Type ℓ} {n : ℕ}
HITs\SphereBouquet\Properties.agda:122:sphereBouquet≃Susp : {A : Type ℓ} {n : ℕ}
HITs\SphereBouquet\Properties.agda:126:sphereBouquetSuspFun : {A : Type ℓ} {n : ℕ}
HITs\SphereBouquet\Properties.agda:130:sphereBouquetSuspInvFun : {A : Type ℓ} {n : ℕ}
HITs\SphereBouquet\Properties.agda:136:bouquetSusp→ : {n : ℕ} {A B : Type ℓ}
HITs\SphereBouquet\Properties.agda:142:bouquetSusp→∘ : {n : ℕ} {A B C : Type ℓ}
HITs\SphereBouquet\Properties.agda:168:preBTC : {Cₙ Cₙ₊₁ : Type ℓ} (n mₙ : ℕ)
HITs\SphereBouquet\Properties.agda:191:  Pushout→Bouquet : {Cₙ Cₙ₊₁ : Type ℓ} (n mₙ : ℕ)
HITs\SphereBouquet\Properties.agda:202:module BouquetFuns {Cₙ Cₙ₊₁ : Type ℓ} (n mₙ : ℕ)
HITs\SphereBouquet\Properties.agda:216:CTB-BTC-cancel : {Cₙ Cₙ₊₁ : Type ℓ} (n mₙ : ℕ)
HITs\SphereBouquet\Properties.agda:371:    ugh : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) → p ∙' sym p ≡ refl
HITs\SphereBouquet\Properties.agda:377:module _ {Cₙ Cₙ₊₁ : Type ℓ} (n mₙ : ℕ)
HITs\SphereBouquet\Properties.agda:392:-- A 'normal form' for functions of type ⋁Sⁿ → ⋁Sⁿ
HITs\SphereBouquet\Properties.agda:410:  lem : ∀ {ℓ} {A : Type ℓ} (x y : A) (inrgid : x ≡ y)
HITs\SphereBouquet\Properties.agda:417:  cool : (x : S₊ (suc n)) → Type
HITs\SphereBouquet\Properties.agda:438:SphereBouquet∙Π : ∀ {ℓ ℓ'} {n : ℕ} {A : Type ℓ} {B : Pointed ℓ'}
HITs\Susp\Base.agda:24:data Susp (A : Type ℓ) : Type ℓ where
HITs\Susp\Base.agda:29:Susp∙ : (A : Type ℓ) → Pointed ℓ
HITs\Susp\Base.agda:33:suspFun : {A : Type ℓ} {B : Type ℓ'} (f : A → B)
HITs\Susp\Base.agda:40:suspFun∙ : {A : Type ℓ} {B : Type ℓ'} (f : A → B)
HITs\Susp\Base.agda:45:suspFun↑ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
HITs\Susp\Base.agda:54:Susp^ : ℕ → Type ℓ → Type ℓ
HITs\Susp\Base.agda:58:Susp^' : ℕ → Type ℓ → Type ℓ
HITs\Susp\Base.agda:62:Susp^'≡Susp^ : (n : ℕ) {A : Type ℓ} → Susp^' n A ≡ Susp^ n A
HITs\Susp\Base.agda:90:SuspBool : Type₀
HITs\Susp\Base.agda:132:SuspS¹ : Type₀
HITs\Susp\Base.agda:176:SuspS² : Type₀
HITs\Susp\Base.agda:220:IsoType→IsoSusp : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → Iso A B → Iso (Susp A) (Susp B)
HITs\Susp\Base.agda:221:fun (IsoType→IsoSusp is) north = north
HITs\Susp\Base.agda:222:fun (IsoType→IsoSusp is) south = south
HITs\Susp\Base.agda:223:fun (IsoType→IsoSusp is) (merid a i) = merid (fun is a) i
HITs\Susp\Base.agda:224:inv (IsoType→IsoSusp is) north = north
HITs\Susp\Base.agda:225:inv (IsoType→IsoSusp is) south = south
HITs\Susp\Base.agda:226:inv (IsoType→IsoSusp is) (merid a i) = merid (inv is a) i
HITs\Susp\Base.agda:227:sec (IsoType→IsoSusp is) north = refl
HITs\Susp\Base.agda:228:sec (IsoType→IsoSusp is) south = refl
HITs\Susp\Base.agda:229:sec (IsoType→IsoSusp is) (merid a i) j = merid (sec is a j) i
HITs\Susp\Base.agda:230:ret (IsoType→IsoSusp is) north = refl
HITs\Susp\Base.agda:231:ret (IsoType→IsoSusp is) south = refl
HITs\Susp\Base.agda:232:ret (IsoType→IsoSusp is) (merid a i) j = merid (ret is a j) i
HITs\Susp\Base.agda:235:IsoSuspS²SuspSuspS¹ = IsoType→IsoSusp S²IsoSuspS¹
HITs\Susp\Properties.agda:26:    A B C : Type ℓ
HITs\Susp\Properties.agda:46:Susp-iso-joinBool : ∀ {ℓ} {A : Type ℓ} → Iso (Susp A) (join A Bool)
HITs\Susp\Properties.agda:72:Susp≃joinBool : ∀ {ℓ} {A : Type ℓ} → Susp A ≃ join A Bool
HITs\Susp\Properties.agda:75:Susp≡joinBool : ∀ {ℓ} {A : Type ℓ} → Susp A ≡ join A Bool
HITs\Susp\Properties.agda:78:-- Here Unit* types are more convenient for general A
HITs\Susp\Properties.agda:79:SuspSpan : ∀ {ℓ} ℓ' ℓ'' (A : Type ℓ) → 3-span {ℓ'} {ℓ} {ℓ''}
HITs\Susp\Properties.agda:82:SuspSquare : ∀ {ℓ} ℓ' ℓ'' (A : Type ℓ) → commSquare {ℓ'} {ℓ} {ℓ''}
HITs\Susp\Properties.agda:93:SuspPushoutSquare : ∀ {ℓ} ℓ' ℓ'' (A : Type ℓ)
HITs\Susp\Properties.agda:112:Susp≃PushoutSusp* : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} → Susp A ≃ spanPushout (SuspSpan ℓ' ℓ'' A)
HITs\Susp\Properties.agda:115:Susp≡PushoutSusp* : ∀ {ℓ ℓ' ℓ''} {A : Type _} → Susp A ≡ spanPushout (SuspSpan ℓ' ℓ'' A)
HITs\Susp\Properties.agda:119:congSuspIso : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → Iso A B → Iso (Susp A) (Susp B)
HITs\Susp\Properties.agda:129:congSuspEquiv : ∀ {ℓ} {A B : Type ℓ} → A ≃ B → Susp A ≃ Susp B
HITs\Susp\Properties.agda:132:suspToPropElim : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Susp A → Type ℓ'} (a : A)
HITs\Susp\Properties.agda:141:suspToPropElim2 : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Susp A → Susp A → Type ℓ'} (a : A)
HITs\Susp\Properties.agda:181:funSpaceSuspIso : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
HITs\Susp\Properties.agda:240:invSusp : ∀ {ℓ} {A : Type ℓ} → Susp A → Susp A
HITs\Susp\Properties.agda:245:invSusp² : ∀ {ℓ} {A : Type ℓ} (x : Susp A) → invSusp (invSusp x) ≡ x
HITs\Susp\Properties.agda:250:invSuspIso : ∀ {ℓ} {A : Type ℓ} → Iso (Susp A) (Susp A)
HITs\Susp\Properties.agda:259:-- for pointed types A and B. This is useful for obtaining a ``nice'' iso
HITs\Susp\Properties.agda:404:  lem : {A : Type ℓ} {x : A} (p q : x ≡ x) (l : refl ≡ p)
HITs\Susp\SuspProduct.agda:28:module PushoutNull {ℓ ℓ'} (X : Type ℓ) (Y : Type ℓ') (y₀ : Y) where
HITs\Susp\SuspProduct.agda:113:      sq : ∀ {ℓ} {C : Type ℓ} {c : C}
HITs\Susp\SuspProduct.agda:135:        → {A : Type ℓ} {B : Type ℓ'}
HITs\Torus\Base.agda:22:data Torus : Type₀ where
HITs\Torus\Base.agda:61:Loop : {A : Type₀} (p : A) → Type₀
HITs\Torus\Base.agda:64:ΩTorus : Type₀
HITs\Torus\Base.agda:68:lemPathAnd : ∀ {ℓ} {A B : Type ℓ} (t u : A × B) →
HITs\Torus\Base.agda:100:data Torus' : Type₀ where
HITs\Truncation\Base.agda:22:data HubAndSpoke {ℓ} (A : Type ℓ) (n : ℕ) : Type ℓ where
HITs\Truncation\Base.agda:27:hLevelTrunc : ∀ {ℓ} (n : ℕ) (A : Type ℓ) → Type ℓ
HITs\Truncation\Base.agda:31:∥_∥_ : ∀ {ℓ} (A : Type ℓ) (n : ℕ) → Type ℓ
HITs\Truncation\Base.agda:34:∣_∣ₕ : ∀ {ℓ} {A : Type ℓ} {n : ℕ} → A → ∥ A ∥ n
HITs\Truncation\Properties.agda:38:    A : Type ℓ
HITs\Truncation\Properties.agda:39:    B : Type ℓ'
HITs\Truncation\Properties.agda:41:sphereFill : (n : ℕ) (f : S₊ n → A) → Type _
HITs\Truncation\Properties.agda:44:isSphereFilled : ℕ → Type ℓ → Type ℓ
HITs\Truncation\Properties.agda:116:       {B : Type ℓ'} →
HITs\Truncation\Properties.agda:127:      {B : Type ℓ'} →
HITs\Truncation\Properties.agda:136:       {B : Type ℓ'} →
HITs\Truncation\Properties.agda:144:       {B : Type ℓ'} →
HITs\Truncation\Properties.agda:152:        {B : ∥ A ∥ (suc n) → Type ℓ'}
HITs\Truncation\Properties.agda:166:       {B : ∥ A ∥ n → Type ℓ'}
HITs\Truncation\Properties.agda:175:        {B : ∥ A ∥ n → ∥ A ∥ n → Type ℓ'}
HITs\Truncation\Properties.agda:184:        {B : (x y z : ∥ A ∥ n) → Type ℓ'}
HITs\Truncation\Properties.agda:198:elimₕ : (n : ℕ) {B : ∥ A ∥ n → Type ℓ'}
HITs\Truncation\Properties.agda:235:ΣTruncElim : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {n m : ℕ}
HITs\Truncation\Properties.agda:236:             {B : (x : ∥ A ∥ n) → Type ℓ'}
HITs\Truncation\Properties.agda:237:             {C : (Σ[ a ∈ (∥ A ∥ n) ] (∥ B a ∥ m)) → Type ℓ''}
HITs\Truncation\Properties.agda:273:univTrunc : ∀ {ℓ} (n : HLevel) {B : TypeOfHLevel ℓ n} → Iso (hLevelTrunc n A → B .fst) (A → B .fst)
HITs\Truncation\Properties.agda:291:∘rec : ∀{ℓ''} {n : HLevel}{C : Type ℓ''}
HITs\Truncation\Properties.agda:311:map : {n : HLevel} {B : Type ℓ'} (g : A → B)
HITs\Truncation\Properties.agda:315:map2 : ∀ {ℓ''} {n : HLevel} {B : Type ℓ'} {C : Type ℓ''} (g : A → B → C)
HITs\Truncation\Properties.agda:321:mapCompIso : {n : HLevel} {B : Type ℓ'} → (Iso A B) → Iso (hLevelTrunc n A) (hLevelTrunc n B)
HITs\Truncation\Properties.agda:384:isContr→isContrTrunc : ∀ {ℓ} {A : Type ℓ} (n : ℕ) → isContr A → isContr (hLevelTrunc n A)
HITs\Truncation\Properties.agda:410:module ΩTrunc {X : Type ℓ} {n : HLevel} where
HITs\Truncation\Properties.agda:412:  Code : ∥ X ∥ (2 + n) → ∥ X ∥ (2 + n) → TypeOfHLevel ℓ (suc n)
HITs\Truncation\Properties.agda:414:    rec2 (isOfHLevelTypeOfHLevel (suc n))
HITs\Truncation\Properties.agda:417:  P : ∥ X ∥ (2 + n) → ∥ X ∥ (2 + n) → Type ℓ
HITs\Truncation\Properties.agda:508:PathPIdTruncIso : {A : I → Type ℓ} {a : A i0} {b : A i1} (n : HLevel)
HITs\Truncation\Properties.agda:512:  lem : ∀ {ℓ} (A B : Type ℓ) (A' : A ≡ B) {a : A} {b : B} (n : HLevel)
HITs\Truncation\Properties.agda:522:PathIdTruncIsoFunct : ∀ {A : Type ℓ} {a : A} (n : HLevel) → (p q : (Path (∥ A ∥ (2 +  n)) ∣ a ∣ ∣ a
∣))
HITs\Truncation\Properties.agda:574:truncOfΣIso : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} {B : A → Type ℓ'}
HITs\Truncation\Properties.agda:598:trunc-respects-≃ : {X Y : Type ℓ} (n : ℕ) → (H : X ≃ Y) → ∥ X ∥ n ≃ ∥ Y ∥ n
HITs\Truncation\FromNegTwo\Base.agda:14:-- data hLevelTrunc {ℓ} (n : HLevel) (A : Type ℓ) : Type (ℓ-max ℓ ℓ') where
HITs\Truncation\FromNegTwo\Base.agda:23:hLevelTrunc : ∀ {ℓ} → HLevel → Type ℓ → Type ℓ
HITs\Truncation\FromNegTwo\Base.agda:27:∥_∥_ : ∀ {ℓ} → Type ℓ → HLevel → Type ℓ
HITs\Truncation\FromNegTwo\Properties.agda:33:    A B : Type ℓ
HITs\Truncation\FromNegTwo\Properties.agda:35:sphereFill : (n : ℕ₋₁) (f : S n → A) → Type _
HITs\Truncation\FromNegTwo\Properties.agda:38:isSphereFilled : ℕ₋₁ → Type ℓ → Type ℓ
HITs\Truncation\FromNegTwo\Properties.agda:118:      {B : Type ℓ'} →
HITs\Truncation\FromNegTwo\Properties.agda:126:       {B : hLevelTrunc n A → Type ℓ'}
HITs\Truncation\FromNegTwo\Properties.agda:134:  {B : hLevelTrunc n A → hLevelTrunc n A → Type ℓ'}
HITs\Truncation\FromNegTwo\Properties.agda:144:  {B : (x y z : hLevelTrunc n A) → Type ℓ'}
HITs\Truncation\FromNegTwo\Properties.agda:174:univTrunc : ∀ {ℓ} (n : HLevel) {B : TypeOfHLevel ℓ n} → Iso (hLevelTrunc n A → B .fst)
(A → B .fst)
HITs\Truncation\FromNegTwo\Properties.agda:183:map : {n : HLevel} {B : Type ℓ'} (g : A → B)
HITs\Truncation\FromNegTwo\Properties.agda:187:mapCompIso : {n : HLevel} {B : Type ℓ'} → (Iso A B) → Iso (hLevelTrunc n A) (hLevelTrunc
n B)
HITs\Truncation\FromNegTwo\Properties.agda:257:isContr→isContrTrunc : ∀ {ℓ} {A : Type ℓ} (n : ℕ) → isContr A → isContr (hLevelTrunc n A)
HITs\Truncation\FromNegTwo\Properties.agda:279:isOfHLevelTypeOfHLevel2 : ∀ n → isOfHLevel (suc n) (TypeOfHLevel ℓ n)
HITs\Truncation\FromNegTwo\Properties.agda:280:isOfHLevelTypeOfHLevel2 n = isOfHLevelTypeOfHLevel n
HITs\Truncation\FromNegTwo\Properties.agda:286:  P : {X : Type ℓ} {n : HLevel} → ∥ X ∥ (suc n) → ∥ X ∥ (suc n) → Type ℓ
HITs\Truncation\FromNegTwo\Properties.agda:287:  P {n = n} x y =  elim2 (λ _ _  → isOfHLevelTypeOfHLevel2 (n))
HITs\TypeQuotients\Base.agda:5:- Definition of type quotients (i.e. non-truncated quotients)
HITs\TypeQuotients\Base.agda:8:module Cubical.HITs.TypeQuotients.Base where
HITs\TypeQuotients\Base.agda:12:-- Type quotients as a higher inductive type:
HITs\TypeQuotients\Base.agda:13:data _/ₜ_ {ℓ ℓ'} (A : Type ℓ) (R : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
HITs\TypeQuotients\Properties.agda:3:Type quotients:
HITs\TypeQuotients\Properties.agda:7:module Cubical.HITs.TypeQuotients.Properties where
HITs\TypeQuotients\Properties.agda:15:open import Cubical.HITs.TypeQuotients.Base
HITs\TypeQuotients\Properties.agda:20:    A : Type ℓ
HITs\TypeQuotients\Properties.agda:21:    R : A → A → Type ℓ'
HITs\TypeQuotients\Properties.agda:22:    B : A /ₜ R → Type ℓ''
HITs\TypeQuotients\Properties.agda:23:    C : A /ₜ R → A /ₜ R → Type ℓ''
HITs\TypeQuotients\Properties.agda:33:rec : {X : Type ℓ''}
HITs\UnorderedPair\Base.agda:8:  A : Type ℓ
HITs\UnorderedPair\Base.agda:12:data UnorderedPair (A : Type ℓ) : Type ℓ where
HITs\UnorderedPair\Base.agda:17:module _ {B : UnorderedPair A → Type ℓ′}
HITs\UnorderedPair\Base.agda:28:module _ {B : UnorderedPair A → Type ℓ′}
HITs\UnorderedPair\Base.agda:36:module _ {B : Type ℓ′} (BType : isSet B)
HITs\UnorderedPair\Base.agda:40:  rec = elim _,*_ swap* λ _ → BType
HITs\UnorderedPair\Properties.agda:15:  A : Type ℓ
HITs\UnorderedPair\Properties.agda:17:SetCoequalizerPair : Type ℓ → Type ℓ
HITs\Wedge\Base.agda:10:_⋁_ : ∀ {ℓ ℓ'} → Pointed ℓ → Pointed ℓ' → Type (ℓ-max ℓ ℓ')
HITs\Wedge\Base.agda:14:⋁gen : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Pointed ℓ') → Type (ℓ-max ℓ ℓ')
HITs\Wedge\Base.agda:25:⋁gen∙ : ∀ {ℓ ℓ'} (A : Type ℓ) (B : A → Pointed ℓ') → Pointed (ℓ-max ℓ ℓ')
HITs\Wedge\Properties.agda:98:  help : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : y ≡ z)
HITs\Wedge\Properties.agda:187:  Bouquet→ΩBouquetSusp-filler : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:201:Bouquet→ΩBouquetSusp : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:208:SuspBouquet→Bouquet : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:214:Bouquet→SuspBouquet : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:222:SuspBouquet-Bouquet-cancel : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:319:Iso-SuspBouquet-Bouquet : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:326:SuspBouquet≃Bouquet : (A : Type ℓ) (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:457:module _ {A : Type ℓ} {B : Type ℓ'}
HITs\Wedge\Properties.agda:500:module _ {ℓ ℓ'} {A : Type ℓ} (B : A → Pointed ℓ')
HITs\Wedge\Properties.agda:502:  cofibFst : Type _
HITs\Wedge\Properties.agda:543:module _ {ℓA ℓB ℓC : Level} {A : Type ℓA} {B : A → Pointed ℓB} (C : Pointed ℓC)
HITs\Wedge\Properties.agda:643:    weirdSquare : ∀ {ℓ ℓ' ℓ''} {X : Type ℓ} {Y : Type ℓ'} {Z : Type ℓ''}
HITs\Wedge\Properties.agda:651:    weirdPushoutSquare : ∀ {ℓ ℓ' ℓ''} {X : Type ℓ} {Y : Type ℓ'} {Z : Type ℓ''}
HITs\Wedge\Properties.agda:710:    F : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A)
HITs\Wedge\Properties.agda:717:    F' : ∀ {ℓ} {A : Type ℓ} {x : A}
HITs\Wedge\Properties.agda:721:    H : ∀ {ℓ} {A : Type ℓ} {x : A} (y : A)
Homotopy\Base.agda:11:_∼_ : {X : Type ℓ} {Y : X → Type ℓ'} → (f g : (x : X) → Y x) → Type (ℓ-max ℓ ℓ')
Homotopy\Base.agda:14:funExt∼ : {X : Type ℓ} {Y : X → Type ℓ'} {f g : (x : X) → Y x} (H : f ∼ g) → f ≡ g
Homotopy\Base.agda:17:∼-refl : {X : Type ℓ} {Y : X → Type ℓ'} {f : (x : X) → Y x} → f ∼ f
Homotopy\BlakersMassey.agda:5:Based on the previous type-theoretic proof described in
Homotopy\BlakersMassey.agda:7:  "A Mechanization of the Blakers–Massey Connectivity Theorem in Homotopy Type Theory"
Homotopy\BlakersMassey.agda:45:  (X : Type ℓ₁)(Y : Type ℓ₂)(Q : X → Y → Type ℓ₃)
Homotopy\BlakersMassey.agda:53:  leftFiber  : X → Type (ℓ-max ℓ₂ ℓ₃)
Homotopy\BlakersMassey.agda:56:  rightFiber : Y → Type (ℓ-max ℓ₁ ℓ₃)
Homotopy\BlakersMassey.agda:67:    → inl x₁ ≡ p → inl x₀ ≡ p → Type ℓ
Homotopy\BlakersMassey.agda:72:    → inl x₀ ≡ inr y₁ → Type ℓ
Homotopy\BlakersMassey.agda:75:  fiber' : {x₀ : X}{y₀ : Y}(q₀₀ : Q x₀ y₀){x₁ : X}{p : PushoutQ} → inl x₁ ≡ p → inl x₀ ≡ p → Type ℓ
Homotopy\BlakersMassey.agda:78:  fiber'Push : {x₀ x₁ : X}{y₀ y₁ : Y}(q₀₀ : Q x₀ y₀)(q₁₁ : Q x₁ y₁) → inl x₀ ≡ inr y₁ → Type ℓ
Homotopy\BlakersMassey.agda:83:    → (x₁ : X){p : PushoutQ} → inl x₁ ≡ p → inl x₀ ≡ p → Type ℓ
Homotopy\BlakersMassey.agda:86:  rightCode : {x₀ : X}(y : Y) → Path PushoutQ (inl x₀) (inr y) → Type ℓ
Homotopy\BlakersMassey.agda:558:    leftCode' : (x : X){p : PushoutQ} → inl x ≡ p → inl x₀ ≡ p → Type ℓ
Homotopy\BlakersMassey.agda:561:    leftCode : (x : X) → inl x₀ ≡ inl x → Type ℓ
Homotopy\BlakersMassey.agda:569:      → PathP (λ i → inl x₀ ≡ push q i → Type ℓ) (leftCode x) (rightCode y)
Homotopy\BlakersMassey.agda:575:    Code : (p : PushoutQ) → inl x₀ ≡ p → Type ℓ
Homotopy\BlakersMassey.agda:594:      fiber-filler : I → Type ℓ
Homotopy\BlakersMassey.agda:707:       {ℓ ℓ' ℓ'' : Level} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Homotopy\BlakersMassey.agda:719:  shuffleFibIso₂ : {ℓ ℓ' ℓ'' : Level} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Homotopy\BlakersMassey.agda:730:  {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Homotopy\BlakersMassey.agda:759:  fib× : (B × C) → Type _
Homotopy\BlakersMassey.agda:762:  PushoutGenPath× : B × C → Type _
Homotopy\BlakersMassey.agda:765:  PushoutPath× : B × C → Type _
Homotopy\Connected.agda:42:    X₀ X₁ X₂ Y₀ Y₁ Y₂ : Type ℓ
Homotopy\Connected.agda:45:isConnected : ∀ {ℓ} (n : HLevel) (A : Type ℓ) → Type ℓ
Homotopy\Connected.agda:48:isConnectedFun : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} {B : Type ℓ'} (f : A → B) → Type (ℓ-max ℓ ℓ')
Homotopy\Connected.agda:51:isConnectedZero : ∀ {ℓ} (A : Type ℓ) → isConnected 0 A
Homotopy\Connected.agda:54:isConnectedSubtr : ∀ {ℓ} {A : Type ℓ} (n m : HLevel)
Homotopy\Connected.agda:64:isConnectedSubtr' : ∀ {ℓ} {A : Type ℓ} (n m : HLevel)
Homotopy\Connected.agda:70:isConnectedFunSubtr : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (n m : HLevel) (f : A → B)
Homotopy\Connected.agda:75:isConnectedFun≤ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (n m : HLevel) (f : A → B)
Homotopy\Connected.agda:82:  typeToFiberIso : ∀ {ℓ} (A : Type ℓ) → Iso A (fiber (λ (x : A) → tt) tt)
Homotopy\Connected.agda:83:  Iso.fun (typeToFiberIso A) x = x , refl
Homotopy\Connected.agda:84:  Iso.inv (typeToFiberIso A) = fst
Homotopy\Connected.agda:85:  Iso.sec (typeToFiberIso A) b i = fst b , (isOfHLevelSuc 1 (isPropUnit) tt tt (snd b) refl) i
Homotopy\Connected.agda:86:  Iso.ret (typeToFiberIso A) a = refl
Homotopy\Connected.agda:88:  typeToFiber : ∀ {ℓ} (A : Type ℓ) → A ≡ fiber (λ (x : A) → tt) tt
Homotopy\Connected.agda:89:  typeToFiber A = isoToPath (typeToFiberIso A)
Homotopy\Connected.agda:91:isConnectedFun→isConnected : {X : Type ℓ} (n : HLevel)
Homotopy\Connected.agda:94:  subst (isConnected n) (sym (typeToFiber _)) (h tt)
Homotopy\Connected.agda:96:isConnected→isConnectedFun : {X : Type ℓ} (n : HLevel)
Homotopy\Connected.agda:98:isConnected→isConnectedFun n h = λ { tt → subst (isConnected n) (typeToFiber _) h }
Homotopy\Connected.agda:100:isOfHLevelIsConnectedStable : ∀ {ℓ} {A : Type ℓ} (n : ℕ)
Homotopy\Connected.agda:107:module elim {ℓ ℓ' : Level} {A : Type ℓ} {B : Type ℓ'} (f : A → B) where
Homotopy\Connected.agda:109:    inv : ∀ {ℓ'''} (n : HLevel) (P : B → TypeOfHLevel ℓ''' (suc n))
Homotopy\Connected.agda:118:  isIsoPrecompose : ∀ {ℓ'''} (n : ℕ) (P : B → TypeOfHLevel ℓ''' n)
Homotopy\Connected.agda:140:  isIsoPrecomposeβ : ∀ {ℓ'''} (n : ℕ) (P : B → TypeOfHLevel ℓ''' n)
Homotopy\Connected.agda:150:  isEquivPrecompose : ∀ {ℓ'''} (n : ℕ) (P : B → TypeOfHLevel ℓ''' n)
Homotopy\Connected.agda:162:  isConnectedPrecompose : (n : ℕ) → ((P : B → TypeOfHLevel (ℓ-max ℓ ℓ') n)
Homotopy\Connected.agda:168:    P : (n : HLevel) → ((P : B → TypeOfHLevel ℓ (suc n))
Homotopy\Connected.agda:170:     → B → Type _
Homotopy\Connected.agda:173:    c : (n : HLevel) → ((P : B → TypeOfHLevel (ℓ-max ℓ ℓ') (suc n))
Homotopy\Connected.agda:179:    fun : (n : HLevel) (P→sect : ((P : B → TypeOfHLevel (ℓ-max ℓ ℓ') (suc n))
Homotopy\Connected.agda:192:  {A : Type ℓ} {B : Type ℓ'} (P : B → TypeOfHLevel ℓ'' (k + n)) (f : A → B)
Homotopy\Connected.agda:212:indMapEquiv→conType : ∀ {ℓ} {A : Type ℓ} (n : HLevel)
Homotopy\Connected.agda:213:                   → ((B : TypeOfHLevel ℓ n)
Homotopy\Connected.agda:216:indMapEquiv→conType {A = A} zero BEq = isContrUnit*
Homotopy\Connected.agda:217:indMapEquiv→conType {A = A} (suc n) BEq =
Homotopy\Connected.agda:218:  isOfHLevelRetractFromIso 0 (mapCompIso {n = (suc n)} (typeToFiberIso A))
Homotopy\Connected.agda:224:isConnectedComp : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''}
Homotopy\Connected.agda:237:isConnectedFunCancel : ∀ {ℓ} {X Y Z : Type ℓ} (f : X → Y) (g : Y → Z) (n : HLevel)
Homotopy\Connected.agda:243:    module _ (P : Z → TypeOfHLevel ℓ (suc n)) where
Homotopy\Connected.agda:272:  module _ (P : Y → TypeOfHLevel ℓ' (suc n)) where
Homotopy\Connected.agda:307:isEquiv→isConnected : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Homotopy\Connected.agda:314:isConnectedId : ∀ {ℓ} {A : Type ℓ} {n : HLevel} → isConnectedFun n (idfun A)
Homotopy\Connected.agda:318:isConnectedPath : ∀ {ℓ} (n : HLevel) {A : Type ℓ}
Homotopy\Connected.agda:325:isConnectedPathP : ∀ {ℓ} (n : HLevel) {A : I → Type ℓ}
Homotopy\Connected.agda:332:isConnectedCong : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} {B : Type ℓ'} (f : A → B)
Homotopy\Connected.agda:340:isConnectedCong² : ∀ {ℓ ℓ'} (n : HLevel) {A : Type ℓ} {B : Type ℓ'} (f : A → B)
Homotopy\Connected.agda:360:isConnectedCong' : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {x : A} {y : B}
Homotopy\Connected.agda:418:  {A : Type ℓ} {B : Type ℓ'}
Homotopy\Connected.agda:432:    {A : Type ℓ} {B : Type ℓ'}
Homotopy\Connected.agda:441:isConnectedPoint : ∀ {ℓ} (n : HLevel) {A : Type ℓ}
Homotopy\Connected.agda:449:isConnectedPoint2 : ∀ {ℓ} (n : HLevel) {A : Type ℓ} (a : A)
Homotopy\Connected.agda:452:isConnectedPoint2 n {A = A} a connMap = indMapEquiv→conType _ λ B → isoToIsEquiv (theIso B)
Homotopy\Connected.agda:454:  module _  {ℓ' : Level} (B : TypeOfHLevel ℓ' (suc n))
Homotopy\Connected.agda:466:module isConnectedPoint {ℓ ℓ'} (n : HLevel) {A : Type ℓ}
Homotopy\Connected.agda:467:     {B : A → Type ℓ'}
Homotopy\Connected.agda:473:    P : A → TypeOfHLevel ℓ' n
Homotopy\Connected.agda:483:connectedTruncIso : ∀ {ℓ} {A B : Type ℓ} (n : HLevel) (f : A → B)
Homotopy\Connected.agda:504:    helper : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : A → Type ℓ'} (P : hLevelTrunc (suc n) A → Type ℓ'')
Homotopy\Connected.agda:519:connectedTruncIso2 : ∀ {ℓ} {A B : Type ℓ} (n m : HLevel) (f : A → B)
Homotopy\Connected.agda:526:connectedTruncEquiv : ∀ {ℓ} {A B : Type ℓ} (n : HLevel) (f : A → B)
Homotopy\Connected.agda:531:isConnectedSuc→isSurjection : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} {f : A → B} {n : HLevel}
Homotopy\Connected.agda:536:isConnectedSuspFun : ∀ {ℓ ℓ'} {X : Type ℓ} {Y : Type ℓ'}
Homotopy\Connected.agda:546:  module _ (P : Susp Y → TypeOfHLevel ℓ'' (suc n)) where
Homotopy\Connected.agda:577:isConnectedSusp : ∀ {ℓ} {X : Type ℓ} (n : HLevel)
Homotopy\Connected.agda:590:isConnected-map-× : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} (n : HLevel)
Homotopy\Connected.agda:597:inrConnected : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} (n : HLevel)
Homotopy\Connected.agda:604:  module _ {ℓ : Level} (P : (Pushout f g) → TypeOfHLevel ℓ n)
Homotopy\Connected.agda:607:    Q : A → TypeOfHLevel _ n
Homotopy\Connected.agda:624:inlConnected : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {B : Type ℓ'} {C : Type ℓ''} (n : ℕ)
Homotopy\Connected.agda:650:  module _ (P : Pushout g₁ g₂ → TypeOfHLevel ℓ' (suc n)) where
Homotopy\Connected.agda:810:  (m n : HLevel) {A : Type ℓ} {A' : Type ℓ'} {v : A → A'} {B : Type ℓ''}
Homotopy\Connected.agda:813:  private module _ {ℓ''' : Level} (P : join A' B → TypeOfHLevel ℓ''' (m + n)) where
Homotopy\Connected.agda:818:      --   A' → Type
Homotopy\Connected.agda:822:      X : A' → Type _
Homotopy\Connected.agda:831:      -- Equivalent type to X, whose h-level we can estimate.
Homotopy\Connected.agda:832:      X' : A' → Type _
Homotopy\Connected.agda:842:        ≃⟨ invEquiv (Σ-cong-equiv-fst (UnitToType≃ _)) ⟩
Homotopy\Connected.agda:860:      Xl : (a' : A') → TypeOfHLevel _ m
Homotopy\Connected.agda:891:{- Given two fibration B , C : A → Type and a family of maps on fibres
Homotopy\Connected.agda:894:module _ {ℓ ℓ' ℓ'' : Level} {A : Type ℓ} {B : A → Type ℓ'} {C : A → Type ℓ''}
Homotopy\Connected.agda:946:isConnectedCofib : ∀ {ℓ} {A B : Type ℓ} (n : ℕ) {f : A → B}
Homotopy\Connected.agda:951:connectedFunPresConnected : ∀ {ℓ} {A B : Type ℓ} (n : ℕ) {f : A → B}
Homotopy\EilenbergSteenrod.agda:37:record coHomTheory {ℓ ℓ' : Level} (H : (n : ℤ) → Pointed ℓ → AbGroup ℓ') : Type (ℓ-suc (ℓ-max ℓ ℓ'))
Homotopy\EilenbergSteenrod.agda:55:record coHomTheoryGen {ℓ ℓ' : Level} (H : (n : ℤ) → Pointed ℓ → AbGroup ℓ') : Type (ℓ-suc (ℓ-max ℓ
ℓ'))
Homotopy\EilenbergSteenrod.agda:72:    Wedge : (n : ℤ) {I : Type ℓ} (satAC : satAC (ℓ-max ℓ ℓ') 2 I) {A : I → Pointed ℓ}
Homotopy\EilenbergSteenrod.agda:77:  Wedge→AbGroupEquiv : (n : ℤ) {I : Type ℓ} (satAC : satAC (ℓ-max ℓ ℓ') 2 I) {A : I → Pointed ℓ}
Homotopy\Freudenthal.agda:90:  Code : (y : Susp (typ A)) → north ≡ y → Type ℓ
Homotopy\Freudenthal.agda:111:    gluePath : I → Type _
Homotopy\Freudenthal.agda:114:    lem : ∀ {ℓ} {A : Type ℓ} {x y z : A} (p : x ≡ y) (q : z ≡ y) → (p ∙ q ⁻¹) ∙ q ≡ p
Homotopy\HiltonMilnor.agda:6:  for pointed types X and Y.
Homotopy\HiltonMilnor.agda:60:-- So we try to characterize the type.
Homotopy\Hopf.agda:37:  retEq≡secEq : ∀ {ℓ} {A B : Type ℓ} (e : A ≃ B)
Homotopy\Hopf.agda:65:  Hopf : Susp (typ A) → Type ℓ
Homotopy\Hopf.agda:70:  TotalSpaceHopfPush : Type _
Homotopy\Hopf.agda:165:      lem : ∀ {ℓ} {A B : Type ℓ} (e : A ≃ B) →
Homotopy\Hopf.agda:260:  TotalSpaceHopfPush² : Type _
Homotopy\Hopf.agda:263:  P : TotalSpaceHopfPush² → Type _
Homotopy\Hopf.agda:268:  TotalSpacePush² : Type _
Homotopy\Hopf.agda:271:  TotalSpacePush²' : Type _
Homotopy\Hopf.agda:386:  Border : (x : S¹) → (j : I) → Partial (j ∨ ~ j) (Σ Type₀ (λ T → T ≃ S¹))
Homotopy\Hopf.agda:391:  HopfSuspS¹ : SuspS¹ → Type₀
Homotopy\Hopf.agda:398:  HopfS² : S² → Type₀
Homotopy\Hopf.agda:407:  HopfS²' : S² → Type₀
Homotopy\Hopf.agda:415:  TotalHopf : Type₀
Homotopy\Hopf.agda:447:  fibℤ : S¹ → S¹ → Type₀
Homotopy\Hopf.agda:450:  S¹→HSet : (A : Type₀) (p : isSet A) (F : S¹ → A) (x : S¹) → F base ≡ F x
Homotopy\Hopf.agda:473:  discretefib : (F : S¹ → S¹ → Type₀) → Type₀
Homotopy\Hopf.agda:497:  -- assocFiller-3-endpoint is used only in the type of the next function, to specify the
Homotopy\Hopf.agda:500:  -- TODO : use cubical extension types when available to remove assocFiller-3-endpoint
Homotopy\Hopf.agda:558:  PseudoHopf : Type₀
Homotopy\Hopf.agda:579:  -- TODO : use cubical extension types when available to remove assocFiller-4-endpoint
Homotopy\HSpace.agda:20:record HSpace (A : Pointed ℓ) : Type ℓ where
Homotopy\HSpace.agda:28:record AssocHSpace {A : Pointed ℓ} (e : HSpace A) : Type ℓ where
Homotopy\HSpace.agda:41:record LeftInvHSpace {A : Pointed ℓ} (e : HSpace A) : Type ℓ where
Homotopy\HSpace.agda:75:   expressed here with a pointed Π-type -}
Homotopy\Loopspace.agda:28:{- loop space of a pointed type -}
Homotopy\Loopspace.agda:32:{- n-fold loop space of a pointed type -}
Homotopy\Loopspace.agda:227:isComm∙ : ∀ {ℓ} (A : Pointed ℓ) → Type ℓ
Homotopy\Loopspace.agda:446:ptdIso→comm : ∀ {ℓ ℓ'} {A : Pointed ℓ} {B : Type ℓ'} (e : Iso (typ A) B)
Homotopy\Loopspace.agda:472:module _ {ℓ} {B C : Type ℓ} (b₀ : B) (π : B → C) where
Homotopy\Loopspace.agda:519:          lemma : ∀ {ℓ} {X : Type ℓ} {x : X} (p : x ≡ x) (q : p ≡ refl)
Homotopy\MayerVietorisCofiber.agda:5:  Let X be a pointed type, and let a span B ←[f]- X -[g]→ C be given.
Homotopy\MayerVietorisCofiber.agda:27:module _ {ℓX ℓB ℓC} {X : Pointed ℓX} {B : Type ℓB} {C : Type ℓC} (f : X .fst → B) (g : X .fst → C)
Homotopy\MayerVietorisCofiber.agda:53:  module Helper {ℓD} {D : Cone wedgeToPushout → Type ℓD}
Homotopy\Prespectrum.agda:25:record GenericPrespectrum (S : SuccStr ℓ) (ℓ' : Level) : Type (ℓ-max (ℓ-suc ℓ') ℓ) where
Homotopy\Spectrum.agda:22:record Spectrum (ℓ : Level) : Type (ℓ-suc ℓ) where
Homotopy\Spectrum.agda:43:isSpectrumMap : (X Y : Spectrum ℓ) → (f : (n : ℤ) → (X .space n →∙ Y .space n)) → Type ℓ
Homotopy\Spectrum.agda:46:_→Sp_ : (X Y : Spectrum ℓ) → Type ℓ
Homotopy\WedgeConnectivity.agda:22:  (P : typ A → typ B → TypeOfHLevel ℓ'' (n + m))
Homotopy\WedgeConnectivity.agda:29:    Q : typ A → TypeOfHLevel _ n
Homotopy\Whitehead.agda:107:      ∙∙Distr∙ : ∀ {ℓ} {A : Type ℓ} {x y z w u : A}
Homotopy\Whitehead.agda:164:module _ (A B : Type) (a₀ : A) (b₀ : B) where
Homotopy\WhiteheadsLemma.agda:33:  SetTrunc→PropTrunc : {A : Type ℓ} → ∥ A ∥₂ → ∥ A ∥₁
Homotopy\WhiteheadsLemma.agda:81:  squareWithEquivs→Equiv : {A B C D : Type ℓ}
Homotopy\WhiteheadsLemma.agda:105:ΩCongSquare : {A B : Type ℓ} {a b : A} (f : A → B) (p : a ≡ b)
Homotopy\WhiteheadsLemma.agda:120:  πHomπHomCongSquareAux : {A B : Type ℓ} {a : A} {n : ℕ} (f : A → B)
Homotopy\WhiteheadsLemma.agda:152:  flipIsoSquare : {A B C D : Type ℓ} (f : A → B) (g : C → D)
Homotopy\WhiteheadsLemma.agda:175:Ω+1ΩCongSquare : {A B : Type ℓ} {a : A} {n : ℕ} (f : A → B)
Homotopy\WhiteheadsLemma.agda:203:πHomπHomCongSquare : {A B : Type ℓ} {a : A} {n : ℕ} (f : A → B)
Homotopy\WhiteheadsLemma.agda:215:πHomEquiv→πHomCongEquiv : {A B : Type ℓ} {a : A} {n : ℕ} (f : A → B)
Homotopy\WhiteheadsLemma.agda:232:  congEquiv→EquivAux : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:238:  congEquiv→EquivAux''' : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:252:  congEquiv→EquivAux'' : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:261:  congEquiv→EquivAux' : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:279:congEquiv→Equiv : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:289:mapEquiv→imId→Id₋₁ : {A B : Type ℓ} {a b : A} (f : A → B)
Homotopy\WhiteheadsLemma.agda:298:ΩEquiv→Equiv : {A B : Type ℓ}
Homotopy\WhiteheadsLemma.agda:324:WhiteheadsLemma : {A B : Type ℓ} {n : ℕ}
Homotopy\EilenbergMacLane\Base.agda:37:EM-raw : (G : AbGroup ℓ) (n : ℕ) → Type ℓ
Homotopy\EilenbergMacLane\Base.agda:42:EM-raw' : ∀ {ℓ} (G : AbGroup ℓ) (n : ℕ) → Type ℓ
Homotopy\EilenbergMacLane\Base.agda:52:raw-elim : (G : AbGroup ℓ) (n : ℕ) {A : EM-raw G (suc n) → Type ℓ'}
Homotopy\EilenbergMacLane\Base.agda:65:EM : (G : AbGroup ℓ) (n : ℕ) → Type ℓ
Homotopy\EilenbergMacLane\Base.agda:97:elim : {G : AbGroup ℓ} (n : ℕ) {A : EM G n → Type ℓ'}
Homotopy\EilenbergMacLane\Base.agda:105:elim2 : ∀ {ℓ''}{G : AbGroup ℓ} {H : AbGroup ℓ'} (n : ℕ) {A : EM G n → EM H n → Type ℓ''}
Homotopy\EilenbergMacLane\Base.agda:124:EM-raw'-elim : ∀ {ℓ ℓ'} (G : AbGroup ℓ) (n : ℕ) {B : EM G n → Type ℓ'}
Homotopy\EilenbergMacLane\Base.agda:134:EM-raw'-trivElim : (G : AbGroup ℓ) (n : ℕ) {A : EM-raw' G (suc n) → Type ℓ'}
Homotopy\EilenbergMacLane\Base.agda:143:EM→Prop : (G : AbGroup ℓ) (n : ℕ) {A : EM G (suc n) → Type ℓ'}
Homotopy\EilenbergMacLane\CupProductTensor.agda:71:  pathType : {G : AbGroup ℓ} (n : ℕ) (x : EM G (2 + n)) (p : 0ₖ (2 + n) ≡ x) → Type ℓ
Homotopy\EilenbergMacLane\CupProductTensor.agda:72:  pathType n x p = sym (rUnitₖ (2 + n) x) ∙ (λ i → x +ₖ p i)
Homotopy\EilenbergMacLane\CupProductTensor.agda:75:  pathTypeMake : {G : AbGroup ℓ} (n : ℕ) (x : EM G (2 + n)) (p : 0ₖ (2 + n) ≡ x)
Homotopy\EilenbergMacLane\CupProductTensor.agda:76:      → pathType n x p
Homotopy\EilenbergMacLane\CupProductTensor.agda:77:  pathTypeMake n x = J (λ x p → pathType n x p) refl
Homotopy\EilenbergMacLane\CupProductTensor.agda:389:      l≡r z = sym (pathTypeMake _ _ (sym (⌣ₖ-0ₖ (suc n) (suc zero) z)))
Homotopy\EilenbergMacLane\CupProductTensor.agda:420:     l≡r z = sym (pathTypeMake _ _ (sym (⌣ₖ-0ₖ (suc n) (suc (suc m)) z)))
Homotopy\EilenbergMacLane\CupProductTensor.agda:537:      l≡r z = pathTypeMake _ _ _
Homotopy\EilenbergMacLane\CupProductTensor.agda:568:      r≡l z = pathTypeMake _ _ _
Homotopy\EilenbergMacLane\GradedCommTensor.agda:51:  ⌣-ℕ-elim2 : {A : ℕ → ℕ → Type ℓ}
Homotopy\EilenbergMacLane\GroupStructure.agda:329:    lUnit-rUnit-coh : ∀ {ℓ} {A : Type ℓ} {x : A} (p : x ≡ x) (r : refl ≡ p)
Homotopy\EilenbergMacLane\GroupStructure.agda:383:    where -- useless where clause. Needed for fast type checking for some reason.
Homotopy\EilenbergMacLane\Order2.agda:88:      → TypeOfHLevel ℓ (suc n)
Homotopy\EilenbergMacLane\Order2.agda:91:       (λ _ → isOfHLevelΠ 2 λ _ → isOfHLevelTypeOfHLevel 1)
Homotopy\EilenbergMacLane\Order2.agda:96:        → PathP (λ i → Path (EM G 1) embase (emloop g i) → Type ℓ)
Homotopy\EilenbergMacLane\Order2.agda:111:        → PathP (λ i → Path (EM G 1) embase (emloop g i) → TypeOfHLevel ℓ 1)
Homotopy\EilenbergMacLane\Order2.agda:118:              λ _ → isOfHLevelSuc (3 +ℕ n) (isOfHLevelTypeOfHLevel (2 +ℕ n)))
Homotopy\EilenbergMacLane\Order2.agda:121:      Code : (a : EM-raw G (suc (suc n))) → 0ₖ (suc (suc n)) ≡ ∣ a ∣ₕ → Type ℓ
Homotopy\EilenbergMacLane\Order2.agda:131:        h : (a : _) → PathP (λ i → Path K2 ∣ north ∣ ∣ merid a i ∣ → Type ℓ)
Homotopy\EilenbergMacLane\Order2.agda:137:                   {A = λ i → Path K2 ∣ north ∣ ∣ merid a i ∣ → Type ℓ}
Homotopy\EilenbergMacLane\Properties.agda:132:  CodesSet = EMrec Ĝ (isOfHLevelTypeOfHLevel 2) (G , is-set) RE REComp
Homotopy\EilenbergMacLane\Properties.agda:151:  Codes : EM₁ Ĝ → Type ℓ
Homotopy\EilenbergMacLane\Properties.agda:188:  CODE : (n : ℕ) → EM G (suc (suc n)) → TypeOfHLevel ℓ (3 + n)
Homotopy\EilenbergMacLane\Properties.agda:190:    Trunc.elim (λ _ → isOfHLevelTypeOfHLevel (3 + n))
Homotopy\EilenbergMacLane\Properties.agda:196:        → Path (TypeOfHLevel _ (3 + n))
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:30:              → {A : EM-raw G (suc n) → EM-raw H (suc zero) → Type ℓ''}
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:37:              → {A : EM-raw G (suc n) → EM-raw H (suc zero) → Type ℓ''}
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:159:                 (k n m : ℕ) → (n + m ≡ k) → {A : EM-raw G (suc n) → EM-raw H (suc
m) → Type ℓ''}
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:166:                 {A : EM-raw G (suc n) → EM-raw H (suc m) → Type ℓ''}
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:173:                 (k n m : ℕ) (P : n + m ≡ k) {A : EM-raw G (suc n) → EM-raw H (suc
m) → Type ℓ''}
Homotopy\EilenbergMacLane\WedgeConnectivity.agda:273:                  {A : EM-raw G (suc n) → EM-raw H (suc m) → Type ℓ''}
Homotopy\Group\Base.agda:51:π : ∀ {ℓ} (n : ℕ) (A : Pointed ℓ) → Type ℓ
Homotopy\Group\Base.agda:56:π' : ∀ {ℓ} (n : ℕ) (A : Pointed ℓ) → Type ℓ
Homotopy\Group\Base.agda:374:  doubleComp-lem : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) (q r : y ≡ y)
Homotopy\Group\Base.agda:867:  bigLemma : ∀ {ℓ ℓ'} {A₁ B₁ C₁ : Type ℓ} {A₂ B₂ C₂ : Type ℓ'}
Homotopy\Group\Base.agda:1180:  lem : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) → Square p refl (refl ∙ p) refl
Homotopy\Group\Base.agda:1183:  mainEq : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B) (a : A) (b : B)
Homotopy\Group\Join.agda:179:π* : ∀ {ℓ} (n m : ℕ) (A : Pointed ℓ) → Type ℓ
Homotopy\Group\Join.agda:204:         → (e : A1 ≃∙ A2) {P : A1 →∙ A → Type ℓ''}
Homotopy\Group\Join.agda:208:    Equiv∙J (λ A1 e → {P : A1 →∙ A → Type ℓ''}
Homotopy\Group\LES.agda:43:module _ {ℓ : Level} {A : Type ℓ} {x y : A} (p : x ≡ x) (q : x ≡ y) where
Homotopy\Group\LES.agda:103:  {ℓ : Level} {A : Type ℓ} {x : A} (p : refl {x = x} ≡ refl)
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:180:    _·f_ : ∀ {ℓ} {A : Type ℓ} → FreeGroup A → FreeGroup A → FreeGroup A
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:191:  FinBouquetCode : Bouquet (Fin k) → Type
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:225:  CofibFinBoquetFunCode : cofib (fst α) → Type
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:474:    typecheck : ∀ {ℓ} (A B : Type ℓ) (p : A ≡ B)
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:478:    typecheck = λ A → J> λ f g p
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:481:    typecheck' : ∀ {ℓ} {A B : Type ℓ} (p : A ≃ B)
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:484:    typecheck' p {f = f} {g} h =
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:485:      typecheck _ _ (ua p) f g λ b
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:499:     typecheck' (isoToEquiv (·GroupAutomorphismR
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:545:    Code : (x : cofib (fst α)) (p : inr base ≡ x) → Type
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:690:  -- Locked versions for faster type checking
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:750:    Goal : (α : _) (s : (w : _) → _) → Type
Homotopy\Group\PiAbCofibFinSphereBouquetMap.agda:920:    Goal : (s : (w : _) → _) → Type
Homotopy\Group\PinSn.agda:156:  setTruncTrunc2IsoFunct : ∀ {ℓ} {A : Type ℓ} {x : A}
Homotopy\Group\PinSn.agda:219:    genBot+side : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y)
Homotopy\Group\PinSn.agda:326:  speedUp : (x : _) -- stated like this for faster type checking
Homotopy\Group\PinSn.agda:481:    P : (f g : _) → Type
Homotopy\Group\PiSphereBouquet.agda:78:  conLem : ∀ {ℓ ℓ' ℓ''} {A : Type ℓ} {A' : Type ℓ'} {B : Type ℓ''}
Homotopy\Group\SuspensionMap.agda:503:  help : ∀ {ℓ} {A : Type ℓ} {x y : A} (p : x ≡ y) (q s : x ≡ x)
Homotopy\Group\SuspensionMap.agda:514:  transportLem : ∀ {ℓ} {A B : Type ℓ}
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:43:join∙ : Pointed₀ → Type₀ → Pointed₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:50:mapΩrefl : {A : Pointed₀} {B : Type₀} (f : A .fst → B) → Ω A .fst → Ω (B , f (pt A))
.fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:53:mapΩ²refl : {A : Pointed₀} {B : Type₀} (f : A .fst → B) → Ω² A .fst → Ω² (B , f (pt
A)) .fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:56:mapΩ³refl : {A : Pointed₀} {B : Type₀} (f : A .fst → B) → Ω³ A .fst → Ω³ (B , f (pt
A)) .fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:68:connectionBoth : {A : Type₀} {a : A} (p : Path A a a) → PathP (λ i → Path A (p i) (p
i)) p p
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:79:data PostTotalHopf : Type₀ where
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:110:fibΩ : {B : Pointed₀} (P : B .fst → Type₀) → P (pt B) → Ω B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:113:fibΩ² : {B : Pointed₀} (P : B .fst → Type₀) → P (pt B) → Ω² B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:116:fibΩ³ : {B : Pointed₀} (P : B .fst → Type₀) → P (pt B) → Ω³ B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:119:Ω³Hopf : Ω³ S²∙ .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:201:tHopf³ : S³ → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:220:codeTruncS² = 2GroupoidTrunc.rec (isOfHLevelTypeOfHLevel 3) codeS²
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:229:codeTruncS¹ = GroupoidTrunc.rec (isOfHLevelTypeOfHLevel 2) codeS¹
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:310:  Code : Susp S² → Type ℓ-zero
Homotopy\Group\Pi4S3\BrunerieNumber.agda:144:-- The central types
Homotopy\Group\Pi4S3\BrunerieNumber.agda:145:coFib-fold∘W : Type
Homotopy\Group\Pi4S3\BrunerieNumber.agda:396:-- For type checking reasons, let's first prove it for the abstract
Homotopy\Group\Pi4S3\DirectProof.agda:21:addition on this type. This is already done in
Homotopy\Group\Pi4S3\DirectProof.agda:126:  σ-filler : ∀ {ℓ} {A : Type ℓ} (x y : A) (i j : I) → Susp A
Homotopy\Group\Pi4S3\DirectProof.agda:664:-- Iso for underlying type
Homotopy\Group\Pi4S3\DirectProof.agda:760:    JLem : ∀ {ℓ} {A : Type ℓ} (* : A)
Homotopy\Group\Pi4S3\S3PushoutIso.agda:2:This file has been split in two due to slow type checking
Homotopy\Group\Pi4S3\S3PushoutIso.agda:59:Pushout⋁↪fold⋁ : ∀ {ℓ} (A : Pointed ℓ) → Type ℓ
Homotopy\Group\Pi4S3\S3PushoutIso.agda:66:-- The type of interest -- ''almost`` equivalent to ΩS³
Homotopy\Group\Pi4S3\S3PushoutIso.agda:68:-- Same type, using base/surf definition of S² (easier to work with)
Homotopy\Group\Pi4S3\S3PushoutIso.agda:76:module _ {ℓ : Level} {P : Pushout⋁↪fold⋁S² → Type ℓ}
Homotopy\Group\Pi4S3\S3PushoutIso.agda:112:stated for general dependent types, but it's easier to work with
Homotopy\Group\Pi4S3\S3PushoutIso.agda:113:in the special case of path types -}
Homotopy\Group\Pi4S3\S3PushoutIso.agda:114:module Pushout⋁↪fold⋁S²WedgeCon {ℓ : Level } {A : Type ℓ}
Homotopy\Group\Pi4S3\S3PushoutIso.agda:346:  coh-lem : ∀ {ℓ} {A : Type ℓ} {x y : A} (p q : x ≡ y) (r : p ≡ q)
Homotopy\Group\Pi4S3\S3PushoutIso.agda:463:PreCode : (x : Susp S²) → Type
Homotopy\Group\Pi4S3\S3PushoutIso.agda:472:Code : (hLevelTrunc 6 (Susp S²)) → Type ℓ-zero
Homotopy\Group\Pi4S3\S3PushoutIso.agda:474:  fst ∘ trRec {B = TypeOfHLevel ℓ-zero 5} (isOfHLevelTypeOfHLevel 5)
Homotopy\Group\Pi4S3\S3PushoutIso.agda:478:  cong-coherence : ∀ {ℓ} {A : Type ℓ} {x : A} (p : x ≡ x) (r : refl ≡ p)
Homotopy\Group\Pi4S3\S3PushoutIso.agda:524:      ∀ {ℓ} {A : Type ℓ} {x : A} {p : x ≡ x}
Homotopy\Group\Pi4S3\S3PushoutIso.agda:643:  lem : ∀ {ℓ} {A B : Type ℓ} {x x' y : A} {l w u : B}
Homotopy\Group\Pi4S3\Summary.agda:16:The --lossy-unification flag is used to speed up type checking.
Homotopy\Group\Pi4S3\Summary.agda:17:The file still type checks without it, but it's a lot slower (about 10 times).
Homotopy\Group\Pi4S3\Summary.agda:58:-- Nicer notation for the spheres (as pointed types)
Homotopy\Group\Pi4S3\Summary.agda:132:-- As a sanity check we have proved (commented as typechecking is quite slow):
Homotopy\HopfInvariant\Base.agda:58:             → Type _
Homotopy\HopfInvariant\Base.agda:119:      -- Currently, type checking is very slow without the abstract flag.
Homotopy\HopfInvariant\Base.agda:296:    → {P : HopfInvariantPush n f → Type ℓ}
Homotopy\HopfInvariant\Brunerie.agda:66:-- ZCohomology.Groups.SphereProduct for faster type checking.
Homotopy\HopfInvariant\Brunerie.agda:117:-- The type C and generator α, β in dim 2 and 4 respectively
Homotopy\HopfInvariant\Brunerie.agda:119:  CHopf : Type
Homotopy\HopfInvariant\Brunerie.agda:156:  ×UnitEquiv : {A B C : Type}
Homotopy\HopfInvariant\Brunerie.agda:205:-- H⁴(S²×S²) ≅ ℤ in order to speed up type checking.
Homotopy\HopfInvariant\Homomorphism.agda:56:C·Π : (n : ℕ) (f g : S₊∙ (3 +ℕ (n +ℕ n)) →∙ S₊∙ (2 +ℕ n)) → Type _
Homotopy\HopfInvariant\Homomorphism.agda:62:C* : ∀ n → (f g : S₊∙ (3 +ℕ (n +ℕ n)) →∙ S₊∙ (2 +ℕ n)) → Type _
Homotopy\HopfInvariant\Homomorphism.agda:107:              {P : S₊∙ (3 +ℕ (n +ℕ n)) ⋁ S₊∙ (3 +ℕ (n +ℕ n)) → Type ℓ}
Homotopy\HopfInvariant\Homomorphism.agda:752:coHomFun⌣ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} (f : A → B)
Homotopy\HopfInvariant\HopfMap.agda:76:TotalHopf' : Type _
Homotopy\HopfInvariant\HopfMap.agda:92:    indLem : ∀ {ℓ} {A : hopfS¹.TotalSpaceHopfPush → Type ℓ}
Homotopy\HopfInvariant\HopfMap.agda:132:joinS¹S¹→Groupoid : ∀ {ℓ} (P : join S¹ S¹ → Type ℓ)
Homotopy\HopfInvariant\HopfMap.agda:141:TotalHopf→Gpd : ∀ {ℓ} (P : hopfS¹.TotalSpaceHopfPush → Type ℓ)
Homotopy\HopfInvariant\HopfMap.agda:150:TotalHopf→Gpd' : ∀ {ℓ} (P : Σ (S₊ 2) hopfS¹.Hopf → Type ℓ)
Homotopy\HopfInvariant\HopfMap.agda:160:CP²→Groupoid : ∀ {ℓ} {P : CP² → Type ℓ}
Homotopy\HopfInvariant\HopfMap.agda:409:isGenerator≃ℤ : ∀ {ℓ} (G : Group ℓ) (g : fst G) → Type ℓ
Homotopy\HopfInvariant\HopfMap.agda:442:CP²' : Type _
Homotopy\HopfInvariant\HopfMap.agda:445:PushoutReplaceBase : ∀ {ℓ ℓ' ℓ''} {A B : Type ℓ} {C : Type ℓ'} {D : Type ℓ''}
Homotopy\HopfInvariant\HopfMap.agda:457:⌣equiv→pres1 : ∀ {ℓ} {G H : Type ℓ} → (G ≡ H)
Homotopy\HopfInvariant\HopfMap.agda:517:    -ₕeq : ∀ {ℓ} {A : Type ℓ} (n : ℕ) → Iso (coHom n A) (coHom n A)
Homotopy\Spectrum\Fiber.agda:30:  EquivJ' : {ℓ ℓ' : Level} {A B : Type ℓ} (P : (B : Type ℓ) → (e : A ≃ B) → Type ℓ')
Homotopy\Spectrum\Fiber.agda:37:  Equiv∙J' : {ℓ ℓ' : Level} {A : Pointed ℓ} (C : (B : Pointed ℓ) → A ≃∙ B → Type ℓ')
Homotopy\Spectrum\Fiber.agda:45:        → (C' : (B'' : Pointed ℓ) → A .fst , a' ≃∙ B'' → Type ℓ')
Induction\WellFounded.agda:7:module _ {ℓ ℓ'} {A : Type ℓ} (_<_ : A → A → Type ℓ') where
Induction\WellFounded.agda:8:  WFRec : ∀{ℓ''} → (A → Type ℓ'') → A → Type _
Induction\WellFounded.agda:11:  data Acc (x : A) : Type (ℓ-max ℓ ℓ') where
Induction\WellFounded.agda:14:  WellFounded : Type _
Induction\WellFounded.agda:18:module _ {ℓ ℓ'} {A : Type ℓ} {_<_ : A → A → Type ℓ'} where
Induction\WellFounded.agda:30:    wfi : ∀{ℓ''} {P : A → Type ℓ''}
Induction\WellFounded.agda:37:    module _ {ℓ''} {P : A → Type ℓ''} (e : ∀ x → (∀ y → y < x → P y) → P x) where
Modalities\Lex.agda:15:  (◯ : ∀ {ℓ} → Type ℓ → Type ℓ)
Modalities\Lex.agda:16:  (η : ∀ {ℓ} {A : Type ℓ} → A → ◯ A)
Modalities\Lex.agda:17:  (isModal : ∀ {ℓ} → Type ℓ → Type ℓ)
Modalities\Lex.agda:18:  (let isModalFam = λ {ℓ ℓ' : Level} {A : Type ℓ} (B : A → Type ℓ') → (x : A) → isModal (B x))
Modalities\Lex.agda:19:  (idemp : ∀ {ℓ} {A : Type ℓ} → isModal (◯ A))
Modalities\Lex.agda:20:  (≡-modal : ∀ {ℓ} {A : Type ℓ} {x y : A} (A-mod : isModal A) → isModal (x ≡ y))
Modalities\Lex.agda:21:  (◯-ind : ∀ {ℓ ℓ'} {A : Type ℓ} {B : ◯ A → Type ℓ'} (B-mod : isModalFam B) (f : (x : A) → B (η x)) → ([x] : ◯
A) → B [x])
Modalities\Lex.agda:22:  (◯-ind-β : ∀ {ℓ ℓ'} {A : Type ℓ} {B : ◯ A → Type ℓ'} (B-mod : isModalFam B) (f : (x : A) → B (η x)) (x : A) →
◯-ind B-mod f (η x) ≡ f x)
Modalities\Lex.agda:23:  (let Type◯ = λ (ℓ : Level) → Σ (Type ℓ) isModal)
Modalities\Lex.agda:24:  (◯-lex : ∀ {ℓ} → isModal (Type◯ ℓ))
Modalities\Lex.agda:32:η-at : (A : Type ℓ) → A → ◯ A
Modalities\Lex.agda:38:      A : Type ℓ
Modalities\Lex.agda:39:      B : Type ℓ'
Modalities\Lex.agda:64:module IsModalToUnitIsEquiv (A : Type ℓ) (A-mod : isModal A) where
Modalities\Lex.agda:85:  unit-is-equiv-to-is-modal : {A : Type ℓ} → isEquiv (η-at A) → isModal A
Modalities\Lex.agda:89:    : {A : Type ℓ} {B : Type ℓ'}
Modalities\Lex.agda:105:module LiftFam {A : Type ℓ} (B : A → Type ℓ') where
Modalities\Lex.agda:106:  module M = IsModalToUnitIsEquiv (Type◯ ℓ') ◯-lex
Modalities\Lex.agda:109:    ◯-lift-fam : ◯ A → Type◯ ℓ'
Modalities\Lex.agda:112:    ⟨◯⟩ : ◯ A → Type ℓ'
Modalities\Lex.agda:130:module LiftFamExtra {A : Type ℓ} {B : A → Type ℓ'} where
Modalities\Lex.agda:149:      A A′ : Type ℓ
Modalities\Lex.agda:150:      B : A → Type ℓ'
Modalities\Lex.agda:151:      C : Σ A B → Type ℓ''
Modalities\Lex.agda:159:module _ {A : Type ℓ} {B : A → Type ℓ'} where
Modalities\Lex.agda:194:module Σ-commute {A : Type ℓ} (B : A → Type ℓ') where
Modalities\Lex.agda:271:isConnected : Type ℓ → Type ℓ
Modalities\Lex.agda:276:module FormalDiskBundle {A : Type ℓ} where
Modalities\Lex.agda:277:  𝔻 : A → Type ℓ
Modalities\Modality.agda:5:  https://github.com/HoTT/HoTT-Agda/blob/master/core/lib/types/Modality.agda
Modalities\Modality.agda:16:record Modality ℓ : Type (ℓ-suc ℓ) where
Modalities\Modality.agda:18:    isModal : Type ℓ → Type ℓ
Modalities\Modality.agda:19:    isPropIsModal : {A : Type ℓ} → isProp (isModal A)
Modalities\Modality.agda:21:    ◯ : Type ℓ → Type ℓ                                  -- \ciO
Modalities\Modality.agda:22:    ◯-isModal : {A : Type ℓ} → isModal (◯ A)
Modalities\Modality.agda:24:    η : {A : Type ℓ} → A → ◯ A
Modalities\Modality.agda:26:    ◯-elim : {A : Type ℓ} {B : ◯ A → Type ℓ}
Modalities\Modality.agda:30:    ◯-elim-β : {A : Type ℓ} {B : ◯ A → Type ℓ}
Modalities\Modality.agda:34:    ◯-=-isModal : {A : Type ℓ} (x y : ◯ A) → isModal (x ≡ y)
Modalities\Modality.agda:36:  ◯-Types : Type (ℓ-suc ℓ)
Modalities\Modality.agda:37:  ◯-Types = TypeWithStr ℓ isModal
Modalities\Modality.agda:41:  module ◯Elim {A : Type ℓ} {B : ◯ A → Type ℓ}
Modalities\Modality.agda:48:  module ◯Rec {A : Type ℓ} {B : Type ℓ}
Modalities\Modality.agda:57:  module ◯Fmap {A B : Type ℓ} (f : A → B) =
Modalities\Modality.agda:63:  ◯-preservesEquiv : {A B : Type ℓ} (f : A → B) → isEquiv f → isEquiv (◯-map f)
Modalities\Modality.agda:76:  ◯-equiv : {A B : Type ℓ} → A ≃ B → ◯ A ≃ ◯ B
Modalities\Modality.agda:82:  equivPreservesIsModal : {A B : Type ℓ} → A ≃ B → isModal A → isModal B
Modalities\Modality.agda:86:  {- modal types and [η] being an equivalence -}
Modalities\Modality.agda:88:  isModalToIso : {A : Type ℓ} → isModal A → Iso A (◯ A)
Modalities\Modality.agda:94:  isModalToIsEquiv : {A : Type ℓ} → isModal A → isEquiv (η {A})
Modalities\Modality.agda:97:  isEquivToIsModal : {A : Type ℓ} → isEquiv (η {A}) → isModal A
Modalities\Modality.agda:100:  retractIsModal : {A B : Type ℓ} (w : isModal A)
Modalities\Modality.agda:115:  {- function types with modal codomain are modal -}
Modalities\Modality.agda:117:  Π-isModal : {A : Type ℓ} {B : A → Type ℓ}
Modalities\Modality.agda:127:  →-isModal : {A B : Type ℓ} → isModal B → isModal (A → B)
Modalities\Modality.agda:130:  {- sigma types of a modal dependent type with modal base are modal -}
Modalities\Modality.agda:132:  Σ-isModal : {A : Type ℓ} (B : A → Type ℓ)
Modalities\Modality.agda:162:  isModal≡ : {A : Type ℓ} → (isModal A) → {x y : A} → (isModal (x ≡ y))
Modalities\Modality.agda:165:  ◯-preservesProp : {A : Type ℓ} → (isProp A) → (isProp (◯ A))
Modalities\Instances\DoubleNegation.agda:18:  ¬ : Type ℓ → Type ℓ
Modalities\Instances\DoubleNegation.agda:21:  ¬¬ : Type ℓ → Type ℓ
Modalities\Instances\DoubleNegation.agda:24:  isStableProp : Type ℓ → Type ℓ
Modalities\Instances\DoubleNegation.agda:27:  module _ {A : Type ℓ} where
Modalities\Instances\DoubleNegation.agda:44:  module _ {A : Type ℓ} where
Modalities\Instances\DoubleNegation.agda:51:  map¬¬ : {A B : Type ℓ} → (A → B) → ¬¬ A → ¬¬ B
Papers\AffineSchemes.agda:12:Available at: https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.TYPES.2022.14
Papers\AffineSchemes.agda:47:import Cubical.Data.FinData.Base                                   as FiniteTypes
Papers\AffineSchemes.agda:82:-- path type in Cubical Agda
Papers\AffineSchemes.agda:157:open FiniteTypes renaming (_++Fin_ to _++_)
Papers\CellularMethods.agda:8:Cellular Methods in Homotopy Type Theory
Papers\CellularMethods.agda:121:    A B C : Type
Papers\CellularMethods.agda:125:_↔_ : Type ℓ → Type ℓ' → Type _
Papers\CellularMethods.agda:143:pSet : Type₁
Papers\CellularMethods.agda:144:pSet = Σ[ A ∈ Type ] Σ[ n ∈ ℕ ] (A ≡ Fin n)
Papers\CellularMethods.agda:235:-- Sequential colimits (for all types)
Papers\CellularMethods.agda:236:SeqColim* : Sequence ℓ-zero → Type
Papers\CellularMethods.agda:240:Definition-6 : CWstr → Type
Papers\CellularMethods.agda:299:  S¹fam : ℕ → Type
Papers\CellularMethods.agda:447:Definition-34 : ∀ {ℓ} (n : ℕ) → Type ℓ → Type (ℓ-suc ℓ)
Papers\CellularMethods.agda:465:Corollary-40 : ∀ {ℓ} (n : ℕ) {C : Type ℓ}
Papers\CohomologyRings.agda:88:𝕋² : Type ℓ-zero
Papers\CohomologyRings.agda:97:-- 2.1 Homotopy Type Theory in Cubical Agda
Papers\CohomologyRings.agda:99:-- Path type in Cubical Agda
Papers\CohomologyRings.agda:105:-- Equality of Σ-types
Papers\CohomologyRings.agda:129:-- Pointed types
Papers\ComputationalSyntheticCohomology.agda:8:Computational Synthetic Cohomology Theory in Homotopy Type Theory
Papers\ComputationalSyntheticCohomology.agda:70:-- 2.1 Homotopy Type Theory in Cubical Agda
Papers\ComputationalSyntheticCohomology.agda:78:-- Definition 3. Homogeneous types
Papers\ComputationalSyntheticCohomology.agda:237:-- Proposition 46. Cohomology of connected types
Papers\FunctorialQcQsSchemes.agda:22:-- 2.1: Univalent type theory in Cubical Agda
Papers\FunctorialQcQsSchemes.agda:70:---------- 2.2: Univalent type theory Cubical Agda ----------
Papers\FunctorialQcQsSchemes.agda:72:-- path type in Cubical Agda
Papers\Pi4S3-JournalVersion.agda:28:open import Cubical.Data.Unit as UnitType
Papers\Pi4S3-JournalVersion.agda:87:------ 2. HOMOTOPY TYPE THEORY IN Cubical Agda ------
Papers\Pi4S3-JournalVersion.agda:95:open UnitType renaming (Unit to 𝟙)
Papers\Pi4S3-JournalVersion.agda:112:--- 2.2 More higher inductive types ---
Papers\Pi4S3.agda:84:-- II. HOMOTOPY TYPE THEORY IN Cubical Agda
Papers\RepresentationIndependence.agda:66:-- 2. Programming in Cubical Type Theory
Papers\RepresentationIndependence.agda:69:-- 2.3 Higher Inductive Types
Papers\RepresentationIndependence.agda:94:-- 2.3 Higher Inductive Types
Papers\RepresentationIndependence.agda:121:open SIP using (TypeWithStr ; StrEquiv ; _≃[_]_
Papers\RepresentationIndependence.agda:129:-- Monoids are defined using records and Σ-types in the library
Papers\RepresentationIndependence.agda:131:RawMonoidStructure : Type → Type
Papers\RepresentationIndependence.agda:134:MonoidAxioms : (M : Type) → RawMonoidStructure M → Type
Papers\RepresentationIndependence.agda:138:MonoidStructure : Type → Type
Papers\RepresentationIndependence.agda:141:Monoid : Type₁
Papers\RepresentationIndependence.agda:142:Monoid = TypeWithStr ℓ-zero MonoidStructure
Papers\RepresentationIndependence.agda:144:MonoidEquiv : (M N : Monoid) → fst M ≃ fst N → Type
Papers\RepresentationIndependence.agda:175:RawMonoid : Type₁
Papers\RepresentationIndependence.agda:176:RawMonoid = TypeWithStr _ RawMonoidStructure
Papers\RepresentationIndependence.agda:186:isPropMonoidAxioms : (M : Type) (s : RawMonoidStructure M) → isProp (MonoidAxioms M s)
Papers\RepresentationIndependence.agda:217:module _ (A : Type) (Aset : isSet A) where
Papers\RepresentationIndependence.agda:219:   AutoEquivStr (λ (X : Type) → X × (A → X → X) × (X → Transp[ Maybe (X × A) ]))
Papers\RepresentationIndependence.agda:257:  replaceGoal : {A B : Type} {x y : A} → (e : A ≃ B)
Papers\SmashProducts.agda:8:Symmetric Monoidal Smash Products in Homotopy Type Theory,
Papers\SmashProducts.agda:36:-- Proposition 2 (Pointed types form a wild cat)
Papers\Synthetic.agda:45:-- 2.1 The Interval and Path Types
Papers\Synthetic.agda:47:-- 2.3 Higher Inductive Types
Papers\Synthetic.agda:48:-- 2.4 Glue Types and Univalence
Papers\Synthetic.agda:51:-- 2.1 The Interval and Path Types
Papers\Synthetic.agda:68:-- 2.3 Higher Inductive Types
Papers\Synthetic.agda:75:-- 2.4 Glue Types and Univalence
Papers\Synthetic.agda:137:open CorePrimitives renaming (Type to Set) public
Papers\Synthetic.agda:139:-- At the time the paper was published, Set was used instead of Type
Papers\ZCohomology.agda:37:open import Cubical.Foundations.HLevels                      as n-types
Papers\ZCohomology.agda:91:----- 2. HOMOTOPY TYPE THEORY IN CUBICAL AGDA -----
Papers\ZCohomology.agda:128:-- n-types Note that we start indexing from 0 in the Cubical Library
Papers\ZCohomology.agda:129:-- (so (-2)-types as referred to as 0-types, (-1) as 1-types, and so
Papers\ZCohomology.agda:131:open n-types using (isOfHLevel)
Papers\ZCohomology.agda:140:truncPathElim : ∀ {ℓ ℓ'} {A : Type ℓ} {x y : A} (n : ℕ)
Papers\ZCohomology.agda:141:              → {B : Path (hLevelTrunc (suc n) A) ∣ x ∣ ∣ y ∣ → Type ℓ'}
Papers\ZCohomology.agda:168:-- Glue types
Papers\ZCohomology.agda:197:wedgeConSn' : ∀ {ℓ} (n m : ℕ) {A : (S₊ (suc n)) → (S₊ (suc m)) → Type ℓ}
Papers\ZCohomology.agda:506:-- The axioms are defined as a record type
Reflection\Base.agda:19:_>>_ : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → R.TC A → R.TC B → R.TC B
Reflection\Base.agda:24:liftTC : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → (A → B) → R.TC A → R.TC B
Reflection\Base.agda:43:newMeta = R.checkType R.unknown
Reflection\Base.agda:45:makeAuxiliaryDef : String → R.Type → R.Term → R.TC R.Term
Reflection\RecordEquiv.agda:3:  Reflection-based tools for converting between iterated record types, particularly between
Reflection\RecordEquiv.agda:4:  record types and iterated Σ-types.
Reflection\RecordEquiv.agda:25:-- Intended to represent a (possibly nested) field of a record type. For example, the list
Reflection\RecordEquiv.agda:29:-- Intended to represent a bijection between two record types by an association list
Reflection\RecordEquiv.agda:31:-- allow dropping fields of Unit (or other definitionally unique) type.
Reflection\RecordEquiv.agda:47:-- Describes a correspondence between a non-nested record and an iterated Σ-type; more
Reflection\RecordEquiv.agda:61:data ΣFormat : Type where
Reflection\RecordEquiv.agda:68:-- Inverse of a correspondence between record types
Reflection\RecordEquiv.agda:76:-- Constructs a ΣFormat from a list of fields meant to represent a right-associated Σ-type
Reflection\RecordEquiv.agda:83:-- The domain of the RecordAssoc is the record type, the codomain is the Σ-type.
Reflection\RecordEquiv.agda:93:-- Define a reflected type with the shape of the Σ-type described by a ΣFormat.
Reflection\RecordEquiv.agda:94:-- The type arguments to the Σ are filled in with unsolved metavariables.
Reflection\RecordEquiv.agda:95:ΣFormat→Ty : ΣFormat → R.Type
Reflection\RecordEquiv.agda:101:-- Given the name of a record type and a ΣFormat describing an isomorphism between this
Reflection\RecordEquiv.agda:102:-- type and a Σ-type, constructs a reflected type of isomorphisms between the record and
Reflection\RecordEquiv.agda:103:-- Σ-type. If the record type takes parameters or indices, then the result is a similarly
Reflection\RecordEquiv.agda:108:  R.inferType (R.def name []) >>= R.normalise >>= go []
Reflection\RecordEquiv.agda:112:  -- Recurses on the type of the named record type
Reflection\RecordEquiv.agda:113:  go : List R.ArgInfo → R.Type → R.TC R.Term
Reflection\RecordEquiv.agda:120:    -- Main case, constructs isomorphism type
Reflection\RecordEquiv.agda:126:  go _ _ = R.typeError (R.strErr "Not a record type name: " ∷ R.nameErr name ∷ [])
Reflection\RecordEquiv.agda:128:-- Given an association list `al` defining a correspondence between record types (say R
Reflection\RecordEquiv.agda:144:-- Here the type of .c should have a definitionally unique element, so
Reflection\RecordEquiv.agda:162:  -- If there end up being zero clauses, then S should be a type with a definitionally
Reflection\RecordEquiv.agda:170:  (List (String × R.Arg R.Type) → List (String × R.Arg R.Type))
Reflection\RecordEquiv.agda:176:-- Given a ΣFormat `σ` relating a record type R and Σ-type S, returns
Reflection\RecordEquiv.agda:195:      -- Introduce a new variable of the input type
Reflection\RecordEquiv.agda:208:      -- Introduce a variable of the input type and an interval variable
Reflection\RecordEquiv.agda:219:-- Given a ΣFormat describing a correspondence between a record and nested Σ-type,
Reflection\RecordEquiv.agda:228:-- nested Σ-type, and the name `recordName` of the record type, declares a function with
Reflection\RecordEquiv.agda:229:-- name `idName` defining an isomorphism between the two types (with implicit parameters
Reflection\RecordEquiv.agda:230:-- corresponding to the parameters and indices of the record type).
Reflection\RecordEquiv.agda:237:-- Given a name `idName` and the name `recordName` of a record type, declares a function
Reflection\RecordEquiv.agda:238:-- with name `idName` defining an isomorphism from the record type to the right-associated
Reflection\RecordEquiv.agda:239:-- Σ-type corresponding to its list of fields (with implicit parameters corresponding to
Reflection\RecordEquiv.agda:240:-- the parameters and indices of the record type).
Reflection\RecordEquiv.agda:244:  (R.record-type _ fs) →
Reflection\RecordEquiv.agda:248:    R.typeError (R.strErr "Not a record type name:" ∷ R.nameErr recordName ∷ [])
Reflection\RecordEquiv.agda:259:      A : Type ℓ
Reflection\RecordEquiv.agda:260:      B : A → Type ℓ'
Reflection\RecordEquiv.agda:262:    record Example0 {A : Type ℓ} (B : A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Reflection\RecordEquiv.agda:269:    -- Declares a function `Example0IsoΣ` that gives an isomorphism between the record type and a
Reflection\RecordEquiv.agda:270:    -- right-associated nested Σ-type (with the parameters to Example0 as implict arguments).
Reflection\RecordEquiv.agda:273:    -- `Example0IsoΣ` has the type we expect
Reflection\RecordEquiv.agda:279:    record Example1 : Type where
Reflection\StrictEquiv.agda:27:strictEquivMacro : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:31:  R.checkType hole equivTy >>
Reflection\StrictEquiv.agda:36:strictIsoToEquivMacro : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:43:defStrictEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:50:defStrictIsoToEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:57:declStrictEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:64:declStrictIsoToEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:72:  strictEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Reflection\StrictEquiv.agda:78:  strictIsoToEquiv : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'}
Relation\Binary\Base.agda:25:Rel : ∀ {ℓa ℓb} (A : Type ℓa) (B : Type ℓb) (ℓ' : Level) → Type (ℓ-max (ℓ-max ℓa ℓb) (ℓ-suc ℓ'))
Relation\Binary\Base.agda:26:Rel A B ℓ' = A → B → Type ℓ'
Relation\Binary\Base.agda:28:PropRel : ∀ {ℓ} (A B : Type ℓ) (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Relation\Binary\Base.agda:31:idPropRel : ∀ {ℓ} (A : Type ℓ) → PropRel A A ℓ
Relation\Binary\Base.agda:35:invPropRel : ∀ {ℓ ℓ'} {A B : Type ℓ}
Relation\Binary\Base.agda:40:compPropRel : ∀ {ℓ ℓ' ℓ''} {A B C : Type ℓ}
Relation\Binary\Base.agda:45:graphRel : ∀ {ℓ} {A B : Type ℓ} → (A → B) → Rel A B ℓ
Relation\Binary\Base.agda:48:data Ordering : Type where
Relation\Binary\Base.agda:53:module HeterogenousRelation {ℓ ℓ' : Level} {A B : Type ℓ} (R : Rel A B ℓ') where
Relation\Binary\Base.agda:54:  isUniversalRel : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:57:module BinaryRelation {ℓ ℓ' : Level} {A : Type ℓ} (R : Rel A A ℓ') where
Relation\Binary\Base.agda:58:  isRefl : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:61:  isRefl' : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:64:  isIrrefl : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:67:  isSym : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:70:  isAsym : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:73:  isAntisym : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:76:  isTrans : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:79:  isTrans' : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:82:  -- Sum types don't play nicely with props, so we truncate
Relation\Binary\Base.agda:83:  isCotrans : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:86:  isWeaklyLinear : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:89:  isConnected : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:92:  isTotal : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:133:      subtype : Type ℓ''
Relation\Binary\Base.agda:134:      subtype = (fst P)
Relation\Binary\Base.agda:136:      toA : subtype → A
Relation\Binary\Base.agda:139:    InducedRelation : Rel subtype subtype ℓ'
Relation\Binary\Base.agda:142:  record isEquivRel : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Base.agda:154:  isPropValued : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:157:  isSetValued : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:160:  isEffective : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:164:  isDecidable : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:167:  impliesIdentity : Type _
Relation\Binary\Base.agda:170:  isTight : Type _
Relation\Binary\Base.agda:173:  inequalityImplies : Type _
Relation\Binary\Base.agda:177:  relSinglAt : (a : A) → Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:181:  contrRelSingl : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:184:  isUnivalent : Type (ℓ-max ℓ ℓ')
Relation\Binary\Base.agda:221:EquivRel : ∀ {ℓ} (A : Type ℓ) (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Relation\Binary\Base.agda:224:EquivPropRel : ∀ {ℓ} (A : Type ℓ) (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Relation\Binary\Base.agda:227:record RelIso {A : Type ℓA} (_≅_ : Rel A A ℓ≅A)
Relation\Binary\Base.agda:228:              {A' : Type ℓA'} (_≅'_ : Rel A' A' ℓ≅A') : Type (ℓ-max (ℓ-max ℓA ℓA') (ℓ-max ℓ≅A ℓ≅A')) where
Relation\Binary\Base.agda:238:RelIso→Iso : {A : Type ℓA} {A' : Type ℓA'}
Relation\Binary\Base.agda:250:isIrreflIrreflKernel : ∀{ℓ ℓ'} {A : Type ℓ} (R : Rel A A ℓ') → isIrrefl (IrreflKernel R)
Relation\Binary\Base.agda:253:isReflReflClosure : ∀{ℓ ℓ'} {A : Type ℓ} (R : Rel A A ℓ') → isRefl (ReflClosure R)
Relation\Binary\Base.agda:256:isSymSymKernel : ∀{ℓ ℓ'} {A : Type ℓ} (R : Rel A A ℓ') → isSym (SymKernel R)
Relation\Binary\Base.agda:259:isSymSymClosure : ∀{ℓ ℓ'} {A : Type ℓ} (R : Rel A A ℓ') → isSym (SymClosure R)
Relation\Binary\Base.agda:263:isAsymAsymKernel : ∀ {ℓ ℓ'} {A : Type ℓ} (R : Rel A A ℓ') → isAsym (AsymKernel R)
Relation\Binary\Extensionality.agda:12:module _ {ℓ ℓ'} {A : Type ℓ} (_≺_ : Rel A A ℓ') where
Relation\Binary\Extensionality.agda:17:  isWeaklyExtensional : Type _
Relation\Binary\Properties.agda:18:    A B : Type ℓ
Relation\Binary\Properties.agda:72:module _ {A B : Type ℓ} (e : A ≃ B) {_∼_ : Rel A A ℓ'} {_∻_ : Rel B B ℓ'}
Relation\Binary\Properties.agda:75:  RelPathP : PathP (λ i → ua e i → ua e i → Type _)
Relation\Binary\Properties.agda:82:module _ {ℓ''} {B : Type ℓ} {_∻_ : B → B → Type ℓ'} where
Relation\Binary\Properties.agda:84:  JRelPathP-Goal : Type _
Relation\Binary\Properties.agda:85:  JRelPathP-Goal = ∀ (A : Type ℓ) (e : A ≃ B) (_~_ : A → A → Type ℓ')
Relation\Binary\Properties.agda:86:             → (_h_ :  ∀ x y → x ~ y ≃ (fst e x ∻ fst e y)) → Type ℓ''
Relation\Binary\Order\QuosetReasoning.agda:29:      (P : Type ℓ)
Relation\Binary\Order\QuosetReasoning.agda:36:      data _<≤≡_ : P → P → Type (ℓ-max ℓ (ℓ-max ℓ< ℓ≤)) where
Relation\Binary\Order\QuosetReasoning.agda:41:      Is< : ∀ {x y} → x <≤≡ y → Type ℓ<
Relation\Binary\Order\QuosetReasoning.agda:55:    (P : Type ℓ)
Relation\Binary\Order\QuosetReasoning.agda:107:    (P : Type ℓ)
Relation\Binary\Order\QuosetReasoning.agda:131:module Examples (P : Type ℓ)
Relation\Binary\Order\Apartness\Base.agda:39:record IsApartness {A : Type ℓ} (_#_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Apartness\Base.agda:53:record ApartnessStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Apartness\Base.agda:58:    _#_     : A → A → Type ℓ'
Relation\Binary\Order\Apartness\Base.agda:65:Apartness : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Apartness\Base.agda:66:Apartness ℓ ℓ' = TypeWithStr ℓ (ApartnessStr ℓ')
Relation\Binary\Order\Apartness\Base.agda:68:apartness : (A : Type ℓ) → (_#_ : Rel A A ℓ') → IsApartness _#_ → Apartness ℓ ℓ'
Relation\Binary\Order\Apartness\Base.agda:71:record IsApartnessEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Apartness\Base.agda:73:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Apartness\Base.agda:86:ApartnessEquiv : (M : Apartness ℓ₀ ℓ₀') (M : Apartness ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀
ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Apartness\Base.agda:89:isPropIsApartness : {A : Type ℓ} (_#_ : A → A → Type ℓ') → isProp (IsApartness _#_)
Relation\Binary\Order\Apartness\Properties.agda:24:isApartness→ImpliesInequality : {A : Type ℓ} {_#_ : Rel A A ℓ'}
Relation\Binary\Order\Apartness\Properties.agda:29:isApartness→isEquivRelNegationRel : {A : Type ℓ} {_#_ : Rel A A ℓ'}
Relation\Binary\Order\Apartness\Properties.agda:40:  {A : Type ℓ}
Relation\Binary\Order\Apartness\Properties.agda:46:  isApartnessInduced : IsApartness R → (B : Type ℓ'') → (f : B ↪ A)
Relation\Binary\Order\Loset\Base.agda:40:record IsLoset {A : Type ℓ} (_<_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Loset\Base.agda:56:record LosetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Loset\Base.agda:61:    _<_     : A → A → Type ℓ'
Relation\Binary\Order\Loset\Base.agda:68:Loset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Loset\Base.agda:69:Loset ℓ ℓ' = TypeWithStr ℓ (LosetStr ℓ')
Relation\Binary\Order\Loset\Base.agda:71:loset : (A : Type ℓ) → (_<_ : Rel A A ℓ') → IsLoset _<_ → Loset ℓ ℓ'
Relation\Binary\Order\Loset\Base.agda:74:record IsLosetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Loset\Base.agda:76:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Loset\Base.agda:89:LosetEquiv : (M : Loset ℓ₀ ℓ₀') (M : Loset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Loset\Base.agda:92:isPropIsLoset : {A : Type ℓ} (_<_ : A → A → Type ℓ') → isProp (IsLoset _<_)
Relation\Binary\Order\Loset\Properties.agda:26:  {A : Type ℓ}
Relation\Binary\Order\Loset\Properties.agda:93:  isLosetInduced : IsLoset R → (B : Type ℓ'') → (f : B ↪ A)
Relation\Binary\Order\Poset\Base.agda:32:record IsPoset {A : Type ℓ} (_≤_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Poset\Base.agda:46:record PosetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Poset\Base.agda:51:    _≤_     : A → A → Type ℓ'
Relation\Binary\Order\Poset\Base.agda:58:Poset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Poset\Base.agda:59:Poset ℓ ℓ' = TypeWithStr ℓ (PosetStr ℓ')
Relation\Binary\Order\Poset\Base.agda:61:poset : (A : Type ℓ) → (_≤_ : Rel A A ℓ') → IsPoset _≤_ → Poset ℓ ℓ'
Relation\Binary\Order\Poset\Base.agda:64:record IsPosetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Base.agda:66:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Poset\Base.agda:85:PosetEquiv : (M : Poset ℓ₀ ℓ₀') (M : Poset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Poset\Base.agda:88:isPropIsPoset : {A : Type ℓ} (_≤_ : A → A → Type ℓ') → isProp (IsPoset _≤_)
Relation\Binary\Order\Poset\Base.agda:97:isPropIsPosetEquiv : {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Covering.agda:38:  _covers_ : P → P → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Interval.agda:34:    record Interval : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Poset\Mappings.agda:36:record IsIsotone {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Mappings.agda:38:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Poset\Mappings.agda:51:isPropIsIsotone : {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Mappings.agda:57:IsIsotone-∘ : {A : Type ℓ₀} {B : Type ℓ₁} {C : Type ℓ₂}
Relation\Binary\Order\Poset\Mappings.agda:66:record IsAntitone {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Mappings.agda:68:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Poset\Mappings.agda:81:isPropIsAntitone : {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Poset\Mappings.agda:226:    -- We can now define the type of residuated maps
Relation\Binary\Order\Poset\Mappings.agda:227:    isResiduated : Type _
Relation\Binary\Order\Poset\Mappings.agda:230:    hasResidual : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:337:           → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:456:          → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:462:              → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:469:           → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:475:               → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Mappings.agda:808:                → Type _
Relation\Binary\Order\Poset\Mappings.agda:813:                    → Type _
Relation\Binary\Order\Poset\Mappings.agda:1008:             → Type _
Relation\Binary\Order\Poset\Mappings.agda:1185:    isGaloisConnection : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:30:  {A : Type ℓ}
Relation\Binary\Order\Poset\Properties.agda:77:  isPosetInduced : IsPoset R → (B : Type ℓ'') → (f : B ↪ A) → IsPoset (InducedRelation R
(B , f))
Relation\Binary\Order\Poset\Properties.agda:110:  {A : Type ℓ}
Relation\Binary\Order\Poset\Properties.agda:160:    {B : Type ℓ''}
Relation\Binary\Order\Poset\Properties.agda:378:    isMeetSemipseudolattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:381:    isMeetCompleteSemipseudolattice : {ℓ'' : Level} → Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-suc
ℓ''))
Relation\Binary\Order\Poset\Properties.agda:382:    isMeetCompleteSemipseudolattice {ℓ'' = ℓ''} = {B : Type ℓ''}
Relation\Binary\Order\Poset\Properties.agda:386:    isJoinSemipseudolattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:389:    isJoinCompleteSemipseudolattice : {ℓ'' : Level} → Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-suc
ℓ''))
Relation\Binary\Order\Poset\Properties.agda:390:    isJoinCompleteSemipseudolattice {ℓ'' = ℓ''} = {B : Type ℓ''}
Relation\Binary\Order\Poset\Properties.agda:394:    isMeetSemilattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:397:    isJoinSemilattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:400:    isPseudolattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:403:    isLattice : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Properties.agda:406:    isCompleteLattice : {ℓ'' : Level} → Type (ℓ-max (ℓ-max ℓ ℓ') (ℓ-suc ℓ''))
Relation\Binary\Order\Poset\Properties.agda:470:              where P↑ : Type _
Relation\Binary\Order\Poset\Properties.agda:480:              where P↓ : Type _
Relation\Binary\Order\Poset\Properties.agda:509:        MeetDistLJoin : Type ℓ
Relation\Binary\Order\Poset\Properties.agda:512:        MeetDistRJoin : Type ℓ
Relation\Binary\Order\Poset\Properties.agda:515:        JoinDistLMeet : Type ℓ
Relation\Binary\Order\Poset\Properties.agda:518:        JoinDistRMeet : Type ℓ
Relation\Binary\Order\Poset\Properties.agda:610:        isDistributive : Type ℓ
Relation\Binary\Order\Poset\Subset.agda:45:        isDownset : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Poset\Subset.agda:51:        isUpset : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Poset\Subset.agda:100:      {I : Type ℓ''}
Relation\Binary\Order\Poset\Subset.agda:221:        isPrincipalDownset : Type _
Relation\Binary\Order\Poset\Subset.agda:240:        isPrincipalUpset : Type _
Relation\Binary\Order\Poset\Subset.agda:269:  ↓ : P → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Subset.agda:285:  ↑ : P → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Instances\Embedding.agda:22:-- The collection of embeddings on a type happens to form a complete lattice
Relation\Binary\Order\Poset\Instances\Embedding.agda:25:isPoset⊆ₑ : {A : Type ℓ} → IsPoset {A = Embedding A ℓ'} _⊆ₑ_
Relation\Binary\Order\Poset\Instances\Embedding.agda:32:EmbeddingPoset : (A : Type ℓ) (ℓ' : Level) → Poset _ _
Relation\Binary\Order\Poset\Instances\Embedding.agda:37:isMeet∩ₑ : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:56:isMeetSemipseudolatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:61:isGreatestEmbeddingPosetTotal : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:68:isMeetSemilatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:75:isJoin∪ₑ : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:95:isJoinSemipseudolatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:100:isLeast∅ : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:104:isJoinSemilatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:111:isLatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:116:isInfimum⋂ₑ : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:117:               {I : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:123:isMeetCompleteSemipseudolatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:128:isSupremum⋃ₑ : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:129:               {I : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:136:isJoinCompleteSemipseudolatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\Embedding.agda:141:isCompleteLatticeEmbeddingPoset : {A : Type ℓ}
Relation\Binary\Order\Poset\Instances\PosetalReflection.agda:40:  Reflection : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Poset\Instances\PosetalReflection.agda:48:  _≤_ : Reflection → Reflection → Type ℓ'
Relation\Binary\Order\Poset\Instances\PosetalReflection.agda:77:    idEmb : {A : Type ℓ''} → Embedding A ℓ''
Relation\Binary\Order\Proset\Base.agda:34:record IsProset {A : Type ℓ} (_≲_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Proset\Base.agda:47:record ProsetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Proset\Base.agda:52:    _≲_     : A → A → Type ℓ'
Relation\Binary\Order\Proset\Base.agda:59:Proset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Proset\Base.agda:60:Proset ℓ ℓ' = TypeWithStr ℓ (ProsetStr ℓ')
Relation\Binary\Order\Proset\Base.agda:62:proset : (A : Type ℓ) → (_≲_ : Rel A A ℓ') → IsProset _≲_ → Proset ℓ ℓ'
Relation\Binary\Order\Proset\Base.agda:65:record IsProsetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Proset\Base.agda:67:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Proset\Base.agda:80:ProsetEquiv : (M : Proset ℓ₀ ℓ₀') (M : Proset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁
ℓ₁'))
Relation\Binary\Order\Proset\Base.agda:83:isPropIsProset : {A : Type ℓ} (_≲_ : A → A → Type ℓ') → isProp (IsProset _≲_)
Relation\Binary\Order\Proset\Properties.agda:26:  {A : Type ℓ}
Relation\Binary\Order\Proset\Properties.agda:51:  isProsetInduced : IsProset R → (B : Type ℓ'') → (f : B ↪ A) → IsProset
(InducedRelation R (B , f))
Relation\Binary\Order\Proset\Properties.agda:75:  {A : Type ℓ}
Relation\Binary\Order\Proset\Properties.agda:92:      subtype = fst P
Relation\Binary\Order\Proset\Properties.agda:96:    isMinimal : (n : subtype) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:97:    isMinimal n = (x : subtype) → toA x ≲ toA n → toA n ≲ toA x
Relation\Binary\Order\Proset\Properties.agda:102:    Minimal : Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:103:    Minimal = Σ[ n ∈ subtype ] isMinimal n
Relation\Binary\Order\Proset\Properties.agda:105:    isMaximal : (n : subtype) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:106:    isMaximal n = (x : subtype) → toA n ≲ toA x → toA x ≲ toA n
Relation\Binary\Order\Proset\Properties.agda:111:    Maximal : Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:112:    Maximal = Σ[ n ∈ subtype ] isMaximal n
Relation\Binary\Order\Proset\Properties.agda:114:    isLeast : (n : subtype) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:115:    isLeast n = (x : subtype) → toA n ≲ toA x
Relation\Binary\Order\Proset\Properties.agda:120:    Least : Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:121:    Least = Σ[ n ∈ subtype ] isLeast n
Relation\Binary\Order\Proset\Properties.agda:123:    isGreatest : (n : subtype) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:124:    isGreatest n = (x : subtype) → toA x ≲ toA n
Relation\Binary\Order\Proset\Properties.agda:129:    Greatest : Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:130:    Greatest = Σ[ n ∈ subtype ] isGreatest n
Relation\Binary\Order\Proset\Properties.agda:133:    {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:137:    isLowerBound : (n : A) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:143:    LowerBound : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:146:    isUpperBound : (n : A) → Type (ℓ-max ℓ' ℓ'')
Relation\Binary\Order\Proset\Properties.agda:152:    UpperBound : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:156:    {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:160:    isMaximalLowerBound : (n : A) → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:172:    MaximalLowerBound : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:175:    isMinimalUpperBound : (n : A) → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:187:    MinimalUpperBound : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:190:    isInfimum : (n : A) → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:202:    Infimum : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:205:    isSupremum : (n : A) → Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:217:    Supremum : Type (ℓ-max (ℓ-max ℓ ℓ') ℓ'')
Relation\Binary\Order\Proset\Properties.agda:228:  isInfimumOfUpperBounds→isUpperBound : {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:235:  isInfimumOfUpperBounds→isSupremum : {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:243:  isSupremumOfLowerBounds→isLowerBound : {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:250:  isSupremumOfLowerBounds→isInfimum : {B : Type ℓ''}
Relation\Binary\Order\Proset\Properties.agda:258:  isMeet : A → A → A → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Proset\Properties.agda:261:  isJoin : A → A → A → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Proset\Properties.agda:264:  Meet : ∀ a b → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Proset\Properties.agda:267:  Join : ∀ a b → Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Pseudolattice\Base.agda:28:record IsPseudolattice {L : Type ℓ} (_≤_ : L → L → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Pseudolattice\Base.agda:49:record PseudolatticeStr (ℓ' : Level) (L : Type ℓ) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Relation\Binary\Order\Pseudolattice\Base.agda:53:    _≤_ : L → L → Type ℓ'
Relation\Binary\Order\Pseudolattice\Base.agda:63:Pseudolattice : ∀ ℓ ℓ' → Type (ℓ-suc (ℓ-max ℓ ℓ'))
Relation\Binary\Order\Pseudolattice\Base.agda:64:Pseudolattice ℓ ℓ' = TypeWithStr ℓ (PseudolatticeStr ℓ')
Relation\Binary\Order\Pseudolattice\Base.agda:66:makeIsPseudolattice : {L : Type ℓ} {_≤_ : L → L → Type ℓ'}
Relation\Binary\Order\Pseudolattice\Base.agda:111:record IsPseudolatticeEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Pseudolattice\Base.agda:113:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Pseudolattice\Base.agda:127:                     → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Pseudolattice\Base.agda:130:isPropIsPseudolattice : {L : Type ℓ} (_≤_ : L → L → Type ℓ') → isProp
(IsPseudolattice _≤_)
Relation\Binary\Order\Pseudolattice\Properties.agda:26:  {A : Type ℓ}
Relation\Binary\Order\Quoset\Base.agda:36:record IsQuoset {A : Type ℓ} (_<_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Quoset\Base.agda:50:record QuosetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Quoset\Base.agda:55:    _<_     : A → A → Type ℓ'
Relation\Binary\Order\Quoset\Base.agda:62:Quoset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Quoset\Base.agda:63:Quoset ℓ ℓ' = TypeWithStr ℓ (QuosetStr ℓ')
Relation\Binary\Order\Quoset\Base.agda:65:quoset : (A : Type ℓ) → (_<_ : Rel A A ℓ') → IsQuoset _<_ → Quoset ℓ ℓ'
Relation\Binary\Order\Quoset\Base.agda:68:record IsQuosetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Quoset\Base.agda:70:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Quoset\Base.agda:83:QuosetEquiv : (M : Quoset ℓ₀ ℓ₀') (M : Quoset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁
ℓ₁'))
Relation\Binary\Order\Quoset\Base.agda:86:isPropIsQuoset : {A : Type ℓ} (_<_ : A → A → Type ℓ') → isProp (IsQuoset _<_)
Relation\Binary\Order\Quoset\Properties.agda:22:  {A : Type ℓ}
Relation\Binary\Order\Quoset\Properties.agda:53:  isQuosetInduced : IsQuoset R → (B : Type ℓ'') → (f : B ↪ A)
Relation\Binary\Order\StrictOrder\Base.agda:38:record IsStrictOrder {A : Type ℓ} (_<_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\StrictOrder\Base.agda:53:record StrictOrderStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\StrictOrder\Base.agda:58:    _<_     : A → A → Type ℓ'
Relation\Binary\Order\StrictOrder\Base.agda:65:StrictOrder : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\StrictOrder\Base.agda:66:StrictOrder ℓ ℓ' = TypeWithStr ℓ (StrictOrderStr ℓ')
Relation\Binary\Order\StrictOrder\Base.agda:68:strictorder : (A : Type ℓ) → (_<_ : Rel A A ℓ') → IsStrictOrder _<_ → StrictOrder ℓ ℓ'
Relation\Binary\Order\StrictOrder\Base.agda:71:record IsStrictOrderEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\StrictOrder\Base.agda:73:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\StrictOrder\Base.agda:86:StrictOrderEquiv : (M : StrictOrder ℓ₀ ℓ₀') (M : StrictOrder ℓ₁ ℓ₁') → Type (ℓ-max
(ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\StrictOrder\Base.agda:89:isPropIsStrictOrder : {A : Type ℓ} (_<_ : A → A → Type ℓ') → isProp (IsStrictOrder _<_)
Relation\Binary\Order\StrictOrder\Properties.agda:27:  {A : Type ℓ}
Relation\Binary\Order\StrictOrder\Properties.agda:81:  isStrictOrderInduced : IsStrictOrder R → (B : Type ℓ'') → (f : B ↪ A)
Relation\Binary\Order\Toset\Base.agda:38:record IsToset {A : Type ℓ} (_≤_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Toset\Base.agda:53:record TosetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Toset\Base.agda:58:    _≤_     : A → A → Type ℓ'
Relation\Binary\Order\Toset\Base.agda:65:Toset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Toset\Base.agda:66:Toset ℓ ℓ' = TypeWithStr ℓ (TosetStr ℓ')
Relation\Binary\Order\Toset\Base.agda:68:toset : (A : Type ℓ) → (_≤_ : Rel A A ℓ') → IsToset _≤_ → Toset ℓ ℓ'
Relation\Binary\Order\Toset\Base.agda:71:record IsTosetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Toset\Base.agda:73:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Toset\Base.agda:86:TosetEquiv : (M : Toset ℓ₀ ℓ₀') (M : Toset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Toset\Base.agda:89:isPropIsToset : {A : Type ℓ} (_≤_ : A → A → Type ℓ') → isProp (IsToset _≤_)
Relation\Binary\Order\Toset\Properties.agda:30:  {A : Type ℓ}
Relation\Binary\Order\Toset\Properties.agda:100:  isTosetInduced : IsToset R → (B : Type ℓ'') → (f : B ↪ A)
Relation\Binary\Order\Toset\Properties.agda:138:  {A : Type ℓ}
Relation\Binary\Order\Woset\Base.agda:37:record IsWoset {A : Type ℓ} (_≺_ : A → A → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\Binary\Order\Woset\Base.agda:51:record WosetStr (ℓ' : Level) (A : Type ℓ) : Type (ℓ-max ℓ (ℓ-suc ℓ')) where
Relation\Binary\Order\Woset\Base.agda:56:    _≺_     : A → A → Type ℓ'
Relation\Binary\Order\Woset\Base.agda:63:Woset : ∀ ℓ ℓ' → Type (ℓ-max (ℓ-suc ℓ) (ℓ-suc ℓ'))
Relation\Binary\Order\Woset\Base.agda:64:Woset ℓ ℓ' = TypeWithStr ℓ (WosetStr ℓ')
Relation\Binary\Order\Woset\Base.agda:66:woset : (A : Type ℓ) (_≺_ : A → A → Type ℓ') (h : IsWoset _≺_) → Woset ℓ ℓ'
Relation\Binary\Order\Woset\Base.agda:69:record IsWosetEquiv {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Woset\Base.agda:71:  : Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') ℓ₁')
Relation\Binary\Order\Woset\Base.agda:90:WosetEquiv : (M : Woset ℓ₀ ℓ₀') (M : Woset ℓ₁ ℓ₁') → Type (ℓ-max (ℓ-max ℓ₀ ℓ₀') (ℓ-max ℓ₁ ℓ₁'))
Relation\Binary\Order\Woset\Base.agda:106:isPropIsWoset : {A : Type ℓ} (_≺_ : A → A → Type ℓ') → isProp (IsWoset _≺_)
Relation\Binary\Order\Woset\Base.agda:118:isPropIsWosetEquiv : {A : Type ℓ₀} {B : Type ℓ₁}
Relation\Binary\Order\Woset\Properties.agda:16:  {A : Type ℓ}
Relation\Binary\Order\Woset\Simulation.agda:36:              → Type (ℓ-max (ℓ-max (ℓ-max ℓa ℓa') ℓb) ℓb')
Relation\Binary\Order\Woset\Simulation.agda:43:        less : ∀ a → Type _
Relation\Binary\Order\Woset\Simulation.agda:84:             → Type (ℓ-max (ℓ-max (ℓ-max ℓa ℓa') ℓb) ℓb')
Relation\Binary\Order\Woset\Simulation.agda:91:        less : ∀ a → Type _
Relation\Binary\Order\Woset\Simulation.agda:727:    { I : Type ℓ' }
Relation\Binary\Order\Woset\Simulation.agda:733:    ΣF : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Woset\Simulation.agda:736:    _≈_ : ΣF → ΣF → Type ℓ
Relation\Binary\Order\Woset\Simulation.agda:739:    _<_ : ΣF → ΣF → Type ℓ
Relation\Binary\Order\Woset\Simulation.agda:839:    -- And now, we forge our quotient type
Relation\Binary\Order\Woset\Simulation.agda:841:    F/ : Type (ℓ-max ℓ ℓ')
Relation\Binary\Order\Woset\Simulation.agda:860:    _</_ : F/ → F/ → Type ℓ
Relation\Binary\Order\Woset\Simulation.agda:926:sup : {I : Type ℓ'} (F : I → Woset ℓ ℓ)
Relation\Nullary\Base.agda:13:    A  : Type ℓ
Relation\Nullary\Base.agda:18:¬_ : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:21:-- Decidable types (inspired by standard library)
Relation\Nullary\Base.agda:22:data Dec (P : Type ℓ) : Type ℓ where
Relation\Nullary\Base.agda:26:decRec : ∀ {ℓ ℓ'} {P : Type ℓ} {A : Type ℓ'} → (P → A) → (¬ P → A) → (Dec P) → A
Relation\Nullary\Base.agda:34:NonEmpty : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:37:Stable : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:44:SplitSupport : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:47:Collapsible : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:50:Populated ⟪_⟫ : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:54:PStable : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:57:onAllPaths : (Type ℓ → Type ℓ) → Type ℓ → Type ℓ
Relation\Nullary\Base.agda:60:Separated : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:63:HSeparated : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:66:Collapsible≡ : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:69:PStable≡ : Type ℓ → Type ℓ
Relation\Nullary\Base.agda:72:Discrete : Type ℓ → Type ℓ
Relation\Nullary\DecidablePropositions.agda:21:DecProp : (ℓ : Level) → Type (ℓ-suc ℓ)
Relation\Nullary\DecidablePropositions.agda:31:isDecProp : Type ℓ → Type ℓ
Relation\Nullary\DecidablePropositions.agda:32:isDecProp P = Σ[ t ∈ Bool ] P ≃ Bool→Type t
Relation\Nullary\DecidablePropositions.agda:34:DecProp' : (ℓ : Level) → Type (ℓ-suc ℓ)
Relation\Nullary\DecidablePropositions.agda:35:DecProp' ℓ = Σ[ P ∈ Type ℓ ] isDecProp P
Relation\Nullary\DecidablePropositions.agda:39:isDecProp→isProp : {P : Type ℓ} → isDecProp P → isProp P
Relation\Nullary\DecidablePropositions.agda:40:isDecProp→isProp h = isOfHLevelRespectEquiv 1 (invEquiv (h .snd)) isPropBool→Type
Relation\Nullary\DecidablePropositions.agda:42:isDecProp→Dec : {P : Type ℓ} → isDecProp P → Dec P
Relation\Nullary\DecidablePropositions.agda:43:isDecProp→Dec h = EquivPresDec (invEquiv (h .snd)) DecBool→Type
Relation\Nullary\DecidablePropositions.agda:45:isPropIsDecProp : {P : Type ℓ} → isProp (isDecProp P)
Relation\Nullary\DecidablePropositions.agda:47:  Σ≡PropEquiv (λ _ → isOfHLevel⁺≃ᵣ 0 isPropBool→Type) .fst
Relation\Nullary\DecidablePropositions.agda:48:    (Bool→TypeInj _ _ (invEquiv (p .snd) ⋆ q .snd))
Relation\Nullary\DecidablePropositions.agda:50:isDecPropRespectEquiv : {P : Type ℓ} {Q : Type ℓ'}
Relation\Nullary\HLevels.agda:13:    A : Type ℓ
Relation\Nullary\Properties.agda:3:Properties of nullary relations, i.e. structures on types.
Relation\Nullary\Properties.agda:5:Includes several results from [Notions of Anonymous Existence in Martin-Löf Type
Theory](https://lmcs.episciences.org/3217)
Relation\Nullary\Properties.agda:27:    A B : Type ℓ
Relation\Nullary\Properties.agda:28:    P : A -> Type ℓ
Relation\Nullary\Properties.agda:50:EquivPresDiscrete : ∀ {ℓ ℓ'}{A : Type ℓ} {B : Type ℓ'} → A ≃ B
Relation\Nullary\Properties.agda:54:isProp¬ : (A : Type ℓ) → isProp (¬ A)
Relation\Nullary\Properties.agda:73:StableΣ : ∀ {A : Type ℓ} {P : A → Type ℓ'} →
Relation\Nullary\Properties.agda:100:mapDec : ∀ {B : Type ℓ} → (A → B) → (¬ A → ¬ B) → Dec A → Dec B
Relation\Nullary\Properties.agda:104:EquivPresDec : ∀ {ℓ ℓ'}{A : Type ℓ} {B : Type ℓ'} → A ≃ B
Relation\Nullary\Properties.agda:166:-- for a a type to be a set.
Relation\Nullary\Properties.agda:214:-- Proof of Hedberg's theorem: a type with decidable equality is an h-set
Relation\Nullary\Properties.agda:221:≡no : ∀ {A : Type ℓ} x y → Path (Dec A) x (no y)
Relation\Nullary\Properties.agda:225:inhabitedFibres? : ∀ {ℓ'} {A : Type ℓ} {B : Type ℓ'}
Relation\Nullary\Properties.agda:226:  (f : A → B) → Type (ℓ-max ℓ ℓ')
Relation\ZigZag\Base.agda:24:isZigZagComplete : {A B : Type ℓ} (R : A → B → Type ℓ') → Type (ℓ-max ℓ ℓ')
Relation\ZigZag\Base.agda:27:ZigZagRel : (A B : Type ℓ) (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Relation\ZigZag\Base.agda:28:ZigZagRel A B ℓ' = Σ[ R ∈ (A → B → Type ℓ') ] (isZigZagComplete R)
Relation\ZigZag\Base.agda:30:record isQuasiEquivRel {A B : Type ℓ} (R : A → B → Type ℓ') : Type (ℓ-max ℓ ℓ') where
Relation\ZigZag\Base.agda:38:QuasiEquivRel : (A B : Type ℓ) (ℓ' : Level) → Type (ℓ-max ℓ (ℓ-suc ℓ'))
Relation\ZigZag\Base.agda:42:invQER : {A B : Type ℓ} {ℓ' : Level} → QuasiEquivRel A B ℓ' → QuasiEquivRel B A ℓ'
Relation\ZigZag\Base.agda:48:QER→EquivRel : {A B : Type ℓ}
Relation\ZigZag\Base.agda:57:module QER→Equiv {A B : Type ℓ} (R : QuasiEquivRel A B ℓ') where
Relation\ZigZag\Base.agda:173:module Universal→ZigZag {A B : Type ℓ} (R : PropRel A B ℓ') where
Relation\ZigZag\Base.agda:182:¬Universal→ZigZag : (∀ {ℓ ℓ'} (A B : Type ℓ) (R : PropRel A B ℓ') → Universal→ZigZag.Claim R) → ⊥
Relation\ZigZag\Applications\MultiSet.agda:32:data AList {ℓ} (A : Type ℓ) : Type ℓ where
Relation\ZigZag\Applications\MultiSet.agda:43:module Lists&ALists {A : Type ℓ} (discA : Discrete A) where
Relation\ZigZag\Applications\MultiSet.agda:45:  multisetShape : Type ℓ → Type ℓ
Relation\ZigZag\Applications\MultiSet.agda:147:  R : List A → AList A → Type ℓ
Relation\ZigZag\Applications\MultiSet.agda:229:    Path (TypeWithStr ℓ S.structure) (List/Rᴸ , LQstructure) (AList/Rᴬᴸ , ALQstructure)
Relation\ZigZag\Applications\MultiSet.agda:239:  hasAssociativeUnion : TypeWithStr ℓ S.structure → Type ℓ
Relation\ZigZag\Applications\MultiSet.agda:254:  multisetShape' : Type ℓ → Type ℓ
Relation\ZigZag\Applications\MultiSet.agda:354:   ∙ There is a QER between lists and the basic data type of the HIT
Structures\Auto.agda:7:  autoDesc (λ (X : Type₀) → X → X × ℕ)   ↦   function+ var (var , constant ℕ)
Structures\Auto.agda:9:We prefer to use the constant structure whenever possible, e.g., [autoDesc (λ (X : Type₀) → ℕ → ℕ)]
Structures\Auto.agda:12:Writing [auto* (λ X → ⋯)] doesn't seem to work, but [auto* (λ (X : Type ℓ) → ⋯)] does.
Structures\Auto.agda:35:  Transp[_] : ∀ {ℓ} → Type ℓ → Type ℓ
Structures\Auto.agda:42:  tType : R.Term → R.Term
Structures\Auto.agda:43:  tType ℓ = R.def (quote Type) [ varg ℓ ]
Structures\Auto.agda:51:  func : (ℓ ℓ' : Level) → Type (ℓ-suc (ℓ-max ℓ ℓ'))
Structures\Auto.agda:52:  func ℓ ℓ' = Type ℓ → Type ℓ'
Structures\Auto.agda:62:  constantShape : ∀ {ℓ'} (ℓ : Level) (A : Type ℓ') → (Type ℓ → Type ℓ')
Structures\Auto.agda:65:  pointedShape : (ℓ : Level) → Type ℓ → Type ℓ
Structures\Auto.agda:69:    → (Type ℓ → Type ℓ₀) → (Type ℓ → Type ℓ₁) → Type ℓ → Type (ℓ-max ℓ₀ ℓ₁)
Structures\Auto.agda:73:    → (Type ℓ → Type ℓ₀) → (Type ℓ → Type ℓ₁) → Type ℓ → Type (ℓ-max ℓ₀ ℓ₁)
Structures\Auto.agda:77:    → (Type ℓ → Type ℓ₀) → Type ℓ → Type ℓ₀
Structures\Auto.agda:81:    → (Type ℓ → Type ℓ₀) → Type ℓ → Type ℓ₀
Structures\Auto.agda:85:  -- Build transport structure descriptor from a function [t : Type ℓ → Type ℓ']
Structures\Auto.agda:87:  buildTranspDesc zero ℓ ℓ' t = R.typeError (R.strErr "Ran out of fuel! at \n" ∷ R.termErr t ∷ [])
Structures\Auto.agda:90:    R.typeError (R.strErr "Can't automatically generate a transp structure for\n" ∷ R.termErr t ∷ [])
Structures\Auto.agda:94:      newMeta (tType ℓ') >>= λ A →
Structures\Auto.agda:135:    R.inferType hole >>= λ H →
Structures\Auto.agda:139:    R.checkType t (tStruct ℓ ℓ') >>
Structures\Auto.agda:142:-- Build structure descriptor from a function [t : Type ℓ → Type ℓ']
Structures\Auto.agda:144:buildDesc zero ℓ ℓ' t = R.typeError (R.strErr "Ran out of fuel! at \n" ∷ R.termErr t ∷ [])
Structures\Auto.agda:148:  R.typeError (R.strErr "Can't automatically generate a structure for\n" ∷ R.termErr t ∷ [])
Structures\Auto.agda:152:    newMeta (tType ℓ') >>= λ A →
Structures\Auto.agda:200:  R.inferType hole >>= λ H →
Structures\Auto.agda:204:  R.checkType t (tStruct ℓ ℓ') >>
Structures\Auto.agda:208:  -- (Type ℓ → Type ℓ₁) → TranspDesc ℓ
Structures\Auto.agda:212:  -- (S : Type ℓ → Type ℓ₁) → EquivAction (AutoStructure S)
Structures\Auto.agda:219:  -- (S : Type ℓ → Type ℓ₁) → TransportStr (autoEquivAction S)
Structures\Auto.agda:226:  -- (S : Type ℓ → Type ℓ₁) → Desc ℓ
Structures\Auto.agda:230:  -- (S : Type ℓ → Type ℓ₁) → (Type ℓ → Type ℓ₁)
Structures\Auto.agda:238:  -- (S : Type ℓ → Type ℓ₁) → StrEquiv (AutoStructure S) _
Structures\Auto.agda:245:  -- (S : Type ℓ → Type ℓ₁) → UnivalentStr (AutoStructure S) (AutoEquivStr S)
Structures\Axioms.agda:24:AxiomsStructure : (S : Type ℓ → Type ℓ₁)
Structures\Axioms.agda:25:  (axioms : (X : Type ℓ) → S X → Type ℓ₂)
Structures\Axioms.agda:26:  → Type ℓ → Type (ℓ-max ℓ₁ ℓ₂)
Structures\Axioms.agda:29:AxiomsEquivStr : {S : Type ℓ → Type ℓ₁} (ι : StrEquiv S ℓ₁')
Structures\Axioms.agda:30:  (axioms : (X : Type ℓ) → S X → Type ℓ₂)
Structures\Axioms.agda:34:axiomsUnivalentStr : {S : Type ℓ → Type ℓ₁}
Structures\Axioms.agda:35:  (ι : (A B : TypeWithStr ℓ S) → A .fst ≃ B .fst → Type ℓ₁')
Structures\Axioms.agda:36:  {axioms : (X : Type ℓ) → S X → Type ℓ₂}
Structures\Axioms.agda:37:  (axioms-are-Props : (X : Type ℓ) (s : S X) → isProp (axioms X s))
Structures\Axioms.agda:50:inducedStructure : {S : Type ℓ → Type ℓ₁}
Structures\Axioms.agda:51:  {ι : (A B : TypeWithStr ℓ S) → A .fst ≃ B .fst → Type ℓ₁'}
Structures\Axioms.agda:53:  {axioms : (X : Type ℓ) → S X → Type ℓ₂}
Structures\Axioms.agda:54:  (A : TypeWithStr ℓ (AxiomsStructure S axioms)) (B : TypeWithStr ℓ S)
Structures\Axioms.agda:56:  → TypeWithStr ℓ (AxiomsStructure S axioms)
Structures\Axioms.agda:60:transferAxioms : {S : Type ℓ → Type ℓ₁}
Structures\Axioms.agda:61:  {ι : (A B : TypeWithStr ℓ S) → A .fst ≃ B .fst → Type ℓ₁'}
Structures\Axioms.agda:63:  {axioms : (X : Type ℓ) → S X → Type ℓ₂}
Structures\Axioms.agda:64:  (A : TypeWithStr ℓ (AxiomsStructure S axioms)) (B : TypeWithStr ℓ S)
Structures\Constant.agda:19:module _ (A : Type ℓ') where
Structures\Constant.agda:21:  ConstantStructure : Type ℓ → Type ℓ'
Structures\Function.agda:28:FunctionStructure : (S : Type ℓ → Type ℓ₁) (T : Type ℓ → Type ℓ₂)
Structures\Function.agda:29:  → Type ℓ → Type (ℓ-max ℓ₁ ℓ₂)
Structures\Function.agda:32:FunctionEquivStr : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Function.agda:38:functionUnivalentStr : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Function.agda:47:functionEquivAction : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Function.agda:52:functionTransportStr : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Function.agda:63:FunctionEquivStr+ : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Function.agda:69:functionUnivalentStr+ : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\LeftAction.agda:9:module _ {ℓ ℓ' : Level} (A : Type ℓ') where
Structures\LeftAction.agda:11:  LeftActionStructure : Type ℓ → Type (ℓ-max ℓ ℓ')
Structures\Macro.agda:28:data TranspDesc (ℓ : Level) : Level → Typeω where
Structures\Macro.agda:30:  constant : ∀ {ℓ₁} (A : Type ℓ₁) → TranspDesc ℓ ℓ₁
Structures\Macro.agda:40:  foreign : ∀ {ℓ₁} {S : Type ℓ → Type ℓ₁} (α : EquivAction S) → TransportStr α → TranspDesc ℓ ℓ₁
Structures\Macro.agda:43:TranspMacroStructure : ∀ {ℓ ℓ₁} → TranspDesc ℓ ℓ₁ → Type ℓ → Type ℓ₁
Structures\Macro.agda:80:  data Desc (ℓ : Level) : Level → Level → Typeω where
Structures\Macro.agda:82:    constant : ∀ {ℓ₁} (A : Type ℓ₁) → Desc ℓ ℓ₁ ℓ₁
Structures\Macro.agda:96:    axioms : ∀ {ℓ₁ ℓ₁' ℓ₂} (d : Desc ℓ ℓ₁ ℓ₁') (ax : ∀ X → MacroStructure d X → Type ℓ₂)
Structures\Macro.agda:102:    foreign : ∀ {ℓ₁ ℓ₁'} {S : Type ℓ → Type ℓ₁} (ι : StrEquiv S ℓ₁') → UnivalentStr S ι → Desc ℓ ℓ₁ ℓ₁'
Structures\Macro.agda:107:  MacroStructure : ∀ {ℓ ℓ₁ ℓ₁'} → Desc ℓ ℓ₁ ℓ₁' → Type ℓ → Type ℓ₁
Structures\Maybe.agda:25:MaybeRel : {A B : Type ℓ} (R : A → B → Type ℓ₁) → Maybe A → Maybe B → Type ℓ₁
Structures\Maybe.agda:31:congMaybeRel : {A B : Type ℓ} {R : A → B → Type ℓ₁} {S : A → B → Type ℓ₁'}
Structures\Maybe.agda:41:  Code : (A : I → Type ℓ) → Maybe (A i0) → Maybe (A i1) → Type ℓ
Structures\Maybe.agda:44:  encodeRefl : {A : Type ℓ} → ∀ ox → Code (λ _ → A) ox ox
Structures\Maybe.agda:48:  encode : (A : I → Type ℓ) → ∀ ox oy → PathP (λ i → Maybe (A i)) ox oy → Code A ox oy
Structures\Maybe.agda:51:  decode : {A : I → Type ℓ} → ∀ ox oy → Code A ox oy → PathP (λ i → Maybe (A i)) ox oy
Structures\Maybe.agda:55:  decodeEncodeRefl : {A : Type ℓ} (ox : Maybe A) → decode ox ox (encodeRefl ox) ≡ refl
Structures\Maybe.agda:59:  decodeEncode : {A : I → Type ℓ} → ∀ ox oy p → decode ox oy (encode A ox oy p) ≡ p
Structures\Maybe.agda:67:  encodeDecode : (A : I → Type ℓ) → ∀ ox oy c → encode A ox oy (decode ox oy c) ≡ c
Structures\Maybe.agda:76:  Code≃PathP : {A : I → Type ℓ} → ∀ ox oy → Code A ox oy ≃ PathP (λ i → Maybe (A i)) ox oy
Structures\Maybe.agda:87:MaybeStructure : (S : Type ℓ → Type ℓ₁) → Type ℓ → Type ℓ₁
Structures\Maybe.agda:90:MaybeEquivStr : {S : Type ℓ → Type ℓ₁}
Structures\Maybe.agda:94:maybeUnivalentStr : {S : Type ℓ → Type ℓ₁} (ι : StrEquiv S ℓ₁')
Structures\Maybe.agda:101:maybeEquivAction : {S : Type ℓ → Type ℓ₁}
Structures\Maybe.agda:105:maybeTransportStr : {S : Type ℓ → Type ℓ₁} (α : EquivAction S)
Structures\MultiSet.agda:20:module _ (A : Type ℓ) (Aset : isSet A) where
Structures\MultiSet.agda:22: CountStructure : Type ℓ → Type ℓ
Structures\MultiSet.agda:30: Count : Type (ℓ-suc ℓ)
Structures\MultiSet.agda:31: Count = TypeWithStr ℓ CountStructure
Structures\MultiSet.agda:33: MultiSetStructure : Type ℓ → Type ℓ
Structures\MultiSet.agda:41: MultiSet : Type (ℓ-suc ℓ)
Structures\MultiSet.agda:42: MultiSet = TypeWithStr ℓ MultiSetStructure
Structures\Parameterized.agda:21:module _ {ℓ₀} (A : Type ℓ₀) where
Structures\Parameterized.agda:23:  ParamStructure : (S : A → Type ℓ → Type ℓ₁)
Structures\Parameterized.agda:24:    → Type ℓ → Type (ℓ-max ℓ₀ ℓ₁)
Structures\Parameterized.agda:27:  ParamEquivStr : {S : A → Type ℓ → Type ℓ₁}
Structures\Parameterized.agda:31:  paramUnivalentStr : {S : A → Type ℓ → Type ℓ₁}
Structures\Parameterized.agda:36:  paramEquivAction : {S : A → Type ℓ → Type ℓ₁}
Structures\Parameterized.agda:40:  paramTransportStr : {S : A → Type ℓ → Type ℓ₁}
Structures\Pointed.agda:22:PointedStructure : Type ℓ → Type ℓ
Structures\Pointed.agda:43:  type checking speed problems, for example in
Structures\Product.agda:21:ProductStructure : (S₁ : Type ℓ → Type ℓ₁) (S₂ : Type ℓ → Type ℓ₂)
Structures\Product.agda:22:  → Type ℓ → Type (ℓ-max ℓ₁ ℓ₂)
Structures\Product.agda:26:  {S₁ : Type ℓ → Type ℓ₁} (ι₁ : StrEquiv S₁ ℓ₁')
Structures\Product.agda:27:  {S₂ : Type ℓ → Type ℓ₂} (ι₂ : StrEquiv S₂ ℓ₂')
Structures\Product.agda:33:  {S₁ : Type ℓ → Type ℓ₁} (ι₁ : StrEquiv S₁ ℓ₁') (θ₁ : UnivalentStr S₁ ι₁)
Structures\Product.agda:34:  {S₂ : Type ℓ → Type ℓ₂} (ι₂ : StrEquiv S₂ ℓ₂') (θ₂ : UnivalentStr S₂ ι₂)
Structures\Product.agda:40:  {S₁ : Type ℓ → Type ℓ₁} (α₁ : EquivAction S₁)
Structures\Product.agda:41:  {S₂ : Type ℓ → Type ℓ₂} (α₂ : EquivAction S₂)
Structures\Product.agda:46:  {S₁ : Type ℓ → Type ℓ₁} (α₁ : EquivAction S₁) (τ₁ : TransportStr α₁)
Structures\Product.agda:47:  {S₂ : Type ℓ → Type ℓ₂} (α₂ : EquivAction S₂) (τ₂ : TransportStr α₂)
Structures\Queue.agda:29:-- We start fixing a set A on which we define what it means for a type Q to have
Structures\Queue.agda:31:module Queues-on (A : Type ℓ) (Aset : isSet A) where
Structures\Queue.agda:37: deqMap : {X Y : Type ℓ} → (X → Y) → Maybe (X × A) → Maybe (Y × A)
Structures\Queue.agda:40: deqMapId : {X : Type ℓ} → ∀ r → deqMap (idfun X) r ≡ r
Structures\Queue.agda:43: deqMap-∘ :{B C D : Type ℓ}
Structures\Queue.agda:51:   autoDesc (λ (X : Type ℓ) → X × (A → X → X) × (X → Transp[ Maybe (X × A) ]))
Structures\Queue.agda:59: RawQueue : Type (ℓ-suc ℓ)
Structures\Queue.agda:60: RawQueue = TypeWithStr ℓ RawQueueStructure
Structures\Queue.agda:62: returnOrEnq : {Q : Type ℓ}
Structures\Queue.agda:67: QueueAxioms : (Q : Type ℓ) → RawQueueStructure Q → Type ℓ
Structures\Queue.agda:86: QueueStructure : Type ℓ → Type ℓ
Structures\Queue.agda:89: Queue : Type (ℓ-suc ℓ)
Structures\Queue.agda:90: Queue = TypeWithStr ℓ QueueStructure
Structures\Queue.agda:99: FiniteQueueAxioms : (Q : Type ℓ) → QueueStructure Q → Type ℓ
Structures\Queue.agda:105: FiniteQueueStructure : Type ℓ → Type ℓ
Structures\Queue.agda:108: FiniteQueue : Type (ℓ-suc ℓ)
Structures\Queue.agda:109: FiniteQueue = TypeWithStr ℓ FiniteQueueStructure
Structures\Record.agda:33:-- Types for specifying inputs to the tactics
Structures\Record.agda:35:data AutoFieldSpec : Typeω where
Structures\Record.agda:36:  autoFieldSpec : ∀ {ℓ ℓ₁ ℓ₂} (R : Type ℓ → Type ℓ₁) {S : Type ℓ → Type ℓ₂}
Structures\Record.agda:37:    → ({X : Type ℓ} → R X → S X)
Structures\Record.agda:42:    data AutoFields (R : Type ℓ → Type ℓ₁) (ι : StrEquiv R ℓ₁') : Typeω
Structures\Record.agda:46:        → ∀ {ℓ₂ ℓ₂'} {S : Type ℓ → Type ℓ₂} {ι' : StrEquiv S ℓ₂'}
Structures\Record.agda:47:        → (f : {X : Type ℓ} → R X → S X)
Structures\Record.agda:48:        → ({A B : TypeWithStr ℓ R} {e : typ A ≃ typ B} → ι A B e → ι' (map-snd f A) (map-snd f B) e)
Structures\Record.agda:51:        → ∀ {ℓ₂} {P : (X : Type ℓ) → GatherFields fs X → Type ℓ₂}
Structures\Record.agda:52:        → ({X : Type ℓ} (r : R X) → P X (projectFields fs r))
Structures\Record.agda:56:    GatherFieldsLevel : {R : Type ℓ → Type ℓ₁} {ι : StrEquiv R ℓ₁'}
Structures\Record.agda:63:    GatherFields : {R : Type ℓ → Type ℓ₁} {ι : StrEquiv R ℓ₁'}
Structures\Record.agda:65:      → Type ℓ → Type (GatherFieldsLevel dat)
Structures\Record.agda:71:    projectFields : {R : Type ℓ → Type ℓ₁} {ι : StrEquiv R ℓ₁'}
Structures\Record.agda:73:      → {X : Type ℓ} → R X → GatherFields fs X
Structures\Record.agda:78:    isPropProperty : ∀ {ℓ₂} (R : Type ℓ → Type ℓ₁)
Structures\Record.agda:81:      (P : (X : Type ℓ) → GatherFields fs X → Type ℓ₂)
Structures\Record.agda:82:      → Type (ℓ-max (ℓ-suc ℓ) (ℓ-max ℓ₁ ℓ₂))
Structures\Record.agda:84:      {X : Type ℓ} (r  : R X) → isProp (P X (projectFields fs r))
Structures\Record.agda:86:  data AutoRecordSpec : Typeω where
Structures\Record.agda:87:    autoRecordSpec : (R : Type ℓ → Type ℓ₁) (ι : StrEquiv R ℓ₁')
Structures\Record.agda:102:  Fun : ∀ {ℓ ℓ'} → Type ℓ → Type ℓ' → Type (ℓ-max ℓ ℓ')
Structures\Record.agda:107:  pathMap : ∀ {ℓ ℓ'} {S : I → Type ℓ} {T : I → Type ℓ'} (f : {i : I} → S i → T i)
Structures\Record.agda:114:    (R : Type ℓ → Type ℓ₁) -- Structure record
Structures\Record.agda:117:    (P : (X : Type ℓ) → GatherFields fs X → Type ℓ₂) -- Property type
Structures\Record.agda:118:    (f : {X : Type ℓ} (r : R X) → P X (projectFields fs r)) -- Property projection
Structures\Record.agda:124:    PropHelperCenterType : Type _
Structures\Record.agda:125:    PropHelperCenterType =
Structures\Record.agda:126:      (A B : TypeWithStr ℓ R) (e : A .fst ≃ B .fst)
Structures\Record.agda:130:    PropHelperContractType : PropHelperCenterType → Type _
Structures\Record.agda:131:    PropHelperContractType c =
Structures\Record.agda:132:      (A B : TypeWithStr ℓ R) (e : A .fst ≃ B .fst)
Structures\Record.agda:140:    PropHelperType : Type _
Structures\Record.agda:141:    PropHelperType =
Structures\Record.agda:142:      Σ PropHelperCenterType PropHelperContractType
Structures\Record.agda:144:    derivePropHelper : isPropProperty R ι fs P → PropHelperType
Structures\Record.agda:151:  module _ {ℓ ℓ₁ ℓ₁'} (S : Type ℓ → Type ℓ₁) (ι : StrEquiv S ℓ₁') where
Structures\Record.agda:153:    fwdShape : Type _
Structures\Record.agda:155:      (A B : TypeWithStr ℓ S) (e : typ A ≃ typ B) → ι A B e → PathP (λ i → S (ua e i)) (str A) (str B)
Structures\Record.agda:157:    bwdShape : Type _
Structures\Record.agda:159:      (A B : TypeWithStr ℓ S) (e : typ A ≃ typ B) → PathP (λ i → S (ua e i)) (str A) (str B) → ι A B e
Structures\Record.agda:161:    fwdBwdShape : fwdShape → bwdShape → Type _
Structures\Record.agda:163:      (A B : TypeWithStr ℓ S) (e : typ A ≃ typ B) → ∀ p → fwd A B e (bwd A B e p) ≡ p
Structures\Record.agda:165:    bwdFwdShape : fwdShape → bwdShape → Type _
Structures\Record.agda:167:      (A B : TypeWithStr ℓ S) (e : typ A ≃ typ B) → ∀ r → bwd A B e (fwd A B e r) ≡ r
Structures\Record.agda:170:    ExplicitUnivalentStr : Type _
Structures\Record.agda:172:      (A B : TypeWithStr _ S) (e : typ A ≃ typ B) → ι A B e ≃ PathP (λ i → S (ua e i)) (str A) (str B)
Structures\Record.agda:186:  ExplicitUnivalentDesc : ∀ ℓ {ℓ₁ ℓ₁'} → (d : M.Desc ℓ ℓ₁ ℓ₁') → Type _
Structures\Record.agda:193:-- Internal record specification type
Structures\Record.agda:195:  record TypedTerm : Type where
Structures\Record.agda:197:      type : R.Term
Structures\Record.agda:200:  record InternalDatumField : Type where
Structures\Record.agda:205:  record InternalPropField : Type where
Structures\Record.agda:209:  InternalField : Type
Structures\Record.agda:212:  record InternalSpec (A : Type) : Type where
Structures\Record.agda:214:      srec : R.Term -- structure record type
Structures\Record.agda:215:      erec : R.Term -- equivalence record type
Structures\Record.agda:218:  open TypedTerm
Structures\Record.agda:227:  findName t = R.typeError (R.strErr "Not a name + spine: " ∷ R.termErr t ∷ [])
Structures\Record.agda:234:    R.typeError (R.strErr "Malformed field specification: " ∷ R.termErr t ∷ [])
Structures\Record.agda:236:  parseSpec : R.Term → R.TC (InternalSpec TypedTerm)
Structures\Record.agda:243:    parseFields : R.Term → R.TC (List (InternalField × TypedTerm))
Structures\Record.agda:253:        f : InternalField × TypedTerm
Structures\Record.agda:256:          ; .snd .type → R.def (quote ExplicitUnivalentDesc) (ℓ v∷ d v∷ [])
Structures\Record.agda:266:        p : InternalField × TypedTerm
Structures\Record.agda:269:          ; .snd .type →
Structures\Record.agda:270:            R.def (quote PropHelperType) (srecTerm v∷ erecTerm v∷ fs v∷ P v∷ fieldTerm v∷ [])
Structures\Record.agda:277:    parseFields t = R.typeError (R.strErr "Malformed autoRecord specification (1): " ∷ R.termErr t ∷ [])
Structures\Record.agda:279:  parseSpec t = R.typeError (R.strErr "Malformed autoRecord specification (2): " ∷ R.termErr t ∷ [])
Structures\Record.agda:423:    -- R.typeError (R.strErr "WOW: " ∷ R.termErr (main spec) ∷ [])
Structures\Record.agda:426:    module _ (spec : InternalSpec TypedTerm) where
Structures\Record.agda:429:      mapUp : ∀ {ℓ ℓ'} {A : Type ℓ} {B : Type ℓ'} → (ℕ → A → B) → ℕ → List A → List B
Structures\Record.agda:450:          (List.map (type ∘ snd) (List.rev fields))
Structures\Successor.agda:15:record SuccStr (ℓ : Level) : Type (ℓ-suc ℓ) where
Structures\Successor.agda:17:    Index : Type ℓ
Structures\Transfer.agda:18:transfer : {ℓ₂' ℓ₀ : Level} {S : Type ℓ → Type ℓ₁} {H : Type ℓ → Type ℓ₂}
Structures\Transfer.agda:19:  (P : ∀ X → S X → H X → Type ℓ₀)
Structures\Transfer.agda:22:  {X Y : Type ℓ} {s : S X} {t : S Y}
Structures\Transfer.agda:33:transfer⁻ : {ℓ₂' ℓ₀ : Level} {S : Type ℓ → Type ℓ₁} {H : Type ℓ → Type ℓ₂}
Structures\Transfer.agda:34:  (P : ∀ X → S X → H X → Type ℓ₀)
Structures\Transfer.agda:37:  {X Y : Type ℓ} {s : S X} {t : S Y}
Structures\TypeEqvTo.agda:1:module Cubical.Structures.TypeEqvTo where
Structures\TypeEqvTo.agda:18:TypeEqvTo : (ℓ : Level) (X : Type ℓ') → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Structures\TypeEqvTo.agda:19:TypeEqvTo ℓ X = TypeWithStr ℓ (λ Y → ∥ Y ≃ X ∥₁)
Structures\TypeEqvTo.agda:21:PointedEqvTo : (ℓ : Level) (X : Type ℓ') → Type (ℓ-max (ℓ-suc ℓ) ℓ')
Structures\TypeEqvTo.agda:22:PointedEqvTo ℓ X = TypeWithStr ℓ (λ Y → Y × ∥ Y ≃ X ∥₁)
Structures\TypeEqvTo.agda:24:module _ (X : Type ℓ') where
Structures\TypeEqvTo.agda:26:  PointedEqvToStructure : Type ℓ → Type (ℓ-max ℓ ℓ')
Structures\Relational\Auto.agda:7:  autoDesc (λ (X : Type₀) → X → X × ℕ)   ↦   function+ var (var , constant ℕ)
Structures\Relational\Auto.agda:9:We prefer to use the constant structure whenever possible, e.g., [autoDesc (λ (X : Type₀) → ℕ → ℕ)]
Structures\Relational\Auto.agda:12:Writing [auto* (λ X → ⋯)] doesn't seem to work, but [auto* (λ (X : Type ℓ) → ⋯)] does.
Structures\Relational\Auto.agda:35:-- Mark a constant type with a proof it is a set
Structures\Relational\Auto.agda:37:  Const[_] : ∀ {ℓ} → hSet ℓ → Type ℓ
Structures\Relational\Auto.agda:44:  tType : R.Term → R.Term
Structures\Relational\Auto.agda:45:  tType ℓ = R.def (quote Type) [ varg ℓ ]
Structures\Relational\Auto.agda:56:  func : (ℓ ℓ' : Level) → Type (ℓ-suc (ℓ-max ℓ ℓ'))
Structures\Relational\Auto.agda:57:  func ℓ ℓ' = Type ℓ → Type ℓ'
Structures\Relational\Auto.agda:67:  constantShape : ∀ {ℓ'} (ℓ : Level) (A : hSet ℓ') → (Type ℓ → Type ℓ')
Structures\Relational\Auto.agda:70:  pointedShape : (ℓ : Level) → Type ℓ → Type ℓ
Structures\Relational\Auto.agda:74:    → (Type ℓ → Type ℓ₀) → (Type ℓ → Type ℓ₁) → Type ℓ → Type (ℓ-max ℓ₀ ℓ₁)
Structures\Relational\Auto.agda:78:    → Type ℓ' → (Type ℓ → Type ℓ₀) → Type ℓ → Type (ℓ-max ℓ' ℓ₀)
Structures\Relational\Auto.agda:82:    → (Type ℓ → Type ℓ₀) → (Type ℓ → Type ℓ₁) → Type ℓ → Type (ℓ-max ℓ₀ ℓ₁)
Structures\Relational\Auto.agda:86:    → (Type ℓ → Type ℓ₀) → Type ℓ → Type ℓ₀
Structures\Relational\Auto.agda:90:  -- Build transport structure descriptor from a function [t : Type ℓ → Type ℓ']
Structures\Relational\Auto.agda:92:  buildPosRelDesc zero ℓ ℓ' t = R.typeError (R.strErr "Ran out of fuel! at \n" ∷ R.termErr t ∷ [])
Structures\Relational\Auto.agda:95:    R.typeError (R.strErr "Can't automatically generate a positive structure for\n" ∷ R.termErr t ∷
[])
Structures\Relational\Auto.agda:129:    R.inferType hole >>= λ H →
Structures\Relational\Auto.agda:133:    R.checkType t (tStruct ℓ ℓ') >>
Structures\Relational\Auto.agda:136:  -- Build structure descriptor from a function [t : Type ℓ → Type ℓ']
Structures\Relational\Auto.agda:138:  buildRelDesc zero ℓ ℓ' t = R.typeError (R.strErr "Ran out of fuel! at \n" ∷ R.termErr t ∷ [])
Structures\Relational\Auto.agda:142:    R.typeError (R.strErr "Can't automatically generate a structure for\n" ∷ R.termErr t ∷ [])
Structures\Relational\Auto.agda:168:      newMeta (tType R.unknown) >>= λ A →
Structures\Relational\Auto.agda:196:    R.inferType hole >>= λ H →
Structures\Relational\Auto.agda:200:    R.checkType t (tStruct ℓ ℓ') >>
Structures\Relational\Auto.agda:204:  -- (Type ℓ → Type ℓ₁) → PosRelDesc ℓ
Structures\Relational\Auto.agda:208:  -- (S : Type ℓ → Type ℓ₁) → RelDesc ℓ
Structures\Relational\Auto.agda:212:  -- (S : Type ℓ → Type ℓ₁) → (Type ℓ → Type ℓ₁)
Structures\Relational\Auto.agda:220:  -- (S : Type ℓ → Type ℓ₁) → StrRel S _
Structures\Relational\Auto.agda:227:  -- (S : Type ℓ → Type ℓ₁) → SuitableStrRel S (AutoStrRel S)
Structures\Relational\Auto.agda:234:  -- (S : Type ℓ → Type ℓ₁) → StrRelMatchesEquiv (AutoRelStr S) (AutoEquivStr S)
Structures\Relational\Equalizer.agda:20:EqualizerStructure : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Equalizer.agda:22:  → Type ℓ → Type (ℓ-max ℓ₁ ℓ₂)
Structures\Relational\Equalizer.agda:25:EqualizerRelStr : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Equalizer.agda:30:equalizerSuitableRel : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Equalizer.agda:33:  (αf : ∀ {X Y} {R : X → Y → Type ℓ} {s s'} → ρ₁ R s s' → ρ₂ R (f X s) (f Y s'))
Structures\Relational\Equalizer.agda:34:  (αg : ∀ {X Y} {R : X → Y → Type ℓ} {s s'} → ρ₁ R s s' → ρ₂ R (g X s) (g Y s'))
Structures\Relational\Function.agda:29:FunctionRelStr : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Function.agda:38:  composeWith[_] : {A : Type ℓ} (R : EquivPropRel A ℓ)
Structures\Relational\Function.agda:46:  [_]∙[_]⁻¹ : {A : Type ℓ} (R : EquivPropRel A ℓ)
Structures\Relational\Function.agda:56:functionSuitableRel : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Function.agda:157:functionRelMatchesEquiv : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Function.agda:166:functionRelMatchesEquiv+ : {S : Type ℓ → Type ℓ₁} {T : Type ℓ → Type ℓ₂}
Structures\Relational\Macro.agda:26:data PosRelDesc (ℓ : Level) : Level → Typeω where
Structures\Relational\Macro.agda:36:data RelDesc (ℓ : Level) : Level → Level → Typeω where
Structures\Relational\Macro.agda:44:  param : ∀ {ℓ₁ ℓ₂ ℓ₂'} → (A : Type ℓ₁) → RelDesc ℓ ℓ₂ ℓ₂' → RelDesc ℓ (ℓ-max ℓ₁ ℓ₂) (ℓ-max ℓ₁ ℓ₂')
Structures\Relational\Macro.agda:74:PosRelMacroStructure : ∀ {ℓ ℓ₁} (d : PosRelDesc ℓ ℓ₁) → Type ℓ → Type ℓ₁
Structures\Relational\Macro.agda:77:RelMacroStructure : ∀ {ℓ ℓ₁ ℓ₁'} (d : RelDesc ℓ ℓ₁ ℓ₁') → Type ℓ → Type ℓ₁
Structures\Relational\Maybe.agda:31:MaybeRelStr : {S : Type ℓ → Type ℓ₁} {ℓ₁' : Level}
Structures\Relational\Maybe.agda:35:maybeSuitableRel : {S : Type ℓ → Type ℓ₁} {ρ : StrRel S ℓ₁'}
Structures\Relational\Maybe.agda:54:maybeRelMatchesEquiv : {S : Type ℓ → Type ℓ₁} (ρ : StrRel S ℓ₁') {ι : StrEquiv S ℓ₁''}
Structures\Relational\Maybe.agda:63:  {S : Type ℓ → Type ℓ₁} {ρ : StrRel S ℓ₁'}
Structures\Relational\Maybe.agda:73:  {S : Type ℓ → Type ℓ₁} {ρ : StrRel S ℓ₁'} {θ : SuitableStrRel S ρ}
Structures\Relational\Maybe.agda:116:maybeRelMatchesTransp : {S : Type ℓ → Type ℓ₁}
Structures\Relational\Parameterized.agda:27:module _ (A : Type ℓ₀) where
Structures\Relational\Parameterized.agda:29:  ParamRelStr : {S : A → Type ℓ → Type ℓ₁}
Structures\Relational\Parameterized.agda:35:  paramSuitableRel : {S : A → Type ℓ → Type ℓ₁} {ρ : ∀ a → StrRel (S a) ℓ₁'}
Structures\Relational\Parameterized.agda:55:  paramRelMatchesEquiv : {S : A → Type ℓ → Type ℓ₁}
Structures\Relational\Parameterized.agda:61:  paramRelAction : {S : A → Type ℓ → Type ℓ₁} {ρ : ∀ a → StrRel (S a) ℓ₁'}
Structures\Relational\Product.agda:30:  {S₁ : Type ℓ → Type ℓ₁} (ρ₁ : StrRel S₁ ℓ₁')
Structures\Relational\Product.agda:31:  {S₂ : Type ℓ → Type ℓ₂} (ρ₂ : StrRel S₂ ℓ₂')
Structures\Relational\Product.agda:37:  {S₁ : Type ℓ → Type ℓ₁} {ρ₁ : StrRel S₁ ℓ₁'}
Structures\Relational\Product.agda:38:  {S₂ : Type ℓ → Type ℓ₂} {ρ₂ : StrRel S₂ ℓ₂'}
Structures\Relational\Product.agda:59:  {S₁ : Type ℓ → Type ℓ₁} (ρ₁ : StrRel S₁ ℓ₁') {ι₁ : StrEquiv S₁ ℓ₁''}
Structures\Relational\Product.agda:60:  {S₂ : Type ℓ → Type ℓ₂} (ρ₂ : StrRel S₂ ℓ₂') {ι₂ : StrEquiv S₂ ℓ₂''}
Structures\Relational\Product.agda:67:  {S₁ : Type ℓ → Type ℓ₁} {ρ₁ : StrRel S₁ ℓ₁'} (α₁ : StrRelAction ρ₁)
Structures\Relational\Product.agda:68:  {S₂ : Type ℓ → Type ℓ₂} {ρ₂ : StrRel S₂ ℓ₂'} (α₂ : StrRelAction ρ₂)
Structures\Relational\Product.agda:75:  {S₁ : Type ℓ → Type ℓ₁} {ρ₁ : StrRel S₁ ℓ₁'} {θ₁ : SuitableStrRel S₁ ρ₁}
Structures\Relational\Product.agda:76:  {S₂ : Type ℓ → Type ℓ₂} {ρ₂ : StrRel S₂ ℓ₂'} {θ₂ : SuitableStrRel S₂ ρ₂}
Structures\Relational\Product.agda:133:  {S₁ : Type ℓ → Type ℓ₁} (ρ₁ : StrRel S₁ ℓ₁') (α₁ : EquivAction S₁)
Structures\Relational\Product.agda:134:  {S₂ : Type ℓ → Type ℓ₂} (ρ₂ : StrRel S₂ ℓ₂') (α₂ : EquivAction S₂)
Tactics\Reflection.agda:11:open import Agda.Builtin.Reflection hiding (Type)
Tactics\Reflection.agda:25:_<$>_ : ∀ {ℓ ℓ'} {A : Type ℓ}{B : Type ℓ'} → (A → B) → TC A → TC B
Tactics\Reflection.agda:28:_<*>_ : ∀ {ℓ ℓ'} {A : Type ℓ}{B : Type ℓ'} → TC (A → B) → TC A → TC B
Tactics\Reflection.agda:32:wait-for-type : Term → TC Term
Tactics\Reflection.agda:34:wait-for-type (var x args) = var x <$> wait-for-args args
Tactics\Reflection.agda:35:wait-for-type (con c args) = con c <$> wait-for-args args
Tactics\Reflection.agda:36:wait-for-type (def f args) = def f <$> wait-for-args args
Tactics\Reflection.agda:37:wait-for-type (lam v (abs x t)) = returnTC (lam v (abs x t))
Tactics\Reflection.agda:38:wait-for-type (pat-lam cs args) = returnTC (pat-lam cs args)
Tactics\Reflection.agda:39:wait-for-type (pi (arg i a) (abs x b)) = do
Tactics\Reflection.agda:40:  a ← wait-for-type a
Tactics\Reflection.agda:41:  b ← wait-for-type b
Tactics\Reflection.agda:43:wait-for-type (agda-sort s) = returnTC (agda-sort s)
Tactics\Reflection.agda:44:wait-for-type (lit l) = returnTC (lit l)
Tactics\Reflection.agda:45:wait-for-type (meta x x₁) = blockOnMeta x
Tactics\Reflection.agda:46:wait-for-type unknown = returnTC unknown
Tactics\Reflection.agda:50:  (_∷_ <$> (arg i <$> wait-for-type a)) <*> wait-for-args xs
Tactics\Reflection.agda:54:  domain ← newMeta (def (quote Type) (l v∷ []))
Tactics\Reflection.agda:63:    dom ← newMeta (def (quote Type) [])
Tactics\Reflection.agda:66:    unify tm (def (quote Type) (dom v∷ l v∷ r v∷ []))
Tactics\Reflection.agda:67:    wait-for-type l
Tactics\Reflection.agda:68:    wait-for-type r
Tactics\Reflection.agda:71:    domain ← newMeta (def (quote Type) (l v∷ []))
Tactics\Reflection.agda:94:      goal ← inferType hole >>= reduce
Tactics\Reflection.agda:99:            → typeError(strErr "The functor solver failed to parse the goal"
Tactics\Reflection.agda:112:        typeError ((strErr "Could not equate the following expressions:\n  "
Tactics\CategorySolver\Reflection.agda:6:open import Agda.Builtin.Reflection hiding (Type)
Tactics\CommRingSolver\AlgebraExpression.agda:21:data Expr {ℓ} (R : RawRing ℓ) (A : Type ℓ') (n : ℕ) : Type ℓ where
Tactics\CommRingSolver\Examples.agda:25:    The following should give an type checking error,
Tactics\CommRingSolver\Examples.agda:26:    making the user aware that the problem is, that 'Type₀'
Tactics\CommRingSolver\Examples.agda:31:  _ = solve Type₀
Tactics\CommRingSolver\HornerForms.agda:25:  This defines the type of multivariate Polynomials over the RawRing R.
Tactics\CommRingSolver\HornerForms.agda:42:data IteratedHornerForms (A : RawAlgebra ℤAsRawRing ℓ) : ℕ → Type ℓ where
Tactics\CommRingSolver\RawAlgebra.agda:29:record RawAlgebra (R : RawRing ℓ) (ℓ' : Level) : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
Tactics\CommRingSolver\RawAlgebra.agda:34:    Carrier : Type ℓ'
Tactics\CommRingSolver\RawAlgebra.agda:46:⟨_⟩ : {R : RawRing ℓ} → RawAlgebra R ℓ' → Type ℓ'
Tactics\CommRingSolver\RawRing.agda:9:record RawRing ℓ : Type (ℓ-suc ℓ) where
Tactics\CommRingSolver\RawRing.agda:14:    Carrier : Type ℓ
Tactics\CommRingSolver\RawRing.agda:25:⟨_⟩ : RawRing ℓ → Type ℓ
Tactics\CommRingSolver\Reflection.agda:3:open import Cubical.Foundations.Prelude hiding (Type)
Tactics\CommRingSolver\Reflection.agda:5:open import Agda.Builtin.Reflection hiding (Type)
Tactics\CommRingSolver\Reflection.agda:39:  record RingNames : Type where
Tactics\CommRingSolver\Reflection.agda:186:  checkIsRing ring = checkType ring (def (quote CommRing) (unknown v∷ []))
Tactics\CommRingSolver\Reflection.agda:192:      goal ← inferType hole >>= normalise
Tactics\CommRingSolver\Reflection.agda:195:      wait-for-type goal
Tactics\CommRingSolver\Reflection.agda:199:            → typeError(strErr "The CommRingSolver failed to parse the goal "
Tactics\CommRingSolver\Solver.agda:30:  ℤExpr : (n : ℕ) → Type _
Tactics\CommRingSolver\Utility.agda:14:byBoolAbsurdity : {Anything : Type ℓ} → false ≡ true → Anything
Tactics\CommRingSolver\Utility.agda:17:byAbsurdity : {Anything : Type ℓ} → ⊥ → Anything
Tactics\FunctorSolver\Reflection.agda:6:open import Agda.Builtin.Reflection hiding (Type)
Tactics\MonoidSolver\CommSolver.agda:23:  Env : ℕ → Type ℓ
Tactics\MonoidSolver\CommSolver.agda:33:  NormalForm : ℕ → Type _
Tactics\MonoidSolver\MonoidExpression.agda:17:-- Expression in a type M with n variables
Tactics\MonoidSolver\MonoidExpression.agda:18:data Expr (M : Type ℓ) (n : ℕ) : Type ℓ where
Tactics\MonoidSolver\Reflection.agda:4:open import Cubical.Foundations.Prelude hiding (Type)
Tactics\MonoidSolver\Reflection.agda:6:open import Agda.Builtin.Reflection hiding (Type)
Tactics\MonoidSolver\Reflection.agda:34:  record VarInfo : Type ℓ-zero where
Tactics\MonoidSolver\Reflection.agda:37:      varType : Arg Term
Tactics\MonoidSolver\Reflection.agda:148:          extractVars (pi argType (abs varName t)) with extractVars t
Tactics\MonoidSolver\Reflection.agda:150:                                                        = (varName , argType) ∷ xs , equation
Tactics\MonoidSolver\Reflection.agda:155:          addIndices (ℕ.suc countVar) ((varName , argType) ∷ list) =
Tactics\MonoidSolver\Reflection.agda:156:            map-Maybe (λ varList → record { varName = varName ; varType = argType ; index =
countVar }
Tactics\MonoidSolver\Reflection.agda:172:      hole′ ← inferType hole >>= normalise
Tactics\MonoidSolver\Reflection.agda:176:            → typeError (strErr "Something went wrong when getting the variable names in "
Tactics\MonoidSolver\Reflection.agda:186:            → typeError(
Tactics\MonoidSolver\Solver.agda:24:  Env : ℕ → Type ℓ
Tactics\MonoidSolver\Solver.agda:33:  NormalForm : ℕ → Type _
Tactics\NatSolver\HornerForms.agda:15:  This defines the type of multivariate Polynomials over ℕ.
Tactics\NatSolver\HornerForms.agda:32:data IteratedHornerForms : ℕ → Type ℓ-zero where
Tactics\NatSolver\NatExpression.agda:14:data Expr (n : ℕ) : Type ℓ-zero where
Tactics\NatSolver\Reflection.agda:11:open import Cubical.Foundations.Prelude hiding (Type)
Tactics\NatSolver\Reflection.agda:14:open import Agda.Builtin.Reflection hiding (Type)
Tactics\NatSolver\Reflection.agda:130:      goal ← inferType hole >>= normalise
Tactics\NatSolver\Reflection.agda:132:      wait-for-type goal
Tactics\NatSolver\Reflection.agda:136:            → typeError(strErr "The NatSolver failed to parse the goal "
Tactics\Reflection\Utilities.agda:3:open import Cubical.Foundations.Prelude hiding (Type)
Tactics\Reflection\Utilities.agda:5:open import Agda.Builtin.Reflection hiding (Type)
Tactics\Reflection\Utilities.agda:27:errorOut something = typeError (strErr "Don't know what to do with " ∷ map (λ {(arg _ t) → termErr
t}) something)
Tactics\Reflection\Utilities.agda:30:errorOut' something = typeError (strErr "Don't know what to do with " ∷ termErr something ∷ [])
Tactics\Reflection\Variables.agda:11:open import Cubical.Foundations.Prelude hiding (Type)
Tactics\Reflection\Variables.agda:13:open import Agda.Builtin.Reflection hiding (Type)
WildCat\Base.agda:17:record WildCat ℓ ℓ' : Type (ℓ-suc (ℓ-max ℓ ℓ')) where
WildCat\Base.agda:20:    ob : Type ℓ
WildCat\Base.agda:21:    Hom[_,_] : ob → ob → Type ℓ'
WildCat\Base.agda:36:_[_,_] : (C : WildCat ℓ ℓ') → (x y : C .ob) → Type ℓ'
WildCat\Base.agda:53:-- Isomorphisms in wild categories (analogous to HoTT-terminology for maps between types)
WildCat\Base.agda:54:record WildCatIso (C : WildCat ℓ ℓ') (x y : C .ob) : Type ℓ' where
WildCat\Base.agda:72:  record wildIsIso : Type (ℓ-max ℓ ℓ') where
WildCat\BraidedSymmetricMonoidal.agda:26:  record isMonoidalWildCat : Type (ℓ-max ℓ ℓ') where
WildCat\BraidedSymmetricMonoidal.agda:63:    BraidingIsoType : Type _
WildCat\BraidedSymmetricMonoidal.agda:64:    BraidingIsoType = WildNatIso (M × M) M _⊗_ (comp-WildFunctor commFunctor _⊗_)
WildCat\BraidedSymmetricMonoidal.agda:66:    HexagonType₁ : (B : BraidingIsoType) → Type _
WildCat\BraidedSymmetricMonoidal.agda:67:    HexagonType₁ B = (x y z : M .ob) →
WildCat\BraidedSymmetricMonoidal.agda:75:    HexagonType₂ : (B : BraidingIsoType) → Type _
WildCat\BraidedSymmetricMonoidal.agda:76:    HexagonType₂ B = (x y z : M .ob) →
WildCat\BraidedSymmetricMonoidal.agda:84:    isSymmetricBraiding : (B : BraidingIsoType)
WildCat\BraidedSymmetricMonoidal.agda:85:      → Type _
WildCat\BraidedSymmetricMonoidal.agda:90:  record isBraidedWildCat : Type (ℓ-max ℓ ℓ') where
WildCat\BraidedSymmetricMonoidal.agda:94:      Braid : BraidingIsoType isMonoidal
WildCat\BraidedSymmetricMonoidal.agda:96:        → HexagonType₁ isMonoidal Braid
WildCat\BraidedSymmetricMonoidal.agda:97:        ×' HexagonType₂ isMonoidal Braid
WildCat\BraidedSymmetricMonoidal.agda:99:  record isSymmetricWildCat : Type (ℓ-max ℓ ℓ') where
WildCat\BraidedSymmetricMonoidal.agda:102:      Braid : BraidingIsoType isMonoidal
WildCat\BraidedSymmetricMonoidal.agda:103:      hexagon : HexagonType₁ isMonoidal Braid
WildCat\BraidedSymmetricMonoidal.agda:106:SymmetricMonoidalWildCat : (ℓ ℓ' : Level) → Type (ℓ-suc (ℓ-max ℓ ℓ'))
WildCat\Functor.agda:19:         Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
WildCat\Functor.agda:32:         Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
WildCat\Functor.agda:45:         Type (ℓ-max (ℓ-max ℓC ℓC') (ℓ-max ℓD ℓD')) where
WildCat\Monad.agda:15:  IsPointed : Type (ℓ-max ℓ ℓ')
WildCat\Monad.agda:18:  record IsMonad : Type (ℓ-max ℓ ℓ') where
WildCat\Monad.agda:29:WildMonad : WildCat ℓ ℓ' → Type (ℓ-max ℓ ℓ')
WildCat\UnderlyingGraph.agda:30:  Interpret : Type _
WildCat\Instances\Path.agda:14:PathCat : (A : Type ℓ) → WildCat ℓ ℓ
WildCat\Instances\Types.agda:1:module Cubical.WildCat.Instances.Types where
WildCat\Instances\Types.agda:11:TypeCat : (ℓ : Level) → WildCat (ℓ-suc ℓ) ℓ
WildCat\Instances\Types.agda:12:ob (TypeCat ℓ) = Type ℓ
WildCat\Instances\Types.agda:13:Hom[_,_] (TypeCat ℓ) A B = A → B
WildCat\Instances\Types.agda:14:WildCat.id (TypeCat ℓ) = idfun _
WildCat\Instances\Types.agda:15:_⋆_ (TypeCat ℓ) f g = g ∘fun f
WildCat\Instances\Types.agda:16:⋆IdL (TypeCat ℓ) = λ _ → refl
WildCat\Instances\Types.agda:17:⋆IdR (TypeCat ℓ) = λ _ → refl
WildCat\Instances\Types.agda:18:⋆Assoc (TypeCat ℓ) f g h = refl




