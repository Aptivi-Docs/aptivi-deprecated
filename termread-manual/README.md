---
description: Welcome to TermRead!
---

# 👋 Welcome!

{% hint style="info" %}
TermRead is being replaced by Terminaux. We recommend that your new projects use Terminaux. The migration guide will be available under the Terminaux manual as soon as it's released.
{% endhint %}

Welcome to TermRead! It's a next-generation console reader that allows you to flexibly write your input to the console without any limitations.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/TermRead/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="TermRead" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the TermRead functions.
