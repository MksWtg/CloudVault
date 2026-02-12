In software, a service is a class with a group of methods that are all related. The service class acts as a logical organization tool for the methods. Services are typically stateless (they contain logic to do things but don't remember information from previous invocations).

Since services have clear concerns, any work that needs to be done that requires data or logic that the service is handled by 'dependencies'

Specifically in ASP.NET, A service is any class whose dependencies are injected via ASP.NET dependency injection.