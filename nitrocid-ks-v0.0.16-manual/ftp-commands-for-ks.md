# FTP-commands-for-KS

### Administrative commands

1. cp: Copies a file to the server
2. del: You can delete unwanted files from the server
3. mv: Moves a remote file to another remote directory
4. put: Send your local file to the server
5. perm: Sets file permissions. This only works on FTP servers that run on Unix.

### Normal user commands

1. pwdl: Get your current working local directory
2. pwdr: Get your current working server directory
3. cdl: Changes your local directory to another directory that exists
4. cdr: Changes your remote directory to another directory that exists in the server
5. connect: Lets you communicate with the server, and with the credentials if specified
6. disconnect: When you're finished communicating with the server, use this command to let the server know that you're leaving
7. get: Gets the remote file from the server to your current local working directory
8. exit: Exits the FTP shell
9. lsl: Lists the contents of your current working directory, or specified directory
10. lsr: Lists the contents of your current working server directory, or specified directory
11. quickconnect: Use the speed dial to quickly connect to any FTP server. Automatically filled when connecting to a server for the first time.
12. type: Changes the data type (ASCII, Binary)

For more information about every command, see the right pane.
