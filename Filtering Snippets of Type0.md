




Codata\M\itree.agda:34:tree-S E R = (R ⊎ (Σ[ A ∈ Type₀ ] (E A))) , (λ { (inl _) -> ⊥* ; (inr (A , e))
-> Lift _ A } )
Codata\M\itree.agda:36:tree : (E : Type₀ -> Type₁) (R : Type₀) -> Type₁
Codata\M\itree.agda:50:itree-S : ∀ (E : Type₀ -> Type₁) (R : Type₀) -> Container (ℓ-suc ℓ-zero)
Codata\M\itree.agda:51:itree-S E R = ((Unit ⊎ R) ⊎ (Σ[ A ∈ Type₀ ] (E A))) , (λ { (inl (inl _)) ->
Unit* ; (inl (inr _)) -> ⊥* ; (inr (A , e)) -> Lift _ A } )
Codata\M\itree.agda:53:itree :  ∀ (E : Type₀ -> Type₁) (R : Type₀) -> Type₁
Codata\M\itree.agda:59:tau' : {E : Type₀ -> Type₁} -> {R : Type₀} -> itree E R -> P₀ (itree-S E R)
(itree E R)
Codata\M\itree.agda:62:vis' : ∀ {E} {R}  -> ∀ {A : Type₀} -> E A -> (A -> itree E R) -> P₀ (itree-S E
R) (itree E R)
Codata\M\itree.agda:68:tau : {E : Type₀ -> Type₁} -> {R : Type₀} -> itree E R -> itree E R
Codata\M\itree.agda:71:vis : ∀ {E} {R}  -> ∀ {A : Type₀} -> E A -> (A -> itree E R) -> itree E R
Codata\M\stream.agda:20:stream : ∀ (A : Type₀) -> Type₀
Codata\Stream\Base.agda:6:record Stream (A : Type₀) : Type₀ where
Codata\Stream\Properties.agda:40:elimS : ∀ {A} (P : Stream A → Type₀) (c : ∀ x xs → P (x , xs)) (xs :
Stream A) → P xs
Codata\Stream\Properties.agda:56:  record _≈_ {A : Type₀} (x y : Stream A) : Type₀ where
Codata\Stream\Properties.agda:64:  bisim : {A : Type₀} → {x y : Stream A} → x ≈ y → x ≡ y
Codata\Stream\Properties.agda:68:  misib : {A : Type₀} → {x y : Stream A} → x ≡ y → x ≈ y
Codata\Stream\Properties.agda:72:  iso1 : {A : Type₀} → {x y : Stream A} → (p : x ≡ y) → bisim (misib
p) ≡ p
Codata\Stream\Properties.agda:76:  iso2 : {A : Type₀} → {x y : Stream A} → (p : x ≈ y) → misib (bisim
p) ≡ p
Codata\Stream\Properties.agda:80:  path≃bisim : {A : Type₀} → {x y : Stream A} → (x ≡ y) ≃ (x ≈ y)
Codata\Stream\Properties.agda:83:  path≡bisim : {A : Type₀} → {x y : Stream A} → (x ≡ y) ≡ (x ≈ y)
Codata\Stream\Properties.agda:87:  refl≈ : {A : Type₀} {x : Stream A} → x ≈ x
Codata\Stream\Properties.agda:91:  cast : ∀ {A : Type₀} {x y : Stream A} (p : x ≡ y) → x ≈ y
Codata\Stream\Properties.agda:94:  misib-refl : ∀ {A : Type₀} {x : Stream A} → misib {x = x} refl ≡
refl≈
Codata\Stream\Properties.agda:98:  misibTransp : ∀ {A : Type₀} {x y : Stream A} (p : x ≡ y) → cast p
≡ misib p
Codata\Stream\Properties.agda:101:module Stream≅Nat→ {A : Type₀} where
Core\Primitives.agda:96:  sys i (i = i0) = Type₀
Core\Primitives.agda:97:  sys i (i = i1) = Type₀ → Type₀
Core\Primitives.agda:102:  sys' i = λ { (i = i0) → Type₀
Core\Primitives.agda:103:             ; (i = i1) → Type₀ → Type₀
Core\Primitives.agda:108:  sys2 i j = λ { (i = i1)          → Type₀
Core\Primitives.agda:109:               ; (i = i1) (j = i1) → Type₀
Data\BinNat\BinNat.agda:75:data Binℕ : Type₀
Data\BinNat\BinNat.agda:76:data Pos : Type₀
Data\BinNat\BinNat.agda:115:posInd : {P : Pos → Type₀} → P pos1 → ((p : Pos) → P p → P (sucPos p)) →
(p : Pos) → P p
Data\BinNat\BinNat.agda:273:record NatImpl (A : Type₀) : Type₀ where
Data\BinNat\BinNat.agda:405:data binnat : Type₀ where
Data\Bool\Base.agda:55:Bool→Type : Bool → Type₀
Data\Bool\Base.agda:63:True : Dec A → Type₀
Data\Bool\Base.agda:66:False : Dec A → Type₀
Data\Bool\Properties.agda:196:  data Table (A : Type₀) (P : Bool ≡ A) : Type₀ where
Data\DescendingList\Base.agda:10: (A : Type₀)
Data\DescendingList\Base.agda:11: (_≥_ : A → A → Type₀)
Data\DescendingList\Base.agda:19:data DL : Type₀
Data\DescendingList\Base.agda:20:data _≥ᴴ_ (x : A) : DL → Type₀
Data\DescendingList\Properties.agda:27: (A : Type₀)
Data\DescendingList\Properties.agda:28: (_≥_ : A → A → Type₀)
Data\DescendingList\Properties.agda:42:data _≥ᴬ_ (x : A) : List A → Type₀ where
Data\DescendingList\Properties.agda:46:data descending : List A → Type₀ where
Data\DescendingList\Properties.agda:110:   P : A → Type₀
Data\DescendingList\Properties.agda:115:     Q : (v : DL) → Type₀
Data\DescendingList\Strict.agda:9: (A : Type₀)
Data\DescendingList\Strict.agda:10: (_>_ : A → A → Type₀)
Data\DescendingList\Strict\Properties.agda:5: (A : Type₀)
Data\DescendingList\Strict\Properties.agda:6: (_>_ : A → A → Type₀)
Data\Empty\Base.agda:9:data ⊥ : Type₀ where
Data\Equality\S1.agda:65:Cover : S¹ → Type₀
Data\Equality\S1.agda:68:ΩS¹ : Type₀
Data\Fin\Base.agda:25:Fin : ℕ → Type₀
Data\Fin\LehmerCode.agda:33:FinExcept : ∀ {n} → (i : Fin n) → Type₀
Data\Fin\LehmerCode.agda:113:data LehmerCode : (n : ℕ) → Type₀ where
Data\Fin\Properties.agda:149:Residue : ℕ → ℕ → Type₀
Data\Fin\Properties.agda:260:    F : Fin (suc m) → Type₀
Data\Fin\Recursive\Base.agda:9:data FinF (X : Type₀) : Type₀ where
Data\Fin\Recursive\Base.agda:13:Fin : ℕ → Type₀
Data\Fin\Recursive\Properties.agda:133:_#_ : Fin m → Fin m → Type₀
Data\FinData\Base.agda:16:data Fin : ℕ → Type₀ where
Data\FinData\Order.agda:46:data FinTrichotomy {n : ℕ} (i j : Fin n) : Type₀ where
Data\FinSet\Binary\Small\Base.agda:11:data Binary : Type₀
Data\FinSet\Binary\Small\Base.agda:12:El : Binary → Type₀
Data\FinSet\Binary\Small\Properties.agda:70:  lemma : ∀(B : Type₀) → ∥ Bool ≃ B ∥₁ → Σ[ b ∈ Binary ]
El b ≃ B
Data\Graph\Examples.agda:42:data Adj : ℕ → ℕ → Type₀ where
Data\Graph\Examples.agda:73:data AdjFin : ∀ {k} → Fin k → Fin k → Type₀ where
Data\InfNat\Base.agda:9:data ℕ+∞ : Type₀ where
Data\Int\Base.agda:15:data ℤ : Type₀ where
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
Data\Int\MoreInts\DeltaInt\Base.agda:32:data DeltaInt : Type₀ where
Data\Int\MoreInts\DiffInt\Base.agda:12:rel : (ℕ × ℕ) → (ℕ × ℕ) → Type₀
Data\Int\MoreInts\QuoInt\Base.agda:21:Sign : Type₀
Data\Int\MoreInts\QuoInt\Base.agda:31:data ℤ : Type₀ where
Data\Nat\Coprime.agda:16:areCoprime : ℕ × ℕ → Type₀
Data\Nat\Divisibility.agda:25:_∣_ : ℕ → ℕ → Type₀
Data\Nat\Divisibility.agda:31:prediv : ℕ → ℕ → Type₀
Data\Nat\Divisibility.agda:36:_∣'_ : ℕ → ℕ → Type₀
Data\Nat\GCD.agda:34:isCD : ℕ → ℕ → ℕ → Type₀
Data\Nat\GCD.agda:45:isGCD : ℕ → ℕ → ℕ → Type₀
Data\Nat\GCD.agda:48:GCD : ℕ → ℕ → Type₀
Data\Nat\Order.agda:28:_≤_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:31:_<_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:34:_≥_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:37:_>_ : ℕ → ℕ → Type₀
Data\Nat\Order.agda:40:data Trichotomy (m n : ℕ) : Type₀ where
Data\Nat\Order.agda:456:    (P : ℕ → Type₀)
Data\Nat\Order\Inductive.agda:51:data Trichotomyᵗ (m n : ℕ) : Type₀ where
Data\Nat\Order\Recursive.agda:22:_≤_ : ℕ → ℕ → Type₀
Data\Nat\Order\Recursive.agda:27:_<_ : ℕ → ℕ → Type₀
Data\Nat\Order\Recursive.agda:35:data Trichotomy (m n : ℕ) : Type₀ where
Data\NatMinusOne\Base.agda:8:record ℕ₋₁ : Type₀ where
Data\NatPlusOne\Base.agda:8:record ℕ₊₁ : Type₀ where
Data\Rationals\Base.agda:25:_∼_ : ℤ × ℕ₊₁ → ℤ × ℕ₊₁ → Type₀
Data\Rationals\Base.agda:28:ℚ : Type₀
Data\Rationals\Order.agda:146:_≤_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:149:_<_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:152:_≥_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:155:_>_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:158:_#_ : ℚ → ℚ → Type₀
Data\Rationals\Order.agda:161:data Trichotomy (m n : ℚ) : Type₀ where
Data\Rationals\MoreRationals\HITQ\Base.agda:17:data ℚ : Type₀ where
Data\Rationals\MoreRationals\QuoQ\Base.agda:28:_∼_ : ℤ × ℕ₊₁ → ℤ × ℕ₊₁ → Type₀
Data\Rationals\MoreRationals\QuoQ\Base.agda:31:ℚ : Type₀
Data\Rationals\MoreRationals\SigmaQ\Base.agda:18:ℚ : Type₀
Data\SumFin\Base.agda:18:Fin : ℕ → Type₀
Data\Unit\Properties.agda:94:isContr→≡Unit : {A : Type₀} → isContr A → A ≡ Unit
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
Experiments\HoTT-UF.agda:65:  data ℕ : Type₀ where
Experiments\Problem.agda:17:ptType = Σ Type₀ \ A → A
Experiments\HAEquivInt\Base.agda:7:data HAEquivInt : Type₀ where
Experiments\IsoInt\Base.agda:22:data IsoInt : Type₀ where
Experiments\NatMinusTwo\Base.agda:8:record ℕ₋₂ : Type₀ where
Experiments\ZCohomologyOld\Base.agda:24:coHomK : (n : ℕ) → Type₀
Experiments\ZCohomologyOld\KcompPrelims.agda:55:    P : (a b : S₊ (2 + n)) → Type₀
Experiments\ZCohomologyOld\KcompPrelims.agda:100:  Code : (y : Susp S2+n) → north ≡ y → Type₀
Experiments\ZCohomologyOld\Properties.agda:506:Unit' : Type₀
Foundations\HLevels.agda:29:HLevel : Type₀
HITs\Delooping\Two\Base.agda:8:data Bℤ₂ : Type₀ where
HITs\Delooping\Two\Properties.agda:50:  El : Bℤ₂ → Type₀
HITs\Delooping\Two\Properties.agda:63:  Loop²-coh : (a b c : Bool) → Type₀
HITs\Delooping\Two\Properties.agda:131:  module _ (B : Type₀) where
HITs\DunceCap\Base.agda:14:data Dunce : Type₀ where
HITs\DunceCap\Base.agda:25:DunceCone : Type₀
HITs\DunceCap\Properties.agda:19:Disk : Type₀
HITs\InfNat\Base.agda:11:data ℕ+∞ : Type₀ where
HITs\Interval\Base.agda:5:data Interval : Type₀ where
HITs\Interval\Base.agda:26:elim : (A : Interval → Type₀) (x : A zero) (y : A one)
HITs\Interval\Base.agda:33:intervalEta : ∀ {A : Type₀} (f : Interval → A) → elim _ (f zero) (f one)
(λ i → f (seg i)) ≡ f
HITs\Join\Properties.agda:106:join-assoc : (A B C : Type₀) → join (join A B) C ≡ join A (join B C)
HITs\Join\Properties.agda:170:        A×join : Type₀
HITs\Join\Properties.agda:252:        join×C : Type₀
HITs\Modulo\Base.agda:15:NonZero : ℕ → Type₀
HITs\Modulo\Base.agda:39:data Modulo (k : ℕ) : Type₀ where
HITs\Modulo\FinEquiv.agda:26:  ResiduePath : ℕ → Type₀
HITs\RPn\Base.agda:45:data RP² : Type₀ where
HITs\RPn\Base.agda:52:2-EltType₀    = TypeEqvTo    ℓ-zero Bool -- Σ[ X ∈ Type₀ ] ∥ X ≃ Bool ∥
HITs\RPn\Base.agda:53:2-EltPointed₀ = PointedEqvTo ℓ-zero Bool -- Σ[ X ∈ Type₀ ] X × ∥ X ≃ Bool ∥
HITs\RPn\Base.agda:55:Bool* : 2-EltType₀
HITs\RPn\Base.agda:93:module ⊕* (X : 2-EltType₀) where
HITs\RPn\Base.agda:108:  elim : ∀ {ℓ'} (P : (A : Type₀) (_⊕'_ : A → A → Bool) → Type ℓ') (propP : ∀ A
_⊕'_ → isProp (P A _⊕'_))
HITs\RPn\Base.agda:115:          R₂ : (B : Type₀) → B ≃ Bool → B → B → Bool
HITs\RPn\Base.agda:145:RP  : ℕ₋₁ → Type₀
HITs\RPn\Base.agda:146:cov⁻¹ : (n : ℕ₋₁) → RP n → 2-EltType₀ -- (see Cubical.Functions.Bundle)
HITs\S1\Base.agda:22:data S¹ : Type₀ where
HITs\S1\Base.agda:36:helix : S¹ → Type₀
HITs\S1\Base.agda:40:ΩS¹ : Type₀
HITs\S1\Base.agda:149:basedΩS¹ : (x : S¹) → Type₀
HITs\S2\Base.agda:6:data S² : Type₀ where
HITs\S3\Base.agda:7:data S³ : Type₀ where
HITs\Sn\Base.agda:12:S : ℕ₋₁ → Type₀
HITs\Sn\Base.agda:16:S₊ : ℕ → Type₀
HITs\Susp\Base.agda:90:SuspBool : Type₀
HITs\Susp\Base.agda:132:SuspS¹ : Type₀
HITs\Susp\Base.agda:176:SuspS² : Type₀
HITs\Torus\Base.agda:22:data Torus : Type₀ where
HITs\Torus\Base.agda:61:Loop : {A : Type₀} (p : A) → Type₀
HITs\Torus\Base.agda:64:ΩTorus : Type₀
HITs\Torus\Base.agda:100:data Torus' : Type₀ where
Homotopy\Hopf.agda:386:  Border : (x : S¹) → (j : I) → Partial (j ∨ ~ j) (Σ Type₀ (λ T → T ≃ S¹))
Homotopy\Hopf.agda:391:  HopfSuspS¹ : SuspS¹ → Type₀
Homotopy\Hopf.agda:398:  HopfS² : S² → Type₀
Homotopy\Hopf.agda:407:  HopfS²' : S² → Type₀
Homotopy\Hopf.agda:415:  TotalHopf : Type₀
Homotopy\Hopf.agda:447:  fibℤ : S¹ → S¹ → Type₀
Homotopy\Hopf.agda:450:  S¹→HSet : (A : Type₀) (p : isSet A) (F : S¹ → A) (x : S¹) → F base ≡ F x
Homotopy\Hopf.agda:473:  discretefib : (F : S¹ → S¹ → Type₀) → Type₀
Homotopy\Hopf.agda:558:  PseudoHopf : Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:43:join∙ : Pointed₀ → Type₀ → Pointed₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:50:mapΩrefl : {A : Pointed₀} {B : Type₀} (f : A .fst →
B) → Ω A .fst → Ω (B , f (pt A)) .fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:53:mapΩ²refl : {A : Pointed₀} {B : Type₀} (f : A .fst →
B) → Ω² A .fst → Ω² (B , f (pt A)) .fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:56:mapΩ³refl : {A : Pointed₀} {B : Type₀} (f : A .fst →
B) → Ω³ A .fst → Ω³ (B , f (pt A)) .fst
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:68:connectionBoth : {A : Type₀} {a : A} (p : Path A a
a) → PathP (λ i → Path A (p i) (p i)) p p
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:79:data PostTotalHopf : Type₀ where
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:110:fibΩ : {B : Pointed₀} (P : B .fst → Type₀) → P (pt
B) → Ω B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:113:fibΩ² : {B : Pointed₀} (P : B .fst → Type₀) → P (pt
B) → Ω² B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:116:fibΩ³ : {B : Pointed₀} (P : B .fst → Type₀) → P (pt
B) → Ω³ B .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:119:Ω³Hopf : Ω³ S²∙ .fst → Type₀
Homotopy\Group\Pi4S3\BrunerieExperiments.agda:201:tHopf³ : S³ → Type₀
Structures\Auto.agda:7:  autoDesc (λ (X : Type₀) → X → X × ℕ)   ↦   function+ var (var , constant ℕ)
Structures\Auto.agda:9:We prefer to use the constant structure whenever possible, e.g., [autoDesc (λ
(X : Type₀) → ℕ → ℕ)]
Structures\Relational\Auto.agda:7:  autoDesc (λ (X : Type₀) → X → X × ℕ)   ↦   function+ var (var ,
constant ℕ)
Structures\Relational\Auto.agda:9:We prefer to use the constant structure whenever possible, e.g.,
[autoDesc (λ (X : Type₀) → ℕ → ℕ)]
Tactics\CommRingSolver\Examples.agda:26:    making the user aware that the problem is, that 'Type₀'
Tactics\CommRingSolver\Examples.agda:31:  _ = solve Type₀
ZCohomology\Base.agda:26:coHomK : (n : ℕ) → Type₀
ZCohomology\GroupStructure.agda:800:Unit' : Type₀
ZCohomology\Properties.agda:312:  Code : (n : ℕ) →  coHomK (2 + n) → Type₀
ZCohomology\Properties.agda:316:    Code' : (S₊ (2 + n)) → Type₀
ZCohomology\Groups\CP2.agda:299:  cupIsEquiv : {A B : Type₀}
ZCohomology\Groups\Prelims.agda:232:         helperFun2 : {A : Type₀} {0A a b : A} (main : 0A ≡ 0A)
(start : b ≡ b) (p : a ≡ a) (q : a ≡ b) (r : b ≡ 0A) (Q : a ≡ 0A)
ZCohomology\Groups\Prelims.agda:251:         congFunct₃ : ∀ {A B : Type₀} {a b c d : A} (f : A → B)
(p : a ≡ b) (q : b ≡ c) (r : c ≡ d)
