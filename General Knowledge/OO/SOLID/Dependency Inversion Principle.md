
Prerequisites: [[Services in Software]]

The Dependency Inversion Principle is the 5th SOLID principle. It states that high level classes should not depend on low level classes. Both should depend on abstractions (e.g. interfaces, or abstract classes).

## Bad Example

```C#
public class HomeController : Controller
{
    private readonly SmtpEmailSender _emailSender;  // depends on concrete class!

    public HomeController()
    {
        _emailSender = new SmtpEmailSender(); // tightly coupled
    }

    public IActionResult Index()
    {
        _emailSender.SendEmail("test@example.com", "Hello");
        return View();
    }
}
```

What are the problems with the above?
1) To switch the email provider, you need to modify the `HomeController` class, and other classes that use an email provider (tightly coupled)
2) Hard to test because you cannot mock `SmtpEmailSender`.

Current situation visualized: High level class depends on low level class.

![[Pasted image 20260213144530.png]]

## Fixed Example

Instead of `HomeController` and other services specifically requiring the services of `SmtpEmailSender`, we create an abstraction: an object representing the operations `HomeController` will outsource to an email provider.

```C#
public interface IEmailSender
{
    void SendEmail(string to, string message);
}
```

`SmtpEmailSender` implements this interface.

```C#
public class SmtpEmailSender : IEmailSender
{
    public void SendEmail(string to, string message)
    {
        // send via SMTP
    }
}
```

Finally, inject this abstraction.

```C#
public class HomeController : Controller
{
    private readonly IEmailSender _emailSender;

    public HomeController(IEmailSender emailSender)
    {
        _emailSender = emailSender; // injected
    }

    public IActionResult Index()
    {
        _emailSender.SendEmail("test@example.com", "Hello");
        return View();
    }
}
```

We have achieved loose coupling, the high level module doesn't care about low level details. We have also fixed the problems from before:
1) ~~To switch the email provider, you need to modify the `HomeController` class, and other classes that use an email provider (tightly coupled)~~ We can swap the implementation of `IEmailSender` wherever the object is instantiated.
2) ~~Hard to test because you cannot mock `SmtpEmailSender`.~~ We can inject our own `IEmailSender` with controlled behaviours rather than using the real thing.

![[Pasted image 20260213145406.png]]

Both the high level class and the low level class are now depending on an abstraction.

>Note: Dependency Inversion is commonly achieved through [[Dependency Injection]].
