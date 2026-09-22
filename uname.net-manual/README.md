---
description: Welcome to Uname.NET!
---

# 👋 Welcome!

Welcome to Uname.NET! It's a simple Unix-only library that allows you to get some information about the Linux/Darwin kernel. It's a sister library to Inxi.NET.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/Uname.NET/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="Uname.NET" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the Uname.NET functions.
