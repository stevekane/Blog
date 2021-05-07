# Products and Sums are duals

Category theory tells us that Products and Sums are categorical duals of one-another. This duality is central to why both are needed to express data types in an expressive language. Let's illustrate this duality and then explain why both constructions are so essential for modeling logic and programs.

> "Dual categories reverse all the arrows and the order of composition".

## The categorical product

Product categorical diagram

       fa      fb
     ◁----- Y -----▷
    A     f |       B
     ◁----- ▽ -----▷
       p1  A×B  p2

The universal property of products:

    ∀A B. ∃f : Y → (A × B). f ∘ p1 = fa /\ f ∘ p2 = fb
  
Any object is a product if there are morphisms from it to two other objects. The most fundamental such object is called "the product" if all other products may be rewritten as the composition of a common factor "f" and the fundamental object's morphisms.

    fa = p1 ∘ f
    fb = p2 ∘ f
  
For example, let's take this example of the structure representing a User:

    User = { name: String, weight: Int, strength: Int }
  
We can also define two projection functions called `name` and `strength`:

    name : User → String
    name(user) = user.name

    strength : User → Int
    strength(user) = user.strength

These functions project from the object User to the objects String and Int. Should we consider User to be the fundamental Product in our type system? Perhaps not. What if we instead try out the simple ordered pair of (String,Int) and two functions `first` and `second` which project out the first and second values respectively.

    first : (String,Int) → String
    first (a,b) = a

    second : (String,Int) → Int
    second (a,b) = b

We can then try to define a common morphism from User → (String,Int) that we will say is a common factor of both `name` and `strength`.

    f : User → (String,Int)
    f(user) = (user.name, user.strength)

Notice, with this trivial definition we are now able to write `name` and `strength` in terms of `first`, `second`, and `f`:

    name(user)     = first(f(user))
    strength(user) = second(f(user))

Thus, we say that (String,Int) is more fundamental than User as a candidate for being "the product" because it is more general as shown above.

## The categorical coproduct

Coproduct categorical diagram

       fa      fb
     -----▷ Y ◁-----
    A     f △       B
     -----▷ | ◁-----
       i1  A+B  i2

The universal property of coproducts.

    ∀A B. ∃f : (A + B) → Y. i1 ∘ f = fa /\ i2 ∘ f = fb

## Duality of product and coproduct

We can see that product and coproduct are duals: reversing the direction of arrows and axioms of composition of one yields the other.

## Studying the arrows

We can see that there are two arrows coming out of the product A×B indicating that there are two ways to map from products to types A and B.

We can also see that there is one arrow coming out of A+B indicating that there is a single arrow to map from a coproduct to the type Y.
