# setcolors command

## Summary

You can set the kernel colors

## Description

This command allows you to set the kernel text colors, including the kernel error message, input message, license text, general text, etc. It also lets you set the background color to make your kernel look more personalized.

This command probes colors from ConsoleColors enum values known as integers. You may need to refer to [Color255.vb](https://github.com/EoflaOE/Kernel-Simulator/blob/ee7f10fb420de1f3d41e0be42fcb9d17ee4382cc/Kernel%20Simulator/Console/Color255.vb#L33) to get a list of colors.

If there is "def" in the color sets, then it will get the default color for the specified section. For example, if you execute this command "setcolors Red DarkRed Red DarkRed def def def Red Red DarkRed", the host name shell color, the username shell color and the background color will be set to their default values.

However if there is a RESET between colors, every color will get reset to their default settings. The THEME option is not implemented yet, although it exists in the AvailableColors() string array.

## Command usage

* setcolors (inputColor/def/RESET) (licenseColor/def/RESET) (contKernelErrorColor/def/RESET) (uncontKernelErrorColor/def/RESET) (hostNameShellColor/def/RESET) (userNameShellColor/def/RESET) (backgroundColor/def/RESET) (neutralTextColor/def/RESET) (cmdListColor/def/RESET) (cmdDefColor/def/RESET) (stageColor/def/RESET)

## Examples

* setcolors DarkCyan Blue DarkRed Red Cyan DarkCyan def Cyan Cyan DarkCyan Red
* setcolors DarkMagenta Magenta DarkRed Red Magenta DarkMagenta def Magenta Magenta DarkMagenta Red
* setcolors DarkYellow Yellow DarkRed Red Yellow DarkYellow def Yellow Yellow DarkYellow Red
