While services are not specific to ASP.NET and the generic software definition applies to ASP.NET, ASP.NET services are usually subject to specific conventions/patterns.
### Registering Services

ASP.NET, services need to be registered to be considered services. This enables them to have their dependencies injected by the built in ASP.NET dependency injection library (called the DI container). To learn more read [[Dependency Injection]].

In the `Program.cs` entry point into the ASP.NET app, there will be a `WebApplicationBuilder` object used to configure the app. You can add this code to the `Program.cs` to register a service, and help its dependencies get instantiated:

`builder.Services.AddScoped<OrderService>()`

### Registering Controllers

 Controllers are the highest level of classes. They are stateless, and they require services as dependencies, so they can be treated as services themselves. They don't need to be registered manually, this is handled by ASP.NET.

> Note: as a rule of thumb for ASP.NET, and actually all software frameworks, if there is really only one way something can be done then the framework handles it for you. There is no easy way to instantiate controllers and their dependencies without all the plumbing that would be the same for every webapp, so ASP.NET handles it.