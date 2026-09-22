---
description: Welcome to Inxi.NET!
---

# 👋 Welcome!

Welcome to Inxi.NET! It's a Linux and Windows hardware information frontend using Inxi and Windows Management Instrumentation (WMI) as its backend for getting system information.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/Inxi.NET/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="Inxi.NET" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use Inxi.NET's functions.
