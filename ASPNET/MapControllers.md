(TODO: confirm this) `MapControllers` runs once when the app starts up, it is not middleware. It reads all methods in all controllers and it builds a list of all possible URLs the app can handle and stores them in the routing system before any request ever arrives.

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
Before the requests actually come through runs, `MapControllers` knows that if a request were to come through on a URL like `/api/products/5`,  