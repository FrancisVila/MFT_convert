{
    "title": "Requirements for Microsoft SQL Server databases",
    "linkTitle": "Requirements for Microsoft SQL Server databases",
    "weight": "130"
}-   For a complete list of supported Microsoft SQL Server versions, refer to <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm" class="MCXref xref">Axway and third-party software support</a>.

-   The Microsoft SQL Server collation must be defined as case insensitive (SQL\_Latin1\_General\_CP1\_CI\_AS).

-   {{< SecureTransport/componentshortname >}} can connect to an external Microsoft SQL Server database over a plain or secure connection.
    Starting with SecureTransport 5.5-20201029, the external database server’s certificates that contain `keyUsage` extensions MUST also have the `digitalSignature` indicator enabled. This affects both secure and non-secure connections.

-   The database must have the `READ_COMMITED_SNAPSHOT` option set to ON  
    To check if option is enabled, execute the following query:  
    SELECT `is_read_committed_snapshot_on` FROM `sys.databases` WHERE name = *yourdatabase*  
    If it is not set, you can set it by executing the following:  
    ALTER DATABASE *yourdatabase*
    SET `READ_COMMITTED_SNAPSHOT` ON

-   The database must have the following filegroups defined with at least one file in each filegroup:

    -   `ST_DATA` – configuration, account, sites, and certificates (the default filegroup)
    -   `ST_FILETRACKING` – file tracking tables
    -   `ST_SERVERLOG` – server log tables

      

    > **Note:**
    >
    > You cannot direct log data to separate Microsoft SQL Server databases.

-   Two new filegroups needs to be created: `ST_FILETRACKING_ARCHIVE` and `ST_SERVERLOG_ARCHIVE`. They are used only if {{< SecureTransport/componentshortname >}} uses Microsoft SQL Server Enterprise Edition, and transfer and log entry maintenance applications are configured to export data.
    Also, the database user needs write permissions on the export directory.
    The database user should be granted Backup database and Backup log permissions. Backup log permission is only required only if the database is configured in Full recovery model.

-   The default filegroup for the database user must be `ST_DATA`.

-   The database must have a user defined that is mapped to the login that {{< SecureTransport/componentshortname >}} will use to access the database.

-   The authentication mode for the user must be Microsoft SQL Server Authentication.

-   The user must be a member of the following database roles:
    -   `db_datareader`
    -   `db_datawriter`
    -   `db_ddladmin`

      
    For example, the `db_owner` user has the required permissions.

During the installation, you need the following information:

-   Database access port number
-   Database user name and password
-   Database name
-   If the database is used over secure connection, you will also need the database server certificate signer or JKS keystore which contains it in order to trust the connection. In addition, the optional parameter **Common Name (CN)** can be provided and installer will verify the provided information against the database certificate's CN. If it is not provided, the installer will not check the certificate CN and will trust any.

**Related topics:**

-   <a href="../requirements_for_oracle_databases" class="MCXref xref">Requirements for Oracle databases</a>
-   <a href="../requirements_for_oracle_databases/data_pump_database_management" class="MCXref xref">Data pump database management system</a>
