# Modding-guide

### What is the mod for the kernel?

The mod is the source code file that loads on boot, and can add extensions to the kernel, the shell, and everything. It can also respond to events. However, the mod can only have one command, and a command code.

This is useful if you want to add your own extensions to the kernel, like event handlers for the kernel.

### Can I make my own screensaver?

Yes, but refer to the `Screensaver modding guide` manual page for instructions on how to add your screensaver.

### Mod types

There are two types of mods: the traditional format, and the dynamic format.

#### Traditional mods

They have the file extension of either a Visual Basic code, or a C# code, as follows:

* C# mods: `<mod>.cs`
* VB.NET mods: `<mod>.vb`

#### Dynamic mods

These mods have the file extension of `.dll`, and can support more than one code file for each mod. This will allow you to make bigger mods that can't fit on one source file, or if you want to separate some parts of the big source code to multiple fragments.

### How to start your own mod on Visual Studio?

If you're going to make a traditional mod, you can follow these steps:

1. On the Start Page, click on New Project
2. Click on Empty Project, select VB or C#, and name your mod or modpack. Make sure the project directory is set to your KSMods directory in your home folder. When you're finished, click OK.
3. Right-click on References on the Solution Explorer, and press `Manage NuGet packages...`
4. Find `KS` and install it. Choose any version that's compatible with your mod.
5. You will see that your KS executable files are added to the references.
6. Right-click on the project, not the solution
7. Change the application type to Class Library
8. On the Compile section, click on Build Events, then write this on the Post-build event command line:
   * If you are using VB:

```cmd
copy ..\..\ModFile.vb ..\..\..\..\ModFile.m
del /Q *.*
"path\to\Kernel Simulator.exe" testMods ModFile.m
```

* If you are using C#:

```cmd
copy ..\..\ModFile.cs ..\..\..\..\ModFileCS.m
del /Q *.*
"path\to\Kernel Simulator.exe" testMods ModFileCS.m
```

10. Make sure the post-build event runs only when the build is successful
11. Save everything by pressing CTRL+S
12. Expand the References section on the Solution Explorer
13. Set the Copy Local setting to False as you have the executable so you don't make an extra copy

If you're going to make a dynamic mod, follow these steps:

1. On the Start Page, click on New Project
2. Click on Class Library (.NET Framework), select VB or C#, and name your mod or modpack. When you're finished, click OK.
3. Right-click on References on the Solution Explorer, and press `Manage NuGet packages...`
4. Find `KS` and install it. Choose any version that's compatible with your mod.
5. You will see that your KS executable files are added to the references.
6. Expand the References section on the Solution Explorer
7. Set the Copy Local setting to False as you have the executable so you don't make an extra copy

Now, follow these steps to create your first mod:

1. Right-click on the project, and go to Add > Class
2. Assume that you're making a mod in VB. Name your mod, but leave the .vb intact. Your mod name should be the one that is included in the Post-build built event. If your mod name is changed, you must also change the post-build event for the changes to be reflected.
3. Click Add, and the code will be ready:

```vb
Public Class ModName
    'Your code here
End Class
```

4. Between the Public Class... and the End Class lines, let Visual Studio know that you're going to create your KS mod by writing: `Implements IScript`
5. Define properties for mod information by putting below the Implements IScript:

```vb
Property Commands As Dictionary(Of String, CommandInfo) Implements IScript.Commands
Property ModPart As String Implements IScript.ModPart
Property Def As String Implements IScript.Def
Property Name As String Implements IScript.Name
Property Version As String Implements IScript.Version
```

6. Make your start mod sub named StartMod() that implements the IScript.StartMod, by writing:

```vb
Sub StartMod() Implements IScript.StartMod
    'If you're going to add commands, write your commands here. Explain what are your commands and what they're going to do.
    Commands = New Dictionary(Of String, CommandInfo) From {{"", New CommandInfo("", ShellCommandType.TestShell, "", False, 0)}, ...}
    Name = "ModName"                 'Replace ModName with your mod name whatever you like, but it SHOULD reflect the mod purpose. You can also use verbs, adjectives, space galaxy names, and so on. This field is required.
    Version = "1.0"                  'You can specify your mod version, but it should follow the versioning guidelines and you can find it on the Internet. This field is required.
    CmdType = ShellCommandType.Shell 'Specify the shell command type
    ModPart = "Main"                 'The name of the mod part

    'Your code below
End Sub
```

7. Replace every `'Your code below` comment with your code. Repeat this step on all the interface subs
8. Make your mod stop sub named StopMod() that implements the IScript.StopMod, by writing: (You can leave it blank)

```vb
Sub StopMod() Implements IScript.StopMod
    'Your code below
End Sub
```

9. Make a command handler, which can be one of the following forms: i) If you're making your commands in your mod, write the response code below:

