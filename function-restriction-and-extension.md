# What is if-then-else anyway?

## How disjoint unions and function extension could change your life

Most programmers are familiar with cartesian products. These products are most commonly called tuples and it is common to label the tuples values. These labeled tuples are often called "structs", "classes", or "records". Products are used to group values together to enforce requirements of the domain such as "all users must have both a name and a password".

Let's ask a somewhat natural question: "How can I enforce that a user must have a name or an email?".  Expressing this type of relationship is considerably less elegant in many mainstream programming languages. Languages such as C provide unions within structures which allow the same memory to be used to hold different products of data. The data structure must also store a value on the structure which is used to determine which data a particular instance of the structure actually contains. Other languages such as C# or Java have polymorphism which requires that the difference in underlying data be hidden behind a common interface. We could spend a lot more time here belaboring this point and probably just end up confusing or frustrating the reader.

Let's instead ask another question: "Why do programming languages have if-then-else statements?". Programs often need to execute different logic depending on the values in their inputs. The if-then-else statement has three parts: the condition, the first program, and the second program. The condition determines which program is executed for a given input. In other words, ordinary programming languages include as a fundamental building-block the capacity to write programs out of multiple smaller programs and to select which program to run based on the value in the input.

This general shape of solution is strangely limited to boolean values in many mainstream languages. That is to say, the only syntax they provide for "writing a function out of multiple functions based on the inputs" is to first evaluate the inputs to a boolean value and then select a program to run. We might ask what we would need added to a language to execute different logic based on the data actually found for a given user.

We explore this question by examining two mathematical concepts: function restriction and function extension. These concepts sound lofty ( as most mathematics tends to sound on your first exposure ) but you will hopefully come to agree that they are quite natural and simple ideas. In particular, function extension is used to explain how mathematics creates functions from smaller functions with certain properties such that they can be used to handle data from different sets.

### Function restriction

  > "A function restricted to a smaller set of inputs"

  Function restriction takes a function mapping elements of A to elements of C and produces a function mapping elements of B, a subset of A, to elements of C.

  f is a function mapping elements of A to elements of C

    Assume f ∈ (A → C)

  g is a function mapping elements of B to elements of C

    Assume g ∈ (B → C)

  B is a subset of A

    Assume B ⊆ A

  g restricts f if all g(x) are the same as f(x)

    Restricts(g,f) ≡ ∀x ∈ B: g(x) = f(x)

### Function extension

  > "A function extended to a larger set of inputs"

  Function extension takes a function mapping elements of A to elements of C and produces a function mapping elements of B, a superset of A, to elements of C.

  A, B, and C are sets

    Assume A ∈ Set
    Assume B ∈ Set
    Assume C ∈ Set

  A is a subset of B

    Assume A ⊆ B

  f is a function mapping elements of A to elements of C

    Assume f ∈ (A → C)

  g is a function mapping elements of B to elements of C

    Assume g ∈ (B → C)

  g extends f if all values of f(x) are the same as g(x)

    Extends(g,f) ≡ ∀x ∈ A: f(x) = g(x)

### Function extension and disjoint sets

  > "A function extended with inputs that are not found in the original inputs may be composed of two functions that operate on separate inputs"

  If A and B are disjoint sets meaning they contain no common elements then extending a function from A → C with B may be written g : (A + B) → C. This resulting function may be composed of two functions from A → C and B → C along with a predicate that checks to see if the input is an element of either A or B. In other words, the larger function is really just an if-then-else expression where the condition is a check for being an element of either A or B.

  A and B are disjoint sets containing no common elements

    Assume A ∪ B = Ø

  f is a function from A → C

    Assume f ∈ (A → C)
  
  g is a function from B → C

    Assume g ∈ (B → C)

  h is a function extending f with g

    h ∈ (A + B) → C
    h(x) = { f(x), x ∈ A } 
           { g(x), x ∈ B }

### An example implementing if-then-else

  > If-then-else is a function composed of a function from (0 → C) with a function from (1 → C)

  We can build the familiar notion of if-then-else out of the set representing true ({1}) the set representing false ({0}). To do this, we'll define a function called if_then_else that executes a function f if x is in {1} and a function g if x is in {0}.

  True is the set containing the number 1

    Assume True ≡ {1}

  False is the set containing the number 0

    Assume False ≡ {0}

  f is a function from True to String

    Assume f ∈ (True → String)

  g is a function from False to String

    Assume g ∈ (False → String)

  if_then_else is a function from True or False to String

    if_then_else ∈ (True + False) → String
    if_then_else(x) { f(x), x ∈ True } 
                    { g(x), x ∈ False }

  We can see that we can now pass our function a value from the set True OR from the set False and be confident that we will execute a function of the appropriate signature. This ability to discriminate between the Sum of two domains is made possible by the two domains ( here True and False ) being disjoint.

### What to do when there IS overlap in the two sets we wish to discriminate between

  > "Distinguish between two sets by pairing them with two disjoint sets."

  If we are modeling a user's email and name as elements of the set String then our strategy from above won't work. This is because our function for emails and our function for names both operate on the set String which is obviously not disjoint with itself.
  
    Disjoint(String,String) = false

  However, we could annotate each element with a disjoint "tag" such that the two resulting sets would be disjoint. Specifically, we can create a cartesian product of the word "Email" with every String that should be an email and the word "Name" with every String that should be a name:

    Email × boof@gmail.com = (Email, boof@gmail.com)
    Name × BigBoof = (Name, BigBoof)

  By doing this, we are guaranteeing that a name that LOOKS like an email will not ever be confused for an email. Specifically, if we one user named "ted@gmail.com" and another user with email "ted@gmail.com" they will be stored as elements of two disjoint sets:

    (Email,ted@gmail.com) and (Name,ted@gmail.com)

  Let's see why this works...

  Email is the set containing the String "Email"

    Assume Email ≡ {"Email"}

  Name is the set containing the String "Name"

    Assume Name ≡ {"Name"}

  Email and Name are disjoint

    Disjoint(Name,Email) = true

  Email × String is disjoint to Name × String

    Disjoint(Email × String,Name × String)

  In the general case, any disjoint sets A and B may be used to make disjoint A × C and B × C

    Assume A ∈ Set
    Assume B ∈ Set
    Assume C ∈ Set
    Assume S ∈ Set
    Assume Disjoint(A,B)
    Assume Disjoint(A × S, A × S)
    Assume f ∈ (S → C)
    Assume g ∈ (S → C)

    h ∈ (A × S) + (B × S) → C
    h(tag, x) = { f(x), tag ∈ A } 
                { g(x), tag ∈ B }
  
  That "tag sets" A and B being disjoint allows us to use them to discriminate between two different kinds of data being modeled by the underlying set String. In turn, we can invoke the function f for Strings that were tagged with A and the function g with Strings that were tagged with B. Indeed, this is the fundamental meaning of a sum-type which is, now understandbly, sometimes called a "disjoint-union".

### Languages that include sum-types already

There are many popular languages that do have some support for sum-types. This section simply shows an example of one such language, Haskell, and uses it to illustrate where the above notion of "tag-sets" fits into the syntax of the language.

Let's define a User data type as we did above in Haskell:

```haskell
data User = Email String | Name String
```

That's it. The identifiers Email and Name must be disjoint as explored above enabling functions over users to discriminate between them and execute the appropriate function:

```haskell
processUser :: User -> LoginStatus
processUser (Email email) = validate email
processUser (Name name)   = lookupInCache name
```

The details of these illustrative functions don't matter but they show the power of function extension over disjoint sets.