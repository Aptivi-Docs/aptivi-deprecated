# Configuration-for-KS

### What is the Config?

The config is the configuration for your kernel that stores more kernel options that couldn't be edited in either the arguments or command-line arguments. Some commands do change the config file. [KS Config Tool](https://github.com/EoflaOE/Config-Kernel-Simulator) is suitable for editing configuration.

There are many sections to make reading the config file easier. They are 6 sections. Let's see each entry and what does it do, and what values does it accept.

### Config entries

#### General

1. Prompt for Arguments on Boot: You can force the kernel to give you the argument prompt if the value is set to True. It can have the value of True or False.
2. Maintenance Mode: You can make the kernel not to parse any mods and screensavers when booting, and gives you the opportunity to repair your kernel. It's also known as Safe Mode. It can have the value of True or False.
3. Change Root Password: You can change the administrative password. If you set it to True, the password will change based on the value of "Set Root Password to" config entry. It can have the value of True or False.
4. Set Root Password to: If "Change Root Password" option is set to True, you can write your own root password. Please note that the password aren't stored in the encrypted form.
5. Create Demo Account: You can make the kernel create the test account, demo, by setting this to True. It can have the value of True or False.
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

Each entry mentioned below can take either True, or False.

1. Colored Shell: You can add support for coloring the shell.
2. Simplified Help Command: You can list the commands in the comma-separated form.

#### Misc

1. Show Time/Date on Upper Right Corner: You can establish the live time/date banner that's updating, and the position is on the upper-right corner. It can take either True or False.
2. Screensaver: You can choose your screensavers available.
3. Debug Port: Specifies the remote debugger port. Make sure that the selected port is not used.
4. Debug Size Quota in Bytes: Specifies the maximum log size in bytes. If this was exceeded, it will remove the first 5 lines from the log to free up some space.
5. Remote Debug Default Nick Prefix: The name, which will be prepended to the random device ID.
6. Download Retry Times: How many times does the "get" command retry the download before assuming failure?
7. Log FTP username: Whether or not to log FTP username in the debugger log.
8. Log FTP IP address: Whether or not to log FTP IP address in the debugger log.
9. Size parse mode: Parse whole directory for size. If set to False, it will parse just the surface.
10. Marquee on startup: Whether or not to activate banner animation.
11. Long Time and Date: Whether or not to render time and date using long.
12. Show Hidden Files: Whether or not to list hidden files.
13. Kernel Version: Don't change this entry! It specifies the current kernel version we're at.
