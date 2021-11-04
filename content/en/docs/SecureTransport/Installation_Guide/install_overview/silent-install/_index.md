{
    "title": "Silent installation of SecureTransport",
    "linkTitle": "Silent installation",
    "weight": "100"
}There is an option to perform a silent installation of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> of either Server or Edge to properly fit standalone or clustered deployments.

The current topic provides the basic step-by-step procedure for performing silent installation and includes the following subtopics:

-   <a href="#silent_install_properties" class="MCXref xref">Configurable properties for silent installation</a> - contains
    a detailed list of configurable parameters and their properties, including the ones which are specific to your database deployments
-   <a href="#Silent2" class="MCXref xref">Recommendations for Clustered SecureTransport deployments</a>
-   <a href="#Silent" class="MCXref xref">Silent file editor</a> - contains a basic set of instructions for using the dedicated silent file editor tool, part of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation package

The silent installation process requires you to pass though a few steps:

1.  Start the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation in normal mode.
2.  Complete the installer dialog screens up until the point of installation (for example, before clicking **Install**). This will add two `.properties` files:
    -   `Install_Axway_Installer_<installer-version>.properties`
    -   `Install_SecureTransport_<st-version>.properties`
3.  Create a copy of each of the two `.properties` files under `<installation_root_directory>\SilentFile\<date_and_time>_install\` to a temp folder for later reuse.
4.  Quit the installation in normal mode.
5.  Edit `Install_Axway_Installer_<installer-version>.properties` and make sure to have the following declaration line included:  
6.  Edit `Install_SecureTransport_<st-version>.properties` and make sure to have correct input for the minimum number of configurable properties. Scroll down to see the [Configurable properties](#silent_install_properties) you'll need to configure for successful for all pertinent properties. To facilitate the editing process, see [Silent file editor](#Silent), part of the current topic as well.  
7.  Run the installation with the following switches for silent install:
8.  `# ./setup.sh -s /path/to/Install_Axway_Installer_<version>.properties`

> **Note:**
>
> Use the Axway Installer properties file for the silent install, not the SecureTransport properties file.

> **Note:**
>
> Always provide the full path to the properties file, instead of a relative one.

<span id="silent_install_properties"></span>

## Configurable properties for silent installation

> **Note:**
>
> The following list does not contain all configurable but only the ones you'll need to set for silent installation in different SecureTransport deployments. Please make sure to remove any empty valued properties as leaving these properties blank might adversely affect your silent installation!

The following table presents some useful configuration properties you can edit to perform silent installation of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> in the `Install_SecureTransport_<st-version>.properties` file:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadD-Column1-Header1">Description / Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Component.Version</p>
<p><em>string</em></p>         </td>
         <td><p>The SecureTransport version to install</p>
<p><u>example</u>: <code>5.5</code></p>         </td>
      </tr>
      <tr>
         <td><p>Component.InstallerVersion</p>
<p><em>string</em></p>         </td>
         <td><p>The version of the Axway installer</p>
<p><u>example</u>: <code>4.10.0</code></p>         </td>
      </tr>
      <tr>
         <td><p>Server</p>
<p><em>boolean</em></p>         </td>
         <td>A flag which specifies if you're installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. Must be set to <code>false</code> when installing <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Edge.         </td>
      </tr>
      <tr>
         <td><p>Edge</p>
<p><em>boolean</em></p>         </td>
         <td>A flag which specifies if you're installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge. Must be set to <code>false</code> when installing <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server.         </td>
      </tr>
      <tr>
         <td><p>externalDBUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td><p>A flag which specifies if you're using an external database. Not applicable to <span class="mc-variable suite_variables.SecureTransportEdgeName variable">SecureTransport Edge</span> installation.</p>
<p><strong>Important!</strong> In a LEC deployment using an external database (Oracle or MSSQL), you must configure this value to <code>false</code> with the first Server node and to <code>true</code> all subsequent Server deployments in your LEC.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> This table does not include all installation properties but just the ones you would need to edit in order to perform silent installation.

### MariaDB- and MySQL-specific configurable properties

