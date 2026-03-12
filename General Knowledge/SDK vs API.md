
These two terms often confuse people. Here are the differences:

1) SDK is language specific (like a C# library) while API is language agnostic 
2) SDK is delivered as a package/library; API is delivered as a service/endpoint
3) SDK contains code; API defines a contract (endpoints) that may be implemented elsewhere.
4) SDK wraps the API to simplify usage (reduces boilerplate).

An SDK is a language-specific wrapper around an API.

Examples of APIs:
- dog API: `https://dog.ceo/api/breeds/image/random`

Examples of SDK:
- realsense sdk