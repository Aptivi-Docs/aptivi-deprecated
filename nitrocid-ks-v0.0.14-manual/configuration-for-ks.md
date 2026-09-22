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
7. Language: It can take the three-letter language shortcut. It localizes Kernel Simulator to your country. Currently, it only has 7 languages, including English.

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

#### Hardware

Each entry mentioned below can take either False, or True.

1. Quiet Probe: You can make hardware probing quiet, by not showing results of probed hardware.
2. Probe Slots: You can make the RAM prober probe the RAM slots.

#### Login

1. Show MOTD on Log-in: You can make the log-in prompt show you the Message of the Day before displaying the prompt. It can be True or False.
2. Clear Screen on Log-in: You can remove screen clutter before log-in if it is set to True. It can be True or False.
3. Show available usernames: You can choose whether or not to show available usernames.
4. Host Name: You can change the host name of the kernel.

#### Shell

1. Colored Shell: You can add support for coloring the shell.
2. Simplified Help Command: You can list the commands in the comma-separated form.
3. Prompt Style: Prompt style. Leave blank to use default style. It only affects the main shell. Placeholders here are parsed.
4. FTP Prompt Style: Prompt style. Leave blank to use default style. It only affects the FTP shell. Placeholders here are parsed.
5. Mail Prompt Style: Prompt style. Leave blank to use default style. It only affects the mail shell. Placeholders here are parsed.
6. SFTP Prompt Style: Prompt style. Leave blank to use default style. It only affects the SFTP shell. Placeholders here are parsed.

#### Network

1. Debug Port: Specifies the remote debugger port. Make sure that the selected port is not used.
2. Download Retry Times: How many times does the "get" command retry the download before assuming failure?
3. Upload Retry Times: How many times does the "put" command retry the upload before assuming failure?
4. Remote Debug Default Nick Prefix: The name, which will be prepended to the random device ID.
5. Log FTP username: Whether or not to log FTP username in the debugger log.
6. Log FTP IP address: Whether or not to log FTP IP address in the debugger log.
7. Return only first FTP profile: If true, uses the first working profile to connect to the FTP server.
8. Show progress bar while downloading or uploading from `get` or `put` command: Self-explanatory
9. Show mail message preview: Self-explanatory

#### Screensaver

1. Screensaver: You can choose your screensavers available.
2. Screensaver Timeout in ms: Self-explanatory
3. ColorMix - Activate 255 Color Mode: If true, uses 255 colors. True color has higher priority than 255 colors.
4. Disco - Activate 255 Color Mode: See above
5. GlitterColor - Activate 255 Color Mode: See above
6. Lines - Activate 255 Color Mode: See above
7. Dissolve - Activate 255 Color Mode: See above
8. BouncingBlock - Activate 255 Color Mode: See above
9. ColorMix - Activate True Color Mode: If true, uses true colors.
10. Disco - Activate True Color Mode: See above
11. GlitterColor - Activate True Color Mode: See above
12. Lines - Activate True Color Mode: See above
13. Dissolve - Activate True Color Mode: See above
14. BouncingBlock - Activate True Color Mode: See above
15. Disco - Cycle Colors: Cycles the colors based on the color mode instead of random colors.
16. BouncingText - Text Shown: The text that is shown in BouncingText. If the text is longer than console width, it will be truncated by 15 characters.

#### Misc

1. Show Time/Date on Upper Right Corner: You can establish the live time/date banner that's updating, and the position is on the upper-right corner. It can take either True or False.
2. Debug Size Quota in Bytes: Specifies the maximum log size in bytes. If this was exceeded, it will remove the first 5 lines from the log to free up some space.
3. Size parse mode: Parse whole directory for size. If set to False, it will parse just the surface.
4. Marquee on startup: Whether or not to activate banner animation.
5. Long Time and Date: Whether or not to render time and date using long.
6. Show Hidden Files: Whether or not to list hidden files.
7. Preferred Unit for Temperature: Select the preferred unit for temperature. One of Kelvin (1), Metric (2), or Imperial (3) is accepted.
8. Kernel Version: Don't change this entry! It specifies the current kernel version we're at.
