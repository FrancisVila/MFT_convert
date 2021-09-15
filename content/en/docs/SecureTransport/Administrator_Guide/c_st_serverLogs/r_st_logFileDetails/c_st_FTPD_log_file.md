{
    "title": "FTPD log file",
    "linkTitle": "FTPD log file",
    "weight": "310"
}**cmdlog** – This log file contains the FTP commands and arguments that are sent by FTP clients after they connect successfully. (Thus, it does not show the USER and PASS commands.) Note that this log is not enabled by default. For more information, see [Configure FTP command log](../../../c_st_setup/t_st_ftpcommandlogconfiguration).

The format of this file is:

`<calendar_time> <PID> <user_name> <command>`

Where:

`<current_time>` - The current local time, for example Tue Feb 24 14:28:01

`<PID>` - The process ID

`<user_name>` - Account name

`<command>` - FTP command and (optional) target file name

The possible FTP commands are listed under `Ftp.Commands` configuration option.

The default path of the **cmdlog** file is `<filedrivehome>/var/logs` and is configurable trough the `Ftp.CommandLogging.File` configuration option.

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
