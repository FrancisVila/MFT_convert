{
    "title": "Configure your database",
    "linkTitle": "Configure your database",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses a database to store configuration parameters and data, including log data. With Standard Clustering, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server uses an embedded database server. With the Enterprise Clustering (EC) option, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server uses a shared external database. With the external Oracle database, you can direct log data to separate databases. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge always uses an embedded database server.

> **Note:**
>
> MariaDB, MySQL, and Microsoft SQL Server database are configured to use a case-insensitive collation. For example, searching in the File Tracking and Server Log page or executing requests in the REST API will ignore the case sensitivity of the parameters and will return all matching results. Oracle and PostgreSQL, on the other hand, use a case-sensitive collation.

During installation, you specified the database to use and its parameters. Use the *Database Settings* page to perform the following tasks:

-   Change database parameters:
    -   <a href="t_st_mysql" class="MCXref xref">Change the embedded database configuration</a>
    -   <a href="t_st_sqlserver" class="MCXref xref">Change the external Microsoft SQL Server database</a>
    -   <a href="t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a>
    -   <a href="manage_postgre_database" class="MCXref xref">Change PostgreSQL configuration and manage partitioning</a>
-   <a href="t_st_database" class="MCXref xref">Migrate from embedded database to external Oracle database</a>
-   <a href="t_st_separate_databases" class="MCXref xref">Direct log data to separate Oracle databases</a>
-   <a href="configure-oracle-kerberos" class="MCXref xref">Connect to an Oracle database using Kerberos authentication</a>
-   <a href="t_st_improve_resil" class="MCXref xref">Improve server resiliency in case of Oracle RAC node failure</a>
-   <a href="migrate_oracle_to_postgre" class="MCXref xref">Migrate from Oracle to PostgreSQL</a>
