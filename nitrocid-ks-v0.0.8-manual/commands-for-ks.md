# Commands-for-KS

### Administrative commands

1. adduser: You can add the user's name whenever you need, with the password if required. However, passwords are required to ensure security. Currently, it has an argument of `adduser <username> <password>.`
2. alias: You can manage your aliases to commands so you don't have to type long commands, using `alias <add/rem> <aliasName> <Command>.`
3. arginj: You can inject arguments into the kernel so that when you reboot, the arguments that are injected will be run. It has an argument of `arginj <arguments>.`
4. cdbglog: You can clear debug log, resetting the size to 0
5. chhostname: You can change your hostname of your kernel to personalize things. It has an argument of `chhostname <AnyHostName>.`
6. chlang: Changes your language
7. chmal: You can change your message of the day after login, and it supports the same placeholders, and it has the same argument of `chmal <Anything>.`
8. chmotd: You can change your message of the day, and you can include your own placeholders, including `<user>` which stands for username, `<shortdate>` for the short date in "MM/DD/YYYY" format, `<longdate>` for the long date that looks like "Saturday, December 1, 2018", `<shorttime>` for the short time in "HH:MM" format, `<longtime>` for the long time in "HH:MM:SS AM/PM" format, `<timezone>` for the standard time zone (eg. Egypt Standard Time), `<summertimezone>` for the daylight time zone name (eg. Syria Daylight Time), and has an argument of `chmotd <anything>.`
9. chusrname: You can change your username, or someone else's name, using `chusrname <oldName> <newName>,` although if you changed your own username to new name, you'll be signed out immediately.
10. debuglog: You can check your debugging logs without having to go to the file explorer located at your user profile and open the text editor/viewer on "kernelDbg.log." When it was first appeared, you can only view debugging logs directly from the kernel that has debugging enabled.
11. disconndbgdev: Disconnects a debug device
12. lsdbgdev: Lists all debug devices that are connected
13. lset: Set listing mode (Either parse the size of the subdirectory only, or parse all the sizes in a subdirectory)
14. listdrives: List all parsed drives
15. listparts: List all partitions in a selected drive (zero-based)
16. netinfo: You can check your network status and network interface information, including WiFi support. You can also use this for troubleshooting problems with the network, and you can look at the packets that has an error.
17. perm: You can manage user's permission settings. Right now, we only support disabling and enabling accounts, as well as making the specified user administrator. It has an argument of `perm <username> <Admin/Disabled> <Allow/Disallow>.`
18. rmuser: You can remove usernames, but you can't remove yours, if the specified user doesn't want to use the computer, or is uninvited, or is redundant. You can remove usernames using `rmuser <Username>.`
19. rdebug: Enables or disables remote debugging functionality
20. reloadconfig: You can reload the configuration file to read the new changes, but the changes will be applied after you restart the kernel.
21. reloadsaver: You can reload your screensaver extension file from the KSMods directory. You should load your screensaver file before you can set it as default and use it. It has the usage of `loadsaver <<ScreensaverName>SS.m>.`
22. reloadmods: Reloads all the kernel modifications
23. rexec: Remotely executes a command in another kernel instance (other PC)
24. setsaver: You can set your screensaver of your choice or your customized one as the default one, and if you plan to use customized screensavers, you should name your extension as `<ScreensaverName>SS.m` to be recognized as a screensaver, not as an extension. It has the argument of `setsaver <<ScreensaverName>SS.m/matrix/disco/disco255/colorMix/colorMix255/glitterMatrix/lines/glitterColor/aptErrorSim/hackUserFromAD>.`
25. update: Checks for updates, and if it found one, it tells you.

### Normal user commands

1. bsynth: Plays the beep synth file. For instructions on how to make a beep synth file, see `Beep synths`
2. chdir: You can change your working directory using `chdir <directory>`
3. chpwd: You can change your password, or someone else's password. It's been reported that the normal accounts can use this command to change anyone's password without any consent. Usage: `chpwd <username> <password> <newpassword> <newpassword>`
4. cls: To clear your screen from text.
5. calc: It's back! The Calculator calculates the formulas like `4 / 2`.
6. copy: Copies the source file to the destination
7. dismissnotif: Dismisses a specific notification.
8. ftp: You can transfer files from/to an FTP server, and interact with the servers.
9. get: Downloads a file from the specified URL.
10. list: You can list your current working directory, or list another directory using `list [Directory].`
11. lockscreen: You can lock your screen and show your default screensaver set by you or by the kernel. Default screensaver is Matrix.
12. loteresp: Starts the Love/Hate comment responder game
13. logout: You can log off your account when you're finished working.
14. mathbee: Starts the mathematical bee game
15. md: You can make your directory on the root directory, using `md <anything>.`
16. move: Moves the source file to the destination
17. rd: You can remove your made directory using `rd <anything>.`
18. read: You can see what's inside a file by `read <file>,` much like `cat <path/to/file>.`
19. reboot: You can restart your kernel if you have made manual or tool configuration changes for them to be reflected, or if you want to see the boot sequence again.
20. savescreen: You can show the screensaver to prevent screen burn-outs.
21. search: Searches for a specific string in a specific file.
22. setcolors: You can set the kernel colors using `setcolors <inputColor/def> <licenseColor/def> <contKernelErrorColor/def> <uncontKernelErrorColor/def> <hostNameShellColor/def> <userNameShellColor/def> <backgroundColor/def> <neutralTextColor/def> <cmdListColor/def> <cmdDefColor/def> <stageColor/def>`
23. setthemes: You can set the color set for your kernel, as known as themes, using `setthemes <theme>`
24. showmotd: You can show your changes to the Message of the Day
25. shownotifs: Shows the notifications.
26. showtd: You can show your current time and date, as well as your timezone.
27. showtdzone: You can show the time and date of the timezone, or you can show all of the dates and times of the timezones in the current time and date using `showtdzone <zone>` or `showtdzone all`
28. showmal: You can show your changes to the Message of the Day After Login
29. shutdown: You can shut down your computer (The kernel, not the actual PC)
30. speak: Speaks anything. Currently broken on Windows.
31. spellbee: Plays the spelling bee game
32. sshell: Opens the SSH connection. Press ESC to disconnect when in session.
33. sumfile: Calculates the MD5 or SHA256 sum of a specific file.
34. sysinfo: You can show your system information, as well as the kernel settings.
35. usermanual: Opens https://github.com/EoflaOE/Kernel-Simulator/wiki

For more information about every command, see the right pane.
