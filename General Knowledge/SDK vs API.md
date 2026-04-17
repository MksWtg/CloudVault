
These two terms often confuse me. The definition is a bit blurry, but if there is a difference here it is:

1) SDK is language specific (like a C# library) while API is language agnostic (like an endpoint)
2) SDK is delivered as a package/library; API is delivered as a service/endpoint
3) SDK contains code; API defines a contract (endpoints) that may be implemented elsewhere.
4) SDK wraps the API to simplify usage (reduces boilerplate).

An SDK is a language-specific wrapper around an API.

Examples of APIs:
- dog API: `https://dog.ceo/api/breeds/image/random`

Examples of SDK:
- realsense sdk: `https://www.realsenseai.com/developers/sdk-2/` (wraps the low level hardware api, e.g. reading data streams and usb devices)

an SDK is also bigger than a library. It is the library that abstracts over the API + additional tools, like how the dotnet sdk includes command line tools such as dotnet build, dotnet pack, dotnet test