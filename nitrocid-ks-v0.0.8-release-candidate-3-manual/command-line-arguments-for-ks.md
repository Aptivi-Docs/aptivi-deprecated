# How do I run command-line arguments?

You can run these arguments to make the simulator behave differently, by running Kernel Simulator like below examples:

```cmd
choco install ks
"Kernel Simulator.exe" createConf
"Kernel Simulator.exe" testMod ModToBeTested.m
```

Useful arguments:

1. createConf: Used in the KS Config Tool. It only creates a log then exits
2. testMod: Checks the integrity of the mod by compiling, then exits
