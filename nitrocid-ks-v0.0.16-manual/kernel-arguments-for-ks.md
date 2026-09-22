# Kernel-arguments-for-KS

### How to run arguments? and how do I make the prompt appear?

An argument to the kernel is the option of which the kernel or parts of it will behave differently based on the options you have chosen. It will be run on the start of the kernel, and if no arguments were specified, the kernel will run normally.

You can run arguments on the next reboot by using the arginj command when on shell.

You can make the prompt appear in two methods:

1. By changing config option `Prompt for Arguments on Boot` to True (For more information about config, see `Configuration for KS`)
2. By running Kernel Simulator with the promptArgs cmdline argument (eg. `"Kernel Simulator.exe" promptArgs`)

### Useful arguments

1. safe: Disables custom mods and screensavers. Can be used to check if the mods are causing trouble.
2. quiet: Don't let the kernel say anything on boot
3. cmdinject: Auto-run commands when you're logged in. You can separate multiple commands using a colon with spaces (Ex. cmdinject setthemes Bluespire : arginj debug)
4. debug: Enables the diagnostic messages on the kernel to allow debugging. You can use it to send a bug report to us. It saves to a file.
5. maintenance: Goes into the safe mode, which the mods will not be loaded, and the screensavers cannot be loaded.
6. testInteractive: Enters the test shell
7. help: Gives you tips if you're unsure what to separate
