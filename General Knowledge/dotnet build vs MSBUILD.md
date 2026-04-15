
These are both executables for building .NET code (turning source into IL).

## msbuild

Historically used for .NET framework. now it is cross platform.
old msbuild was tied to .NET framework and shipped with vs
modern msbuild is invoked by dotnet build or dotnet msbuild (see below) and works anywehre .NET runs

E.g. `msbuild MySolution.sln`

## dotnet

Internally calls `msbuild` but abstracts it, designed for modern SDK-style projects
cross platform


TL;DR use dotnet build


Roslyn (the C# compiler platform) is a .NET Standard 2.0 library, meaning that it can run on both .NET Framework 4.6.1+ and .NET Core 2.0+(1).

Visual Studio, which includes MSBuild, runs on .NET Framework. When you build a project using Visual Studio (or directly using MSBuild), it runs Roslyn on .NET Framework. Visual Studio knows how to process both SDK-style csprojs and the legacy non-SDK-style csprojs, and invoke Roslyn accordingly. The version of Roslyn which is used is tied to the Visual Studio version.

`dotnet build` is a separate tool, and is a .NET Core application. It knows how to build SDK-style csprojs only, and it does this by running Roslyn on .NET Core. Roslyn is distributed with the .NET Core SDKs, and `dotnet build` loads Roslyn from one of these installed SDK versions (normally the latest).

These two ways of building a C# project are more-or-less equivalent, and they invoke the same compiler code. However, they differ on where they can run (Visual Studio is .NET Framework and Windows-only, `dotnet build` is .NET Core and can run on multiple platforms), and whether they can build legacy non-SDK-style csprojs. `dotnet build` is also a bit nicer to use from the command-line.

Note that the runtime which Roslyn is loaded into has no bearing on the compiled IL which Roslyn can emit: Roslyn running on .NET Framework can emit IL which is executed by .NET Core just fine, and vice versa.

If you are using analyzers which target .NET Core (unlikely, as Analyzers are encouraged to target .NET Standard 2.0), these will only run from `dotnet build`.