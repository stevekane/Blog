Notation used translated to English:

  Sets:

    "Set construction"
      { a, b, c } is a set containing three elements a,b,c
    "Empty set"
      Ø is the empty set meaning it contains no elements
    "Boolean"
      𝔹 is the set of boolean values: { 0, 1 }
    "Natural numbers"
      ℕ is the set of the natural numbers: { 0, 1, 2, ... }
    "Real numbers"
      ℝ is the set of the real numbers: { 1, 2.4, -1.23, ... }
    "Class of sets"
      Set is the class of all sets. Think of this as the "Set of Sets"

  Set operators:
  
    "Intersection"
      A ∩ B is the set of elements found in both sets A and B: { 1 } ∩ { 1, 2 } + { 1 }
    "Union"
      A ∪ B is the set of all unique elements from sets A and B: { 1 } ∪ { 1, 2 } = { 1, 2 }
    "Disjoint"
      Disjoint(A, B) if there are no common elements between sets A and B: A ∩ B = Ø
    "Disjoint union" 
      A + B is A ∪ B if Disjoint(A, B): A = { 1 }, B = { 2 }, A + B = { 1, 2 }
    "Subset"
      A ⊆ B is a set A contained in set B: A = { 1 }, B = { 1, 2 }
    "Element of"
      a ∈ B is an element a found in set B: a = 1, B = { 1, 2 }

  Logic operators:
    "Negation"
      ¬a means not a: ¬true = false
    "Conjunction"
      a /\ b means a and b: true /\ true = true
    "Disjunction"
      a \/ b means a or b: true \/ false = true
    "Implication"
      a => b means a implies b

  Intervals:

    "Open interval"
      [a,b] = { x ∈ ℝ | a <= x <= b }
    "Closed interval"
      (a,b) = { x ∈ ℝ | a < x < b }
    "Half-open intervals"
      [a,b) = { x ∈ R | a <= x < b }
      (a,b] = { x ∈ R | a < x <= b }

  Functions:
    "Function type"
      A -> B is the type of a function mapping elements of A to elements of B: (f: ℝ -> ℝ)
    "Domain"
      the set of input values to the function: A in (A -> B)
    "Codomain"
      the set of output values from the function: B in (A -> B)
    "Predicate"
      function f is a predicate if its codomain is a boolean value: (A -> 𝔹)
    "Maps to"
      x |-> y reads "x is mapped to y": x |-> x + 1
    "Function definition"
      f : A -> B, x |-> x is a function from set A to set B that maps an element x to itself
    "Function definition by cases"
      h : A -> B, x |-> { f(x), predicate(x) } 
                        { g(x), predicate(x) } function that maps x to f or g depending on predicate

Function restriction:

  Definition:

    Assume A B ∈ Set
    Assume B ⊆ A
    Assume f : A -> C

    f|B: B -> C, x -> f(x)

  Example of function restriction:

    sin : ℝ -> ℝ 
    sin|[0, π] is the restriction of sin to domain defined by the interval [0, π]

Function extension:

  Definition:

    Assume A B C ∈ Set
    Assume A ⊆ B
    Assume f : A -> C
    Assume g : B -> C

    Extends(g, f) <=> ∀x ∈ A: f(x) = g(x)

  Definition generalization:

    Assume A ∪ B = Ø
    Assume A ∪ C = Ø
    Assume B ∪ C = Ø

    Let a : A -> D
    Let b : B -> D
    Let c : C -> D
    Let d : A + B + C -> D

    Extends(d, a) <=> ∀x ∈ A: a(x) = g(x)
    Extends(d, b) <=> ∀x ∈ B: b(x) = g(x)
    Extends(d, c) <=> ∀x ∈ C: c(x) = g(x)
  
  Example of function extension:

    Let A = { "true" }
    Let B = { "false" }
    Let f : A -> ℝ, x |-> 42
    Let g : B -> ℝ, x |-> 0
    let h : A + B -> ℝ, x |-> { f(x), x ∈ A }
                              { g(x), x ∈ B }

    h extends A /\ h extends B