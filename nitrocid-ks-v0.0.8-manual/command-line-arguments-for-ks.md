# How do I run command-line arguments?

You can run these arguments to make the simulator behave differently, by running Kernel Simulator like below examples:

```cmd
choco install ks
"Kernel Simulator.exe" createConf
"Kernel Simulator.exe" testMod ModToBeTested.m
```

## Useful arguments

1. createConf: Used in the KS Config Tool. It only creates a log then exits.
2. testMod: Checks the integrity of the mod by compiling then exits.
3. testInteractive: Opens the test interactive shell.
4. debug: Alternative way to turn on kernel debugging.

## Arguments for CI environments

These arguments may only run on CI environments. It may work locally, but it's recommended not to use them, unless you're on the CI environment.

1. CI-TestPrint: Tests printing the string.
2. CI-TestWdbg: Writes debug log to the console when the kernel has successfully booted then exits.
3. CI-TestConfig: Writes content of generated config file then exits.
4. CI-TestInitialize: Measures how much time taken to successfully boot the kernel in milliseconds.
5. CI-TestEval: Tests string evaluation, then exits.
6. CI-TestStrTrunc: Tests string truncation, then exits.
7. CI-TestSSEs: Checks the processor if SSE, SSE2, and SSE3 instructions are supported.
8. CI-TestMOTD: Reads MOTD, writes it to the console, then exits.
9. CI-TestMAL: Reads MAL, writs it to the console, then exits.
10. CI-TestPlace: Parses the placeholders, then exits.
11. CI-TestCalc: Tests the DataTable.Compute function on three expressions, then exits.