The following table presents some database configuration properties you must configure, depending on your selected database implementation.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadD-Column1-Header1">Description / Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>dbType</code>
<p><em>enum</em></p>         </td>
         <td><p>The database to install: <code>useDBLocal</code> with embedded databases</p>         </td>
      </tr>
      <tr>
         <td><code>internalDBPort</code>
<p><em>integer</em></p>         </td>
         <td><p>Listener port of your embedded database: <code>33060</code> by default</p>         </td>
      </tr>
      <tr>
         <td><span class="code">internalDBPort.Type</span>
<p><em>enum</em></p>         </td>
         <td><p>A flag identifying the embedded listener port type: set to <code>IPPortOwner</code></p>         </td>
      </tr>
      <tr>
         <td><span class="code">internalDBPort.Max</span>
<p><em>integer</em></p>         </td>
         <td><p>Upper threshold of embedded port range</p>
<p><u>example</u>: <code>65535</code></p>         </td>
      </tr>
      <tr>
         <td><span class="code">internalDBPort.Min</span>
<p><em>integer</em></p>         </td>
         <td><p>Lower threshold of embedded port range</p>
<p><u>example</u>: <code>1024</code></p>         </td>
      </tr>
      <tr>
         <td>The following entries concern MariaDB only.         </td>
      </tr>
      <tr>
         <td><code>internalDBUseSecureConnection</code><br />
<em>boolean</em><br />
MariaDB only<br />
         </td>
         <td><p>A flag that specifies whether or not the connection to the database is encrypted: <code>true</code> or <code>false</code>.<br />
The default value is <code>true</code>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>internalDBAutoGenerateCertificates</code></p>
<p><em>boolean</em><br />
MariaDB only</p>         </td>
         <td><p>A flag that specifies whether or not SecureTransport automatically generates the required certificates for a secure connection to the embedded MariaDB database.
The default value is <code>true</code>.</p>
<p>When set to <code>false</code>, you need to provide the certificates by specifying the following options: <code>internalDBCaPath, internalDBServerKeyPath</code>, and <code>internalDBServerCertPath</code>.</p>         </td>
      </tr>
      <tr>
         <td><code>internalDBCaPath</code>
<p><em>string</em><br />
MariaDB only<br />
</p>         </td>
         <td><p>The absolute file path to the CA certificate in PEM format, used to create and sign X.509 certificates.</p>
<p>Only applicable when <code>internalDBUseSecureConnection</code> is set to <code>true</code> and <code>internalDBAutoGenerateCertificates</code> is set to <code>false</code>.</p>         </td>
      </tr>
      <tr>
         <td><code>internalDBServerKeyPath</code>
<p><em>string</em></p>
MariaDB only         </td>
         <td><p>The absolute file path to the private key in PEM format, used by the MariaDB Server.</p>
<p>Only applicable when <code>internalDBUseSecureConnection</code> is set to <code>true</code> and <code>internalDBAutoGenerateCertificates</code> is set to <code>false</code>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>internalDBServerCertPath </code><br />
<em>string</em></p>
<p>MariaDB only</p>         </td>
         <td><p>The absolute file path to the X.509 certificate in PEM format, used by the MariaDB Server.</p>
<p>Only applicable when <code>internalDBUseSecureConnection</code> is set to <code>true</code> and <code>internalDBAutoGenerateCertificates</code> is set to <code>false</code>.</p>         </td>
      </tr>
   </tbody>
</table>

### Oracle-specific configurable properties

The following table presents some Oracle database configuration properties you must configure, depending on your selected database implementation.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadD-Column1-Header1">Description / Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>dbType</p>
<p><em>enum</em></p>         </td>
         <td><p>The database to install: <code>useOracleExternal</code> with Oracle databases</p>         </td>
      </tr>
      <tr>
         <td><p>oracleHost</p>
<p><em>string</em></p>         </td>
         <td>Database hostname or IP address: for example <code>oracle.localdomain.com</code>         </td>
      </tr>
      <tr>
         <td><p>oracleHost.Type</p>
