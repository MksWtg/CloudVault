
Prerequisites: [[What is Nunit]]

Moq is a popular C# library used for mocking interfaces and methods. Typically mocking occurs in unit tests, not in production code, so moq i used on top of a testing framework such as Nunit.

## Example

### Setup

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

Note how `UserService` accepts the dependency through the constructor as per good practices outlined in [[Dependency Injection]]. This enables swapping out implementations of `IUserRepository` for testing and production, which is what we will do. The real `IUserRepository` will probably query a database, this is too heavy duty and expensive for testing, and not our business anyway as the abstraction was created to allow us to focus on the higher level method solely.

### Test

```csharp
using NUnit.Framework;
using Moq;

[TestFixture]
public class UserServiceTests
{
    private Mock<IUserRepository> _mockRepo;
    private UserService _service;

    [SetUp]
    public void Setup()
    {
        _mockRepo = new Mock<IUserRepository>();
        _service = new UserService(_mockRepo.Object);
    }

    [Test]
    public void GreetUser_ReturnsCorrectGreeting()
    {
        // Arrange: setup the mock
        _mockRepo.Setup(r => r.GetUserName(1)).Returns("Alice");

        // Act: call the method under test
        var result = _service.GreetUser(1);

        // Assert: verify result
        Assert.AreEqual("Hello, Alice!", result);

        // Optional: verify the method on the mock was called
        _mockRepo.Verify(r => r.GetUserName(1), Times.Once);
    }
}
```

