
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
	// note: review this
	// we should be able to differentiate an expression wrt another expression
	// variable is standard, constant is trivial, wrt another expr is kind of complicated
	// du/dv = du/dx / dv/dx
		// two problems: where do we get the division operator and where do we get "x"
		// neither of these are captured in du/dv
	// IExpression Differentiate(IExpression wrt);
	
	IExpression Differentiate(Variable wrt);
	
	
}

public class Variable : IExpression
{
	public required string Identifier { get; init; }
	
	// We are differentiating a variable wrt a variable, a variable is atomic and not a function of antoher variable
	public IExpression Differentiate(Variable wrt)
	{
		if (this.Identifier == wrt.Identifier)
		{
			return new Constant(1);
		}
	}
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