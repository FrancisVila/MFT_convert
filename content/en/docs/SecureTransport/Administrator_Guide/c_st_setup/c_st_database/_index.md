{
    "title": "Configure your database",
    "linkTitle": "Configure your database",
    "weight": "160"
}SecureTransport uses a database to store configuration parameters and data, including log data. With Standard Clustering, SecureTransport Server uses an embedded database server. With the Enterprise Clustering (EC) option, SecureTransport Server uses a shared external database. With the external Oracle database, you can direct log data to separate databases. SecureTransport Edge always uses an embedded database server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">MariaDB, MySQL and Microsoft SQL Server database are configured to use a case-insensitive collation. For example, searching in the File Tracking and Server Log page or executing requests in the REST API will ignore the case sensitivity of the parameters and will return all matching results. Oracle and PostgreSQL, on the other hand, use a case-sensitive collation.         </td>
      </tr>
</table>

During installation, you specified the database to use and its parameters. Use the *Database Settings* page to perform the following tasks:

-   Change database parameters:
    -   [Change the embedded database configuration](t_st_mysql),
    -   [Change the external Microsoft SQL Server database](t_st_sqlserver),
    -   [Change the Oracle database configuration](t_st_oracle),
    -   [Change PostgreSQL configuration and manage partitioning](manage_postgre_database)
-   [Migrate from embedded database to external Oracle database](t_st_database)
-   [Direct log data to separate Oracle databases](t_st_separate_databases)
-   [Connect to an Oracle database using Kerberos authentication](configure-oracle-kerberos)
-   [Improve server resiliency in case of Oracle RAC node failure](t_st_improve_resil)
-   [Migrate from Oracle to PostgreSQL](migrate_oracle_to_postgre)
