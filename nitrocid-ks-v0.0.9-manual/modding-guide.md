# Modding-guide

### What is the mod for the kernel?

The mod is the source code file that loads on boot, and can add extensions to the kernel, the shell, and everything. It can also respond to events. However, the mod can only have one command, and a command code.

This is useful if you want to add your own extensions to the kernel, like event handlers for the kernel.

### Can I make my own screensaver?

Yes, but first check out `Screensaver modding guide` manual page for instructions on how to add your screensaver.

### Basic modding

#### How to make your own mods on Visual Studio 2017?

1. On the Start Page, click on New Project
2. Click on Empty Project, select VB or C#, and name your mod or modpack. Make sure the project directory is set to your KSMods directory in your home folder. When you're finished, click OK.
3. Right-click on References on the Solution Explorer, and press Add Reference...
4. Click on the Browse... button, and locate your Kernel Simulator executable file (the file you just ran)
5. When you click OK on Open File, you will see that your KS executable files is added to the reference list.
6. Make sure it has the checkbox that is checked on it, and click on OK.
7. Right-click on the project, not the solution
8. Change the application type to Class Library
9. On the Compile section, click on Build Events, then write this on the Post-build event command line:
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
14. Right-click on the project, and go to Add > Class
15. Assume that you're making a mod in VB. Name your mod, but leave the .vb intact. Your mod name should be the one that is included in the Post-build built event. If your mod name is changed, you must also change the post-build event for the changes to be reflected.
16. Click Add, and the code will be ready:

```vb
    Public Class ModName
        'Your code here
    End Class
```

17. Between the Public Class... and the End Class lines, let Visual Studio 2017 know that you're going to create your KS mod by writing: Implements IScript
18. If you're going to add namespaces, these rules must be met:
    1. Don't import "KS" by itself. KS does that automatically
    2. When importing modules/classes like TextWriterColor, it's written like this: Imports KS.TextWriterColor
19. Define properties for mod information by putting below the Implements IScript: Property Cmd As String Implements IScript.Cmd Property Def As String Implements IScript.Def Property Name As String Implements IScript.Name Property Version As String Implements IScript.Version
20. Make your start mod sub named StartMod() that implements the IScript.StartMod, by writing:

```vb
    Sub StartMod() Implements IScript.StartMod
        Cmd = ""         'If you're going to add commands, write your command here.
        Def = ""         'Explain what is your command and what it's going to do.
        Name = "ModName" 'Replace ModName with your mod name whatever you like, but it SHOULD reflect the mod purpose. You can also use verbs, adjectives, space galaxy names, and so on. This field is required.
        Version = "1.0"  'You can specify your mod version, but it should follow the versioning guidelines and you can find it on the Internet. This field is required.

	'Your code below
    End Sub
```

21. Replace every Your code below comment with your code. Repeat this step on all the interface subs
22. Make your mod stop sub named StopMod() that implements the IScript.StopMod, by writing:

```vb
    Sub StopMod() Implements IScript.StopMod
        'Your code below
    End Sub
```

23.
    1. If you're making your command in your mod, write the response code below:

```vb
       Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	       'Your code below
       End Sub
```

```
2) If you're making your command which handles arguments, write the response code below:
```

```vb
       Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	       If (args = "YourArgHere") Then 'Replace YourArgsHere with your argument set
	           'Your code below
           End If
       End Sub
```

```
3) If you're making your command which handles subsequent arguments, write the response code below:
```

```vb
       Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	   Dim splitArgs As String() = args.Split({" "c})
           If splitArgs.Length > 1 Then
               If (splitArgs(0) = "Part1" And splitArgs(1) = "Part2") Then 'Replace Part1 with your argument, and Part2 with your argument. You can also replace the splitArgs(0) = "Part1" And splitArgs(1) = "Part2" with your statement
                   'Your code below
               Else
                   'Your argument mismatch code below
               End If
           Else
               'Your code that handles not enough arguments
           End If
       End Sub
```

24.
    1. If you're making your event handler which handles what happened in the kernel, write the handle code below:

```vb
       Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
           If (ev = "EventName") Then 'Replace EventName with events that is found on "usermanual Events for Mod Developers" command
	           'Your code below
	       End If
       End Sub
```

```
2) If you're handling multiple events, write the handle code below:
```

