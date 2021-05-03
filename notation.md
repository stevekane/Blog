# Set Theory and Predicate Logic notation

## Sets

### Set construction

  `{a,b,c}`

  The set containing elements a, b and c.

    1 ∈ {1,2} = true
    2 ∈ {1,2} = true
    3 ∈ {1,2} = false

### Ordered pairs

  `∀a ∈ A, ∀b ∈ B: (a,b) ∈ (A × B)`

  Pair of element of set A with an element of set B.

    (1,3) ∈ {1,2} × {3,4} = true

### Empty set

  `Ø`

   The set that contains no elements.

    Cardinality(Ø) = 0

### Boolean values

  `𝔹`
  
  The set of binary digits.

    0 ∈ 𝔹 = true
    1 ∈ 𝔹 = true
    2 ∈ 𝔹 = false

### Natural numbers

  `ℕ`
  
  The set of the natural numbers.

    1 ∈ ℕ = true
    3 ∈ ℕ = true
    0 ∈ ℕ = true

### Real numbers

  `ℝ`
  
  The set of the real numbers.
  
    1.2  ∈ ℝ = true
    3.3  ∈ ℝ = true
    -0.3 ∈ ℝ = true

### Class of sets

  `Set`
  
  The class of all sets. Think of this as the set of sets.

    𝔹 ∈ Set = true
    (𝔹 → 𝔹) ∈ Set = true
    {1,2} ∈ Set = true

## Set operators

### Without

  `A / b`

  The set without the element b.

    {1,2} / 1 = {2}

### Intersection

  `A ∩ B`
  
  The set of elements found in both A and B.
  
    {1} ∩ {1,2} = {1}

### Union

  `A ∪ B`
  
  The set of all unique elements found in A and B.
  
    {1} ∪ {1,2} = {1,2}

### Cartesian Product

  `A × B`

  All elements of A paired with all elements of B.

    {1,2} × {3,4} = {(1,3),(1,4),(2,3),(2,4)}

### Disjoint

  `Disjoint(A,B) ≡ A ∩ B = Ø`

  The intersection of sets A and B is the empty set.
  
    Disjoint({1},{2,3}) = true

### Disjoint union

  `∀A B ∈ Set: Disjoint(A,B) ⇒ A + B = A ∪ B`

  The union of disjoint sets A and B.
  
    {1} + {2} = {1,2}

### Cardinality

  `Cardinality(Ø) = 0`

  The number of elements in the finite set.

    Cardinality({2,3,4}) = 3

### Subset

  `A ⊆ B ≡ ∀x(x ∈ A ⇒ x ∈ B)`
  
  All elements of A are found in B.
  
    {1} ⊆ {1,2} = true

### Element of
  
  `∀a(a ∈ B ≡ {a} ∪ B = B)`

  a is an element of set B.
  
    1 ∈ {1,2} = true

## Predicate logic

### Negation

  `¬a`

  Boolean negation of a.
  
    ¬true  = false
    ¬false = true

### Conjunction

  `a /\ b`

  Both a and b are true.

    true  /\ true  = true
    false /\ true  = false
    true  /\ false = false
    false /\ false = false

### Disjunction

  `a \/ b`

  Either a or b is true.
  
    true  \/ false = true
    false \/ true  = true
    true  \/ true  = true
    false \/ false = false

### Implication

  `a ⇒ b = ¬a \/ b`

  a is true implies b is true.

    true  ⇒ false = false
    false ⇒ true  = true
    true  ⇒ true  = true
    false ⇒ false = true

### Double Implication

  `a ≡ b = (a ⇒ b) /\ (b ⇒ a)`

  a is true implies b is true and b is true implies a is true.

    true  ≡ false = false
    false ≡ true  = false
    true  ≡ true  = true
    false ≡ false = true

### Universal quantification

  `∀x ∈ A: P(x)`

  For all x in set A P(x) is true.

    ∀x ∈ ℕ: x >= 0 

### Existential quantification

  `∃x ∈ A: P(x)`

  There exists an x in A such that P(x) is true.

    ∃x ∈ {1,2,3}: x > 2

## Intervals

### Closed interval

  `[a,b] = { x ∈ ℝ | a <= x <= b }`

  Closed intervals include their endpoints in the set.

    1 ∈ [1,2] = true
    1 ∈ [1,2] = true

### Open interval
  
  `(a,b) = { x ∈ ℝ | a < x < b }`

  Open intervals do not include their endpoints in the set.

    1 ∈ (1,2) = false
    1 ∈ (1,2) = false


### Half-open intervals

  `[a,b) = { x ∈ R | a <= x < b }`

  Half-open intervals include one of their endpoints in the set.

    1 ∈ [1,2) = true
    2 ∈ [1,2) = false

  `(a,b] = { x ∈ R | a < x <= b }`
  
    1 ∈ (1,2] = false
    2 ∈ (1,2] = true

## Functions

### Function

  `A → B`

  Functions are maps from elements of set A to elements of set B.

    f : ℝ → ℝ, x ↦ x * x
    f ∈ (ℝ → ℝ) = true

### Domain

  `∀A B ∈ Set: Domain(A → B) = A`

  The domain of a function is its input set.

    Domain({1} → {2}) = {1}

### Codomain

  `∀A B ∈ Set: Codomain(A → B) = B`

  The domain of a function is its output set.

    Codomain({1} → {2}) = {2}

### Predicate

  `∀f ∈ (A → 𝔹): Predicate(f)`

  Predicates are functions whose codomain is boolean digits.

    f : [-2, 2] → 𝔹
    Predicate(f) = true

### Function definitions

  Functions are sets mapping elements of their domain to elements of their codomain.

  `f : A → B, x ↦ y`

  Functions are often written on a single line as follows:

    not : 𝔹 → 𝔹, x ↦ ¬x
    not(true)  = false
    not(false) = true

  Functions may also be written across multiple lines when cases are used to select how elements of the domain map to the codomain. In these cases, a predicate p is evaluated over any input x to select whether f or g will be used to compute the output of the function h.

  `p : A → 𝔹`

  `f : A → B`

  `g : A → B`

  `h : A → B`

  `h(x) = { f(x),  p(x) } { g(x), ¬p(x) }`

  Maps elements of set A to elements of set B based on the value of predicate p over the input element x.

    positive : ℝ → 𝔹
    positive(x) = { true, x >= 0 } 
                  { false, x < 0 }
    positive(1)  = true
    positive(-1) = false
