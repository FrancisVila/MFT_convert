{
    "title": "Configurable properties for silent installation",
    "linkTitle": "Configurable properties for silent installation",
    "weight": "120"
}  

The following table presents some useful configuration properties you can edit in the  
`Install_SecureTransport_<st-version>.properties` file to perform silent installation of {{< SecureTransport/componentshortname  >}}. <u>Make sure to remove any empty valued properties</u> as leaving these properties blank might adversely affect your silent installation!

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
         <td><p><code>Component.PreferredJavaVersion</code></p>
<p><em>Integer</em></p>         </td>
         <td>The Java version used for the installation. It must be the same as the one from the installation package, for SecureTransport 5.5 it's 11.         </td>
      </tr>
      <tr>
         <td><p>Server</p>
<p><em>boolean</em></p>         </td>
         <td>A flag that specifies if you're installing {{< SecureTransport/componentshortname  >}} Server. Must be set to <code>false</code> when installing {{< SecureTransport/securetransportname  >}} Edge.         </td>
      </tr>
      <tr>
         <td><p>Edge</p>
<p><em>boolean</em></p>         </td>
         <td>A flag that specifies if you're installing {{< SecureTransport/componentshortname  >}} Edge. Must be set to <code>false</code> when installing {{< SecureTransport/securetransportname  >}} Server.         </td>
      </tr>
      <tr>
         <td><p><code>dbType</code></p>
<p><em>string</em></p>         </td>
         <td><p>The database to install.</p>
<p>Possible values:</p>
<ul>
<li><p><code>useDBLocal</code> for the embedded database (MySQL or Mariadb)</p></li>
<li><p><code>useOracleExternal</code>, <code>useOracleExternal</code>, useMSSQLExternal, <code>usePostgreSQLExternal</code> for an external database</p></li>
</ul>
<p>Must be set to <code>useDBLocal</code> when installing {{< SecureTransport/securetransportname  >}} Edge.</p>
<p>For more information, see <a href="#Database">Database-specific configurable properties</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>externalDBUseExistingSchema</p>
<p><em>boolean</em></p>         </td>
         <td><p>A flag that specifies if you're using an external database. Not applicable to {{< SecureTransport/securetransportedgename  >}} installation.</p>
<p><strong>Important!</strong> In a EC deployment using an external database (Oracle or MSSQL), you must configure this value to <code>false</code> with the first Server node and to <code>true</code> all subsequent Server deployments in your EC.</p>         </td>
      </tr>
      <tr>
         <td><p>sslAdminPort</p>
<p><em>Integer</em></p>         </td>
         <td>The default value is 444         </td>
      </tr>
      <tr>
         <td><p>tomcatShutdownPort</p>
<p>Integer</p>         </td>
         <td>The default value is 8005         </td>
      </tr>
      <tr>
         <td><p>enableLogRotation</p>
<p><em>boolean</em></p>
<p> </p>         </td>
         <td><p>A flag that specifies if the system should perform automatic backup and purging of log files. When true, {{< SecureTransport/componentshortname  >}} Server backups log files, generated on the respective day, and creates a new one for the subsequent day.</p>         </td>
      </tr>
      <tr>
         <td>SecretFilePath         </td>
         <td><p>The path to the <code>taeh</code> file you copied to this system. If blank, the installer creates a new secret file.</p>
<ul>
<li><p>If you are installing the first server in a cluster, you can specify a secret file or have the installer create one. Before you install {{< SecureTransport/componentshortname  >}} on the other cluster nodes, you must copy the secret file to those systems.</p></li>
<li><p>If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. See <a href="../../../prereqs_overview/secret_file">Secret file</a>.</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>clusterNodeValue</p>         </td>
         <td>The FQDN or IP address of the
SecureTransport
node to add to the cluster.         </td>
      </tr>
   </tbody>
</table>

<span id="Database"></span>

### Database-specific configurable properties

The following table presents the database properties you must configure, depending on your selected database implementation.

<span id="MariaDB-"></span>

#### MariaDB- and MySQL-specific configurable properties

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
         <td><code>internalDBPort.Type</code>
<p><em>enum</em></p>         </td>
         <td><p>A flag identifying the embedded listener port type: set to <code>IPPortOwner</code></p>         </td>
      </tr>
      <tr>
         <td><code>internalDBPort.Max</code>
<p><em>integer</em></p>         </td>
         <td><p>Upper threshold of embedded port range</p>
<p><u>example</u>: <code>65535</code></p>         </td>
      </tr>
      <tr>
         <td><code>internalDBPort.Min</code>
<p><em>integer</em></p>         </td>
         <td><p>Lower threshold of embedded port range</p>
<p><u>example</u>: <code>1024</code></p>         </td>
      </tr>
      <tr>
         <td><strong>The following entries concern MariaDB only</strong>         </td>
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

#### Oracle-specific configurable properties

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
         <td><p>The Oracle database encrypted password: for correct behavior, set the <code>oraclePassword.Format</code> property to <code>AES128</code>.</p>         </td>
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
         <td>A flag that specifies if you are using HostName or IP address for your database: either <code>HostName</code> or <code>IPaddress</code>         </td>
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
         <td>A flag specifying whether to use SSL encryption for connection to the database: <code>true</code> or <code>false</code>         </td>
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
         <td><p><code>externalDBUseSecureConnection</code></p>
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
         <td><p><code>postgreCertificateCN</code></p>
<p><em>[string]</em></p>         </td>
         <td>SSL certificate common name         </td>
      </tr>
      <tr>
         <td><p><code>externalDBUseSecureConnection</code></p>
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

 

<span id="Configur"></span>

## Configurable database parameters for Clustered {{< SecureTransport/componentshortname  >}} deployments

Standard Cluster works with an embedded MariaDB database (or MySQL, only on AIX). No additional edits are required.

Enterprise Cluster (EC) deployments offer the use of external databases which adds some additional steps in performing successful silent installation on all nodes. To simplify this process, we can separate the {{< SecureTransport/componentshortname  >}} Server deployments apart from the deployments. The big difference is in the fact that Server nodes are in EC deployment (using an external database) while Edge nodes are in Standard Cluster deployment (using an embedded database).

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

 

**Related topics**

-   [Example silent installation files: SecureTransport Server with MariaDB database on Windows](../silent-install-example-mariadb)
-   [Example silent installation files: SecureTransport Server with Oracle database on a Linux cluster](../silent-install-cluster-externaldb)

 
