# Kernel-Testing-and-Commands

### What is kernel testing?

Kernel testing is the special feature which lets you test some parts of the kernel. Currently, it doesn't cover all of the mandatory kernel features, but it will cover everything as soon as possible in the next versions. It also lets you turn debugging on and off, and so the remote debugging feature. The testing shell provides these commands:

### print

It lets you test the `W()` call to print every text, using the lines and colors that you need.

Usage: `print <Color> <Line> <Message>`

The types of the colors, which are used to display messages colorfully, are located below:

```vb.net
    Neutral = 0
    Input = 1
    Continuable = 2
    Uncontinuable = 3
    HostName = 4
    UserName = 5
    License = 6
    Gray = 7
    ListValue = 8
    ListEntry = 9
    Stage = 10
    [Error] = 11
    Warning = 12
    [Option] = 12
    Banner = 13
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

Refer to \[\[Events for Mod Developers|Events for Mod Developers]] for the events that can be used in the `<Event>` argument.

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

You can find strings inside the text files in the [Resources](https://github.com/EoflaOE/Kernel-Simulator/tree/master/Kernel%20Simulator/Resources) folder.

### places

It lets you parse placeholders in the text without the option of changing color and the newline.

Usage: `places <Message>`

Refer to PlaceParse.vb for the list of placeholders.

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

### testsha512

It lets you estimate the time taken to encode a specified string on milliseconds using SHA512 algorithm.

Usage: `testsha512 <message>`

### testregexp

It lets you test the regular expression pattern on a specific string. It prints all matches.

Usage: `Usage: testregexp <pattern> <string>`

### colortest

It lets you test the 255 color compatibility.

Usage: `colortest <index>`

### colortruetest

It lets you test the 24-bit color compatibility, assuming that R, G, and B aren't less than 0 or greater than 255.

Usage: `colortruetest <R;G;B>`

### sendnot

It lets you test the notification system by sending the notification with the specified title and description on a specific priority.

Usage: `sendnot <Priority> <title> <desc>`

### dcalend

It lets you render date using different calendar types (one of Gregorian, Hijri, Persian, Saudi-Hijri, Thai-Buddhist)

Usage: `dcalend <CalendType>`

### listcodepages

It lets you list all the available codepages installed on the system.

### lscompilervars

It lets you list all the compiler variables used to build Kernel Simulator.

### testlistwriterstr

It lets you test the list writer using the String type.

### testlistwriterint

It lets you test the list writer using the Integer type.

### testlistwriterchar

It lets you test the list writer using the Char type.

### lscultures

It lets you test the available cultures installed on the system.

Usage: `lscultures [search]`

### getcustomsaversetting

It lets you get a setting from a custom saver. Load all the mods and screensavers first before using this command.

Usage: `getcustomsaversetting <saver> <setting>`

### setcustomsaversetting

It lets you set a setting from a custom saver. Load all the mods and screensavers first before using this command.

Usage: `setcustomsaversetting <saver> <setting> <value>`

### help

It lists all the commands and its usages.

### exit

It exits the test shell, and starts up the kernel.

### shutdown

It shuts down the system.