```vb
       Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
           If (ev = "EventName") Then 'Replace EventName with events that is found on "usermanual Events for Mod Developers" command
	           'Your code below
	       ElseIf (ev = "AnotherEvent") Then ' Replace AnotherEvent with events that is found on "usermanual Events for Mod Developers" command
               'Your code below
	       End If
       End Sub
```

```
3) IMPORTANT NOTICE! Never try to use infinite loops in handlers unless you're making infinite loops that exits if the specified condition is met, or in the test environment. That will lock the kernel up.
```

25\. You can make your subs anywhere on the class, but if: 1) they're on the different class, press Enter on End Class and make a public new class that stores new subs:

```vb
       Public Class AnotherClass
	       'Your definitions below, and so your subs, functions, interfaces, etc.
       End Class
```

```
2) they're trying to re-initialize the mod by re-calling StartMod(), Try so on your test environment first, then the Production environment if that worked properly.
And the following conditions should be met:
1) They shouldn't make an infinite loop unless you're making them that exits if specified conditions are met
2) They shouldn't try to cause errors with the kernel.
3) If you're an exploiter and are making the exploit code for the kernel, do so on your test environment first then the production environment, then make your CVE report so we get attention and fix that quickly.
4) If your mod is going to extend the kernel, place your extension codes on separate subs
5) Put your sub call on one of the four subs that implements the IScript interface. Ex. If you're going to make a sub that's going to be called on mod start, place your sub call on the StartMod() sub, and then your code on your sub.
```

26\. Run the build. When the build is successful, ignore the dialog box that appears. 27. Run your Kernel Simulator you've just referenced to in your project.

1. Hello World on Kernel Start, and Goodbye World on Kernel Stop

Hello World is the popular starting example for all of the programmers. These examples usually start with printing the "Hello World" string to the console output or command prompt. To make your first Hello World mod, follow these steps:

1. Right-click on the project, and go to Add > Class
2. Name your mod, but leave the .vb intact. Your mod name should be the one that is included in the Post-build built event. If your mod name is changed, you must also change the post-build event for the changes to be reflected.
3. Click Add, and the code will be ready.
4. Write below the (Assume that your mod name is HelloGuys) Public Class HelloGuys: Implements IScript
5. Write above the Public Class HelloGuys:

```vb
   Imports KS.ModParser
   Imports KS.TextWriterColor
```

6. You should get errors saying that these subs should be created.
7. Make your start mod event handler by writing:

```vb
    Property Cmd As String Implements IScript.Cmd
    Property Def As String Implements IScript.Def
    Property Name As String Implements IScript.Name
    Property Version As String Implements IScript.Version
    Sub StartMod() Implements IScript.StartMod
        Cmd = ""
        Def = ""
        Name = "HelloGuys"
        Version = "1.0"
        W("Hello World", True, ColTypes.Neutral)
    End Sub
```

8. Make your stop event handler by writing:

```vb
    Sub StopMod() Implements IScript.StopMod
        W("Goodbye World", True, ColTypes.Neutral)
    End Sub
```

9. Since we're not implementing commands nor event responders, we're going to leave these blank:

```vb
    Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
    End Sub
    Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    End Sub
```

10. The code should look like this in VB:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Public Class HelloGuys
    	Implements IScript
	Property Cmd As String Implements IScript.Cmd
    	Property Def As String Implements IScript.Def
    	Property Name As String Implements IScript.Name
    	Property Version As String Implements IScript.Version
    	Sub StartMod() Implements IScript.StartMod
            Cmd = ""
            Def = ""
            Name = "HelloGuys"
            Version = "1.0"
            W("Hello World", True, ColTypes.Neutral)
    	End Sub
    	Sub StopMod() Implements IScript.StopMod
            W("Goodbye World", True, ColTypes.Neutral)
    	End Sub
    	Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
    	End Sub
    	Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    	End Sub
    End Class
```

...Or in C#:

```cs
    using MP = KS.ModParser;
    using TWC = KS.TextWriterColor;
	public class HelloGuys : MP.IScript
	{
	public string Cmd {get; set;}
		public string Def {get; set;}
		public string Name {get; set;}
		public string Version {get; set;}
		public void StartMod()
		{
			Cmd = "";
			Def = "";
			Name = "HelloGuys";
			Version = "1.0";
			TWC.W("Hello World", True, ColTypes.Neutral);
		}
		public void StopMod()
		{
			TWC.W("Goodbye World", True, ColTypes.Neutral);
		}
		public void PerformCmd(string args = "")
		{
		}
		public void InitEvents(string ev)
		{
		}
	}
