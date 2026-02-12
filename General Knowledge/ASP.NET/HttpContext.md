HttpContext is a class in ASP.NET. Every time a new request comes into ASP.NET, a new HttpContext object is created that has all the information in the request such as:
- The method (`GET`, `POST`, `PUT`)
- Request information such as headers, the URL, form data, the query string
- The response status code
- Information about the authenticated user, session, etc.
- Client connection information

This is really important and valuable information! So HttpContext is a frequently accessed class.

## Accessing HttpContext Information

The process for getting data from HttpContext changes depending on where you try to access it. Prerequisites for reading forward: [[TODO DI in ASP.NET]].

### Controllers
All controllers inherit from `ControllerBase` which has a `HttpContext` property (not to be confused with the class name). This property is not dynamically reassigned for each request, it is a 1:1 between controller instances and `HttpContext` instances. This implies a new controller class is instantiated for every request!

### Middleware
The main executing method for middleware is passed `HttpContext` as a parameter. The signature is: `public async Task Invoke(HttpContext context)`.

### Services
A service is a typically stateless class with methods g