# Set Theory and Predicate logic notation

## Sets

### Set construction

  ```{ a, b, c } is a set containing three elements a,b,c```

### Empty set

  ```Ø is the empty set meaning it contains no elements```

### Boolean values

  ```𝔹 is the set of boolean values: { 0, 1 }```

### Natural numbers

  ```ℕ is the set of the natural numbers: { 0, 1, 2, ... }```

### Real numbers

  ```ℝ is the set of the real numbers: { 1, 2.4, -1.23, ... }```

### Class of sets

  ```Set is the class of all sets. Think of this as the Set of Sets```

## Set operators

### Intersection

  ```A ∩ B is the set of elements found in both sets A and B: { 1 } ∩ { 1, 2 } + { 1 }```

### Union

  ```A ∪ B is the set of all unique elements from sets A and B: { 1 } ∪ { 1, 2 } = { 1, 2 }```

### Disjoint

  ```Disjoint(A, B) if there are no common elements between sets A and B: A ∩ B = Ø```

### Disjoint union 

  ```A + B is A ∪ B if Disjoint(A, B): A = { 1 }, B = { 2 }, A + B = { 1, 2 }```

### Subset

  ```A ⊆ B is a set A contained in set B: A = { 1 }, B = { 1, 2 }```

### Element of
  
  ```a ∈ B is an element a found in set B: a = 1, B = { 1, 2 }```

## Logic operators

### Negation
  
  ```¬a means not a: ¬true = false```

### Conjunction

  ```a /\ b means a and b: true /\ true = true```

### Disjunction

  ```a \/ b means a or b: true \/ false = true```

### Implication

  ```a => b means a implies b```

### Double Implication

  ```a <=> b means a implies b and b implies a```

## Intervals

### Open interval

  ```[a,b] = { x ∈ ℝ | a <= x <= b }```
### Closed interval
  
  ```(a,b) = { x ∈ ℝ | a < x < b }```

### Half-open intervals

  ```[a,b) = { x ∈ R | a <= x < b }```

  ```(a,b] = { x ∈ R | a < x <= b }```

## Functions

### Function type

  ```A -> B is the type of a function mapping elements of A to elements of B: (f: ℝ -> ℝ)```

### Domain

  ```the set of input values to the function: A in (A -> B)```

### Codomain

  ```the set of output values from the function: B in (A -> B)```

### Predicate

  ```f : (A -> 𝔹) is a predicate because its codomain is boolean values```

### Function definition

  ```f : A -> A, x |-> x is a function mapping x to itself```


### Function definition by cases

  ```h : A -> B, x |-> { f(x), p(x) } { g(x), p(x) } maps x to f when p(x) otherwise to g``` 
