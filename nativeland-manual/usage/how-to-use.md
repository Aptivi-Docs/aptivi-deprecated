---
description: How do I use this library?
---

# 🖥️ How to use

This library contains a class that manages how to load the libraries according to both the operating system and the architecture specification using different paths, called `LibraryManager`. This allows you to load native libraries by copying the native library file or stream to a file in the application executable directory.

You just need to get a byte stream for either your file or a resource found inside your application using one of the available methods, such as [`Assembly.GetManifestResourceStream()`](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.assembly.getmanifestresourcestream?view=net-8.0) + [`Stream.CopyTo()`](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.copyto?view=net-8.0) for embedded resource streams or [`File.ReadAllBytes()`](https://learn.microsoft.com/en-us/dotnet/api/system.io.file.readallbytes?view=net-8.0) for file streams. This is an example of how to create a new instance of the library manager:

```csharp
var libManager = new LibraryManager(
    _factory,
    new LibraryItem(Platform.MacOS, Architecture.X64,
        new LibraryFile("libTestLib.dylib", accessor.Binary("libTestLib.dylib"))),
    new LibraryItem(Platform.Windows, Architecture.X64,
        new LibraryFile("TestLib.dll", accessor.Binary("TestLib.dll"))),
    new LibraryItem(Platform.Linux, Architecture.X64,
        new LibraryFile("libTestLib.so", accessor.Binary("libTestLib.so"))),
    new LibraryItem(Platform.Linux, Architecture.Arm64,
        new LibraryFile("libTestLib.so", accessor.Binary("libTestLib_Arm64.so"))));
```

Once you're done creating new instances of library manager classes, you can now load all of them when needed, as in `LoadNativeLibrary()`. To verify that it's truly loaded, place a P/Invoke of one or more of the library's functions and call it somewhere after initialization.
