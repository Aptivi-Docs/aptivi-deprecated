# setsaver command

## Summary

Sets your default screensaver as your own screensaver or built-in savers

## Description

You can set your default screensaver as your own screensaver by the modfile or built-in savers such as matrix, disco, colorMix, ...

* glitterColor: Glitter of color backgrounds.
* glitterColor255: A 255-color version of `glitterColor`
* glitterMatrix: Glitter of matrix (0, 1) in green text color
* matrix: Displays the basic matrix that prints between 0 and 1 in green text color
* disco: Displays the disco lights
* disco255: A 255-color version of `disco`
* colorMix: It changes the background color to the random color and prints a " " to make a colored block, and repeats.
* colorMix255: A 255-color version of `colorMix`
* lines: Displays a randomly-moving line like a laser beam colorfully.
* lines255: A 255-color version of `lines`
* aptErrorSim: Simulates a Ubuntu environment failing to download software from apt repo
* hackUserFromAD: Simulates a Windows command prompt on how to hack a user from Active Directory

## Command usage

* setsaver ((ScreenSaverName)SS.m/matrix/disco/disco255/colorMix/colorMix255/glitterMatrix/lines/glitterColor/aptErrorSim/hackUserFromAD)

## Examples

* setsaver matrix
* setsaver GameOfLifeSS.m
* setsaver LinesSS.m
