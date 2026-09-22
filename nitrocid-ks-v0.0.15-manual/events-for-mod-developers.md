# List of events that KS fires

KS fires an event after its own actions which can be seen below:

|               Event               |                            When                            |                              Arguments                              |
| :-------------------------------: | :--------------------------------------------------------: | :-----------------------------------------------------------------: |
|           KernelStarted           |                 When the kernel is started                 |                                  -                                  |
|              PreLogin             |                     Fired before login                     |                                  -                                  |
|             PostLogin             |                      Fired after login                     |                               Username                              |
|          ShellInitialized         |                When the shell is initialized               |                                  -                                  |
|         PreExecuteCommand         |               Fired before command execution               |                               Command                               |
|         PostExecuteCommand        |                Fired after command execution               |                               Command                               |
|            KernelError            |                    Fired on kernel error                   | Error Type, Reboot?, Reboot Time, Description, Exception, Arguments |
|          ContKernelError          |              Fired on continuable kernel error             | Error Type, Reboot?, Reboot Time, Description, Exception, Arguments |
|            PreShutdown            |                    Fired before shutdown                   |                                  -                                  |
|            PostShutdown           |                    Fired after shutdown                    |                                  -                                  |
|             PreReboot             |                     Fired before reboot                    |                                  -                                  |
|             PostReboot            |                     Fired after reboot                     |                                  -                                  |
|         PreShowScreensaver        |                 Fired on screensaver start                 |                             Screensaver                             |
|        PostShowScreensaver        |                 Fired on screensaver finish                |                             Screensaver                             |
|             PreUnlock             |                   Fired before unlocking                   |                             Screensaver                             |
|             PostUnlock            |                    Fired after unlocking                   |                             Screensaver                             |
|            CommandError           |                   Fired on command error                   |                          Command, Exception                         |
|          PreReloadConfig          |                 Fired before config reload                 |                                  -                                  |
|          PostReloadConfig         |                  Fired after config reload                 |                                  -                                  |
|         PlaceholderParsing        |        Fired while the placeholders are being parsed       |                            Target String                            |
|         PlaceholderParsed         |              Fired after parsing placeholders              |                            Target String                            |
|          GarbageCollected         |               Fired after garbage collection               |                                  -                                  |
|        FTPShellInitialized        |              When the FTP shell is initialized             |                                  -                                  |
|        FTPPreExecuteCommand       |             Fired before FTP command execution             |                               Command                               |
|       FTPPostExecuteCommand       |              Fired after FTP command execution             |                               Command                               |
|          FTPCommandError          |                 Fired on FTP command error                 |                          Command, Exception                         |
|           FTPPreDownload          | Fired before an FTP file is transferred locally (download) |                                 File                                |
|          FTPPostDownload          |  Fired after an FTP file is transferred locally (download) |                           File, Succeeded?                          |
|            FTPPreUpload           |  Fired before an FTP file is transferred remotely (upload) |                                 File                                |
|           FTPPostUpload           |  Fired after an FTP file is transferred remotely (upload)  |                           File, Succeeded?                          |
|        IMAPShellInitialized       |             When the IMAP shell is initialized             |                                  -                                  |
|       IMAPPreExecuteCommand       |             Fired before IMAP command execution            |                               Command                               |
|       IMAPPostExecuteCommand      |             Fired after IMAP command execution             |                               Command                               |
|          IMAPCommandError         |                 Fired on IMAP command error                |                          Command, Exception                         |
|   RemoteDebugConnectionAccepted   |                  A connection is accepted                  |                                Target                               |
| RemoteDebugConnectionDisconnected |                A connection is disconnected                |                                Target                               |
|     RemoteDebugExecuteCommand     |           Fired on remote debug command execution          |                           Target, Command                           |
|      RemoteDebugCommandError      |             Fired on remote debug command error            |                      Target, Command, Exception                     |
|           RPCCommandSent          |                     RPC command is sent                    |                               Command                               |
|         RPCCommandReceived        |                   RPC command is received                  |                               Command                               |
|          RPCCommandError          |                 Fired on RPC command error                 |                          Command, Exception                         |
|            SSHConnected           |                      Connected to SSH                      |                                Target                               |
|          SSHDisconnected          |                    Disconnected from SSH                   |                                  -                                  |
|              SSHError             |                     Fired on SSH error                     |                              Exception                              |
|           UESHPreExecute          |             Fired vefore UESH script execution             |                               Command                               |
|          UESHPostExecute          |              Fired after UESH script execution             |                               Command                               |
|             UESHError             |                     Fired on UESH error                    |                          Command, Exception                         |
|        TextShellInitialized       |           When the text edit shell is initialized          |                                  -                                  |
|       TextPreExecuteCommand       |          Fired before text edit command execution          |                               Command                               |
|       TextPostExecuteCommand      |           Fired after text edit command execution          |                               Command                               |
|          TextCommandError         |              Fired on text edit command error              |                          Command, Exception                         |
