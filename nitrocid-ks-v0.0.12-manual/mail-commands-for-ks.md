# Mail-commands-for-KS

### Brief overview of mail shell

The mail shell, invoked by `lsmail`, is one of the shells available in the kernel that provides you basic mail functions, such as reading mail, reading encrypted mail, sending mail, listing mail, and so on. It supports folder management.

### All mail commands

1. cd: Changes directory to another mail folder.
2. lsdirs: Lists directories.
3. exit: Exits the mail shell and returns to shell.
4. list: Lists messages. You can use page number to navigate your messages.
5. mkdir: Makes a mail directory
6. mv: Moves a message to another directory.
7. mvall: Moves all messages from a specified sender to another directory.
8. read: Reads a message.
9. readenc: Reads an encrypted message. You should have the sender's GPG public key.
10. ren: Renames a directory.
11. rm: Removes a message.
12. rmall: Removes all messages from a specified sender.
13. rmdir: Removes a mail directory
14. send: Sends mail.
15. sendenc: Sends encrypted mail. You should have your own private key, and the recipient should have your public key.

For more information about every command, see the right pane.
