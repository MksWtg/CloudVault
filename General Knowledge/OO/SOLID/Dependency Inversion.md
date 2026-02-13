Dependency Inversion is the 5th SOLID principle. It states that high level classes should not depend on low level classes. Both should depend on abstractions (e.g. interfaces, or abstract classes).

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

>Note: Dependency Inversion is commonly achieved through [[Dependency Injection]]
