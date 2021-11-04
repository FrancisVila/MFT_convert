{
    "title": "Control log fallback from database to file",
    "linkTitle": "Control log fallback from database to file",
    "weight": "350"
}If the embedded or external database stops accepting log messages, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> directs the messages to `<FILEDRIVEHOME>/var/logs/admin/serverlog-fallback.log`.

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

-   <a href="../r_st_log4j_files" class="MCXref xref">Log4j files</a>
-   <a href="../c_st_database_log_files" class="MCXref xref">Database log files</a>
-   <a href="../c_st_ftpd_log_file" class="MCXref xref">FTPD log file</a>
-   <a href="../c_st_admin_log_file" class="MCXref xref">Admin log file</a>
-   <a href="../c_st_general_log_files" class="MCXref xref">General log files</a>
-   <a href="../t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a>
-   <a href="../t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a>
-   <a href="../t_st_server_log_rotation_scheduling" class="MCXref xref">Server log rotation and monitor scheduling</a>
