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

When the method finally gets called for real with: `mock.Object.GetData();` it inspects this expression tree to decide what to do, letting it keep track of what functions get called, matchers such as `It.IsAny<int>()` etc.

If you used an ordinary delegate you wouldn't be able to track what it calls or pattern match the arguments.

## Proxy

a "proxy" from Castle DynamicProxy is a runtime-generated object that stands in place of your real type and intercepts all calls to it.

If you have:

```csharp
public interface IMyService
{
    string GetData();
}
```

Castle generates a proxy:

```csharp
public class MyServiceProxy : IMyService
{
    private readonly IInterceptor _interceptor;

    public string GetData()
    {
        return (string)_interceptor.Intercept(
            method: "GetData",
            args: []
        );
    }
}
```