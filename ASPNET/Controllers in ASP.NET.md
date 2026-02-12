A controller in ASP.NET is a C# class that handles incoming HTTP requests and returns responses, such as JSON (information) or HTML (a webpage). Classes in OO are very useful for organizing related code together. Controllers are just classes- they group related request handling logic (for example all customer system related requests might go into one class, one controller). Controllers are invoked by the routing system when a matching URL and HTTP verb is requested.

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

The above code is an example controller. It is a class, it has a rule for what requests come to it based on URL (those ending with `/api/hello`). Controllers have methods for different subroutines that should run based on the path parameters of the request (e.g. a request ending in `items` might go to one C# method and requests ending in `buy` might go to another). This controller has one method `Get` that will only be accessed if the incoming HTTP request uses a `Get` HTTP verb. It returns an `IActionResult` object with a message. `Ok` returns code `200`.