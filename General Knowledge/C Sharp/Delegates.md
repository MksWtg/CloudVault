Delegates are type safe function pointers in C#. A delegate when defined is given a series of input types and an output type. This delegate can now reference any inputs whose inputs match the input type and whose output matches the output type.

```csharp
// Define a delegate type
public delegate int MathOperation(int x, int y);

```