```vb
Sub PerformCmd(ByVal Command As CommandInfo, Optional ByVal args As String = "") Implements IScript.PerformCmd
    If Command.Command = "" Then
        'Your code below for the first command
    ElseIf Command.Command = "" Then
        'Your code below for the second command
    ElseIf ...
    End If
End Sub
```

ii) If you're making your commands which handle arguments, write the response code below:

```vb
Sub PerformCmd(ByVal Command As CommandInfo, Optional ByVal args As String = "") Implements IScript.PerformCmd
    If Command.Command = "" Then
        If (args = "YourArgHere") Then 'Replace YourArgsHere with your argument set
            'Your code below for the first command
        End If
    ElseIf Command.Command = "" Then
        If (args = "YourArgHere") Then 'Replace YourArgsHere with your argument set
            'Your code below for the second command
        End If
    ElseIf ...
    End If
End Sub
```

iii) If you're making your commands which handle subsequent arguments, write the response code below: (you can change how you handle spaces between arguments)

```vb
Sub PerformCmd(ByVal Command As CommandInfo, Optional ByVal args As String = "") Implements IScript.PerformCmd
    Dim splitArgs As String() = args.Split({" "c})
    If Command.Command = "" Then
        If splitArgs.Length > Command.MinimumArguments Then
            If (splitArgs(0) = "Part1" And splitArgs(1) = "Part2") Then 'Replace Part1 with your argument, and Part2 with your argument. You can also replace the splitArgs(0) = "Part1" And splitArgs(1) = "Part2" with your statement
                'Your code below
            Else
                'Your argument mismatch code below
            End If
        Else
            'Your code that handles not enough arguments
        End If
    ElseIf Command.Command = "" Then
        If splitArgs.Length > Command.MinimumArguments Then
            If (splitArgs(0) = "Part1" And splitArgs(1) = "Part2") Then 'Replace Part1 with your argument, and Part2 with your argument. You can also replace the splitArgs(0) = "Part1" And splitArgs(1) = "Part2" with your statement
                'Your code below
            Else
                'Your argument mismatch code below
            End If
        Else
            'Your code that handles not enough arguments
        End If
    ElseIf ...
    End If
End Sub
```

10. Make an event handler code for your mod, which can be one of the following: i) If you're making your event handler which handles what happened in the kernel, write the handle code below:

```vb
Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    If (ev = "EventName") Then 'Replace EventName with events that are found on "Events for Mod Developers"
        'Your code below
    End If
End Sub
```

ii) If you're handling multiple events, write the handle code below:

```vb
Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    If (ev = "EventName") Then 'Replace EventName with events that are found on "Events for Mod Developers" 
        'Your code below
    ElseIf (ev = "AnotherEvent") Then ' Replace AnotherEvent with events that are found on "Events for Mod Developers" 
        'Your code below
    End If
End Sub
```

iii) IMPORTANT NOTICE! Never try to use infinite loops in handlers unless you're making infinite loops that exits if the specified condition is met, or in the test environment. That will lock the kernel up. 11. Make the same event handler code, but this time, with arguments provided:

```vb
Sub InitEvents(ByVal ev As String, ParamArray Args As Object()) Implements IScript.InitEvents
    If (ev = "EventName") Then 'Replace EventName with events that are found on "Events for Mod Developers" 
        'Your code below
    ElseIf (ev = "AnotherEvent") Then ' Replace AnotherEvent with events that are found on "Events for Mod Developers" 
        'Your code below
    End If
End Sub
```

