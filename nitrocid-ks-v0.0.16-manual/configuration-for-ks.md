# Configuration-for-KS

### What is the config?

The config is the configuration for your kernel that stores more kernel options that couldn't be edited in either the arguments or command-line arguments. Some commands do change the config file. Use the `settings` command to change the kernel settings as KS Config Tool is obsolete.

There are many sections to make reading the config file easier. Let's see each entry and what does it do, and what values does it accept.

### Config entries

#### General

1. Prompt for Arguments on Boot: You can force the kernel to give you the argument prompt if the value is set to True. It can have the value of True or False.
2. Maintenance Mode: You can make the kernel not to parse any mods and screensavers when booting, and gives you the opportunity to repair your kernel. It's also known as Safe Mode. It can have the value of True or False.
3. Change Root Password: You can change the administrative password. If you set it to True, the password will change based on the value of "Set Root Password to" config entry. It can have the value of True or False.
4. Set Root Password to: If "Change Root Password" option is set to True, you can write your own root password. Please note that the password aren't stored in the encrypted form.
5. Change Culture when Switching Languages: You can make the kernel change the culture based on language.
6. Check for Updates on Startup: If true, the kernel will check for updates on startup.
7. Language: It can take the three-letter language shortcut. It localizes Kernel Simulator to your country.
8. Culture: It can take the two-letter language code as well as the two-letter country code like this: en-US

#### Colors

Each entry mentioned below can take color names or values. See ConsoleColor for more information.

1. User Name Shell Color: You can change the username displaying part color in the whole prompt.
2. Host Name Shell Color: You can change the hostname displaying part color in the whole prompt.
3. Continuable Kernel Error Color: You can change the continuable kernel error text color.
4. Uncontinuable Kernel Error Color: You can change the fatal error color text color.
5. Text Color: You can change the general text color.
6. License Color: You can change the license text color.
7. Background Color: You can change the background color.
8. Input Color: You can change the text input color.
9. Listed command in Help Color: You can change the printed command color in the command list.
10. Definition of command in Help Color: You can change the printed description of the command color in the command list.
11. Kernel Stage Color: You can change the kernel stage indicator color.
12. Error Text Color: You can change the error text color.
13. Warning Text Color: You can change the warning text color.
14. Option Color: You can change the option text color.
15. Banner Color: You can change the banner text color.

#### Hardware

Each entry mentioned below can take either False, or True.

1. Quiet Probe: You can make hardware probing quiet, by not showing results of probed hardware.
2. Full Probe: Ensures that each hardware is probed.

#### Login

1. Show MOTD on Log-in: You can make the log-in prompt show you the Message of the Day before displaying the prompt. It can be True or False.
2. Clear Screen on Log-in: You can remove screen clutter before log-in if it is set to True. It can be True or False.
3. Show available usernames: You can choose whether or not to show available usernames.
4. Host Name: You can change the host name of the kernel.

#### Shell

1. Colored Shell: You can add support for coloring the shell.
2. Simplified Help Command: You can list the commands in the comma-separated form.
3. Current Directory: Each time the main shell runs, it will be set to this directory. It should exist.
4. Lookup Directories: When running a common system command (a file) that are located in these paths, ensure that it runs. This works the same as PATH.
5. Prompt Style: Prompt style. Leave blank to use default style. It only affects the main shell. Placeholders here are parsed.
6. FTP Prompt Style: Prompt style. Leave blank to use default style. It only affects the FTP shell. Placeholders here are parsed.
7. Mail Prompt Style: Prompt style. Leave blank to use default style. It only affects the mail shell. Placeholders here are parsed.
8. SFTP Prompt Style: Prompt style. Leave blank to use default style. It only affects the SFTP shell. Placeholders here are parsed.

#### Filesystem

1. Filesystem sort mode: Chooses how to sort files (FullName, Length, CreationTime, LastWriteTime, LastAccessTime)
2. Filesystem sort direction: Chooses what direction the sort works (Ascending, Descending)
3. Debug Size Quota in Bytes: Specifies the maximum log size in bytes. If this was exceeded, it will remove the first 5 lines from the log to free up some space.
4. Size parse mode: Parse whole directory for size. If set to False, it will parse just the surface.
5. Show Hidden Files: Whether or not to list hidden files.

