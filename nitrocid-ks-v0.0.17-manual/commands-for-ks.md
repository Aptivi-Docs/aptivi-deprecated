# Commands-for-KS

### Commands for KS

The below commands for Kernel Simulator can be used in the normal UESH shell, the one that is started after you log in to your account. Some have arguments, and some don't.

### Administrative commands

1. `adduser <username> <password>`: You can add the user's name whenever you need, with the password if required. However, passwords are required to ensure security.
2. `alias <add/rem> <aliastype> <alias> <command>`: You can manage your aliases to commands so you don't have to type long commands.
3. `arginj <arguments>`: You can inject arguments into the kernel so that when you reboot, the arguments that are injected will be run.
4. `blockdbgdev <address>`: You can block an IP address of a debug device to prevent it from entering remote debug until it's unblocked.
5. `cdbglog`: You can clear debug log, resetting the size to 0
6. `chhostname <Hostname>`: You can change your hostname of your kernel to personalize things. It has an argument of `chhostname <AnyHostName>.`
7. `chlang <language>`: Changes your language
8. `chmal [anything]`: You can change your message of the day after login, and it supports the same placeholders.
9. `chmotd [anything]`: You can change your message of the day, and you can include your own placeholders, including `<user>` which stands for username, `<shortdate>` for the short date in "MM/DD/YYYY" format, `<longdate>` for the long date that looks like "Saturday, December 1, 2018", `<shorttime>` for the short time in "HH:MM" format, `<longtime>` for the long time in "HH:MM:SS AM/PM" format, `<timezone>` for the standard time zone (eg. Egypt Standard Time), `<summertimezone>` for the daylight time zone name (eg. Syria Daylight Time).
10. `chpwd <username> <password> <newpassword> <newpassword>`: You can change your password, or someone else's password.
11. `chusrname <oldname> <newname>`: You can change your username, or someone else's name, although if you changed your own username to new name, you'll be signed out immediately.
12. `disconndbgdev <address>`: Disconnects a debug device
13. `lsdbgdev`: Lists all debug devices that are connected
14. `netinfo`: You can check your network status and network interface information, including WiFi support. You can also use this for troubleshooting problems with the network, and you can look at the packets that has an error.
15. `perm <username> <permtype> <1=Allow/2=Disallow>`: You can manage user's permission settings. Right now, we only support disabling and enabling accounts, as well as making the specified user administrator.
16. `rmuser <username>`: You can remove usernames, but you can't remove yours, if the specified user doesn't want to use the computer, or is uninvited, or is redundant.
17. `rdebug`: Enables or disables remote debugging functionality
18. `reloadconfig`: You can reload the configuration file to read the new changes, but the changes will be applied after you restart the kernel.
19. `reloadmods`: Reloads all the kernel modifications
20. `reloadsaver <modName.ss.vb/modName.ss.cs>`: Reloads the specified screensaver mod file
21. `rexec <address> <command>`: Remotely executes a command in another kernel instance (other PC)
22. `savecurrdir`: Saves the current directory information to kernel config.
23. `setsaver <saver/modName.ss.vb/modName.ss.cs>`: You can set your screensaver of your choice or your customized one as the default one, and if you plan to use customized screensavers, you should name your extension as `<ScreensaverName>SS.m` to be recognized as a screensaver, not as an extension.
24. `settings`: Changes kernel settings.
25. `unblockdbgdev <address>`: You can unblock an IP address so it can enter remote debug again.
26. `update`: Checks for updates, and if it found one, it tells you.

### Normal user commands

