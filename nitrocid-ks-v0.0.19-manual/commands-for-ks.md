# Commands-for-KS

### Commands for KS

The below commands for Kernel Simulator can be used in the normal UESH shell, the one that is started after you log in to your account. Some have arguments, and some don't.

### Administrative commands

1. \[\[adduser|KS Command adduser]]: You can add the user's name whenever you need, with the password if required. However, passwords are required to ensure security.
2. \[\[alias|KS Command alias]]: You can manage your aliases to commands so you don't have to type long commands.
3. \[\[arginj|KS Command arginj]]: You can inject arguments into the kernel so that when you reboot, the arguments that are injected will be run.
4. \[\[blockdbgdev|KS Command blockdbgdev]]: You can block an IP address of a debug device to prevent it from entering remote debug until it's unblocked.
5. \[\[cdbglog|KS Command cdbglog]]: You can clear debug log, resetting the size to 0
6. \[\[chhostname|KS Command chhostname]]: You can change your hostname of your kernel to personalize things. It has an argument of `chhostname <AnyHostName>.`
7. \[\[chlang|KS Command chlang]]: Changes your language
8. \[\[chmal|KS Command chmal]]: You can change your message of the day after login, and it supports the same placeholders.
9. \[\[chmotd|KS Command chmotd]]: You can change your message of the day, and you can include your own placeholders, including `<user>` which stands for username, `<shortdate>` for the short date in "MM/DD/YYYY" format, `<longdate>` for the long date that looks like "Saturday, December 1, 2018", `<shorttime>` for the short time in "HH:MM" format, `<longtime>` for the long time in "HH:MM:SS AM/PM" format, `<timezone>` for the standard time zone (eg. Egypt Standard Time), `<summertimezone>` for the daylight time zone name (eg. Syria Daylight Time).
10. \[\[chpwd|KS Command chpwd]]: You can change your password, or someone else's password.
11. \[\[chusrname|KS Command chusrname]]: You can change your username, or someone else's name, although if you changed your own username to new name, you'll be signed out immediately.
12. \[\[disconndbgdev|KS Command disconndbgdev]]: Disconnects a debug device
13. \[\[lsdbgdev|KS Command lsdbgdev]]: Lists all debug devices that are connected
14. \[\[modman|KS Command modman]]: Manages your mods
15. \[\[netinfo|KS Command netinfo]]: You can check your network status and network interface information, including WiFi support. You can also use this for troubleshooting problems with the network, and you can look at the packets that has an error.
16. \[\[perm|KS Command perm]]: You can manage user's permission settings. Right now, we only support disabling and enabling accounts, as well as making the specified user administrator.
17. \[\[rmuser|KS Command rmuser]]: You can remove usernames, but you can't remove yours, if the specified user doesn't want to use the computer, or is uninvited, or is redundant.
18. \[\[rdebug|KS Command rdebug]]: Enables or disables remote debugging functionality
19. \[\[reloadconfig|KS Command reloadconfig]]: You can reload the configuration file to read the new changes, but the changes will be applied after you restart the kernel.
20. \[\[reloadmods|KS Command reloadmods]]: Reloads all the kernel modifications
21. \[\[reloadsaver|KS Command reloadsaver]]: Reloads the specified screensaver mod file
22. \[\[rexec|KS Command rexec]]: Remotely executes a command in another kernel instance (other PC)
23. \[\[savecurrdir|KS Command savecurrdir]]: Saves the current directory information to kernel config.
24. \[\[setsaver|KS Command setsaver]]: You can set your screensaver of your choice or your customized one as the default one, and if you plan to use customized screensavers, you should name your extension as `<ScreensaverName>SS.m` to be recognized as a screensaver, not as an extension.
25. \[\[settings|KS Command settings]]: Changes kernel settings.
26. \[\[unblockdbgdev|KS Command unblockdbgdev]]: You can unblock an IP address so it can enter remote debug again.
27. \[\[update|KS Command update]]: Checks for updates, and if it found one, it tells you.

### Normal user commands

