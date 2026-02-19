
Monads are a pattern in functional programming. The aim of a monad is to be able to sequence computations.

## Rationale

In functional programming, functions are pure and don't have side effects.

Effects, like writing to a file or printing to a console are modelled using return types like `IO`.
