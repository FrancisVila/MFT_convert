{
    "title": "Database log files",
    "linkTitle": "Database log files",
    "weight": "290"
}These log files exist on {{< SecureTransport/componentshortname  >}} Edge systems and on {{< SecureTransport/componentshortname  >}} Server systems that use an embedded (MySQL or MariaDB) database.

**mariadb\_error.log / mysql\_error.log** – This log file contains the messages from the embedded database server. The log file contains information indicating when `mariadbd / mysqld` was started and stopped and also any critical errors that occur while the server is running. For more information on MySQL, refer to the documentation of the error log on the MySQL Developer Zone website.  
For more information on MariaDB, refer to the official documentation of the error log on the MariaDB website.

**mariadb\_slow\_query.log / mysql\_slow\_query.log** – This log file contains SQL statements that took more than `long_query_time` seconds to execute. For more information on MySQL, refer to the documentation of the slow query log on the MySQL Developer Zone website. For more information on MariaDB, refer to the official documentation of the error log on the MariaDB website.

**Related topics:**

-   <a href="../r_st_log4j_files" class="MCXref xref">Log4j files</a>
-   <a href="../c_st_ftpd_log_file" class="MCXref xref">FTPD log file</a>
-   <a href="../c_st_admin_log_file" class="MCXref xref">Admin log file</a>
-   <a href="../c_st_general_log_files" class="MCXref xref">General log files</a>
-   <a href="../t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a>
-   <a href="../t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a>
-   <a href="../t_st_control_log_fallback_from_database_to_file" class="MCXref xref">Control log fallback from database to file</a>
-   <a href="../t_st_server_log_rotation_scheduling" class="MCXref xref">Server log rotation and monitor scheduling</a>