1. \[\[chattr|KS Command chattr]]: Changes the attributes of a file
2. \[\[chdir|KS Command chdir]]: You can change your working directory.
3. \[\[cls|KS Command cls]]: To clear your screen from text.
4. \[\[calc|KS Command calc]]: It's back! The Calculator calculates the formulas like `4 / 2`.
5. \[\[copy|KS Command copy]]: Copies the source file to the destination
6. \[\[dirinfo|KS Command dirinfo]]: Gets directory information
7. \[\[dismissnotif|KS Command dismissnotif]]: Dismisses a specific notification.
8. \[\[edit|KS Command edit]]: Opens the text editor shell to an existing text file.
9. \[\[fileinfo|KS Command fileinfo]]: Gets file information
10. \[\[firedevents|KS Command firedevents]]: Lists all fired events
11. \[\[ftp|KS Command ftp]]: You can transfer files from/to an FTP server, and interact with the servers.
12. \[\[get|KS Command get]]: Downloads a file from the specified URL.
13. \[\[gettimeinfo|KS Command gettimeinfo]]: Gets the time information for the specified time
14. \[\[hwinfo|KS Command hwinfo]]: Shows hardware information
15. \[\[jsonbeautify|KS Command jsonbeautify]]: Beautifies the JSON file
16. \[\[jsonminify|KS Command jsonminify]]: Minifies the JSON file
17. \[\[list|KS Command list]]: You can list your current working directory, or another directory.
18. \[\[lockscreen|KS Command lockscreen]]: You can lock your screen and show your default screensaver set by you or by the kernel. Default screensaver is Matrix.
19. \[\[loteresp|KS Command loteresp]]: Starts the Love/Hate comment responder game
20. \[\[logout|KS Command logout]]: You can log off your account when you're finished working.
21. \[\[lsmail|KS Command lsmail]]: Opens the mail shell to your mail account.
22. \[\[mathbee|KS Command mathbee]]: Starts the mathematical bee game
23. \[\[md|KS Command md]]: You can make your directory on the root directory.
24. \[\[mkfile|KS Command mkfile]]: You can create your file under any name.
25. \[\[mktheme|KS Command mktheme]]: Makes a new theme.
26. \[\[modinfo|KS Command modinfo]]: Gets mod information for specified mod
27. \[\[move|KS Command move]]: Moves the source file to the destination
28. \[\[ping|KS Command ping]]: Pings addresses.
29. \[\[put|KS Command put]]: Uploads a file to the URL using a file.
30. \[\[rm|KS Command rm]]: You can remove a directory or file.
31. \[\[reboot|KS Command reboot]]: You can restart your kernel if you have made manual or tool configuration changes for them to be reflected, or if you want to see the boot sequence again.
32. \[\[reportbug|KS Command reportbug]]: Opens a prompt to let you file a bug report.
33. \[\[rss|KS Command rss]]: Opens an RSS shell.
34. \[\[savescreen|KS Command savescreen]]: You can show the screensaver to prevent screen burn-outs.
35. \[\[search|KS Command search]]: Searches for a specific string in a specific file using regular expressions.
36. \[\[searchword|KS Command searchword]]: Searches for a specific string in a specified file using text.
37. \[\[setthemes|KS Command setthemes]]: You can set the color set for your kernel, as known as themes.
38. \[\[sftp|KS Command sftp]]: You can transfer files from/to an SFTP server, and interact with the servers.
39. \[\[shownotifs|KS Command shownotifs]]: Shows the notifications.
40. \[\[showtd|KS Command showtd]]: You can show your current time and date, as well as your timezone.
41. \[\[showtdzone|KS Command showtdzone]]: You can show the time and date of the timezone, or you can show all of the dates and times of the timezones in the current time and date.
42. \[\[shutdown|KS Command shutdown]]: You can shut down your computer (The kernel, not the actual PC)
43. \[\[speedpress|KS Command speedpress]]: Initializes the speedpress game
44. \[\[spellbee|KS Command spellbee]]: Plays the spelling bee game
45. \[\[sshell|KS Command sshell]]: Opens the SSH connection. Press ESC to disconnect when in session.
46. \[\[sumfile|KS Command sumfile]]: Calculates the MD5, SHA1, SHA256, or SHA512 sum of a specific file.
47. \[\[sumfiles|KS Command sumfiles]]: Calculates the MD5, SHA1, SHA256, or SHA512 sums of the files in the specified directory.
48. \[\[sysinfo|KS Command sysinfo]]: You can show your system information, as well as the kernel settings.
49. \[\[unzip|KS Command unzip]]: Extracts a zip file
50. \[\[usermanual|KS Command usermanual]]: Opens the Kernel Simulator wiki
51. \[\[verify|KS Command verify]]: Verifies a file.
52. \[\[weather|KS Command weather]]: Gets weather information for a city.
53. \[\[wrap|KS Command wrap]]: Wraps a command
54. \[\[zip|KS Command zip]]: Makes a zip file
55. \[\[zipshell|KS Command zipshell]]: Opens a ZIP shell to the specified zip file

### Scripting commands

These commands can be used in shell and in scripting, though it works better in scripting.

1. \[\[beep|KS Command beep]]: Makes your PC speaker beep in specified n Hz in n ms.
2. \[\[cat|KS Command cat]]: Prints the content of a specific file to console
3. \[\[choice|KS Command choice]]: Makes user choices
4. \[\[echo|KS Command echo]]: Prints written strings
5. \[\[input|KS Command input]]: Makes user input
6. \[\[set|KS Command set]]: Sets a variable to a specified value.

For more information about every command, click the command.