```

11. Run the build. When the build is successful, ignore the dialog box that appears.
12. Run your Kernel Simulator you've just referenced to in your project.
13. Hello World on command execute
14. Repeat the steps 1-5 on the first example: Hello World on Kernel Start and Goodbye World on Kernel Stop
15. Make your start mod event handler by writing (assuming that your mod name is HelloShell):

```vb
    Property Cmd As String Implements IScript.Cmd
    Property Def As String Implements IScript.Def
    Property Name As String Implements IScript.Name
    Property Version As String Implements IScript.Version
    Sub StartMod() Implements IScript.StartMod
        Cmd = "SayHello"
        Def = ""
        Name = "HelloShell"
        Version = "1.0"
    End Sub
```

3. Since we're not implementing shutdown handler nor event responders, we're going to leave these blank:

```vb
    Sub StopMod() Implements IScript.StopMod
    End Sub
    Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    End Sub
```

4. Make your command handler, and let it respond to the SayHello mod command:

```vb
    Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
		W("Hello World", True, ColTypes.Neutral)
    End Sub
```

5. The code should look like this in VB:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Public Class HelloShell
    	Implements IScript
	Property Cmd As String Implements IScript.Cmd
    	Property Def As String Implements IScript.Def
    	Property Name As String Implements IScript.Name
    	Property Version As String Implements IScript.Version
    	Sub StartMod() Implements IScript.StartMod
            Cmd = "SayHello"
            Def = ""
            Name = "HelloShell"
            Version = "1.0"
    	End Sub
    	Sub StopMod() Implements IScript.StopMod
    	End Sub
    	Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	    W("Hello World", True, ColTypes.Neutral)
    	End Sub
    	Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    	End Sub
    End Class
```

...Or in C#

```cs
	using MP = KS.ModParser;
    using TWC = KS.TextWriterColor;
	public class HelloShell : MP.IScript
	{
	public string Cmd {get; set;}
		public string Def {get; set;}
		public string Name {get; set;}
		public string Version {get; set;}
		public void StartMod()
		{
			Cmd = "SayHello";
			Def = "";
			Name = "HelloShell";
			Version = "1.0";
		}
		public void StopMod()
		{
		}
		public void PerformCmd(string args = "")
		{
		TWC.W("Hello World", True, ColTypes.Neutral);
		}
		public void InitEvents(string ev)
		{
		}
	}
```

6. Repeat the steps 11-12 on the first example: Hello World on Kernel Start and Goodbye World on Kernel Stop
7. Hello World on command execute with arguments (single)
8. Assuming that your mod name is HelloArgs, your argument that will make your command say Hello World is HW, and that your command is SayHello, Repeat the steps 1-3 on the second example: Hello World on command execute
9. Make your command handler, and let it respond to the SayHello mod command:

```vb
    Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
		If (args = "HW") Then
			W("Hello World", True, ColTypes.Neutral)
		Else
			W("Make me say Hello by running ""SayHello HW.""", True, ColTypes.Neutral)
		End If
    End Sub
```

3. The code should look like this in VB:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Public Class HelloArgs
    	Implements IScript
	Property Cmd As String Implements IScript.Cmd
    	Property Def As String Implements IScript.Def
    	Property Name As String Implements IScript.Name
    	Property Version As String Implements IScript.Version
    	Sub StartMod() Implements IScript.StartMod
            Cmd = "SayHello"
            Def = ""
            Name = "HelloArgs"
            Version = "1.0"
    	End Sub
    	Sub StopMod() Implements IScript.StopMod
    	End Sub
    	Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
			If (args = "HW") Then
	    		W("Hello World", True, ColTypes.Neutral)
			Else
	    		W("Make me say Hello by running ""SayHello HW.""", True, ColTypes.Neutral)
			End If
        End Sub
    	Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    	End Sub
    End Class
```

...Or in C#:

```cs
	using MP = KS.ModParser;
    using TWC = KS.TextWriterColor;
	public class HelloArgs : MP.IScript
	{
	public string Cmd {get; set;}
		public string Def {get; set;}
		public string Name {get; set;}
		public string Version {get; set;}
		public void StartMod()
		{
			Cmd = "SayHello";
			Def = "";
			Name = "HelloArgs";
			Version = "1.0";
		}
		public void StopMod()
		{
		}
		public void PerformCmd(string args = "")
		{
		if (args == "HW")
		{
			TWC.W("Hello World", True, ColTypes.Neutral);
		}
		else
		{
			TWC.W("Make me say Hello by running \"SayHello HW.\"", True, ColTypes.Neutral);
		}
		}
		public void InitEvents(string ev)
		{
		}
	}
