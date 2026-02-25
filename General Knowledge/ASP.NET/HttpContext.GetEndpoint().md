Prerequisites: [[HttpContext]]

`GetEndpoint()` is an extension method that retrieves the chosen endpoint for the current request. 

An endpoint is:
- A delegate that will execute for the request (like a controller action, minimal api route, razor page)
- Associated metadata such as display name

#### Signature

`public static Endpoint GetEndpoint(this HttpContext context);`

## When Does GetEndpoint() Return an Endpoint?

If routing system finds a match via controller, minimal api or razor page, GetEndpoint() returns an Endpoint object representing the route.

```csharp
var endpoint = context.GetEndpoint();
Console.WriteLine(endpoint.DisplayName);
// e.g., "MyApp.Controllers.WeatherController.GetWeather (GET)"
```