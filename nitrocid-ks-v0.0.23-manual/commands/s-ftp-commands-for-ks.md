# Commands for (S)FTP client for KS

The commands below are available for the (S)FTP client that is built-in to KS. Some of the commands are available only for FTP shells.

For more information about every command, click on the command.

## Administrative commands

| Command                                               | Description                                                             |
| ----------------------------------------------------- | ----------------------------------------------------------------------- |
| [cp](sftp/ftponly/ks-ftp-command-cp.md)               | Copies a file to the server                                             |
| [del](sftp/ks-s-ftp-command-del.md)                   | You can delete unwanted files from the server                           |
| [mv](sftp/ftponly/ks-ftp-command-mv.md)               | Moves a remote file to another remote directory                         |
| [put](sftp/ks-s-ftp-command-put.md)                   | Send your local file to the server                                      |
| [putfolder](sftp/ftponly/ks-ftp-command-putfolder.md) | Send your local folder to the server                                    |
| [perm](sftp/ftponly/ks-ftp-command-perm.md)           | Sets file permissions. This only works on FTP servers that run on Unix. |

## Normal user commands

| Command                                               | Description                                                                                                                   |
| ----------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [pwdl](sftp/ks-s-ftp-command-pwdl.md)                 | Get your current working local directory                                                                                      |
| [pwdr](sftp/ks-s-ftp-command-pwdr.md)                 | Get your current working server directory                                                                                     |
| [cdl](sftp/ks-s-ftp-command-cdl.md)                   | Changes your local directory to another directory that exists                                                                 |
| [cdr](sftp/ks-s-ftp-command-cdr.md)                   | Changes your remote directory to another directory that exists in the server                                                  |
| [connect](sftp/ks-s-ftp-command-connect.md)           | Lets you communicate with the server, and with the credentials if specified                                                   |
| [disconnect](sftp/ks-s-ftp-command-disconnect.md)     | When you're finished communicating with the server, use this command to let the server know that you're leaving               |
| [get](sftp/ks-s-ftp-command-get.md)                   | Gets the remote file from the server to your current local working directory                                                  |
| [getfolder](sftp/ftponly/ks-ftp-command-getfolder.md) | Gets the remote folder from the server to your current local working directory                                                |
| [lsl](sftp/ks-s-ftp-command-lsl.md)                   | Lists the contents of your current working directory, or specified directory                                                  |
| [lsr](sftp/ks-s-ftp-command-lsr.md)                   | Lists the contents of your current working server directory, or specified directory                                           |
| [quickconnect](sftp/ks-s-ftp-command-quickconnect.md) | Use the speed dial to quickly connect to any FTP server. Automatically filled when connecting to a server for the first time. |
| [type](sftp/ftponly/ks-ftp-command-type.md)           | Changes the data type (ASCII, Binary)                                                                                         |
