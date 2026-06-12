
```cs
public class Program
{
	public static void Main(string[] args)
	{
		Console.WriteLine($"Output: {string.Join(",", args)}");
	}
}

public interface IExpression
{
	IExpression Differentiate(IExpression wrt);
}

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
	public required string Name { get; init; }
}

public class UnaryApplicationApplication : IExpression
{
	public required UnaryOperation operation { get; init; }
	public required IExpression argument { get; init; }
}

public class BinaryOperation
{
	public required string Name { get; init; }
}

public class BinaryOperationApplication : IExpression
{
	public required BinaryOperation operation { get; init; }
	public required IExpression argument1 { get; init; }
	public required IExpression argument2 { get; init; }
}

// an expression is either an entity, or a unary operation of an entity or a binary operation of an entity
```