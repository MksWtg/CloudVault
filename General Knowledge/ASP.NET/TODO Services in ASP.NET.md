In software, a service is a class with a group of methods that are all related. The service class acts as a logical organization tool for the methods. Services are typically stateless (they contain logic to do things but don't remember information from previous invocations).

Since services have clear concerns, any work that needs to be done that requires data or logic that the service is handled by 'dependencies'. The class that has the power/permission/data to execute an operation (typically another service) is provided to the service class as an object through the constructor. This object is known as a dependency, as the service depends on it to function. The service now has the ability to invoke this specific functionality through the specialized dependency.

[EXAMPLE]

Specifically in ASP.NET, services need to have their dependencies injected by the built in ASP.NET dependency injection system.