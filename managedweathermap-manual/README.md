---
description: Welcome to ManagedWeatherMap!
---

# 👋 Welcome!

Welcome to ManagedWeatherMap! It's a OpenWeatherMap API frontend for .NET. It allows you to see the weather conditions in a city with detailed information about the forecast.

To use this library, go to any page in the left side of the screen.

{% hint style="info" %}
It currently only supports the free weather and forecast information API. It doesn't support paid features yet. If you can contribute, great!
{% endhint %}

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/ManagedWeatherMap/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="ManagedWeatherMap" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the ManagedWeatherMap functions.
