# Set Theory and Predicate Logic notation

## Sets

### Set construction

  ```{ a, b, c }```

  The set containing elements a, b and c.

    1 ∈ { 1, 2 } = true
    2 ∈ { 1, 2 } = true
    3 ∈ { 1, 2 } = false

### Empty set

  ```Ø```

   The set that contains no elements.

    Cardinality(Ø) = 0

### Boolean values

  ```𝔹```
  
  The set of binary digits.

    0 ∈ 𝔹 = true
    1 ∈ 𝔹 = true
    2 ∈ 𝔹 = false


### Natural numbers

  ```ℕ```
  
  The set of the natural numbers.

    1 ∈ ℕ = true
    3 ∈ ℕ = true
    0 ∈ ℕ = true

### Real numbers

  ```ℝ```
  
  The set of the real numbers.
  
    1.2  ∈ ℝ = true
    3.3  ∈ ℝ = true
    -0.3 ∈ ℝ = true

### Class of sets

  ```Set```
  
  The class of all sets. Think of this as the set of sets.

    𝔹 ∈ Set = true
    (𝔹 → 𝔹) ∈ Set = true
    { 1, 2 } ∈ Set = true

## Set operators

### Without

  ```A / b```

  The set without the element b.

    1 ∈ ({ 1, 2 } / 1) = false

### Intersection

  ```A ∩ B```
  
  The set of elements found in both A and B.
  
    { 1 } ∩ { 1, 2 } = { 1 }

### Union

  ```A ∪ B```
  
  The set of all unique elements found in A and B.
  
    { 1 } ∪ { 1, 2 } = { 1, 2 }

### Disjoint

  ```Disjoint(A, B) <=> A ∩ B = Ø``` 

  The inersection of sets A and B is the empty set.
  
    A = { 1 }
    B = { 2 }
    A ∩ B = Ø
    Disjoint(A, B) = true

### Disjoint union 

  ```∀A B ∈ Set: Disjoint(A,B) => A + B = A ∪ B```

  The union of disjoint sets A and B.
  
    A = { 1 }
    B = { 2 }
    A ∩ B = Ø
    A + B = { 1, 2 }

### Cardinality

  ```Cardinality({ 2, 3, 4 }) = 3```

  The number of elements in the finite set.

    Cardinality({ 2, 3, 4 }) = 3

### Subset

  ```A ⊆ B```
  
  All elements of A are found in B.
  
    A = { 1 }
    B = { 1, 2 }
    A ⊆ B = true

### Element of
  
  ```a ∈ B```

  a is an element of set B.
  
    a = 1
    B = { 1, 2 }
    a ∈ B = true

## Predicate logic

### Negation

  ```¬a```

  Boolean negation of a.
  
    ¬true  = false
    ¬false = true

### Conjunction

  ```a /\ b```

  Both a and b are true.

    true  /\ true  = true
    false /\ true  = false
    true  /\ false = false
    false /\ false = false

### Disjunction

  ```a \/ b```

  Either a or b is true.
  
    true  \/ false = true
    false \/ true  = true
    true  \/ true  = true
    false \/ false = false

### Implication

  ```a ⇒ b = ¬a \/ b```

  a is true implies b is true.

    true  ⇒ false = false
    false ⇒ true  = true
    true  ⇒ true  = true
    false ⇒ false = true

### Double Implication

  ```a ≡ b = (a ⇒ b) /\ (b ⇒ a)```

  a is true implies b is true and b is true implies a is true.

    true  ≡ false = false
    false ≡ true  = false
    true  ≡ true  = true
    false ≡ false = true

### Universal quantification

  ```∀x ∈ A: P(x)```

  For all x in set A P(x) is true.

    ∀x ∈ ℕ: x >= 0 

### Existential quantification

  ```∃x ∈ A: P(x)```

  There exists an x in A such that P(x) is true.

    ∃x ∈ { 1, 2, 3 }: x > 2

## Intervals

### Closed interval

  ```[a,b] = { x ∈ ℝ | a <= x <= b }```

  Closed intervals include their endpoints in the set.

    1 ∈ [1,2] = true
    1 ∈ [1,2] = true

### Open interval
  
  ```(a,b) = { x ∈ ℝ | a < x < b }```

  Open intervals do not include their endpoints in the set.

    1 ∈ (1,2) = false
    1 ∈ (1,2) = false


### Half-open intervals

  ```[a,b) = { x ∈ R | a <= x < b }```

  Half-open intervals include one of their endpoints in the set.

    1 ∈ [1,2) = true
    2 ∈ [1,2) = false

  ```(a,b] = { x ∈ R | a < x <= b }```
  
    1 ∈ (1,2] = false
    2 ∈ (1,2] = true

## Functions

### Function type

  ```A → B```

  Functions are maps from elements of set A to elements of set B.

    f : ℝ → ℝ, x |-> x * x
    f ∈ (ℝ → ℝ) = true

### Domain

  ```∀A B ∈ Set: Domain(A → B) = A```

  The domain of a function is its input set.

    Domain({ 1 } → { 2 }) = { 1 }

### Codomain

  ```∀A B ∈ Set: Codomain(A → B) = B```

  The domain of a function is its output set.

    Codomain({ 1 } → { 2 }) = { 2 }

### Predicate

  ```∀f ∈ (A → 𝔹): Predicate(f)```

  Predicates are functions whose codomain is boolean digits.

    f : [-2, 2] → 𝔹
    Predicate(f) = true

### Function definition

  ```f : A → B, x ↦ y```

  Function definitions declare how elements of set A are mapped to elements of set B.

    not : 𝔹 → 𝔹, x ↦ ¬x
    not(true)  = false
    not(false) = true

### Function definition by cases

  ```h : A → B, x ↦ { f(x), p(x) } { g(x), ¬p(x) }```

  Function definitions by cases declare how elements of set A are mapped to elements of set B arbitrated by a predicate over the value of the element of set A.

    positive : ℝ → 𝔹, x ↦ { true, x >= 0 } { false, x < 0 }
    positive(1)  = true
    positive(-1) = false
