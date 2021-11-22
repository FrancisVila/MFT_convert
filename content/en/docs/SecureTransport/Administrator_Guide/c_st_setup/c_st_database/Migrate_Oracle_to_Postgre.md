{
    "title": "Migrate  from Oracle to PostgreSQL",
    "linkTitle": "Migrate from Oracle to PostgreSQL",
    "weight": "250"
}You can migrate an existing Oracle database to PostgreSQL only by using the Administration tool. Currently, the migration cannot be done through the Admin Rest API.

> **Note:**
>
> After you switch to PostgreSQL, you cannot switch back to Oracle.

Before you migrate to PostgreSQL, ensure that the following prerequisites are met:

-   You have a license for Enterprise Cluster with PostgreSQL database
-   The external PostgreSQL database is already installed

When you migrate from an Oracle database to a PostgreSQL one, you must set up the new database. In this process, you specify the parameters of the PostgreSQL database and {{< SecureTransport/componentshortname  >}} migrates the configuration and data from the existing database to the new one. When the migration completes, you can use the {{< SecureTransport/componentshortname  >}} Server as a stand-alone server or as the first server in an Enterprise Cluster (EC).

> **Note:**
>
> Caution  
> If you have installed any SecureTransport 2021 Update and migrate to a PostgreSQL database with non-superuser privileges, reverting to a 5.5 Update released in 2020 will cause issues as there are some incompatibilities. Refer to the Update Readme file for a workaround and revert instructions.

To migrate from Oracle to PostgreSQL:

1.  Make sure the PostgreSQL database has the characteristics listed in the *Database installation prerequisites* section of the {{< SecureTransport/componentshortname >}} Installation Guide.
2.  Select **Operations > Server Control** and stop all servers.
3.  Select **Setup > Database Settings > Setup PostgreSQL**.  
    The PostgreSQL setup wizard opens.
4.  On the *Target database settings* page of the wizard, provide the values necessary to connect to the PostgreSQL database.  
    1.  Input the standard connection parameters. For a list of database connection parameters, see <a href="../manage_postgre_database" class="MCXref xref">Change PostgreSQL configuration and manage partitioning</a>.
    2.  Specify whether {{< SecureTransport/componentshortname >}} to connect to the database server using SSL. When **Use secure connection** check box is selected, you need to import the public key certificate file.
5.  Click **Test Connection**.  
    If {{< SecureTransport/componentshortname >}} displays a failure message, correct the network, PostgreSQL, or other error reported and try again.
6.  Type the password again, and click **Next**.
7.  On the *Data Migration* page, select the **Migration Type**.  
    -   If you are upgrading the first server in a cluster, select **Migrate All Existing Oracle Data**. The process creates a new database schema that contains all the data from the existing database and configuration.
    -   If you are upgrading the second and subsequent servers in a cluster, select **Migrate Local Setting Only**. The installer updates the local data for this server to point to the existing database schema it created for the first server.
8.  Leave **Roll-back to Oracle Database on Error** selected.
9.  Click **Next**.
10. On the *Summary* page, review your settings. Click **Back** to return to a previous page and change a setting. Click **Setup Now** to migrate the data from the Oracle database to the PostgreSQL database.  
    {{< SecureTransport/componentshortname >}} reports its progress as it transfers the server configuration and data to the PostgreSQL database.  
    When the data migration is complete, the Oracle database is no longer available and the *Database Settings* page includes the new database settings under *Enterprise Clustering - PostgreSQL External Database*.  
    The log output for the migration is in `<FILEDRIVEHOME>/var/logs/migration.log`.
11. Once the data migration is completed, switch from the current Oracle license to your PostgreSQL license.
12. Shut down and restart the {{< SecureTransport/componentshortname >}} server instance.

> **Note:**
>
> The data\_migrate command-line utility cannot be used for migrating from Oracle to PostgreSQL.

**Related topics:**

-   <a href="../manage_postgre_database" class="MCXref xref">Change PostgreSQL configuration and manage partitioning</a>
