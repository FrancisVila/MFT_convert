{
    "title": "Silent installation",
    "linkTitle": "Silent installation",
    "weight": "100"
}There is an option to perform a silent installation of SecureTransport of either Server or Edge to properly fit standalone or clustered deployments.

The current topic provides the basic step-by-step procedure for performing silent installation and includes the following subtopics:

-   [Configurable properties for silent installation](#silent_install_properties) - contains
    a detailed list of configurable parameters and their properties, including the ones which are specific to your database deployments
-   [Recommendations for Clustered SecureTransport deployments](#silent2)
-   [Silent file editor](#silent) - contains a basic set of instructions for using the dedicated silent file editor tool, part of the SecureTransport installation package

The silent installation process requires you to pass though a few steps:

1.  Start the SecureTransport installation in normal mode.
2.  Complete the installer dialog screens up until the point of installation (for example, before clicking **Install**). This will add two `.properties` files:
    -   `Install_Axway_Installer_<installer-version>.properties`
    -   `Install_SecureTransport_<st-version>.properties`
3.  Create a copy of each of the two `.properties` files under `<installation_root_directory>\SilentFile\<date_and_time>_install\` to a temp folder for later reuse.
4.  Quit the installation in normal mode.
5.  Edit `Install_Axway_Installer_<installer-version>.properties` and make sure to have the following declaration line included:  
6.  Edit `Install_SecureTransport_<st-version>.properties` and make sure to have correct input for the minimum number of configurable properties. Scroll down to see the [Configurable properties](#silent_install_properties) you'll need to configure for successful for all pertinent properties. To facilitate the editing process, see [Silent file editor](#silent), part of the current topic as well.  
7.  Run the installation with the following switches for silent install:
8.  `# ./setup.sh -s /path/to/Install_Axway_Installer_<version>.properties`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Use the Axway Installer properties file for the silent install, not the SecureTransport properties file.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Always provide the full path to the properties file, instead of a relative one.         </td>
      </tr>
</table>

## <span id="silent_install_properties"></span>Configurable properties for silent installation

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The following list does not contain all configurable but only the ones you'll need to set for silent installation in different <span>SecureTransport</span> deployments. Please <u>make sure to remove any empty valued properties</u> as leaving these properties blank might adversely affect your silent installation!         </td>
      </tr>
</table>

The following table presents some useful configuration properties you can edit to perform silent installation of SecureTransport in the `Install_SecureTransport_<st-version>.properties` file:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description / Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Component.Version</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The SecureTransport version to install</p>
            <p><u>example</u>: <code>5.5</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Component.InstallerVersion</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The version of the Axway installer </p>
            <p><u>example</u>: <code>4.10.0</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Server</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag which specifies if you're installing <span>SecureTransport</span> Server. Must be set to <code>false</code> when installing <span>SecureTransport</span> Edge.         </td>
      </tr>
      <tr>
         <td>
            <p>Edge</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag which specifies if you're installing <span>SecureTransport</span> Edge. Must be set to <code>false</code> when installing <span>SecureTransport</span> Server.         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBUseExistingSchema </p>
            <p><i>boolean</i>
</p>
         </td>
         <td>
            <p>A flag which specifies if you're using an external database. Not applicable to <span>SecureTransport Edge</span> installation.</p>
            <p><b>Important!</b> In a LEC deployment using an external database (Oracle or MSSQL), you must configure this value to <code>false</code> with the first Server node and to <code>true</code> all subsequent Server deployments in your LEC. </p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">This table does not include all installation properties but just the ones you would need to edit in order to perform silent installation.         </td>
      </tr>
</table>

### MariaDB- and MySQL-specific configurable properties

The following table presents some database configuration properties you must configure, depending on your selected database implementation.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description / Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>dbType</code>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The database to install:  <code>useDBLocal</code> with embedded databases</p>
         </td>
      </tr>
      <tr>
         <td><code>internalDBPort</code>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Listener port of your embedded database:  <code>33060</code> by default</p>
         </td>
      </tr>
      <tr>
         <td><span>internalDBPort.Type</span>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>A flag identifying the embedded listener port type: set to  <code>IPPortOwner</code></p>
         </td>
      </tr>
      <tr>
         <td><span>internalDBPort.Max</span>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Upper threshold of embedded port range</p>
            <p><u>example</u>: <code>65535</code></p>
         </td>
      </tr>
      <tr>
         <td><span>internalDBPort.Min</span>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Lower threshold of embedded port range</p>
            <p><u>example</u>: <code>1024</code></p>
         </td>
      </tr>
      <tr>
         <td colspan="2">The following entries concern MariaDB only.         </td>
      </tr>
      <tr>
         <td><code>internalDBUseSecureConnection</code>
<br/><i>boolean</i>
<br/>MariaDB only<br/>         </td>
         <td>
            <p>A flag specifying whether to use SSL encryption for connection to the Database: <code>true </code>or <code>false</code>. <br/>The procedure for generating the certificates required for an SSL connection to the embedded MariaDB database can be found on the official MariaDB website. </p>
         </td>
      </tr>
      <tr>
         <td><code>internalDBCaPath</code>
            <p><i>string</i>
<br/>MariaDB only<br/></p>
         </td>
         <td>
            <p>The absolute file path to the CA certificate in PEM format, used to create and sign X.509 certificates. </p>
         </td>
      </tr>
      <tr>
         <td><code>internalDBServerKeyPath </code>
<br/>MariaDB only         </td>
         <td>A private key in PEM format, used by the MariaDB Server.          </td>
      </tr>
      <tr>
         <td><code>internalDBServerCertPath </code>
<br/>MariaDB only         </td>
         <td>An X.509 certificate in PEM format, used by the MariaDB Server.          </td>
      </tr>
   </tbody>
</table>

### Oracle-specific configurable properties

The following table presents some Oracle database configuration properties you must configure, depending on your selected database implementation.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description / Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>dbType</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The database to install:  <code>useOracleExternal</code> with Oracle databases</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oracleHost</p>
            <p><i>string</i>
</p>
         </td>
         <td> Database hostname or IP address: for example <code>oracle.localdomain.com</code>          </td>
      </tr>
      <tr>
         <td>
            <p>oracleHost.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td>
            <p>oraclePort</p>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Listener port of your Oracle database:  <code>1521</code> by default</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oraclePort.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>A flag identifying the listener port number format</p>
            <p><u>Example</u>: <code>Integer</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oracleUserName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The name of the database user account</p>
            <p><u>Example</u>: <code>st_user</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oraclePassword</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The Oracle database encrypted password: for correct behavior, set the <code>oraclePassword.Format</code> property to <code>AES128</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oraclePassword.Format</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The encryption format of your database password: <code>DefenceV1</code> Do not change this value! </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>oracleServiceName</p>
            <p><i>enum</i>
</p>
         </td>
         <td>Service name of Oracle database: <code>orcl</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>oracleUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>oracleUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing Oracle DB schema or not: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>oracleUseSecureConnection</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>oracleCertificateDN</p>
            <p><i>string</i>
</p>
         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td>
            <p>OracleTrustStoreFilePath</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td>
            <p>OracleTrustStoreFilePath.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>Type of SSL certificate: set this value to <code>File</code></p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBUseSecureConnection</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>oracleUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBCertificateName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>oracleCertificateDN</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBTrustStore</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

### MSSQL-specific configurable properties

The following table presents some MSSQL database configuration properties you must configure, depending on your selected database implementation.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description / Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>dbType</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The database to install:  <code>useMSSQLExternal</code> with MSSQL databases</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlHost</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p> Database hostname or IP address </p>
            <p><u>Example:</u> <code>sqlserver.localdomain.com</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlHost.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlPort</p>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Listener port of your MSSQL database:  <code>1433</code> by default</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlPort.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>A flag identifying the listener port number format</p>
            <p><u>Example</u>: <code>Integer</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlLoginName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The name of the database user account</p>
            <p><u>Example</u>: <code>st_user</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlPassword</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The MSSQL database encrypted password:  for correct behavior, set the <code>mssqlPassword.Format</code> property to <code>AES128</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlPassword.Format</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The encryption format of your database password: <code>DefenceV1</code>. Do not change this value!  Do not change this value! </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlDatabaseName</p>
            <p><i>string</i>
</p>
         </td>
         <td>Name of MSSQL database: <code>mssql_db4</code>         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing MSSQL DB schema or not: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>mssqlUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlUseSecureConnection</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>mssqlCertificateDN</p>
            <p><i>string</i>
</p>
         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td>
            <p>MssqlTrustStoreFilePath</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td>
            <p>MssqlTrustStoreFilePath.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>Type of SSL certificate: set this value to <code>File</code>         </td>
      </tr>
      <tr>
         <td>
            <p><span>externalDBUseSecureConnection</span>
</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>mssqlUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBCertificateName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>mssqlCertificateDN</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBTrustStore</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

### PostgreSQL-specific configurable properties

The following table presents some PostgreSQL database configuration properties you must configure, depending on your selected database implementation.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Property</th>
         <th>Description / Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>dbType</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The database to install:  <code>usePostgreSQLExternal</code> with PostgreSQL databases</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgreHost</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p> Database hostname or IP address </p>
            <p><u>Example:</u> <code>postgresqlserver.localdomain.com</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgreHost.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td>
            <p>postgrePort</p>
            <p><i>integer</i>
</p>
         </td>
         <td>
            <p>Listener port of your PostgreSQL database:  <code>5432</code> by default</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgrePort.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>A flag identifying the listener port number format</p>
            <p><u>Example</u>: <code>Integer</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgreLoginName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The name of the database user account</p>
            <p><u>Example</u>: <code>st_user</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgrePassword</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>The PostgreSQL database encrypted password:  for correct behavior, set the <code>postgresqlPassword.Format</code> property to <code>DefenceV1</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgrePassword.Format</p>
            <p><i>enum</i>
</p>
         </td>
         <td>
            <p>The encryption format of your database password: <code>DefenceV1</code>. Do not change this value!  Do not change this value! </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>postgreDatabaseName</p>
            <p><i>string</i>
</p>
         </td>
         <td>Name of PostgreSQL database: <code>st_db4</code>         </td>
      </tr>
      <tr>
         <td>
            <p>postgreUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing PostgreSQL DB schema or not : <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBUseExistingSchema</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>postgreUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>postgreUseSecureConnection</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>postgreCertificateDN</p>
            <p><i>string</i>
</p>
         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td>
            <p>postgreTrustStoreFilePath</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td>
            <p>postgreTrustStoreFilePath.Type</p>
            <p><i>enum</i>
</p>
         </td>
         <td>Type of SSL certificate: set this value to <code>File</code>         </td>
      </tr>
      <tr>
         <td>
            <p><span>postgreCertificateCN</span>
</p>
            <p><i>[string]</i>
</p>
         </td>
         <td>SSL certificate common name         </td>
      </tr>
      <tr>
         <td>
            <p><span>externalDBUseSecureConnection</span>
</p>
            <p><i>boolean</i>
</p>
         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>postgreUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBCertificateName</p>
            <p><i>string</i>
</p>
         </td>
         <td>
            <p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>mssqlCertificateDN</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>externalDBTrustStore</p>
            <p><i>string</i>
</p>
         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

 

 

## <span id="Silent2"></span>Recommendations for Clustered SecureTransport deployments

This subtopic contains instructions and tips to aid you to successful silent installations of SecureTransport (Server and Edge) in clustered deployments:

-   Standard Cluster
-   Enterprise Cluster (EC) with external databases

Please observe the listed info before proceeding with silent installations of your cluster nodes.

### <span id="silent_standard_cl"></span>Silent installation on Standard Cluster nodes

With Standard Cluster, after you perform silent installation on your first node, you can re-use the `Install_SecureTransport_<st-version>.properties` file for silent installation of all other nodes.

Standard Cluster works with an embedded MariaDB database (or MySQL, only on AIX). No additional edits are required.

### Silent installation on Enterprise Cluster nodes

Enterprise Cluster (EC) deployments offer the use of external databases which adds some additional steps in performing successful silent installation on all nodes.

To simplify this process, we can separate the SecureTransport Server deployments apart from the SecureTransport Edge deployments.

The big difference is in the fact that Server nodes are in LEC deployment (using an external database) while Edge nodes are in Standard Cluster deployment (using an embedded database).

#### SecureTransport Server **nodes in LEC**

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In Enterprise Cluster deployments, all your SecureTransport Server nodes must have the same version as your first installed Server node. Do not attempt to add Server nodes to your cluster if the SecureTransport version does not match the one on already installed nodes.         </td>
      </tr>
</table>

When using external databases (Oracle, MSSQL or PostgreSQL) you must make sure the correct values are added to the respective properties, as listed in the following table:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Database</th>
         <th>First node</th>
         <th>Every following node</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Oracle</p>
         </td>
         <td>
            <p>oracleUseExistingSchema = false
</p>
            <p>externalDBUseExistingSchema = false</p>
         </td>
         <td>
            <p>oracleUseExistingSchema = true</p>
            <p>externalDBUseExistingSchema = true</p>
            <p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>MSSQL</p>
         </td>
         <td>
            <p>mssqlUseExistingSchema = false</p>
            <p>
externalDBUseExistingSchema = false</p>
         </td>
         <td>
            <p>mssqlUseExistingSchema = true</p>
            <p>externalDBUseExistingSchema = true</p>
            <p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>
            <p>PostgreSQL</p>
         </td>
         <td>
            <p>postgreUseExistingSchema = false</p>
            <p>externalDBUseExistingSchema = false</p>
         </td>
         <td>
            <p>postgreUseExistingSchema = true</p>
            <p>externalDBUseExistingSchema = true</p>
            <p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

#### SecureTransport Edge nodes in Standard Cluster

Follow the instructions as stated above in the [Silent installation on Standard Cluster nodes](#silent_standard_cl) subsection. There are no additional steps in terms of silent installation.

## <span id="Silent"></span>Silent file editor

The Silent file editor is a tool dedicated to editing your SecureTransport `.properties` file and it is located in Tools/SilentFileEditor directory of the product distributive.

Before using the silent file editor you must export the `JAVA_HOME` variable containing path to supported version of JRE.

### Usage

The following syntax is used:

`./SilentFileEditor.sh silent_file_path key value -u key value_to_be_encrypted -c`

Here is typical example of silent file editor usage:

    ./SilentFileEditor.sh $ST_SILENT_FILE_PATH InstallDir $ST_INSTALLDIR  -u mssqlPort $DB_PORT_NUMBER -u mssqlLoginName $DB_USER -u mssqlPassword $DB_USER_PASSWORD -c mssqlDatabaseName $DB_NAME -u mssqlHost $DB_HOSTNAME -u

Where:

-   `$ST_SILENT_FILE_PATH` is the path to silent file
-   `$ST_INSTALLDIR` is the path where SecureTransport should be installed
-   `$DB_PORT_NUMBER` is the database port number
-   `$DB_USER` is the database username
-   `$DB_USER_PASSWORD` is the database password in plaintext. Use `-c` to encrypt it. Use `-u` to update it.
-   `$DB_NAME` is the database name
-   `$DB_HOSTNAME` is the database hostname

**Notes**

-   Silent file editor is only setting plain or encrypted values to keys.
-   Silent file editor cannot add new keys.
-   Silent file editor does not check if the name of the key is valid.

**Related topics**

See [Silent installation example file](silent-install-example)