```

4. Repeat the last step on the second example: Hello World on command execute
5. Hello World on command execute with multiple arguments
6. Assuming that your mod name is HelloArgs, your argument that will make your command say Hello World is Say Hello, and that your command is WhatDoISay, Repeat the steps 1-3 on the second example: Hello World on command execute
7. Make your command handler, and let it respond to the WhatDoISay mod command:

```vb
    Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	Dim splitArgs As String() = args.Split({" "c})
        Dim ArgCount As Integer = 1
        If splitArgs.Length > 1 Then
            If (splitArgs(0) = "Say" And splitArgs(1) = "Hello") Then
                W("Hello World", True, ColTypes.Neutral)
            Else
                W("Make me say Hello by running ""WhatDoISay Say Hello.""", True, ColTypes.Neutral)
            End If
        Else
            W("Make me say Hello by running ""WhatDoISay Say Hello.""", True, ColTypes.Neutral)
        End If
        For Each arg As String In splitArgs
            W("Argument {0}: {1}", True, ColTypes.Neutral, ArgCount, splitArgs(ArgCount - 1))
            ArgCount += 1
        Next
    End Sub
```

3. The code should look like this in VB:

```vb
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Public Class HelloArgs
    	Implements IScript
	Property Cmd As String Implements IScript.Cmd
    	Property Def As String Implements IScript.Def
    	Property Name As String Implements IScript.Name
    	Property Version As String Implements IScript.Version
    	Sub StartMod() Implements IScript.StartMod
            Cmd = "WhatDoISay"
            Def = ""
            Name = "HelloArgs"
            Version = "1.0"
    	End Sub
    	Sub StopMod() Implements IScript.StopMod
    	End Sub
    	Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
	    Dim splitArgs As String() = args.Split({" "c})
            Dim ArgCount As Integer = 1
            If splitArgs.Length > 1 Then
            	If (splitArgs(0) = "Say" And splitArgs(1) = "Hello") Then
                    W("Hello World", True, ColTypes.Neutral)
            	Else
                    W("Make me say Hello by running ""WhatDoISay Say Hello.""", True, ColTypes.Neutral)
            	End If
            Else
            	W("Make me say Hello by running ""WhatDoISay Say Hello.""", True, ColTypes.Neutral)
            End If
            For Each arg As String In splitArgs
            	W("Argument {0}: {1}", True, ColTypes.Neutral, ArgCount, splitArgs(ArgCount - 1))
            	ArgCount += 1
            Next
        End Sub
    	Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    	End Sub
    End Class
```

...Or in C#:

```cs
    using MP = KS.ModParser;
    using TWC = KS.TextWriterColor;
	public class HelloArgs : MP.IScript
	{
		public string Cmd {get; set;}
		public string Def {get; set;}
		public string Name {get; set;}
		public string Version {get; set;}
		public void StartMod()
		{
			Cmd = "WhatDoISay";
			Def = "";
			Name = "HelloArgs";
			Version = "1.0";
		}
		public void StopMod()
		{
		}
		public void PerformCmd(string args = "")
		{
		string[] splitArgs = args.Split(new[] {' '});
			int ArgCount = 1;
			if (splitArgs.Length > 1)
			{
				if (splitArgs[0] == "Say" && splitArgs[1] == "Hello")
				{
					TWC.W("Hello World", True, ColTypes.Neutral);
				}
				else
				{
					TWC.W("Make me say Hello by running \"WhatDoISay Say Hello.\"", True, ColTypes.Neutral);
				}
			}
			else
			{
				TWC.W("Make me say Hello by running \"WhatDoISay Say Hello.\"", True, ColTypes.Neutral);
			}
			foreach (string arg in splitArgs)
			{
				TWC.W("Argument {0}: {1}", True, ColTypes.Neutral, ArgCount, splitArgs[ArgCount - 1]);
				ArgCount += 1;
			}
		}
		public void InitEvents(string ev)
		{
		}
	}
```

4. Repeat the last step on the second example: Hello World on command execute
5. Network Speed Testing
6. Assuming that your mod name is InternetSpeed, and that your command is getnetspeed, Repeat the steps 1-3 on the second example: Hello World on command execute
7. Put these namespaces above the file:

```vb
    Imports System.Net
    Imports System.Linq
    Imports System.IO
    Imports System.Math
    Imports Microsoft.VisualBasic.Interaction
