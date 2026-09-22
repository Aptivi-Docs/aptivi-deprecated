---
description: Welcome to SemanVer!
---

# 👋 Welcome!

Welcome to SemanVer! It's a library that parses your semantic version strings according to the [SemVer 2.0](https://semver.org/) standards.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/SemanVer/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="SemanVer" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the SemanVer functions.
