While services are not specific to ASP.NET and the generic software definition applies to ASP.
### Registering Services

Specifically in ASP.NET, services need to be registered to be considered services. This enables them to have their dependencies injected by the built in ASP.NET dependency injection library (called the DI container). To learn more read [[DI in ASP.NET]].

In the `Program.cs` entry point into the ASP.NET app, there will be a `WebApplicationBuilder` object used to configure the app. You can add this code to the `Program.cs` to register a service, and help its dependencies get instantiated:

`builder.Services.AddScoped<OrderService>()`

### Registering Controllers

 Controllers are the highest level of classes. They are stateless, and they require services as dependencies, so they can be treated as services themselves. They also need to be registered:
 
`builder.Services.AddControllers();`