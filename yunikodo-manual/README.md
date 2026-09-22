---
description: Welcome to Yunikodo!
---

# 👋 Welcome!

Welcome to Yunikodo! It's a library that hosts Unicode character information for all the known characters. This information is taken from the Unicode UCD.

To use this library, go to any page in the left side of the screen.

{% hint style="info" %}
This library is demanding because it loads an XML file with +100000 Unicode characters, so you need at least 8 GB RAM to 16 GB RAM to be able to run applications that use Yunikodo.
{% endhint %}

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/Yunikodo/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="Yunikodo" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the Yunikodo functions.
