{
    "title": "Control log fallback from database to file",
    "linkTitle": "Control log fallback from database to file",
    "weight": "360"
}If the embedded or external database stops accepting log messages, SecureTransport directs the messages to `<FILEDRIVEHOME>/var/logs/admin/serverlog-fallback.log`.

You can control this behavior by setting the following parameters for each server in `<FILEDRIVEHOME>/conf/configuration.xml`:

-   When the embedded database is used, the `hibernate.c3p0.timeout` attribute of the component for each server controls the timeout after which an idle connection will be removed from the pool. The default value is 30 minutes.
-   When an external Oracle database is used, the `hibernate.connection.oracle.jdbc.ReadTimeout` attribute of the
    component for each server controls the read timeout, how long to wait for a response from the
    database before failing a query, for all TCP sockets to the database. The default is five minutes.
-   When an external database is used, the `hibernate.c3p0.checkoutTimeout` attribute of the
    component for each server
    controls the Database connect timeout, how long to wait for a
    connection to be established. The default is five minutes.

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
