---
description: Welcome to NameNumerizer!
---

# 👋 Welcome

Welcome to NameNumerizer! It's a library that lets you numerize all the tracks that are found in the folder of your choice. It renames all the tracks to the format that has the track number prior to the artist and the song name. For example:

```
Before: Allen Watts & Chris Schweizer - Cabrones (Extended Mix).mp3
After:  012. Allen Watts & Chris Schweizer - Cabrones (Extended Mix).mp3
        It's not necessarily number 12. It could be any position in your tracklist.
```

To use this library, go to any page in the left side of the screen.

{% hint style="warning" %}
Currently, the console application only supports numerizing the tracks that are in these formats: `.mp3, .wav, .ogg, .aac`. However, we hope to expand the support in the future. Meanwhile, use the core library provided.
{% endhint %}

## Installation

This library is very easy to install. It's available at [NuGet](https://www.nuget.org/packages/NameNumerizer/). Just follow these steps:

1. Open your project file (`.csproj` or `.fsproj`)
2. Place the `PackageReference` line on a property group like so:
   * `<PackageReference Include="NameNumerizer" Version="x.x.x" />`
   * ...where `Version` is the current version of the library
3. Run a package restore using `dotnet restore`

If you follow these steps correctly, you should be able to use the NameNumerizer functions.