12. Right-click on the solution and press Build.
13. If your mod is dynamic, copy the output `.dll` file to KSMods directory in your profile folder (`/home/<user>/` in Linux, and `Users\<user>\` in Windows)
14. Run your Kernel Simulator you've just referenced to in your project.

### Optional Stuff

1. You can make your subs anywhere on the class, but if: i) they're on the different class, either press Enter on End Class and make a public new class that stores new subs (traditional mod), or make a separate code file for it (dynamic mod):

```vb
Public Class AnotherClass
    'Your definitions below, and so your subs, functions, interfaces, etc.
End Class
```

ii) they're trying to re-initialize the mod by re-calling StartMod(), Try so on your test environment first, then the production environment if that worked properly. 2. The new subs or functions should meet the following conditions: i) They shouldn't make an infinite loop unless you're making them that exits if specified conditions are met ii) They shouldn't try to cause errors with the kernel. iii) If you're an exploiter and are making the exploit code for the kernel, do so on your test environment first then the production environment, then make your CVE report so we get attention and fix that quickly. iv) If your mod is going to extend the kernel, place your extension codes on separate subs v) Put your sub call on one of the four subs that implements the IScript interface. Ex. If you're going to make a sub that's going to be called on mod start, place your sub call on the StartMod() sub, and then your code on your sub. 3. You can put your custom referenced assemblies in the beginning of your code. Refer to the section below for more information. 4. If you're going to add imports, these rules must be met: 1) Don't import "KS" by itself. KS does that automatically 2) When importing modules/classes like TextWriterColor, it's written like this: Imports KS.TextWriterColor

### Custom Referenced Assemblies

If you want to reference either an extra dependency on either the GAC or as a aeparate file, you can do so by placing either of the following comments in the beginning of your traditional mod code:

* `' Reference GAC: <ref>`: A reference, `<ref>`, that is found on the GAC will be loaded. For example, if you want to implement a mod that uses the `System.IO.Compression.dll`, you can write it like this: `' Reference GAC: System.IO.Compression.dll`
* `' Reference File: <ref>`: A file path to the existing reference. If said reference is not found, the kernel warns about it. You can also use one of the libraries that Kernel Simulator ships, like `Newtonsoft.Json.dll`, `Extensification.dll`, etc.

### Example

Here is the simplest example of how to make a mod:

#### Hello World on Mod Start, and Goodbye World on Mod Stop (traditional)

Hello World is the popular starting example for all of the programmers. These examples usually start with printing the "Hello World" string to the console output or command prompt. To make your first Hello World mod, follow these steps:

1. Right-click on the project, and go to Add > Class
2. Name your mod, but leave the .vb intact. Your mod name should be the one that is included in the Post-build build event. If your mod name is changed, you must also change the post-build event for the changes to be reflected.
3. Click Add, and the code will be ready.
4. Write below the (assuming that your mod name is HelloGuys) Public Class HelloGuys: `Implements IScript`

```vb
Public Class HelloGuys
    Implements IScript
End Class
```

5. Write above the Public Class HelloGuys:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Imports KS.CommandType
    Imports System.Collections.Generic
```

6. Make your start mod event handler by writing:

```vb
    Property Commands As Dictionary(Of String, CommandInfo) Implements IScript.Commands
    Property ModPart As String Implements IScript.ModPart
    Property Name As String Implements IScript.Name
    Property Version As String Implements IScript.Version
    Sub StartMod() Implements IScript.StartMod
        Name = "HelloGuys"
        Version = "1.0"
        ModPart = "Main"
        W("Hello World", True, ColTypes.Neutral)
    End Sub
```

7. Make your stop event handler by writing:

```vb
    Sub StopMod() Implements IScript.StopMod
        W("Goodbye World", True, ColTypes.Neutral)
    End Sub
```

8. Since we're not implementing commands nor event handlers, we're going to leave these blank:

```vb
    Sub PerformCmd(ByVal Command As CommandInfo, Optional ByVal args As String = "") Implements IScript.PerformCmd
    End Sub
    Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    End Sub
    Sub InitEvents(ByVal ev As String, ParamArray Args As Object()) Implements IScript.InitEvents
    End Sub
```

9. The code should look like this in VB:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Imports KS.CommandType
    Imports System.Collections.Generic
    Public Class HelloGuys
        Implements IScript
        Property Commands As Dictionary(Of String, CommandInfo) Implements IScript.Commands
        Property ModPart As String Implements IScript.ModPart
        Property Name As String Implements IScript.Name
        Property Version As String Implements IScript.Version
        Sub StartMod() Implements IScript.StartMod
            Name = "HelloGuys"
            Version = "1.0"
            ModPart = "Main"
            W("Hello World", True, ColTypes.Neutral)
        End Sub
        Sub StopMod() Implements IScript.StopMod
            W("Goodbye World", True, ColTypes.Neutral)
        End Sub
        Sub PerformCmd(ByVal Command As CommandInfo, Optional ByVal args As String = "") Implements IScript.PerformCmd
        End Sub
        Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
        End Sub
        Sub InitEvents(ByVal ev As String, ParamArray Args As Object()) Implements IScript.InitEvents
        End Sub
    End Class
```

...Or in C#:

```cs
    using MP = KS.ModParser;
    using TWC = KS.TextWriterColor;
    using CT = KS.CommandType;
    using ColorTools = KS.ColorTools;
    using System.Collections.Generic;
    public class HelloGuys : MP.IScript
    {
        public Dictionary<string, CommandInfo> Commands {get; set;}
        public string ModPart {get; set;}
        public string Name {get; set;}
        public string Version {get; set;}
        public void StartMod()
        {
            Name = "HelloGuys";
            Version = "1.0";
            ModPart = "Main";
            TWC.W("Hello World", true, ColorTools.ColTypes.Neutral);
        }
        public void StopMod()
        {
            TWC.W("Goodbye World", true, ColorTools.ColTypes.Neutral);
        }
        public void PerformCmd(CommandInfo Command, string args = "")
        {
        }
        public void InitEvents(string ev)
        {
        }
        public void InitEvents(string ev, params object[] Args)
        {
        }
    }
```

10. Right-click on the solution and press Build.
11. Run your Kernel Simulator you've just referenced to in your project.

### More Examples

If you want to check out more examples, feel free to check them out in the [KSModExamples](https://github.com/EoflaOE/KSModExamples) respository in GitHub.
