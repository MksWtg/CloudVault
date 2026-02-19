Prerequisites: [[What is Functional Programming]], [[Patterns]]

Monads are a pattern in functional programming. The aim of a monad is to be able to sequence computations.

## What is a Monad

A monad is anything that implements the monadic interface (or typeclass in haskell). This interface requires the following*:

- A type constructor `T` of kind `* -> *` representing an embedding of a type into a context.
- A generic function `fmap` that takes inputs of type `a -> b` and returns an instance of `T[a] -> T[b]`
- A way to enter an instance of `a` into the ecosystem and get back `T[a]`. This action is called return.
- A way to take 1) data in context (an instance of `T[a]`), 2) a function that sends maps data and embeds it in context (an instance of `a -> T[b]`) and get back data in context after the mapping. This action is called the monadic bind, or `(>>=)`.

### In Code



## Rationale

In functional programming, functions are pure and don't have side effects.

Effects, like writing to a file or printing to a console are modelled using return types like `IO`.

Since we are constantly modelling effects with types, we are constantly wrapping results in containers.

Monads are the framework that enables entering data into the ecosystem (with unit) and chaining actions on wrapped data (with bind).

> * This definition describes a monad that is historically correct and functionally correct. But technically, following the [[FAMP]], Monads in haskell must inherit 
