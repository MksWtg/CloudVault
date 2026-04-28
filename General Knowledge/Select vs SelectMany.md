`Select` and `SelectMany` are both LINQ methods

Select is a one to one projection- for each element in the sequence it selects one thing. So your output size corresponds to your input size.

```csharp
var numbers = new[] { 1, 2, 3 };

var squares = numbers.Select(x => x * x);
// Result: { 1, 4, 9 }

var squares = numbers.Select(x => 1);
// Result: { 1, 1, 1 }
```

SelectMany is used when each element returns a collection and then you flatten it.

```csharp
var words = new[] { "hello", "world" };

var chars = words.SelectMany(w => w.ToCharArray());
// Result: IEnumerable<char>
// { 'h','e','l','l','o','w','o','r','l','d' }
```