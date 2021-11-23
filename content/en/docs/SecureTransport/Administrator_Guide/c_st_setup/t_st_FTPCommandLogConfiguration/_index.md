{
    "title": "Configure FTP command log",
    "linkTitle": "Configure FTP command log",
    "weight": "200"
}The {{< SecureTransport/componentshortname  >}} command logging feature works as a tracking system. It maintains a log of the commands entered by the users during an FTP session. Command logging is available for the FTP server only. You can use the `Ftp.CommandLogging.File` server configuration parameter to set the location of the command log. By default, the location is `<FILEDRIVEHOME>/var/logs/cmdlog`.

Use the *Command Logging* page to view and determine which user classes should have their commands logged. You can restrict this feature by user class, so that the FTP sessions of only certain user classes are logged.

The following topics provide how-to instructions for configuring and managing the FTP command log:

-   [Add a command logging entry](t_st_add_command_logging_entry) - Provides how-to instructions for adding a command logging entry.
-   [Enable or disable command logging entries](t_st_enable_disable_command_logging_entries) - Provides how-to instructions for enabling or disabling command logging entries.
-   [Edit a command logging entry](t_st_edit_command_logging_entry) - Provides how-to instructions for editing a command log entry.
-   [Delete command logging entries](t_st_delete_command_logging_entries) - Provides how-to instructions for deleting command logging entries.
