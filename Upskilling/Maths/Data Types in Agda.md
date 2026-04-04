
Define data types the following way:

```agda
data {name} : Sort where
	constructor1 : param1 -> name
	constructor2 : param1 -> param2 -> name
```

You can have as many data constructors as you like.