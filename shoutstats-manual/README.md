---
description: Welcome to ShoutStats!
---

# 👋 Welcome!

Welcome to ShoutStats! It's a library that allows you to get the detailed statistics from the Shoutcast server according to its API. It uses the Shoutcast `/7.html` and the `/statistics` APIs, so it's compatible with Shoutcast 1.0 and 2.0 servers.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/ShoutStats/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="ShoutStats" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the ShoutStats functions.