```

3. Make your command handler:

```vb
    Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
        Dim speeds As Double() = New Double(4) {}
        For i As Integer = 0 To 4
            Dim jQueryFileSize As Integer = 261
            Dim client As New WebClient()
            Dim startTime As DateTime = DateTime.Now
            client.DownloadFile("http://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.js", Environ("USERPROFILE") + "\jQuery.js")
            Dim endTime As DateTime = DateTime.Now
            speeds(i) = Round((jQueryFileSize / (endTime - startTime).TotalSeconds))
        Next
        File.Delete(Environ("USERPROFILE") + "\jQuery.js")
        W("Download speed: {0}KB/s", True, ColTypes.Neutral, speeds.Average())
    End Sub
```

4. The code should look like this in VB:

```vb
    Imports System.Net
    Imports System.Linq
    Imports System.IO
    Imports System.Math
    Imports Microsoft.VisualBasic.Interaction
    Imports KS.ModParser
    Imports KS.TextWriterColor
    Public Class InternetSpeed
    	Implements IScript
    	Property Cmd As String Implements IScript.Cmd
    	Property Def As String Implements IScript.Def
    	Property Name As String Implements IScript.Name
    	Property Version As String Implements IScript.Version
    	Sub StartMod() Implements IScript.StartMod
            Cmd = "getnetspeed"
            Def = ""
            Name = "InternetSpeed"
            Version = "1.0"
    	End Sub
    	Sub StopMod() Implements IScript.StopMod
    	End Sub
    	Sub PerformCmd(Optional ByVal args As String = "") Implements IScript.PerformCmd
            Dim speeds As Double() = New Double(4) {}
            For i As Integer = 0 To 4
            	Dim jQueryFileSize As Integer = 261
            	Dim client As New WebClient()
            	Dim startTime As Date = Date.Now
            	client.DownloadFile("http://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.js", Environ("USERPROFILE") + "\jQuery.js")
            	Dim endTime As Date = Date.Now
            	speeds(i) = Round(jQueryFileSize / (endTime - startTime).TotalSeconds)
            Next
            File.Delete(Environ("USERPROFILE") + "\jQuery.js")
            W("Download speed: {0}KB/s", True, ColTypes.Neutral, speeds.Average())
    	End Sub
    	Sub InitEvents(ByVal ev As String) Implements IScript.InitEvents
    	End Sub
    End Class
```

...Or in C#:

```cs
    using System;
	using System.Net;
	using System.Linq;
	using System.IO;
	using M = System.Math;
	using MP = KS.ModParser;
	using TWC = KS.TextWriterColor;
	public class InternetSpeed : MP.IScript
	{
		public string Cmd {get; set;}
		public string Def {get; set;}
		public string Name {get; set;}
		public string Version {get; set;}
		public void StartMod()
		{
			Cmd = "getnetspeed";
			Def = "";
			Name = "InternetSpeed";
			Version = "1.0";
		}
		public void StopMod()
		{
		}
		public void PerformCmd(string args = "")
		{
			double[] speeds = new double[5];
			for (int i = 0; i <= 4; i++)
			{
				int jQueryFileSize = 261;
				WebClient client = new WebClient();
				DateTime startTime = DateTime.Now;
				client.DownloadFile("http://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.js", System.Environment.GetEnvironmentVariable("USERPROFILE") + "\\jQuery.js");
				DateTime endTime = DateTime.Now;
				speeds[i] = M.Round(jQueryFileSize / (endTime - startTime).TotalSeconds);
			}
			File.Delete(System.Environment.GetEnvironmentVariable("USERPROFILE") + "\\jQuery.js");
			TWC.W("Download speed: {0}KB/s", True, ColTypes.Neutral, speeds.Average());
		}
		public void InitEvents(string ev)
		{
		}
	}
```

5. Repeat the last step on the second example: Hello World on command execute

More examples

If you want to check out more examples, feel free to check them out in the KSModExamples respository in GitHub (Not available yet).

Sources:

1. [https://www.aspsnippets.com/Articles/Check-Internet-Connection-Download-Speed-using-C-and-VBNet-in-ASPNet.aspx](https://www.aspsnippets.com/Articles/Check-Internet-Connection-Download-Speed-using-C-and-VBNet-in-ASPNet.aspx)