<p><em>enum</em></p>         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td><p>oraclePort</p>
<p><em>integer</em></p>         </td>
         <td><p>Listener port of your Oracle database: <code>1521</code> by default</p>         </td>
      </tr>
      <tr>
         <td><p>oraclePort.Type</p>
<p><em>enum</em></p>         </td>
         <td><p>A flag identifying the listener port number format</p>
<p><u>Example</u>: <code>Integer</code></p>         </td>
      </tr>
      <tr>
         <td><p>oracleUserName</p>
<p><em>string</em></p>         </td>
         <td><p>The name of the database user account</p>
<p><u>Example</u>: <code>st_user</code></p>         </td>
      </tr>
      <tr>
         <td><p>oraclePassword</p>
<p><em>string</em></p>         </td>
         <td><p>The Oracle database encrypted password: for correct behavior, set the <code>oraclePassword.Format</code> property to <code>AES128</code></p>         </td>
      </tr>
      <tr>
         <td><p>oraclePassword.Format</p>
<p><em>enum</em></p>         </td>
         <td><p>The encryption format of your database password: <code>DefenceV1</code> Do not change this value!</p>         </td>
      </tr>
      <tr>
         <td><p>oracleServiceName</p>
<p><em>enum</em></p>         </td>
         <td>Service name of Oracle database: <code>orcl</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>oracleUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>oracleUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing Oracle DB schema or not: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>oracleUseSecureConnection</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>oracleCertificateDN</p>
<p><em>string</em></p>         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td><p>OracleTrustStoreFilePath</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td><p>OracleTrustStoreFilePath.Type</p>
<p><em>enum</em></p>         </td>
         <td><p>Type of SSL certificate: set this value to <code>File</code></p>
<p> </p>         </td>
      </tr>
      <tr>
         <td><p>externalDBUseSecureConnection</p>
<p><em>boolean</em></p>         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>oracleUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBCertificateName</p>
<p><em>string</em></p>         </td>
         <td><p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>oracleCertificateDN</code></p>         </td>
      </tr>
      <tr>
         <td><p>externalDBTrustStore</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

### MSSQL-specific configurable properties

The following table presents some MSSQL database configuration properties you must configure, depending on your selected database implementation.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadD-Column1-Header1">Description / Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>dbType</p>
<p><em>enum</em></p>         </td>
         <td><p>The database to install: <code>useMSSQLExternal</code> with MSSQL databases</p>         </td>
      </tr>
      <tr>
         <td><p>mssqlHost</p>
<p><em>enum</em></p>         </td>
         <td><p>Database hostname or IP address</p>
<p><u>Example:</u> <code>sqlserver.localdomain.com</code></p>         </td>
      </tr>
      <tr>
         <td><p>mssqlHost.Type</p>
<p><em>enum</em></p>         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td><p>mssqlPort</p>
<p><em>integer</em></p>         </td>
         <td><p>Listener port of your MSSQL database: <code>1433</code> by default</p>         </td>
      </tr>
      <tr>
         <td><p>mssqlPort.Type</p>
<p><em>enum</em></p>         </td>
         <td><p>A flag identifying the listener port number format</p>
<p><u>Example</u>: <code>Integer</code></p>         </td>
      </tr>
      <tr>
         <td><p>mssqlLoginName</p>
<p><em>string</em></p>         </td>
         <td><p>The name of the database user account</p>
<p><u>Example</u>: <code>st_user</code></p>         </td>
      </tr>
      <tr>
         <td><p>mssqlPassword</p>
<p><em>string</em></p>         </td>
         <td><p>The MSSQL database encrypted password: for correct behavior, set the <code>mssqlPassword.Format</code> property to <code>AES128</code></p>         </td>
      </tr>
      <tr>
         <td><p>mssqlPassword.Format</p>
<p><em>enum</em></p>         </td>
         <td><p>The encryption format of your database password: <code>DefenceV1</code>. Do not change this value! Do not change this value!</p>         </td>
      </tr>
      <tr>
         <td><p>mssqlDatabaseName</p>
