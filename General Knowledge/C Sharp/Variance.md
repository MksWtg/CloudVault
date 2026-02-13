Extra reading: https://mukundks2004.github.io/BetweenBooks/posts/what-is-the-co-in-covariant/
Note that both the linked article and the following note are written in a somewhat technical way.
Prerequisites: [[Generics]]
## What is Variance: Requirements

Variance needs two things to exist, without these it doesn't make sense to talk about variance. The first is that the set of types in a programming language need to form a poset. This is the case in C#. 

>Let $P$ be the set of all types. There is a partial order $(P, \le)$ where $\le \subseteq P \times P$ satisfying reflexivity, transitivity, and antisymmetry, given by $a \le b$ if an instance of $a$ can be assigned to an identifier of type $b$.

The second is that types need to be able to index other types. C# supports this with generics.

Variance is a property of type constructors. A type constructor `F` (with type parameter `T`) is described as being one of 'covariant', 'contravariant', 'invariant' or 'bivariant' in `T`. When there is only one type parameter, `T` is implicit when describing the variance of `F`. We simply say `F` is covariant, for example.

### Ok, But What Is It Actually

Variance describes how one variable varies as another varies. Loosely speaking, if they are positively correlated they are covariant and if they are negatively correlated they are contravariant. If one cannot vary at all while the other varies they are invariant or bivariant depending on which is which. This is the same reasoning behind the 'variant' terminology in other fields, such as this one: https://en.wikipedia.org/wiki/Covariance_matrix.

In the context of programming, the independent variable is the indexing type `T` and the dependent variable is the type `F<T>`.

![[Pasted image 20260213162551.png]]

## How Can Types Vary

Let's look at some code.

Consider this inheritance chain:

```C#
class Animal {}

class Canine : Animal {}

class Dog : Canine {}

class Poodle : Dog {}
```

This creates the poset `{(Poodle, Dog), (Dog, Canine), (Canine, Animal), (Dog, Canine), (Dog, Animal), (Canine, Animal)}`.

We know that $Poodle \le Dog$ for example, because we can compile: 
```C#
Poodle a = new Poodle();
Dog b = a;
```

Now fix the type constructor `List`. Will the following code compile?

```C#
List<Poodle> a = new List<Poodle>();
List<Dog> b = a;
```

In other words, does the transformation of the poset $P$ by the functor `List` preserve the poset?

In this case no. Although `Poodle` $\le$ `Dog`, `List<Poodle>` $\nleq$ `List<Dog`. Logically, this is because if we did assign `a` to `List<Dog> b`, we would be able to perform `b.Add(new Doberman());` and treat `a` as if it really were `b`. Which it isn't. Adding a doberman to a list of poodles violates type safety.

What is an example that is covariant? The `IEnumerable<T>` interface. This code compiles:
```C#
IEnumerable<Poodle> a = new List<Poodle>();
IEnumerable<Dog> b = a;
```

What is an example that is contravariant? The `Action<T>` delegate. This code compiles:
```C#
Action<Dog> a = (x) => new Dog();
Action<Poodle> b = a;
```

What is an example that is bivariant? Anything not generic, trivially, although C# doesn't officially support annotating generics with