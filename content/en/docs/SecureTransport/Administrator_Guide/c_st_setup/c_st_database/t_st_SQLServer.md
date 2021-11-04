{
    "title": "Change the external Microsoft SQL Server database",
    "linkTitle": "Change the external Microsoft SQL Server database",
    "weight": "230"
}If the SecureTransport Server uses an external Microsoft SQL Server database and any of the database settings
change, you must change the corresponding settings in the Administration Tool.

1.  Log on to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool as user `dbsetup`.
2.  Select **Setup > Database Settings**.  
    The *Database Settings* page is displayed with the external database settings under *Enterprise Clustering - Microsoft SQL Server External Database*.
3.  Type the values necessary to connect to the new external database:
    -   **Host** – The FQDN or IP address of the Microsoft SQL Server system

    -   **Port** – The number of the port used to access the server, 1433 is the default

    -   **User Name** – The name of the user authorized to connect to the database

    -   **Password** – The password for the user, not displayed

    -   **Database Name** – Used to connect to the Microsoft SQL Server.

    -   **Use secure connection** – When **Use secure connection** is checked, the connection between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and the database server will be encrypted. If **Use secure connection** is checked, the following option should be configured:
        -   **Server Certificate CN** (optional) – If specified, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will match the specified value with the database server certificate CN. If it is not specified, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will match the host name with the database server certificate CN. If neither of them is matched, the connection will fail.
        -   **Certificate Path** – Browse and select the TrustStore file to import the trusted certificates.

    -   **Use Custom JDBC URL** – Unchecked by default. When checked, you can specify a custom connection string for SecureTransport to use to connect to a Microsoft SQL Server database. In the URL, specify the host, port, database name, user name and password or use the available placeholders. You can include additional connection properties to define specific behavior, for example, a connection via SSL. If the custom JDBC URL connects to your database using SSL, make sure the **Use secure connection** checkbox is selected.  
        The exact syntax of a JDBC URL is specified by your DBMS.  

            #Example
             To specify an encrypted connection to mirror SQL instances by using a username and password:
            jdbc:sqlserver://${host}:${port};databaseName=${databaseName};user=${user};password=${password};encrypt=${encrypt};trustStore=${trustStorePath};trustStorePassword=${trustStorePassword};hostNameInCertificate=${hostNameInCertificate};failoverPartner=${failoverHost};

        The option to specify a custom JDBC URL is also exposed as a REST API resource.
4.  Click **Test Connection**.  
    If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays a failure message, correct the network, database, or other error reported and try again.
5.  Click **Save**.

> **Note:**
>
> You can retrieve and update an existing Microsoft SQL Server database configuration, and test the connection to the database using the Admin REST API .

**Related topics:**

-   <a href="../t_st_mysql" class="MCXref xref">Change the embedded database configuration</a>
-   <a href="../t_st_database" class="MCXref xref">Migrate from embedded database to external Oracle database</a>
-   <a href="../t_st_separate_databases" class="MCXref xref">Direct log data to separate Oracle databases</a>
-   <a href="../t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a>
