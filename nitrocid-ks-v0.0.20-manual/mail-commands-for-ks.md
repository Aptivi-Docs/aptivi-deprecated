# Brief overview of mail shell

The mail shell, invoked by `mail`, is one of the shells available in the kernel that provides you basic mail functions, such as reading mail, reading encrypted mail, sending mail, listing mail, and so on. It supports folder management.

For more information about every command, click the command.

## All mail commands

| Command                                | Description                                                                                                |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| \[\[cd\|KS Mail Command cd]]           | Changes directory to another mail folder.                                                                  |
| \[\[exit\|KS Mail Command exit]]       | Exits the mail shell and returns to shell.                                                                 |
| \[\[list\|KS Mail Command list]]       | Lists messages. You can use page number to navigate your messages.                                         |
| \[\[lsdirs\|KS Mail Command lsdirs]]   | Lists directories.                                                                                         |
| \[\[mkdir\|KS Mail Command mkdir]]     | Makes a mail directory                                                                                     |
| \[\[mv\|KS Mail Command mv]]           | Moves a message to another directory.                                                                      |
| \[\[mvall\|KS Mail Command mvall]]     | Moves all messages from a specified sender to another directory.                                           |
| \[\[read\|KS Mail Command read]]       | Reads a message.                                                                                           |
| \[\[readenc\|KS Mail Command readenc]] | Reads an encrypted message. You should have the sender's GPG public key.                                   |
| \[\[ren\|KS Mail Command ren]]         | Renames a directory.                                                                                       |
| \[\[rm\|KS Mail Command rm]]           | Removes a message.                                                                                         |
| \[\[rmall\|KS Mail Command rmall]]     | Removes all messages from a specified sender.                                                              |
| \[\[rmdir\|KS Mail Command rmdir]]     | Removes a mail directory                                                                                   |
| \[\[send\|KS Mail Command send]]       | Sends mail.                                                                                                |
| \[\[sendenc\|KS Mail Command sendenc]] | Sends encrypted mail. You should have your own private key, and the recipient should have your public key. |