<p><em>string</em></p>         </td>
         <td>Name of MSSQL database: <code>mssql_db4</code>         </td>
      </tr>
      <tr>
         <td><p>mssqlUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing MSSQL DB schema or not: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>mssqlUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>mssqlUseSecureConnection</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>mssqlCertificateDN</p>
<p><em>string</em></p>         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td><p>MssqlTrustStoreFilePath</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td><p>MssqlTrustStoreFilePath.Type</p>
<p><em>enum</em></p>         </td>
         <td>Type of SSL certificate: set this value to <code>File</code>         </td>
      </tr>
      <tr>
         <td><p><span class="code">externalDBUseSecureConnection</span></p>
<p><em>boolean</em></p>         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>mssqlUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBCertificateName</p>
<p><em>string</em></p>         </td>
         <td><p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>mssqlCertificateDN</code></p>         </td>
      </tr>
      <tr>
         <td><p>externalDBTrustStore</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

### PostgreSQL-specific configurable properties

The following table presents some PostgreSQL database configuration properties you must configure, depending on your selected database implementation.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Property         </th>
<th class="HeadD-Column1-Header1">Description / Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>dbType</p>
<p><em>enum</em></p>         </td>
         <td><p>The database to install: <code>usePostgreSQLExternal</code> with PostgreSQL databases</p>         </td>
      </tr>
      <tr>
         <td><p>postgreHost</p>
<p><em>enum</em></p>         </td>
         <td><p>Database hostname or IP address</p>
<p><u>Example:</u> <code>postgresqlserver.localdomain.com</code></p>         </td>
      </tr>
      <tr>
         <td><p>postgreHost.Type</p>
<p><em>enum</em></p>         </td>
         <td>A flag identifying if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
      </tr>
      <tr>
         <td><p>postgrePort</p>
<p><em>integer</em></p>         </td>
         <td><p>Listener port of your PostgreSQL database: <code>5432</code> by default</p>         </td>
      </tr>
      <tr>
         <td><p>postgrePort.Type</p>
<p><em>enum</em></p>         </td>
         <td><p>A flag identifying the listener port number format</p>
<p><u>Example</u>: <code>Integer</code></p>         </td>
      </tr>
      <tr>
         <td><p>postgreLoginName</p>
<p><em>string</em></p>         </td>
         <td><p>The name of the database user account</p>
<p><u>Example</u>: <code>st_user</code></p>         </td>
      </tr>
      <tr>
         <td><p>postgrePassword</p>
<p><em>string</em></p>         </td>
         <td><p>The PostgreSQL database encrypted password: for correct behavior, set the <code>postgresqlPassword.Format</code> property to <code>DefenceV1</code></p>         </td>
      </tr>
      <tr>
         <td><p>postgrePassword.Format</p>
<p><em>enum</em></p>         </td>
         <td><p>The encryption format of your database password: <code>DefenceV1</code>. Do not change this value! Do not change this value!</p>         </td>
      </tr>
      <tr>
         <td><p>postgreDatabaseName</p>
<p><em>string</em></p>         </td>
         <td>Name of PostgreSQL database: <code>st_db4</code>         </td>
      </tr>
      <tr>
         <td><p>postgreUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing PostgreSQL DB schema or not : <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use existing external DB schema or not. Its value must be the same as the one with the <code>postgreUseExistingSchema</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>postgreUseSecureConnection</p>
<p><em>boolean</em></p>         </td>
         <td>A flag specifying whether to use SSL encryption for connection to the Database: <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>postgreCertificateDN</p>
<p><em>string</em></p>         </td>
         <td>Distinguished name as specified in your SSL certificate         </td>
      </tr>
      <tr>
         <td><p>postgreTrustStoreFilePath</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
      <tr>
         <td><p>postgreTrustStoreFilePath.Type</p>
<p><em>enum</em></p>         </td>
         <td>Type of SSL certificate: set this value to <code>File</code>         </td>
      </tr>
      <tr>
         <td><p><span class="code">postgreCertificateCN</span></p>
<p><em>[string]</em></p>         </td>
         <td>SSL certificate common name         </td>
      </tr>
      <tr>
         <td><p><span class="code">externalDBUseSecureConnection</span></p>
