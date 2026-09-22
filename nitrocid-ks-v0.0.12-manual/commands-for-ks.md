# Commands-for-KS

### Commands for KS

The below commands for Kernel Simulator can be used in the normal UESH shell, the one that is started after you log in to your account. Some have arguments, and some don't.

### Administrative commands

1. `adduser <username> <password>`: You can add the user's name whenever you need, with the password if required. However, passwords are required to ensure security.
2. `alias <add/rem> <1=Shell/2=RDebug> <alias> <command>`: You can manage your aliases to commands so you don't have to type long commands.
3. `arginj <arguments>`: You can inject arguments into the kernel so that when you reboot, the arguments that are injected will be run.
4. `blockdbgdev <address>`: You can block an IP address of a debug device to prevent it from entering remote debug until it's unblocked.
5. `cdbglog`: You can clear debug log, resetting the size to 0
6. `chhostname <Hostname>`: You can change your hostname of your kernel to personalize things. It has an argument of `chhostname <AnyHostName>.`
7. `chlang <language>`: Changes your language
8. `chmal [anything]`: You can change your message of the day after login, and it supports the same placeholders.
9. `chmotd [anything]`: You can change your message of the day, and you can include your own placeholders, including `<user>` which stands for username, `<shortdate>` for the short date in "MM/DD/YYYY" format, `<longdate>` for the long date that looks like "Saturday, December 1, 2018", `<shorttime>` for the short time in "HH:MM" format, `<longtime>` for the long time in "HH:MM:SS AM/PM" format, `<timezone>` for the standard time zone (eg. Egypt Standard Time), `<summertimezone>` for the daylight time zone name (eg. Syria Daylight Time).
10. `chpwd <username> <password> <newpassword> <newpassword>`: You can change your password, or someone else's password.
11. `chusrname <oldname> <newname>`: You can change your username, or someone else's name, although if you changed your own username to new name, you'll be signed out immediately.
12. `debuglog`: You can check your debugging logs without having to go to the file explorer located at your user profile and open the text editor/viewer on kernelDbg.log. When it was first appeared, you can only view debugging logs directly from the kernel that has debugging enabled.
13. `disconndbgdev <address>`: Disconnects a debug device
14. `lsdbgdev`: Lists all debug devices that are connected
15. `listdrives`: List all parsed drives
16. `listparts <drivenum>`: List all partitions in a selected drive (zero-based)
17. `netinfo`: You can check your network status and network interface information, including WiFi support. You can also use this for troubleshooting problems with the network, and you can look at the packets that has an error.
18. `perm <username> <1=Administrator/2=Disabled> <1=Allow/2=Disallow>`: You can manage user's permission settings. Right now, we only support disabling and enabling accounts, as well as making the specified user administrator.
19. `rmuser <username>`: You can remove usernames, but you can't remove yours, if the specified user doesn't want to use the computer, or is uninvited, or is redundant.
20. `rdebug`: Enables or disables remote debugging functionality
21. `reloadconfig`: You can reload the configuration file to read the new changes, but the changes will be applied after you restart the kernel.
22. `reloadmods`: Reloads all the kernel modifications
23. `reloadsaver <modnameSS.m>`: Reloads the specified screensaver mod file
24. `rexec <address> <command>`: Remotely executes a command in another kernel instance (other PC)
25. `setsaver <saver/modnameSS.m>`: You can set your screensaver of your choice or your customized one as the default one, and if you plan to use customized screensavers, you should name your extension as `<ScreensaverName>SS.m` to be recognized as a screensaver, not as an extension.
26. `settings`: Changes kernel settings.
27. `unblockdbgdev <address>`: You can unblock an IP address so it can enter remote debug again.
28. `update`: Checks for updates, and if it found one, it tells you.

### Normal user commands

1. `bsynth <synthfile>`: Plays the beep synth file. For instructions on how to make a beep synth file, see `Beep synths`
2. `chattr <file> +/-<attrib>`: Changes the attributes of a file
3. `chdir <directory>`: You can change your working directory.
4. `cls`: To clear your screen from text.
5. `calc <expression>`: It's back! The Calculator calculates the formulas like `4 / 2`.
6. `copy <source> <target>`: Copies the source file to the destination
7. `dirinfo <directory>`: Gets directory information
8. `dismissnotif <notifnum>`: Dismisses a specific notification.
9. `edit <textfile>`: Opens the text editor shell to an existing text file.
10. `fileinfo <file>`: Gets file information
11. `ftp [address]`: You can transfer files from/to an FTP server, and interact with the servers.
12. `get <URL> [username]`: Downloads a file from the specified URL.
13. `list [directory]`: You can list your current working directory, or another directory.
14. `lockscreen`: You can lock your screen and show your default screensaver set by you or by the kernel. Default screensaver is Matrix.
15. `loteresp`: Starts the Love/Hate comment responder game
16. `logout`: You can log off your account when you're finished working.
17. `lsmail [mailaddress]`: Opens the mail shell to your mail account.
18. `mathbee`: Starts the mathematical bee game
19. `md <directory>`: You can make your directory on the root directory.
20. `mkfile <file>`: You can create your file under any name.
21. `move <source> <target>`: Moves the source file to the destination
22. `ping <address1> <address2> ...`: Pings addresses.
23. `put <file> <URL> [username]`: Uploads a file to the URL using a file.
24. `rd <directory>`: You can remove a directory.
25. `reboot`: You can restart your kernel if you have made manual or tool configuration changes for them to be reflected, or if you want to see the boot sequence again.
26. `savescreen`: You can show the screensaver to prevent screen burn-outs.
27. `search <string> <file>`: Searches for a specific string in a specific file.
28. `setcolors <inputColor/def> <licenseColor/def> <contKernelErrorColor/def> <uncontKernelErrorColor/def> <hostNameShellColor/def> <userNameShellColor/def> <backgroundColor/def> <neutralTextColor/def> <cmdListColor/def> <cmdDefColor/def> <stageColor/def> <errorColor/def>`: You can set the kernel colors.
29. `setthemes <theme>`: You can set the color set for your kernel, as known as themes.
30. `shownotifs`: Shows the notifications.
31. `showtd`: You can show your current time and date, as well as your timezone.
32. `showtdzone <timezone/all>`: You can show the time and date of the timezone, or you can show all of the dates and times of the timezones in the current time and date.
33. `shutdown`: You can shut down your computer (The kernel, not the actual PC)
34. `spellbee`: Plays the spelling bee game
35. `sshell <address>`: Opens the SSH connection. Press ESC to disconnect when in session.
36. `sumfile <algorithm> <file>`: Calculates the MD5, SHA1, or SHA256 sum of a specific file.
37. `sumfiles <algorithm> <directory> [output]`: Calculates the MD5, SHA1, or SHA256 sums of the files in the specified directory.
38. `sysinfo`: You can show your system information, as well as the kernel settings.
39. `usermanual`: Opens the Kernel Simulator wiki
40. `verify <MD5/SHA1/SHA256> <calculatedhash> <hashfile/expectedhash> <file>`: Verifies a file.
41. `weather <cityID>`: Gets weather information for a city.

### Scripting commands

These commands can be used in shell and in scripting, though it works better in scripting.

1. `beep <37-32767 Hz> <milliseconds>`: Makes your PC speaker beep in specified n Hz in n ms.
2. `choice <$variable> <answers> <input>`: Makes user choices
3. `echo <string>`: Prints written strings
4. `input <$variable> <question>`: Makes user input

For more information about every command, see the right pane.
