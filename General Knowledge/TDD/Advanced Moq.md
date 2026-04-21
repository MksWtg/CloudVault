Prerequisites: [[Mocking]], [[What is Moq]]

When you write 
`var mock = new Mock<IMyService>();`

Moq uses Castle DynamicProxy to generate a new class at runtime that implements `IMyService` that has the implementations that you have set up. the class looks something like

```csharp
class Proxy_IMyService : IMyService
{
    public string GetData() {
        return interceptor.Handle("GetData");
    }
}
```

`mock.Object` returns an instance of this.

When you write `mock.Setup(x => x.GetData()).Returns("hello");`

Moq does not just store the lambda/delegate instance, it stores the expression tree of the code.