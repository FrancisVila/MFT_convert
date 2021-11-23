{
    "title": "Database log files",
    "linkTitle": "Database log files",
    "weight": "290"
}These log files exist on {{< SecureTransport/componentshortname  >}} Edge systems and on {{< SecureTransport/componentshortname  >}} Server systems that use an embedded (MySQL or MariaDB) database.

**mariadb\_error.log / mysql\_error.log** – This log file contains the messages from the embedded database server. The log file contains information indicating when `mariadbd / mysqld` was started and stopped and also any critical errors that occur while the server is running. For more information on MySQL, refer to the documentation of the error log on the MySQL Developer Zone website.  
For more information on MariaDB, refer to the official documentation of the error log on the MariaDB website.

**mariadb\_slow\_query.log / mysql\_slow\_query.log** – This log file contains SQL statements that took more than `long_query_time` seconds to execute. For more information on MySQL, refer to the documentation of the slow query log on the MySQL Developer Zone website. For more information on MariaDB, refer to the official documentation of the error log on the MariaDB website.

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
