# Sets, Types, and Categories... wtf

## Different models of the foundations of math and some relationships to programming

### Let's build a type theory from sets

Type theory refers to a whole collection of possible rules one can place on top of a mathematical language to prevent or reduce the ability to construct meaningless statements. Imagine this as you learned the rules of Enlish grammar: "Cat is a noun". "Jump is an verb". "Sentence is a combination of at least one verb and one noun". These rules take the "stuff" of English and give them "types" then describe how these types are used to construct other types. This is what a type-theory essentially does.

#### IHOL (intuitionistic higher-order logic)

1. Basic type symbols

    `B1, B2, ...`

2. Type constructors
  
    `A × B, P(A) for type symbols A and B`

3. Variables
  
    `x1,x2: A, for each type A`

4. Basic terms

    `b1: A1, b2: A2`

5. Term constructors
  
    `Given a: A, b: B, c: A × B,  <a,b>:A × B, π1(c):A, π2(c):B`

6. Function constructors

    `(λx:A.φ):P(A) where φ is any formula`

7. Formulas

    `Given a:A, b:A, p: P(A) and formulas φ and ψ`

    `a = b, p(a), ¬ψ, ψ /\ φ, ψ \/ φ, ψ ⇒ φ, ∀x:A.ψ, ∃x:A.ψ`

8. Theorems

    `Some formulas are theorems denoted |- ν`

#### Defining the semantics

Let's create a meaning for our type theory by creating a model. To create a model, we assign a meaning to each syntax in the type theory. The meaning of thing is denoted by being written between square brackets: `[THING] = MEANING`.

Let's model the basic types as sets:

  `[B1] = S1`

  `[S2] = S2`

Products are modeled as cartesian products from set theory. Think of these as the set of ordered pairs (a,b) for all elements a and b in A and B.

  `[A × B] = [A] × [B]`

Functions are modeled as powerset operations from set theory. Think of this as the set of all possible subsets of A.

  `[P(A)] = P([A])`

Terms that are pairs are interpreted as ordered pairs:

  `[<a,b>] = ([a], [b])`

Given the formula ψ:

  `[λx:A.ψ] = {x ∈ [A] | [ψ]}`

All formulas are directly interpretable in set theory as shown:

  `[p(a)] = [a] ∈ [p]`

  `[¬ψ] = ¬[ψ]`

  `[ψ /\ φ] = [ψ] /\ [φ]`

  `[ψ \/ φ] = [ψ] \/ [φ]`

  `[ψ ⇒ φ] = [ψ] ⇒ [φ]`
  
  `[∀x:A.ψ] = ∀x ∈ [A].[ψ]`

  `[∃x:A.ψ] = ∃x ∈ [A].[ψ]`
