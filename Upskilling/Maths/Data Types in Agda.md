
Define data types the following way:

```agda
data {name} : {sort} where
	{constructor1} : {param1} -> {name}
	{constructor2} : {param1} -> {param2} -> {name}
```

The curly braces indicate name.

You can have as many data constructors as you like.

e.g.

```agda
data Nat : Set where
    zero : Nat
    succ : Nat -> Nat
```

