{
    "title": "Direct log data to separate Oracle databases",
    "linkTitle": "Direct log data to separate Oracle databases",
    "weight": "190"
}If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server uses an external Oracle database, you can direct transfer log (file tracking) data and server log data to different databases from the one used for the rest of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> configuration and data.

You can direct the transfer log data and server log data to the same database or to different databases. When you change the database used to store log data, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not copy the data from its current location to the new location.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> continues to operate when the external server log database is unavailable. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> directs the server log data to `<FILEDRIVEHOME>/var/logs/serverlog-fallback.log`. The *Server Log* page indicates that the log is unavailable and provides a link you can use to download the file.

1.  Make sure the Oracle databases have the characteristics listed in the *Database installation prerequisites* topic of the <span class="redirect_st_inst" cshid="install" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Installation Guide*</span>. Depending on the log data you direct to a database, you must define the `ST_FILETRACKING` tablespace or the `ST_SERVERLOG` tablespace.
2.  Select **Setup > Database Settings**.  
    The *Database Settings* page is displayed with the external database settings under *Enterprise Clustering - Oracle External Database*.
3.  Select **Show Advanced Settings**.  
    The settings for the two additional databases are displayed.
4.  Under *Enterprise Clustering - Oracle External Database - Transfer Log* and *Enterprise Clustering - Oracle External Database - Server Log*, type the values necessary to connect to the external databases. To continue to use the primary database, retain the default values.  
    For description of the required values, see <a href="../t_st_database#top" class="MCXref xref">Migrate from embedded database to external Oracle database</a>.
5.  For each database, click **Test Connection to Oracle Database**.  
    If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays a failure message, correct the network, Oracle, or other error reported and try again.
6.  Type the passwords again and click **Save**.  
    The first time the new database is referenced, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> creates the tables for the log data. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not copy the log data from the previous database to the new database and does not display the log entries from the previous database in the *File Tracking* and *Server Log* pages.
7.  Select **Operations > Server Control**.
8.  On the *Server Control* page, stop and restart all the protocol servers and the TM Server.
9.  Log out of the Administration Tool.
10. Log on to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server and stop and restart the Administration Tool service using the `stop_admin` and `start_admin` commands in `<FILEDRIVEHOME>/bin`.
11. In an Enterprise Cluster (EC), repeat steps 2 though 10 for all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers.

**Related topics:**

-   <a href="../t_st_mysql" class="MCXref xref">Change the embedded database configuration</a>
-   <a href="../t_st_database" class="MCXref xref">Migrate from embedded database to external Oracle database</a>
-   <a href="../t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a>
-   <a href="../t_st_sqlserver" class="MCXref xref">Change the external Microsoft SQL Server database</a>
