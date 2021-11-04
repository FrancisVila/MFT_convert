{
    "title": "FTPD log file",
    "linkTitle": "FTPD log file",
    "weight": "300"
}**cmdlog** – This log file contains the FTP commands and arguments that are sent by FTP clients after they connect successfully. (Thus, it does not show the USER and PASS commands.) Note that this log is not enabled by default. For more information, see <a href="../../../c_st_setup/t_st_ftpcommandlogconfiguration#SetupMenu_1217491348_1048366" class="MCXref xref">Configure FTP command log</a>.

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

-   <a href="../r_st_log4j_files" class="MCXref xref">Log4j files</a>
-   <a href="../c_st_database_log_files" class="MCXref xref">Database log files</a>
-   <a href="../c_st_admin_log_file" class="MCXref xref">Admin log file</a>
-   <a href="../c_st_general_log_files" class="MCXref xref">General log files</a>
-   <a href="../t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a>
-   <a href="../t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a>
-   <a href="../t_st_control_log_fallback_from_database_to_file" class="MCXref xref">Control log fallback from database to file</a>
-   <a href="../t_st_server_log_rotation_scheduling" class="MCXref xref">Server log rotation and monitor scheduling</a>
