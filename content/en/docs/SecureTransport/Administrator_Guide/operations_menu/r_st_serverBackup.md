{
    "title": "Server backup",
    "linkTitle": "Server backup",
    "weight": "170"
}To minimize the risk of data loss, perform regular backups of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge data.

When performing a server backup, you must back up the following files and directories in `<FILEDRIVEHOME>`:

-   `conf/`
-   `lib/certs/`
-   `brules/conf/brules.xml`
-   `brules/local/`
-   `bin/agents/`
-   `var/db/mysql/` (AIX only)
-   `var/db/mariadb/` (for servers using the embedded database)

Include the following files if changes have been made after the initial installation of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>:

-   `lib/msgs/`
-   `share/ftdocs/`

Include the user account home folders.

Add the following files to keep existing log files, statistics, and MDN receipts:

-   `var/logs/`
-   `var/db/hist/logs/`
-   `var/db/stats/`

For <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server with an external database, back up the database using standard Oracle or Microsoft SQL Server procedures.

For <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server with an embedded database or <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, use `<FILEDRIVEHOME>/bin/backup_db` to back up the database tables. The `backup_db Backup_File` command writes the backup data to the file named. You must enter the database password. You can use the `-skiplog` option to prevent the `TransactionStatus` or `TransactionData` tables from being included. To restore the data, use the following command:

-   for servers with MySQL

`<FILEDRIVEHOME>/mysql/bin/mysql --defaults-file=<FILEDRIVEHOME>/conf/internaldb.conf -ptumbleweed st < Backup_file.sql`

-   for servers with MariaDB

`<FILEDRIVEHOME>/mariadb/bin/mariadb --defaults-file=<FILEDRIVEHOME>/conf/internaldb.conf -ptumbleweed st < Backup_file.sql`

For additional information about export and importing server configuration parameters and files for backup and restore, see <a href="../c_st_serverconfiguration#ServerMenu_1832073003_1107076" class="MCXref xref">Server configuration</a>.