{
    "title": "Server backup",
    "linkTitle": "Server backup",
    "weight": "180"
}To minimize the risk of data loss, perform regular backups of the SecureTransport Server and SecureTransport Edge data.

When performing a server backup, you must back up the following files and directories in `<FILEDRIVEHOME>`:

-   `conf/`
-   `lib/certs/`
-   `brules/conf/brules.xml`
-   `brules/local/`
-   `bin/agents/`
-   `var/db/mysql/` (AIX only)
-   `var/db/mariadb/` (for servers using the embedded database)

Include the following files if changes have been made after the initial installation of SecureTransport:

-   `lib/msgs/`
-   `share/ftdocs/`

Include the user account home folders.

Add the following files to keep existing log files, statistics, and MDN receipts:

-   `var/logs/`
-   `var/db/hist/logs/`
-   `var/db/stats/`

For SecureTransport Server with an external database, back up the database using standard Oracle or Microsoft SQL Server procedures.

For SecureTransport Server with an embedded database or SecureTransport Edge, use `<FILEDRIVEHOME>/bin/backup_db` to back up the database tables. The `backup_db Backup_File` command writes the backup data to the file named. You must enter the database password. You can use the `-skiplog` option to prevent the `TransactionStatus` or `TransactionData` tables from being included. To restore the data, use the following command:

-   for servers with MySQL

`<FILEDRIVEHOME>/mysql/bin/mysql --defaults-file=<FILEDRIVEHOME>/conf/internaldb.conf -ptumbleweed st < Backup_file.sql`

-   for servers with MariaDB

`<FILEDRIVEHOME>/mariadb/bin/mariadb --defaults-file=<FILEDRIVEHOME>/conf/internaldb.conf -ptumbleweed st < Backup_file.sql`

For additional information about export and importing server configuration parameters and files for backup and restore, see [Server configuration](../c_st_serverconfiguration).