#### Network

1. Debug Port: Specifies the remote debugger port. Make sure that the selected port is not used.
2. Download Retry Times: How many times does the "get" command retry the download before assuming failure?
3. Upload Retry Times: How many times does the "put" command retry the upload before assuming failure?
4. Record chat to debug log: Whether or not to log the chat history of all devices to the debug log.
5. Log FTP username: Whether or not to log FTP username in the debugger log.
6. Log FTP IP address: Whether or not to log FTP IP address in the debugger log.
7. Return only first FTP profile: If true, uses the first working profile to connect to the FTP server.
8. Show progress bar while downloading or uploading from `get` or `put` command: Self-explanatory
9. Show mail message preview: Self-explanatory
10. Show SSH banner: Whether or not to show the SSH banner if the server has one configured.
11. Enable RPC: Self-explanatory
12. RPC Port: Specifies the RPC port. Make sure that the selected port is not used.

#### Screensaver

1. Screensaver: You can choose your screensavers available.
2. Screensaver Timeout in ms: Self-explanatory

**Built-in screensavers**

These screensavers are built-in directly to Kernel Simulator and are always available. If you want your screensaver to be included by default to Kernel Simulator, let us know. Here are the available screensavers:

**ColorMix**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?

**Disco**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?
4. Cycle Colors: Cycles the colors based on the color mode instead of random colors.

**GlitterColor**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?

**Lines**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?

**Dissolve**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.

**BouncingBlock**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?

**BouncingText**

1. Delay in Milliseconds: How many milliseconds to wait before the next write?
2. Text Shown: The text that is shown. If the text is longer than console width, it will be truncated by 15 characters.

**GlitterMatrix**

1. Delay in Milliseconds: How many milliseconds to wait before the next write?

**Matrix**

1. Delay in Milliseconds: How many milliseconds to wait before the next write?

**ProgressClock**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Cycle Colors: Cycles the colors based on the color mode instead of random colors.
4. Ticks to change color: If color cycling is enabled, how many ticks before changing colors?
5. Color of Seconds Bar: The color of seconds progress bar. It can be 1-16, 1-255, or "1-255;1-255;1-255".
6. Color of Minutes Bar: The color of minutes progress bar. It can be 1-16, 1-255, or "1-255;1-255;1-255".
7. Color of Hours Bar: The color of hours progress bar. It can be 1-16, 1-255, or "1-255;1-255;1-255".
8. Color of Information: The color of date information. It can be 1-16, 1-255, or "1-255;1-255;1-255".

**Lighter**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?
4. Max Positions Count: How many positions are lit before dimming? If the block count exceeded this number, the earliest block that appeared will disappear.

**Wipe**

1. Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
2. Activate True Color Mode: If true, uses true colors.
3. Delay in Milliseconds: How many milliseconds to wait before the next write?
4. Wipes to change direction: How many wipes to do before changing direction randomly?

**Fader**

1. Delay in Milliseconds: How many milliseconds to wait before the next write?
2. Fade Out Delay in Milliseconds: How many milliseconds to wait before fading out text?
3. Text Shown: The text that is shown.
4. Max Fade Steps: How many fade steps to do?

**Typo**

1. Delay in Milliseconds: How many milliseconds to wait before the next write?
2. Write Again Delay in Milliseconds: How many milliseconds to wait before writing text again?
3. Text Shown: The text that is shown.
4. Minimum writing speed in WPM: Self-explanatory
5. Maximum writing speed in WPM: Self-explanatory
6. Probability of typo in percent: Self-explanatory

#### Misc

1. Show Time/Date on Upper Right Corner: You can establish the live time/date banner that's updating, and the position is on the upper-right corner. It can take either True or False.
2. Marquee on startup: Whether or not to activate banner animation.
3. Long Time and Date: Whether or not to render time and date using long.
4. Preferred Unit for Temperature: Select the preferred unit for temperature. One of Kelvin (1), Metric (2), or Imperial (3) is accepted.
5. Enable text editor autosave: Turns on or off the text editor autosave feature.
6. Text editor autosave interval: If autosave is enabled, the text file will be saved for each "n" seconds.
7. Wrap list outputs: If enabled, the console will stop printing on wrappable commands until a key is pressed if the printed lines exceed the console window height.
