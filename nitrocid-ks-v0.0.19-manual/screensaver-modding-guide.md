# Screensaver-modding-guide

### What is the screensaver for the kernel?

The screensaver is the idle process that will activate if your computer went idle. You can also see the default screensaver by savescreen that is set by you or by the kernel.

The screensaver can also be customized, and we'll teach you how to make your first screensaver, to make from the simplest screensaver to legendary ones.

The screensavers are glorified mods that can be either a traditional mod or a dynamic one.

### How to start your own screensaver on Visual Studio?

If you're going to make a screensaver based on traditional mod codebase, you can follow these steps:

1. Repeat steps 1-8 from the Modding guide (traditional)
2. On the Compile section, click on Build Events, then write this on the Post-build event command line:
   * If you're using VB:

```cmd
   copy ..\..\ModFile.vb ..\..\..\..\ModFile.ss.vb
   del /Q *.*
```

* If you're using C#:

```cmd
   copy ..\..\ModFile.cs ..\..\..\..\ModFile.ss.cs
   del /Q *.*
```

3. Repeat steps 10-13 from the Modding guide (traditional), as well as steps 1-3 from the creation steps, but replace the Imports KS.ModParser with Imports KS.Screensaver

If you're going to use a dynamic mod codebase, follow these steps:

1. Repeat steps 1-7 from the Modding guide (dynamic), as well as steps 1-3 from the creation steps, but replace the Imports KS.ModParser with Imports KS.Screensaver

Now, follow these steps:

1. Between the Public Class... and the End Class lines, let Visual Studio know that you're going to create your KS screensaver by writing: `Implements ICustomSaver`
2. Define properties for mod information by putting below the Implements IScript:

```vb
    Public Property Initialized As Boolean Implements ICustomSaver.Initialized
    Public Property DelayForEachWrite As Integer Implements ICustomSaver.DelayForEachWrite
    Public Property SaverName As String Implements ICustomSaver.SaverName
```

3. Make your init screensaver sub named InitSaver() that implements the ICustomSaver.InitSaver, by writing:

```vb
    Sub InitSaver() Implements ICustomSaver.InitSaver
        'Your code here
        Initialized = True 'Put it anywhere in the sub if you're making If conditions, otherwise, leave it here.
    End Sub
```

4. Replace every Your code here comment with your code. Repeat this step on all the interface subs
5. Make your pre-display (Called before displaying screensaver) sub named PreDisplay() and post-display (called after displaying scrensaver) sub named PostDisplay() that implement the ICustomSaver.PreDisplay and ICustomSaver.PostDisplay, by writing:

```vb
    Sub PreDisplay() Implements ICustomSaver.PreDisplay
        'Your code here
    End Sub
    Sub PostDisplay() Implements ICustomSaver.PostDisplay
        'Your code here
    End Sub
```

6. Make your display code (it should display something) sub named ScrnSaver() that implements the ICustomSaver.ScrnSaver, by writing:

```vb
    Sub ScrnSaver() Implements ICustomSaver.ScrnSaver
        'Your code here
    End Sub
```

7. Run the build. When the build is successful, ignore the dialog box that appears.
8. Run your Kernel Simulator you've just referenced to in your project, and load, set default, and lock your screen and your screensaver is there.

### Optional stuff

1. You can make your subs anywhere on the class, but if:
   * they're on the different class, either press Enter on End Class and make a public new class that stores new subs (traditional mod), or make a separate code file for it (dynamic mod):

```vb
Public Class AnotherClass
    'Your definitions below, and so your subs, functions, interfaces, etc.
End Class
```

* they're trying to re-initialize the screensaver by re-calling InitSaver(), Try so on your test environment first, then the production environment if that worked properly.

2. The new subs or functions should meet the following conditions:
   * They shouldn't make an infinite loop unless you're making them that exits if specified conditions are met
   * They shouldn't try to cause errors with the kernel.
   * Put your sub call on one of the three subs that implements the ICustomSaver interface. Ex. If you're going to make a sub that's going to be called on screensaver display, place your sub call on the ScrnSaver() sub, and then your code on your sub.
3. You can put your custom referenced assemblies in the beginning of your code. Refer to the Custom Referenced Assemblies section in Modding guide for more information.
4. If you're going to add imports, these rules must be met:
   * Don't import KS by itself. KS does that automatically
   * When importing modules/classes like TextWriterColor, it's written like this: `Imports KS.TextWriterColor`

### Examples

Here are two examples of how to make a screensaver:

#### In-Console Message Box, and Soon, Overnight, or Rude (Go away...) messages

The back message box screensaver tells people that the computer owner is gone, or the owner tells that they should go away because there is important things going on in their computers. This is achieved in XLock in old Linux systems by putting 3 modes, Soon, Overnight, and Rude.

1. Right-click on the project, and go to Add > Class
2. Name your screensaver, but leave the .vb intact. Your mod name should be the one that is included in the Post-build build event. If your mod name is changed, you must also change the post-build event for the changes to be reflected.
3. Click Add, and the code will be ready.
4. Write below the (Assume that your mod name is SOR) Public Class SOR: `Implements ICustomSaver`
5. Write above the Public Class SOR:

```vb
    Imports System
    Imports System.Threading
    Imports System.Collections.Generic
    Imports KS.Screensaver
    Imports KS.TextWriterColor
    Imports KS.Login
```

6. You should get errors saying that these subs should be created.
7. Make your start screensaver event handler by writing:

```vb
    Public Property Initialized As Boolean Implements ICustomSaver.Initialized
    Public Property DelayForEachWrite As Integer Implements ICustomSaver.DelayForEachWrite
    Public Property SaverName As String Implements ICustomSaver.SaverName
    Public Property SaverSettings As Dictionary(Of String, Object) Implements ICustomSaver.SaverSettings
    Sub InitSaver() Implements ICustomSaver.InitSaver
        W("Load this screensaver using ""setsaver SORSS""", False, True, ColTypes.Neutral)
        SaverName = "SORSS"
        Initialized = True
    End Sub
```

8. Since we're not implementing anything before displaying screensaver, we're going to leave this blank:

```vb
    Sub PreDisplay() Implements ICustomSaver.PreDisplay
    End Sub
```

9. Write above the Property Initialized...:

```vb
    Public SOR_Random As New Random() 'Initializes the random number generator
    Public S_Random As New Random() 'Initializes the random number generator
    Public O_Random As New Random() 'Initializes the random number generator
    Public R_Random As New Random() 'Initializes the random number generator
```

9. Write on the ScrnSaver() sub:

```vb
    Console.Clear()
    If Custom.CancellationPending = True Then 'This will fix the issue for the task being busy.
        Exit Sub
    End If
    Dim SOR_Integer As Integer = SOR_Random.Next(1, 4) 'Chooses whether it's Soon, Overnight or Rude
    Dim Soon_MsgID As Integer = SOR_Random.Next(0, 2) 'Selects messages in the Soon array
    Dim Over_MsgID As Integer = SOR_Random.Next(0, 2) 'Selects messages in the Overnight array
    Dim Rude_MsgID As Integer = SOR_Random.Next(0, 3) 'Selects messages in the Rude array
    Console.SetWindowPosition(0, 1)
    Select Case SOR_Integer
        Case 1 'Soon
            WriteMsg(SOR_Integer, Soon_MsgID)
        Case 2 'Overnight
            WriteMsg(SOR_Integer, Over_MsgID)
        Case 3 'Rude
            WriteMsg(SOR_Integer, Rude_MsgID)
    End Select
    Thread.Sleep(10000)
```

11. You may need to create 1 function and 2 subs for this to work. Write them below the last End Sub:

```vb
    Public Shared Function ParsePlaces(ByVal text As String)
        text = text.Replace("<OWNER>", signedinusrnm)
        Return text
    End Function
    Public Shared Sub InitializeBar(ByVal strlen As Integer)
        W("   +-", False, ColTypes.Neutral)
        For l As Integer = 0 To strlen - 1
            W("-", False, ColTypes.Neutral)
        Next
        W("-+", True, ColTypes.Neutral)
    End Sub
    Public Shared Sub WriteMsg(ByVal TypeID As Integer, ByVal MsgID As Integer)
        Dim BackMessages As String() = {"<OWNER> will be back soon.", "<OWNER> is busy. He will be back soon."}
        Dim OvernightMsg As String() = {"It seems that <OWNER> will be back overnight", "He'll be back overnight."}
        Dim RudeMessages As String() = {"Can you go away?", "Go away, <OWNER> will be back soon", "<OWNER> isn't here. Go away."}
        Dim text As String = ""
        Select Case TypeID
            Case 1
                text = ParsePlaces(BackMessages(MsgID))
            Case 2
                text = ParsePlaces(OvernightMsg(MsgID))
            Case 3
                text = ParsePlaces(RudeMessages(MsgID))
        End Select
        InitializeBar(text.Length)
        W("   | {0} |", True, ColTypes.Neutral, text)
        InitializeBar(text.Length)
    End Sub
```

12. The code should look like this:

```vb
    Imports System
    Imports System.Threading
    Imports System.Collections.Generic
    Imports KS.Screensaver
    Imports KS.TextWriterColor
    Imports KS.Login
    Public Class SoonOvernightRude
        Implements ICustomSaver
        Public Property Initialized As Boolean Implements ICustomSaver.Initialized
        Public Property DelayForEachWrite As Integer Implements ICustomSaver.DelayForEachWrite
        Public Property SaverName As String Implements ICustomSaver.SaverName
        Public Property SaverSettings As Dictionary(Of String, Object) Implements ICustomSaver.SaverSettings
        Public SOR_Random As New Random() 'Initializes the random number generator
        Public S_Random As New Random() 'Initializes the random number generator
        Public O_Random As New Random() 'Initializes the random number generator
        Public R_Random As New Random() 'Initializes the random number generator
        Sub InitSaver() Implements ICustomSaver.InitSaver
            W("Set this screensaver as default using ""setsaver SORSS""", True, ColTypes.Neutral)
            SaverName = "SORSS"
            Initialized = True
        End Sub
        Sub PreDisplay() Implements ICustomSaver.PreDisplay
        End Sub
        Sub PostDisplay() Implements ICustomSaver.PostDisplay
        End Sub
        Sub ScrnSaver() Implements ICustomSaver.ScrnSaver
            Console.Clear()
            If Custom.CancellationPending = True Then 'This will fix the issue for the task being busy.
                Exit Sub
            End If
            Dim SOR_Integer As Integer = SOR_Random.Next(1, 4) 'Chooses whether it's Soon, Overnight or Rude
            Dim Soon_MsgID As Integer = S_Random.Next(0, 2) 'Selects messages in the Soon array
            Dim Over_MsgID As Integer = O_Random.Next(0, 2) 'Selects messages in the Overnight array
            Dim Rude_MsgID As Integer = R_Random.Next(0, 3) 'Selects messages in the Rude array
            Console.SetCursorPosition(0, 1)
            Select Case SOR_Integer
                Case 1 'Soon
                    WriteMsg(SOR_Integer, Soon_MsgID)
                Case 2 'Overnight
                    WriteMsg(SOR_Integer, Over_MsgID)
                Case 3 'Rude
                    WriteMsg(SOR_Integer, Rude_MsgID)
            End Select
        Thread.Sleep(10000)
        End Sub
        Public Shared Function ParsePlaces(ByVal text As String)
            text = text.Replace("<OWNER>", signedinusrnm)
            Return text
        End Function
        Public Shared Sub InitializeBar(ByVal strlen As Integer)
            W("   +-", False, ColTypes.Neutral)
            For l As Integer = 0 To strlen - 1
                W("-", False, ColTypes.Neutral)
            Next
            W("-+", True, ColTypes.Neutral)
        End Sub
        Public Shared Sub WriteMsg(ByVal TypeID As Integer, ByVal MsgID As Integer)
            Dim BackMessages As String() = {"<OWNER> will be back soon.", "<OWNER> is busy. He will be back soon."}
            Dim OvernightMsg As String() = {"It seems that <OWNER> will be back overnight", "He'll be back overnight."}
            Dim RudeMessages As String() = {"Can you go away?", "Go away, <OWNER> will be back soon", "<OWNER> isn't here. Go away."}
            Dim text As String = ""
            Select Case TypeID
                Case 1
                    text = ParsePlaces(BackMessages(MsgID))
                Case 2
                    text = ParsePlaces(OvernightMsg(MsgID))
                Case 3
                    text = ParsePlaces(RudeMessages(MsgID))
            End Select
            InitializeBar(text.Length)
            W("   | {0} |", True, ColTypes.Neutral, text)
            InitializeBar(text.Length)
        End Sub
    End Class
```

13. Run the build. When the build is successful, ignore the dialog box that appears.
14. Run your Kernel Simulator you've just referenced to in your project, and load, set as default, and run savescreen.

#### Simple Blank screen

1. Repeat the steps 1-4 on the first example: In-Console Message Box, and Soon, Overnight, or Rude (Go away...) messages
2. Write above the Public Class Blank (assuming that your classname is Blank):

```vb
    Imports System
    Imports System.Collections.Generic
    Imports KS.Screensaver
```

3. Write these below the Implements ICustomSaver:

```vb
    Public Property Initialized As Boolean Implements ICustomSaver.Initialized
    Public Property DelayForEachWrite As Integer Implements ICustomSaver.DelayForEachWrite
    Public Property SaverName As String Implements ICustomSaver.SaverName
    Public Property SaverSettings As Dictionary(Of String, Object) Implements ICustomSaver.SaverSettings
    Public Sub InitSaver() Implements ICustomSaver.InitSaver
        SaverName = "Blank"
        Initialized = True
    End Sub
    Public Sub PreDisplay() Implements ICustomSaver.PreDisplay
    End Sub
    Public Sub PostDisplay() Implements ICustomSaver.PostDisplay
    End Sub
    Public Sub ScrnSaver() Implements ICustomSaver.ScrnSaver
    
    End Sub
```

4. Write inside the ScrnSaver sub:

```vb
Console.Clear()
```

5. The code should look like this:

```vb
    Imports System
    Imports KS.Screensaver
    Public Class Blank
        Implements ICustomSaver
        Public Property Initialized As Boolean Implements ICustomSaver.Initialized
        Public Property DelayForEachWrite As Integer Implements ICustomSaver.DelayForEachWrite
        Public Property SaverName As String Implements ICustomSaver.SaverName
        Public Property SaverSettings As Dictionary(Of String, Object) Implements ICustomSaver.SaverSettings
        Public Sub InitSaver() Implements ICustomSaver.InitSaver
            SaverName = "Blank"
            Initialized = True
        End Sub
        Public Sub PreDisplay() Implements ICustomSaver.PreDisplay
        End Sub
        Public Sub ScrnSaver() Implements ICustomSaver.ScrnSaver
            Console.Clear()
        End Sub
    End Class
```

5. Repeat the steps 13-14 on the first example: In-Console Message Box, and Soon, Overnight, or Rude (Go away...) messages

### More examples

If you want to check out more examples, feel free to check them out in the [KSModExamples](https://github.com/EoflaOE/KSModExamples) respository in GitHub.