<p><em>boolean</em></p>         </td>
         <td>A flag that specifies whether to use SSL encrypted communication to your external database. Its value must be the same as the one of the <code>postgreUseSecureConnection</code> property: either <code>true</code> or <code>false</code>         </td>
      </tr>
      <tr>
         <td><p>externalDBCertificateName</p>
<p><em>string</em></p>         </td>
         <td><p>Distinguished name as specified in your SSL certificate. Its value must be the same as the one with the <code>mssqlCertificateDN</code></p>         </td>
      </tr>
      <tr>
         <td><p>externalDBTrustStore</p>
<p><em>string</em></p>         </td>
         <td>Path to DB public certificate in X.509 format         </td>
      </tr>
   </tbody>
</table>

 

 

<span id="Silent2"></span>

## Recommendations for Clustered <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployments

This subtopic contains instructions and tips to aid you to successful silent installations of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> (Server and Edge) in clustered deployments:

-   Standard Cluster
-   Enterprise Cluster (EC) with external databases

Please observe the listed info before proceeding with silent installations of your cluster nodes.

<span id="silent_standard_cl"></span>

### Silent installation on Standard Cluster nodes

With Standard Cluster, after you perform silent installation on your first node, you can re-use the `Install_SecureTransport_<st-version>.properties` file for silent installation of all other nodes.

Standard Cluster works with an embedded MariaDB database (or MySQL, only on AIX). No additional edits are required.

### Silent installation on Enterprise Cluster nodes

Enterprise Cluster (EC) deployments offer the use of external databases which adds some additional steps in performing successful silent installation on all nodes.

To simplify this process, we can separate the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server deployments apart from the <span class="mc-variable SecureTransport_Variables.st_server_edge variable">SecureTransport Edge</span> deployments.

The big difference is in the fact that Server nodes are in LEC deployment (using an external database) while Edge nodes are in Standard Cluster deployment (using an embedded database).

#### <span class="mc-variable SecureTransport_Variables.st_server variable" style="font-weight: bold;">SecureTransport Server</span> **nodes in LEC**

> **Note:**
>
> In Enterprise Cluster deployments, all your SecureTransport Server nodes must have the same version as your first installed Server node. Do not attempt to add Server nodes to your cluster if the SecureTransport version does not match the one on already installed nodes.

When using external databases (Oracle, MSSQL or PostgreSQL) you must make sure the correct values are added to the respective properties, as listed in the following table:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Database         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">First node         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Every following node         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Oracle</p>         </td>
         <td><p>oracleUseExistingSchema = false</p>
<p>externalDBUseExistingSchema = false</p>         </td>
         <td><p>oracleUseExistingSchema = true</p>
<p>externalDBUseExistingSchema = true</p>
<p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>MSSQL</p>         </td>
         <td><p>mssqlUseExistingSchema = false</p>
<p>externalDBUseExistingSchema = false</p>         </td>
         <td><p>mssqlUseExistingSchema = true</p>
<p>externalDBUseExistingSchema = true</p>
<p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>PostgreSQL</p>         </td>
         <td><p>postgreUseExistingSchema = false</p>
<p>externalDBUseExistingSchema = false</p>         </td>
         <td><p>postgreUseExistingSchema = true</p>
<p>externalDBUseExistingSchema = true</p>
<p>SecretFilePath = &lt;path_to_taeh_file&gt;</p>         </td>
      </tr>
   </tbody>
</table>

#### <span class="mc-variable suite_variables.SecureTransportEdgeName variable">SecureTransport Edge</span> nodes in Standard Cluster

Follow the instructions as stated above in the <a href="#silent_standard_cl" class="MCXref xref">Silent installation on Standard Cluster nodes</a> subsection. There are no additional steps in terms of silent installation.

<span id="Silent"></span>

## Silent file editor

The Silent file editor is a tool dedicated to editing your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> `.properties` file and it is located in Tools/SilentFileEditor directory of the product distributive.

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

See <a href="silent-install-example" class="MCXref xref">Silent installation example file</a>
