---
description: Welcome to NativeLand!
---

# 👋 Welcome

{% hint style="info" %}
This library is going to be replaced soon, and this manual is not updated for version 2.0.0. Refer to the SpecProbe manual for [more info about the merger](https://app.gitbook.com/s/HwStOOqLbZN15cxkDYf6/usage/how-to-use#native-libraries).
{% endhint %}

Welcome to NativeLand! It's a C# library that allows you to load native libraries for all the platforms and CPU architectures. It supports .NET Framework 4.8 and .NET Core 3.1 or higher.

To use this library, go to any page in the left side of the screen.

{% hint style="info" %}
Normally, you won't need to use this library on .NET Core 3.1+ applications unless you're maintaining compatibility with .NET Framework 4.8. A good alternative is [NativeLibrary](https://learn.microsoft.com/en-us/dotnet/standard/native-interop/native-library-loading) built into .NET Core 3.1 or higher.
{% endhint %}

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/SpecProbe/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="NativeLand" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use this library's functions.
