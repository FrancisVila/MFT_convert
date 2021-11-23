{
    "title": "Change PostgreSQL configuration and manage partitioning",
    "linkTitle": "Change PostgreSQL configuration and manage partitioning",
    "weight": "240"
}If your {{< SecureTransport/componentshortname  >}} installation is using a PostgreSQL database, select **Setup &gt; Database Settings** to perform the following tasks:

-   Update the database configuration
-   Create and manage table partitions

The PostgreSQL configuration is stored in the `<FILEDRIVEHOME>/conf/configuration.xml` file.

<img src="/Images/SecureTransport/setup_database_settings_Postgre.png" class="maxWidth" alt="Database Settings - Change Oracle database settings." />

## Update PostgreSQL database configuration

{{< SecureTransport/componentshortname  >}} administrators with database reconfiguration permissions can change the database connection parameters and test the database connection using the Administration tool or the Admin REST API.

To update database configuration using the Administration tool:

1.  Log on to the {{< SecureTransport/componentshortname >}} Administration Tool as an administrator with permissions to access *Database Settings* page.
2.  Select **Setup > Database Settings**.  
    The *Database Settings* page is displayed.
3.  Make the necessary updates in the database configuration.  
    -   **Host** – The host name or IP address of the PostgreSQL server
    -   **Port** – The port used to access the server, 5432 is the default.
    -   **User Name** – The name of the user authorized to create the {{< SecureTransport/componentshortname >}} schema and populate it
    -   **Password** – The password for the user, not displayed. The password cannot contain any of the following symbols: `%`, `&` or `+`.
    -   **Database Name** – Used to connect to the PostgreSQL server or cluster
    -   **Use secure connection** – When **Use secure connection** is checked, the connection between {{< SecureTransport/securetransportname >}} and the database server will be encrypted. If **Use secure connection** is checked, the following option should be configured:
        -   **Certificate File** – Browse and select the public key certificate file. TrustStore files are not supported.
4.  Click **Test Connection**.  
    If {{< SecureTransport/componentshortname >}} displays a failure message, correct the network, database, or other error reported and try again.
5.  Click **Save**.

## Manage database partitioning

By default, {{< SecureTransport/componentshortname  >}} is scheduled to daily partition log tables at midnight, 00:00, pre-creating partitions three days in advance. Partition names are in the form of

*table\_name>\_&lt;start\_date>v&lt;end\_date\_epoch\_to\_millis>*.

### Change partition creation time

By default, the daily partitions are created every day at 00:00. To change the partition creation time, update the value of the `PartitionManagement.Create.triggerTime` server configuration option either using the Administration tool or the Admin REST API. The format is HH:MM, with hours in the range 0–23.

### Create partitions manually

In situations where you have high volumes of data you can manually create partitions in advance to prevent table locking. {{< SecureTransport/componentshortname  >}} allows you to pre-create partitions for minimum 3 days and up to 365 days ahead.

You can pre-create partitions in two ways:

-   Using the Admin Rest API
-   Using the Administration tool  
    Select **Setup > Database Settings**. In the **Manually create** field, specify the number of days into the future for which to pre-create partitions. Then, click **Create now**.

**Related topics:**

-   [Migrate from Oracle to PostgreSQL](../migrate_oracle_to_postgre)
-   [Change the embedded database configuration](../t_st_mysql)
-   [Direct log data to separate Oracle databases](../t_st_separate_databases)
-   [Change the Oracle database configuration](../t_st_oracle)
-   [Change the external Microsoft SQL Server database](../t_st_sqlserver)
