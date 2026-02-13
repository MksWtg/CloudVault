Extra reading: https://mukundks2004.github.io/BetweenBooks/posts/what-is-the-co-in-covariant/
Note that both the linked article and the following note are written in a somewhat technical way.
Prerequisites: [[Generics]]
## What is Variance

Variance needs two things to exist, without these it doesn't make sense to talk about variance. The first is the set of types in a programming language need to form a poset. This is the case in C#- there is a partial order $(P, f : T x T -> 

Variance is a property of type constructors. A type constructor `F` (with type parameter `T`) is described as being one of 'covariant', 'contravariant', 'invariant' or 'bivariant' in `T`. When there is only one type parameter, `T` is implicit when describing the variance of `F`. We simply say `F` is covariant, for example.

So how do we know which it is?

Variance describes how one t