1. `chattr <file> +/-<attrib>`: Changes the attributes of a file
2. `chdir <directory>`: You can change your working directory.
3. `cls`: To clear your screen from text.
4. `calc <expression>`: It's back! The Calculator calculates the formulas like `4 / 2`.
5. `copy <source> <target>`: Copies the source file to the destination
6. `dirinfo <directory>`: Gets directory information
7. `dismissnotif <notifnum>`: Dismisses a specific notification.
8. `edit <textfile>`: Opens the text editor shell to an existing text file.
9. `fileinfo <file>`: Gets file information
10. `firedevents`: Lists all fired events
11. `ftp [address]`: You can transfer files from/to an FTP server, and interact with the servers.
12. `get <URL> [username]`: Downloads a file from the specified URL.
13. `gettimeinfo <date>`: Gets the time information for the specified time
14. `hwinfo`: Shows hardware information
15. `list [directory]`: You can list your current working directory, or another directory.
16. `lockscreen`: You can lock your screen and show your default screensaver set by you or by the kernel. Default screensaver is Matrix.
17. `loteresp`: Starts the Love/Hate comment responder game
18. `logout`: You can log off your account when you're finished working.
19. `lsmail [mailaddress]`: Opens the mail shell to your mail account.
20. `mathbee`: Starts the mathematical bee game
21. `md <directory>`: You can make your directory on the root directory.
22. `mkfile <file>`: You can create your file under any name.
23. `mktheme <theme>`: Makes a new theme.
24. `modinfo <mod>`: Gets mod information for specified mod
25. `move <source> <target>`: Moves the source file to the destination
26. `ping <address1> <address2> ...`: Pings addresses.
27. `put <file> <URL> [username]`: Uploads a file to the URL using a file.
28. `rm <directory/file>`: You can remove a directory or file.
29. `reboot`: You can restart your kernel if you have made manual or tool configuration changes for them to be reflected, or if you want to see the boot sequence again.
30. `reportbug`: Opens a prompt to let you file a bug report.
31. `rss [feedlink]`: Opens an RSS shell.
32. `savescreen`: You can show the screensaver to prevent screen burn-outs.
33. `search <regex> <file>`: Searches for a specific string in a specific file using regular expressions.
34. `searchword <word> <file>`: Searches for a specific string in a specified file using text.
35. `setthemes <theme>`: You can set the color set for your kernel, as known as themes.
36. `sftp [address]`: You can transfer files from/to an SFTP server, and interact with the servers.
37. `shownotifs`: Shows the notifications.
38. `showtd`: You can show your current time and date, as well as your timezone.
39. `showtdzone <timezone/all>`: You can show the time and date of the timezone, or you can show all of the dates and times of the timezones in the current time and date.
40. `shutdown`: You can shut down your computer (The kernel, not the actual PC)
41. `speedpress`: Initializes the speedpress game
42. `spellbee`: Plays the spelling bee game
43. `sshell <address>`: Opens the SSH connection. Press ESC to disconnect when in session.
44. `sumfile <algorithm> <file>`: Calculates the MD5, SHA1, SHA256, or SHA512 sum of a specific file.
45. `sumfiles <algorithm> <directory> [output]`: Calculates the MD5, SHA1, SHA256, or SHA512 sums of the files in the specified directory.
46. `sysinfo`: You can show your system information, as well as the kernel settings.
47. `unzip <zipfile> [path] [-createdir]`: Extracts a zip file
48. `usermanual`: Opens the Kernel Simulator wiki
49. `verify <algorithm> <calculatedhash> <hashfile/expectedhash> <file>`: Verifies a file.
50. `weather <cityID>`: Gets weather information for a city.
51. `wrap <command>`: Wraps a command
52. `zip <zipfile> <path> [-fast/-nocomp] [-nobasedir]`: Makes a zip file
53. `zipshell <zipfile>`: Opens a ZIP shell to the specified zip file

### Scripting commands

These commands can be used in shell and in scripting, though it works better in scripting.

1. `beep <37-32767 Hz> <milliseconds>`: Makes your PC speaker beep in specified n Hz in n ms.
2. `cat <file>`: Prints the content of a specific file to console
3. `choice <$variable> <answers> <input>`: Makes user choices
4. `echo <string>`: Prints written strings
5. `input <$variable> <question>`: Makes user input
6. `set <$variable> <value>`: Sets a variable to a specified value.

For more information about every command, see the right pane.
