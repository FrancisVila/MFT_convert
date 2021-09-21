{
    "title": "Change the external Microsoft SQL Server database",
    "linkTitle": "Change the external Microsoft SQL Server database",
    "weight": "240"
}If the SecureTransport Server uses an external Microsoft SQL Server database and any of the database settings
change, you must change the corresponding settings in the Administration Tool.

1.  Log on to the SecureTransport Administration Tool as user `dbsetup`.
2.  Select **Setup > Database Settings**.  
    The *Database Settings* page is displayed with the external database settings under *Enterprise Clustering - Microsoft SQL Server External Database*.
3.  Type the values necessary to connect to the new external database:
    -   **Host** – The FQDN or IP address of the Microsoft SQL Server system

    -   **Port** – The number of the port used to access the server, 1433 is the default

    -   **User Name** – The name of the user authorized to connect to the database

    -   **Password** – The password for the user, not displayed

    -   **Database Name** – Used to connect to the Microsoft SQL Server.

    -   **Use secure connection** – When **Use secure connection** is checked, the connection between SecureTransport and the database server will be encrypted. If **Use secure connection** is checked, the following option should be configured:
        -   **Server Certificate CN** (optional) – If specified, SecureTransport will match the specified value with the database server certificate CN. If it is not specified, SecureTransport will match the host name with the database server certificate CN. If neither of them is matched, the connection will fail.
        -   **Certificate Path** – Browse and select the TrustStore file to import the trusted certificates.

    -   **Use Custom JDBC URL** – Unchecked by default. When checked, you can specify a custom connection string for SecureTransport to use to connect to a Microsoft SQL Server database. In the URL, specify the host, port, database name, user name and password or use the available placeholders. You can include additional connection properties to define specific behavior, for example, a connection via SSL. If the custom JDBC URL connects to your database using SSL, make sure the **Use secure connection** checkbox is selected.  
        The exact syntax of a JDBC URL is specified by your DBMS.  

        <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>#Example</p>            <p> To specify an encrypted connection to mirror SQL instances by using a username and password:</p>            <p>jdbc:sqlserver://${host}:${port};databaseName=${databaseName};user=${user};password=${password};encrypt=${encrypt};trustStore=${trustStorePath};trustStorePassword=${trustStorePassword};hostNameInCertificate=${hostNameInCertificate};failoverPartner=${failoverHost};</p>         </td>      </tr>   </tbody></table>

        The option to specify a custom JDBC URL is also exposed as a REST API resource.
4.  Click **Test Connection**.  
    If SecureTransport displays a failure message, correct the network, database, or other error reported and try again.
5.  Click **Save**.

<table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When specified, the custom JDBC configuration is kept on patch revert.         </td>      </tr></table>

**Related topics:**

-   [Change the embedded database configuration](../t_st_mysql)
-   [Migrate from embedded database to external Oracle database](../t_st_database)
-   [Direct log data to separate Oracle databases](../t_st_separate_databases)
-   [Change the Oracle database configuration](../t_st_oracle)
