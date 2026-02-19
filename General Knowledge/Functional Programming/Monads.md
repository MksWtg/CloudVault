Prerequisites: [[What is Functional Programming]], [[Patterns]]

Monads are a pattern in functional programming. The aim of a monad is to be able to sequence computations.

## What is a Monad

A monad is anything that implements the monadic interface (or typeclass in haskell). This interface requires the following:

- A type constructor `T` of kind `* -> *` representing an embedding of a type into a context.
- A way to enter an instance of `a` into the ecosystem and get back `T[a]`. This action is called return.
- A way to take 1) data in context (an instance of `T[a]`), 2) a function that sends maps data and embeds it in context (an instance of `a -> T[b]`) and get back data in context after the mapping. This action is called the monadic bind, or `(>>=)`.

### In Code

Example in haskell:

```haskell
class Monad m where
    return :: a -> m a
    (>>=) :: m a -> (a -> m b) -> m b
```

The above definition is what 90% of developers would accept as a monad, but there is an argument to be made that this is not technically correct. 

1) Firstly see * for how monads are defined in haskell.
2) Secondly, this definition leverages [[Higher-Kinded Types]] to be generic- `m a` can be `List<int>` or `Maybe<string>` or anything of kind `* -> *` (HKTs allow the developer to abstract over type constructors). Monads are constructable in languages like C# that do not have HKTs, but this generic interface must be forgone.
3) Thirdly, this definition does not mandate that the monad follows the [[Monadic Laws]]. [If you are a dependently typed programmer, this might look kind of sparse to you](https://youtu.be/caSOTjr1z18?si=cOPwgNM4i2CuL9nf&t=1160) without those laws enforced.


## Rationale

In functional programming, functions are pure and don't have side effects.

Effects, like writing to a file or printing to a console are modelled using return types like `IO`.

Since we are constantly modelling effects with types, we are constantly wrapping results in containers.

Monads are the framework that enables entering data into the ecosystem (with unit) and chaining actions on wrapped data (with bind).

> * In haskell, which is the only language in which most developers use monads as a formal construct, the given definition is historically correct and functionally correct. But technically, following the [[FAMP]], Monads in haskell must inherit from the `Applicative` typeclass.
