# Placeholders

Placeholders in KS is the pre-defined variables for usage with common kernel variables, like the current directory. They're enclosed in these characters `<` and `>`, surrounding the specific placeholder.

Currently, these placeholders can be used:

| Placeholder                       | Description                                                                                       | Usages             |
| --------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------ |
| `<user>`                          | Gets the current user name (Ex: joe)                                                              | Login, MAL, Shells |
| `<host>`                          | Gets the current host name                                                                        | Everywhere         |
| `<currentdirectory>`              | Gets the current directory                                                                        | Shells             |
| `<currentdirectoryname>`          | Gets the current directory name                                                                   | Shells             |
| `<shortdate>`                     | Gets the system date in MM/DD/YYYY format (Ex: 12/7/2018)                                         | Everywhere         |
| `<longdate>`                      | Gets the system date in `<DayName>`, `<MonthName>` DD, YYYY format (Ex: Friday, December 7, 2018) | Everywhere         |
| `<shorttime>`                     | Gets the system time in HH:MM format (Ex: 4:30)                                                   | Everywhere         |
| `<longtime>`                      | Gets the system time in HH:MM:SS AM/PM format (Ex: 4:30:10 PM)                                    | Everywhere         |
| `<timezone>`                      | Gets the system standard time zone (Ex: Egypt Standard Time)                                      | Everywhere         |
| `<summertimezone>`                | Gets the system daylight saving time zone (Ex: Syria Daylight Time)                               | Everywhere         |
| `<system>`                        | Gets the operating system                                                                         | Everywhere         |
| `<ftpuser>`                       | Gets the current FTP user                                                                         | FTP shell          |
| `<ftpaddr>`                       | Gets the current FTP address                                                                      | FTP shell          |
| `<mailuser>`                      | Gets the current mail user or e-mail address                                                      | mail shell         |
| `<mailaddr>`                      | Gets the current mail server address                                                              | mail shell         |
| `<sftpuser>`                      | Gets the current SFTP user                                                                        | SFTP shell         |
| `<sftpaddr>`                      | Gets the current SFTP address                                                                     | SFTP shell         |
| `<currentftpdirectory>`           | Gets the current FTP remote directory                                                             | FTP shell          |
| `<currentftplocaldirectory>`      | Gets the current FTP local directory                                                              | FTP shell          |
| `<currentftplocaldirectoryname>`  | Gets the current FTP local directory name                                                         | FTP shell          |
| `<currentmaildirectory>`          | Gets the current mail directory                                                                   | mail shell         |
| `<currentsftpdirectory>`          | Gets the current SFTP remote directory                                                            | SFTP shell         |
| `<currentsftplocaldirectory>`     | Gets the current SFTP local directory                                                             | SFTP shell         |
| `<currentsftplocaldirectoryname>` | Gets the current SFTP local directory name                                                        | SFTP shell         |
| `<f:<foregroundcolor>>`           | Manipulates with the foreground color                                                             | Everywhere         |
| `<b:<backgroundcolor>>`           | Manipulates with the background color                                                             | Everywhere         |
| `<$<variable>>`                   | Uses the UESH variable                                                                            | Everywhere         |
