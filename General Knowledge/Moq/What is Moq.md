Moq is a popular C# library used for mocking interfaces and methods. Typically mocking occurs in unit tests, not in production code, so moq i used on top of a testing framework such as Nunit ([[What is Nunit]]).

## Example

Here is an interface called `IUserRepository` which defines a method to get a username given an id.

```csharp
public interface IUserRepository
{
    string GetUserName(int userId);
}
```

`IUserRepository` is a dependency for `UserService` that needs to be able to get the user by id to do higher level operations, like greeting the user.

```csharp
public class UserService
{
    private readonly IUserRepository _repository;

    public UserService(IUserRepository repository)
    {
        _repository = repository;
    }

    public string GreetUser(int userId)
    {
        var name = _repository.GetUserName(userId);
        return $"Hello, {name}!";
    }
}
```

Note how `UserService` accepts the dependency through the constructor as per good practices outlined in [[Dependency Injection]]. This enables swapping out implementations of `IUserRepository` for testing and production, which is what we will do. The real `IUserRepository` will probably ping th