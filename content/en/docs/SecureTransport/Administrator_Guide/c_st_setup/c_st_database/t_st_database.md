{
    "title": "Migrate from embedded database to an external Oracle database",
    "linkTitle": "Migrate from embedded database to an external Oracle database",
    "weight": "190"
}If you upgraded a SecureTransport Server that used the embedded database or selected the embedded database when you installed SecureTransport Server, you can switch to an external Oracle database. In order to switch to an external Oracle database, you must have a license for the EC option installed or SecureTransport will not run. After you switch to the external database, you cannot switch back to the embedded database.

When you switch from the embedded database to an external Oracle database, you must set up the database. In this process, you specify the parameters of the Oracle database and SecureTransport migrate the configuration and data from the existing embedded database to the Oracle database. When the migration completes, you can use the SecureTransport Server as a stand-alone server or as the first server in an Enterprise Cluster (EC).

1.  Make sure the Oracle database meet the *[requirements](https://docs.axway.com/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/prereqs/Requirements_for_Oracle_databases.htm)*.

2.  Select **Operations > Server Control** and stop all servers.

3.  Select **Setup > Database Settings > Setup Oracle**.  
    
    ![Setup Oracle - Setup Oracle database.](Setup_Database_Oracle_DataMigration.png)

4.  On the *Target Database Settings* page of the Oracle wizard, type the values necessary to connect to the external database.   
    
    1.  Input the connection parameters. For a list of database connection parameters, see [Change the Oracle database configuration](../t_st_oracle).
    2.  Specify whether SecureTransport to connect to the database server using SSL. Before you enable the secure connection, the issuers certificates of the database server certificate, should be imported in the Trusted CA certificates store.  
        When **Use secure connection** check box is selected, you need to configure the following:
        -   **Server Certificate DN** (optional) – If the server is successfully authenticated (meaning its certificate is trusted), its DN can be checked. If a value is entered in this field, it will be compared with the server certificate DN. If they do not match, the connection won't be successful.
        -   **Enabled Protocols** - List of enabled protocols. TLSv1 is the default protocol.
        -   **Enabled Cipher Suites** - List of the enabled cipher suites.
    3.  To configure SecureTransport to connect to the Oracle database using Kerberos authentication, follow the steps described in [Connect to an Oracle database using Kerberos authentication](../configure-oracle-kerberos). When Kerberos authentication is enabled, the **Username** and **Passwords** fields are disabled, as SecureTransport will establish a password-less connection to the database using a ticket-granting (TGT) ticket. This feature requires additional configuration actions to be done on both the SecureTransport and the database server.
    4.  Select the **Use Proxy Authentication** checkbox to connect to the Oracle database through another user. In the **Proxied Username** field, specify the user whose identity and privileges will be assumed by the connecting (proxy) user.

5.  To direct log data to separate external databases, see [Direct log data to separate Oracle databases](../t_st_separate_databases).

6.  Click **Test Connection**.  
    If SecureTransport displays a failure message, correct the network, Oracle, or other error reported and try again.

7.  Type the password again, and click **Next**.

8.  On the *Data Migration* page, select the **Migration Type**:  
    
    ![Oracle Settings - Data Migration](Setup_Database_Oracle_DataMigration.png)
      
    

    -   If you are upgrading the first server in a cluster, select **Migrate All Existing MariaDB/MySQL Data**. The process creates a new database schema that contains all the data from the existing database and configuration.
    -   If you are upgrading the second and subsequent servers in a cluster, select **Migrate Local Setting Only**. The installer adds the local data for this server from the embedded database to the existing database schema it created for the first server.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Set the <code>Cluster.mode</code> server configuration parameter to <strong>disabled</strong> prior migrating from a Standard Cluster to an Enterprise Cluster. For more information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters">View and change server configuration parameters</a>.         </td>
      </tr>
</table>

9.  Leave **Roll-back to MariaDB/MySQL Database on Error** selected.

10. Click **Next**.

11. On the *Summary* page, review your settings. Click **Back** to return to a previous page and change a setting. Click **Setup Now** to migrate the data from the embedded database to the Oracle database or create the Oracle database.  
    SecureTransport reports it progress as it transfers the server configuration and data from the embedded database to the external Oracle database.  
    When the data migration is complete, the embedded database is no longer available and the *Database Settings* page includes the external database settings under *Enterprise Clustering - Oracle External Database*.  
    The log output for the migration is in `<FILEDRIVEHOME>/var/logs/migration.log`.

12. Once the data migration is completed, shutdown and restart the SecureTransport server instance.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can also migrate configuration data using the <code>data_migrate</code> command-line utility in the <code>&lt;FILEDRIVEHOME&gt;/bin</code> directory. For usage information, run <code>data_migrate -h</code>. Before you migrate the data, stop all servers except the database.         </td>
      </tr>
</table>

**Related topics:**

-   [Change the embedded database configuration](../t_st_mysql)
-   [Direct log data to separate Oracle databases](../t_st_separate_databases)
-   [Change the Oracle database configuration](../t_st_oracle)
-   [Change the external Microsoft SQL Server database](../t_st_sqlserver)
