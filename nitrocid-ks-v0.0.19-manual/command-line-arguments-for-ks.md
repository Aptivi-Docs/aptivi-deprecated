# How do I run command-line arguments?

You can run these arguments to make the simulator behave differently, by running Kernel Simulator like below examples:

```cmd
choco install ks
"Kernel Simulator.exe" debug
"Kernel Simulator.exe" testMod ModToBeTested.vb
```

## Useful arguments

1. testMod: Checks the integrity of the mod by compiling then exits.
2. testInteractive: Opens the test interactive shell.
3. debug: Alternative way to turn on kernel debugging.
4. args: Makes the kernel prompt the user to write arguments on boot.
5. help: Opens help page for command-line arguments
