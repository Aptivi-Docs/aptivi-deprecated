# Commands for (S)FTP client for KS

The commands below are available for the (S)FTP client that is built-in to KS. Some of the commands are available only for FTP shells.

For more information about every command, click on the command.

## Administrative commands

| Command                                   | Description                                                             |
| ----------------------------------------- | ----------------------------------------------------------------------- |
| \[\[cp\|KS FTP Command cp]]               | Copies a file to the server                                             |
| \[\[del\|KS (S)FTP Command del]]          | You can delete unwanted files from the server                           |
| \[\[mv\|KS FTP Command mv]]               | Moves a remote file to another remote directory                         |
| \[\[put\|KS (S)FTP Command put]]          | Send your local file to the server                                      |
| \[\[putfolder\|KS FTP Command putfolder]] | Send your local folder to the server                                    |
| \[\[perm\|KS FTP Command perm]]           | Sets file permissions. This only works on FTP servers that run on Unix. |

## Normal user commands

| Command                                            | Description                                                                                                                   |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| \[\[pwdl\|KS (S)FTP Command pwdl]]                 | Get your current working local directory                                                                                      |
| \[\[pwdr\|KS (S)FTP Command pwdr]]                 | Get your current working server directory                                                                                     |
| \[\[cdl\|KS (S)FTP Command cdl]]                   | Changes your local directory to another directory that exists                                                                 |
| \[\[cdr\|KS (S)FTP Command cdr]]                   | Changes your remote directory to another directory that exists in the server                                                  |
| \[\[connect\|KS (S)FTP Command connect]]           | Lets you communicate with the server, and with the credentials if specified                                                   |
| \[\[disconnect\|KS (S)FTP Command disconnect]]     | When you're finished communicating with the server, use this command to let the server know that you're leaving               |
| \[\[get\|KS (S)FTP Command get]]                   | Gets the remote file from the server to your current local working directory                                                  |
| \[\[getfolder\|KS FTP Command getfolder]]          | Gets the remote folder from the server to your current local working directory                                                |
| \[\[lsl\|KS (S)FTP Command lsl]]                   | Lists the contents of your current working directory, or specified directory                                                  |
| \[\[lsr\|KS (S)FTP Command lsr]]                   | Lists the contents of your current working server directory, or specified directory                                           |
| \[\[quickconnect\|KS (S)FTP Command quickconnect]] | Use the speed dial to quickly connect to any FTP server. Automatically filled when connecting to a server for the first time. |
| \[\[type\|KS FTP Command type]]                    | Changes the data type (ASCII, Binary)                                                                                         |
