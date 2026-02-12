A controller in ASP.NET is a C# class that handles incoming HTTP requests and returns responses, such as JSON (information) or HTML (webpage). Classes in OO are very useful for organizing related code together. Similarly, controllers group related request handling logic. Controllers are invoked by the routing system when a matching URL and HTTP verb is requested.

```C#
using Microsoft.AspNetCore.Mvc;

[ApiController]
[Route("api/hello")]
public class HelloController : ControllerBase
{
    [HttpGet]
    public IActionResult Get()
    {
        return Ok("Hello from a controller");
    }
}
```

The above code is an example controller. It is a class, it has a rule for what requests come to it based on url (those ending with `/api/hello`). Controllers have methods for different subroutines that should run based on what request is sent. This controller has one method `Get` that will only be accessed if the incoming HTTP request uses a `Get` method type. It returns an `IActionResult` object with a message. `Ok` returns code `200`.