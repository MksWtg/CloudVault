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

Prerequisites: [[Unit Testing]]

a "proxy" from Castle DynamicProxy is a runtime-generated object that stands in place of your real type and intercepts all calls to it.

If you have:

```csharp
public interface IMyService
{
    string GetData();
}
```

Castle generates a proxy (it creates a new type at runtime and emits the IL for this type to look like the below, making the cs file would be too slow).

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

When you call `var result = mock.Object.GetData();` you are calling the proxy, which contains an interceptor. The proxy invokes `Intercept(...)` which goes to moq (remember that moq defined this interceptor). Moq records the call for `Verify`, searches for a matching setup that is built from an exception tree (or has a default) and runs that.

If you try to set up a moq object to execute a callback at runtime (which functionally means execute this code instead of just returning a result), you might write something like this:

```csharp
mock.Setup(x => x.Save(It.IsAny<string>()))
    .Callback<string>(s => Console.WriteLine(s));
```

It stores a reference to the callback as a delegate.

When it gets called as `mock.Object.Save("hello");`, the call goes to the proxy, then to moq's interceptor implementation, moq matches the setup to what we defined in the UT. Then mock does `callback("hello");` where callback is what you provided.