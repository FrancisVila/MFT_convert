{
    "title": "Change the Oracle database configuration",
    "linkTitle": "Change the external Oracle database",
    "weight": "200"
}If your {{< SecureTransport/componentshortname  >}} installation is using an Oracle database, select **Setup &gt; Database Settings** to perform the following tasks:

-   Update the database configuration
-   Direct Transfer and Server log data to separate Oracle databases
-   Migrate your Oracle database to PostgreSQL

You can also update the database connection parameters and test the connection via the Admin REST API.

## Update Oracle database configuration

1.  Log on to the {{< SecureTransport/componentshortname >}} Administration Tool as user `dbsetup`.

2.  Select **Setup > Database Settings**.  
    The *Database Settings* page is displayed.

3.  <span id="Oracle_parameters"></span>Make the necessary updates in the database configuration.  

    -   Required settings  
        ![](/Images/SecureTransport/db-oracle-settings.png)
        -   **Host** – The host name or IP address of the Oracle server
        -   **Port** – The port used to access the server, 1521 is the default
        -   **User Name** – The name of the user authorized to create the {{< SecureTransport/componentshortname >}} schema.
        -   **Password** – The password for the user, not displayed.
        -   **Service Name** – Used to connect to the Oracle server or cluster
    -   **Use Kerberos Authentication**  
        Check this option to SecureTransport to connect to the Oracle database with Kerberos authentication. For detailed instructions, refer to <a href="../configure-oracle-kerberos" class="MCXref xref">Connect to an Oracle database using Kerberos authentication</a>.  
        ![](/Images/SecureTransport/db-oracle-kerberos.png)  
        <img src="/Images/SecureTransport/DBSettings_Kerberos_521x74.png" class="maxWidth" alt="Configuration file path" />  
    -   **Use Proxy Authentication**  
        Select this checkbox to connect to the database through another user. In the **Proxied Username** field, specify the user whose identity and privileges will be assumed by the connecting (proxy) user.  
        ![](/Images/SecureTransport/setup-oracle-proxy.png)  
    -   **Use Secure connection**  
        If you select this checkbox, the connection between {{< SecureTransport/securetransportname >}} and the database server will be encrypted.  
        ![](/Images/SecureTransport/db-oracle-secure.png)  
        You need to specify the following:
        -   **Server Certificate DN** (optional) – If the server is successfully authenticated (meaning its certificate is trusted), its DN can be checked. If a value is entered in this field, it will be compared with the server certificate DN. If they do not match, the connection won't be successful.
        -   **Enabled Protocols** – List of enabled protocols. TLSv1 is the default protocol.
        -   **Enabled Cipher Suites** – List of the enabled cipher suites.
        -   **Certificate File** – Import a PEM or DER file, or JKS (Java Key Store) keystore containing the trusted certificates.
    -   **Use Custom JDBC URL**  
        Unchecked by default. When checked, you can specify a custom JDBC URL string for {{< SecureTransport/componentshortname >}} to use to connect to one or multiple Oracle databases. In the URL, you can specify an address list that lists the protocol, host, port, and service name of each database.
        In addition to the standard connection parameters, you can include additional properties to define specific behavior, for example, a connection via SSL. If the custom JDBC URL connects to your database using SSL, make sure the **Use secure connection** checkbox is selected.

    <!-- -->



        #Example 
         JDBC URL with two support databases using both placeholders and  data defined by the admin:
        jdbc:oracle:thin:${user}/${password}@(DESCRIPTION=(ADDRESS_LIST=(LOAD_BALANCE=OFF)(FAILOVER=ON)(ADDRESS=(PROTOCOL=TCP)(HOST=2.2.2.2)(PORT=1521))(ADDRESS=(PROTOCOL=TCP)(HOST=3.3.3.3)(PORT=1521)))(CONNECT_DATA=(SERVICE_NAME=${databaseName})))

    > **Note:**
    >
    > When specified, the custom JDBC configuration is kept on patch revert.

4.  Click **Test Connection**.  
    If {{< SecureTransport/componentshortname >}} displays a failure message, correct the network, database, or other error reported and try again.

5.  Click **Save**.

> **Note:**
>
> To enable encrypted communication between the SecureTransport Server and the Oracle database, add SQLNET.ENCRYPTION\_SERVER=requested to the $ORACLE\_HOME/network/admin/sqlnet.ora file for your Oracle server. For more information, refer to the Oracle documentation.

**Related topics:**

-   <a href="../t_st_separate_databases" class="MCXref xref">Direct log data to separate Oracle databases</a>
-   <a href="../migrate_oracle_to_postgre" class="MCXref xref">Migrate from Oracle to PostgreSQL</a>
