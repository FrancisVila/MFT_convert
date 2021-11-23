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

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
