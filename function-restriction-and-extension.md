Notation used translated to English:

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