{
    "title": "Admin log file",
    "linkTitle": "Admin log file",
    "weight": "310"
}**audit.log** – This log file contains information on configuration changes made by Java components of the {{< SecureTransport/componentshortname  >}} Administration Tool and database starts and stops. When the configuration changes are logged to the database (the default), failed administrator login attempts and database starts, stops, and configuration changes are still logged to this file.

The format and content of this file is controlled by the `<FILEDRIVEHOME>/conf/admin-log4j.xml` file. This file uses the log4j format. By default, the logs are in the following format:

`%d %s   %m`

Where:

-   `%d` is the date
-   `%s` is the subcomponent
-   `%m` is the log message

**admin\_tomcat&lt;date>.log** – This log file contains Tomcat-specific error messages. The file contains the Java stack traces for the errors.

**Related topics:**

-   <a href="../r_st_log4j_files" class="MCXref xref">Log4j files</a>
-   <a href="../c_st_database_log_files" class="MCXref xref">Database log files</a>
-   <a href="../c_st_ftpd_log_file" class="MCXref xref">FTPD log file</a>
-   <a href="../c_st_general_log_files" class="MCXref xref">General log files</a>
-   <a href="../t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a>
-   <a href="../t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a>
-   <a href="../t_st_control_log_fallback_from_database_to_file" class="MCXref xref">Control log fallback from database to file</a>
-   <a href="../t_st_server_log_rotation_scheduling" class="MCXref xref">Server log rotation and monitor scheduling</a>
