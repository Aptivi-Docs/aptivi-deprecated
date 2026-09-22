---
description: Welcome to ColorSeq!
---

# 👋 Welcome!

{% hint style="info" %}
ColorSeq is being replaced by Terminaux. We recommend that your new projects use Terminaux. The migration guide will be available under the Terminaux manual as soon as it's released.
{% endhint %}

Welcome to ColorSeq! It's a library that manages the VT color sequences and gets information about them. It's used to print the VT sequences to change the color, check whether the color is bright or dark, get RGB values from 255 colors, and much more.

To use this library, go to any page in the left side of the screen.

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/ColorSeq/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="ColorSeq" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the ColorSeq functions.

{% hint style="info" %}
You can also install this library under Rust, though this port may have limitations compared to the C# versions. Go to [this page](https://crates.io/crates/colorseq) to download the dependency to your app or your library.
{% endhint %}
