---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `Inxi.NET` namespace in any piece of code you want to use the library, as in: `using InxiFrontend;`

In order to get hardware information, just invoke the `Inxi` constructor when assigning a new variable that holds hardware information. For example,

```csharp
var InxiInstance = new InxiFrontend.Inxi();
```

This gets all hardware information from your computer, assuming that you have the following files installed on your Linux computer:

* `/usr/bin/inxi`
  * Can be obtained by installing Inxi using your favorite package manager (usually `inxi`)
* `/usr/bin/cpanel_json_xs`
  * Can be obtained by installing CPanel Json Perl Module using your favorite package manager (usually `libcpanel-json-xs-perl`)
* `/usr/bin/json_xs`
  * Can be obtained by installing Json Perl Module using your favorite package manager (usually `libjson-xs-perl`)

In order to selectively parse the computer hardware information, you can use the constructor that lets you set the hardware type to be parse:

```csharp
var InxiInstance = new InxiFrontend.Inxi(InxiHardwareType.type);
```

where `type` is:

* `InxiHardwareType.BIOS`
* `InxiHardwareType.Graphics`
* `InxiHardwareType.HardDrive`
* `InxiHardwareType.HardDriveLogical`
* `InxiHardwareType.Machine`
* `InxiHardwareType.Network`
* `InxiHardwareType.PCMemory`
* `InxiHardwareType.Processor`
* `InxiHardwareType.Sound`
* `InxiHardwareType.System`
* `InxiHardwareType.Battery`

Very rarely, if your system doesn't have the above paths to required programs (either you've compiled Json Perl modules using CPAN, or you've downloaded Inxi straight from its source code, or you've got both), you can supply the paths to the three different paths by invoking the third version of the constructor:

```csharp
var InxiInstance = new InxiFrontend.Inxi("path/to/inxi", "path/to/cpanel_json_xs", "path/to/json_xs", InxiHardwareType.type);
```

You can then use the `InxiInstance.Hardware` class to obtain info about your computer's hardware.

For debugging, listen to the `DebugDataReceived` event by adding the event handler to it, for example:

```csharp
InxiTrace.DebugDataReceived += HandleDebugData;
```

If you're going to use functions, you must implement the function with the following signature (function name can be changed):

```csharp
private static void HandleDebugData(string Message, string PlainMessage)
    => Console.WriteLine(Message);
```
