# listremote or lsr FTP command

## Summary

Lists the contents of the current folder or the folder provided

## Description

You can see the list of the files and sub-directories contained in the current working directory if no directories are specified, or in the specified directory, if specified.

You can also see the list of the files and sub-directories contained in the previous directory of your current position.

Unlike listlocal or lsr, you should connect to the server to use this command, because it lists directories in the server, not in the local hard drive.

## Command usage

* listremote/lsr \[folder/..]

## Examples

* listremote: Lists the contents in the working directory
* listremote ..: Lists the contents in the previous working directory
* lsr cities: Lists the contents of "cities" folder
