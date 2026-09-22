# Kernel-Testing-and-Commands

### What is kernel testing?

Kernel testing is the special feature which lets you test some parts of the kernel. Currently, it doesn't cover all of the mandatory kernel features, but it will cover everything as soon as possible in the next versions. It also lets you turn debugging on and off, so the remote debugging feature. The testing shell provides these commands:

### print

It lets you test the `W()` call to print every text, using the lines and colors that you need.

Usage: `print <Color> <Line> <Message>`

The types of the colors, which are used to display messages colorfully, are located below:

```vb.net
    Neutral = 1
    Input = 2
    Continuable = 3
    Uncontinuable = 4
    HostName = 5
    UserName = 6
    License = 7
    Gray = 8
    HelpDef = 9
    HelpCmd = 10
    Stage = 11
```

### printf

It lets you test the `W()` call to print every text, using the lines and colors that you need. It has an additional feature of variables, but are not parsed yet, so they are parsed as text, but will be fixed in the upcoming release.

Usage: `printf <Color> <Line> <Variable1;Variable2;Variable3;...> <Message>`

### printd

It lets you send any message to the debugger, using `Wdbg()` call. It doesn't provide support for variables unlike `printdf`. It only works if you have enabled the debugger which you can enable by `debug 1`.

Usage: `printd <Message>`

### printdf

It lets you send any message to the debugger, using `Wdbg()` call. It provides support for variables, but are not parsed yet. It only works if you have enabled the debugger which you can enable by `debug 1`.

Usage: `printdf <Variable1;Variable2;Variable3;...> <Message>`

### testevent

It lets you raise any event. If you have loaded mods, you can use this command for testing event raises.

Usage: `testevent <Event>`

From EventsAndExceptions.vb, there are types listed below which you can use for the `<Event>` argument:

```vb.net
    Public Event KernelStarted()
    Public Event PreLogin()
    Public Event PostLogin()
    Public Event ShellInitialized()
    Public Event PreExecuteCommand()
    Public Event PostExecuteCommand()
    Public Event KernelError()
    Public Event ContKernelError()
    Public Event PreShutdown()
    Public Event PostShutdown()
    Public Event PreReboot()
    Public Event PostReboot()
    Public Event PreShowScreensaver()
    Public Event PostShowScreensaver() 'After a key is pressed after screensaver is shown
    Public Event PreUnlock()
    Public Event PostUnlock()
    Public Event CommandError()
    Public Event PreReloadConfig()
    Public Event PostReloadConfig()
    Public Event PreFetchNetworks()
    Public Event PostFetchNetworks()
    Public Event PlaceholderParsing()
    Public Event PlaceholderParsed()
    Public Event GarbageCollected()
    Public Event FTPShellInitialized()
    Public Event FTPPreExecuteCommand()
    Public Event FTPPostExecuteCommand()
    Public Event FTPCommandError()
```

### probehw

It lets you probe hardware in the testing session.

### garbage

Enforces garbage collection to free up some RAM.

### panic

It force crashes the kernel using custom exception types, messages, reboot times, etc. It does not provide support for variables.

Usage: `panic <ErrorType> <Reboot> <RebootTime> <Description>`

`<ErrorType>` options:

```
S = Severe
F = Fatal
U = Unrecoverable
D = Double panic
C = Continuable
```

`<RebootTime>` is measured in seconds. It is used if `<Reboot>` is True or 1.

### panicf

It force crashes the kernel using custom exception types, messages, reboot times, etc. It provides support for variables, but are not parsed yet.

Usage: `panic <ErrorType> <Reboot> <RebootTime> <Variable1;Variable2;Variable3;...> <Description>`

### translate

It lets you translate strings that are found in the current language file in the source code from the current source language to the target language, and prints it in the console.

Usage: `translate <Lang> <Message>`

You can find strings inside the text files in the [Resources](https://github.com/EoflaOE/Kernel-Simulator/tree/master/Kernel%20Simulator/Resources) folder. Target language options:

```
arb = Arabic
chi = Chinese Simplified
cro = Croatian
cze = Czech
dan = Danish
dtc = Dutch
eng = English
fin = Finnish
fre = French
ger = German
ind = Hindi
ita = Italian
jpn = Japan
kor = Korean
mal = Malay
ndo = Indonesian
nwg = Norwegian
pol = Polish
ptg = Portuguese
rmn = Romanian
rus = Russian
spa = Spanish
swe = Swedish
tky = Turkish
uzb = Uzbek
vtn = Vietnamese
```

### places

It lets you parse placeholders in the text without the option of changing color and the newline.

Usage: `places <Message>`

```
<user> = Current user name
<shortdate> = Short date format
<longdate> = Long date format
<shorttime> = Short time format
<longtime> = Logn time format
<timezone> = Current time zone
<summertimezone> = Current summer time zone
<system> = Operating system
```

### loadmods

It lets you load mods in the testing shell. If the `Enabled` flag is True or 1, it will start mods, else, stop mods.

Usage: `loadmods <Enable>`

### debug

It lets you enable and disable debugging mode. It only enables the local debugging which will write to your home directory. This allows `printd` and `printdf` to function.

Usage: `debug <Enable>`

### rdebug

It lets you enable remote debugger inside the debugging core. This allows users who need to see what's going on in another computer running KS to see its debugging logs. It uses port number `3014` and can be changed.

Usage: `rdebug <Enable>`

### testmd5

It lets you estimate the time taken to encode a specified string on milliseconds using MD5 algorithm.

Usage: `testmd5 <message>`

### testsha1

It lets you estimate the time taken to encode a specified string on milliseconds using SHA1 algorithm.

Usage: `testsha1 <message>`

### testsha256

It lets you estimate the time taken to encode a specified string on milliseconds using SHA256 algorithm.

Usage: `testsha256 <message>`

### testregexp

It lets you test the regular expression pattern on a specific string. It prints all matches.

Usage: `Usage: testregexp <pattern> <string>`

### colortest

It lets you test the 255 color compatibility.

Usage: `colortest <index>`

### colortruetest

It lets you test the 24-bit color compatibility, assuming that R, G, and B aren't less than 0 or greater than 255.

Usage: `colortruetest <R;G;B>`

### soundtest

It lets you play a sound that is specified. Full path needed.

Usage: `soundtest <file>`

### sendnot

It lets you test the notification system by sending the notification with the specified title and description on a specific priority.

Usage: `sendnot <Priority> <title> <desc>`

### dcalend

It lets you render date using different calendar types (one of Gregorian, Hijri, Persian, Saudi-Hijri, Thai-Buddhist)

Usage: `dcalend <CalendType>`

### listcodepages

It lets you list all the available codepages installed on the system.

### help

It lists all the commands and its usages.

### exit

It shuts down the system.
