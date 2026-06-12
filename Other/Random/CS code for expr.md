
```cs
public class Program
{
	public static void Main(string[] args)
	{
		Console.WriteLine($"Output: {string.Join(",", args)}");
	}
}

public interface IExpression { }

public class Variable : IExpression
{
	public required string Identifier { get; init; }
}

public class Constant : IExpression
{
	public required string Value { get; init; }
}

public class UnaryOperation
{
	public UnaryOperation()
}

// an expression is either an entity, or a unary operation of an entity or a binary operation of an entity
```