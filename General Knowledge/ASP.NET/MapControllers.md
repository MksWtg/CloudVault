`MapControllers` runs once when the app starts up, it is not middleware. It reads all methods in all controllers and it builds a list of all possible URLs the app can handle and stores them in the routing system before any request ever arrives (in `EndpointDataSource`).

E.g. consider the following class

```C#
using Microsoft.AspNetCore.Mvc;

[ApiController]
[Route("api/[controller]")]
public class ProductsController : ControllerBase
{
    [HttpGet]
    public IActionResult GetAll()
    {
        return Ok(new string[] { "Laptop", "Mouse", "Keyboard" });
    }

    [HttpGet("{id}")]
    public IActionResult GetById(int id)
    {
        return Ok($"Product ID: {id}");
    }
}
```
Before the requests actually come through, `MapControllers` knows that if a request were to come through on a URL like `/api/products/5`,  they should go to `GetById`.

You might be asking, well ok mukund, what middleware actually sends the request to the controller then? This is handled by the 'Endpoint Middleware' (internally, in the `EndpointMiddleware` class). Because this is integral to web apps, it gets added by ASP.NET at the end of all middlewares, automatically.

TODO: difference between MapControllers, MapControllerRoute, MapDefaultControllerRoute, etc.
https://stackoverflow.com/questions/59107064/difference-between-mapcontrollerroute-mapdefaultcontrollerroute-and-mapco