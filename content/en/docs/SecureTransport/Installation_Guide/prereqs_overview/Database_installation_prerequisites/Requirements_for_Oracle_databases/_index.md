{
    "title": "Requirements for Oracle databases",
    "linkTitle": "Requirements for Oracle databases",
    "weight": "110"
}-   For a complete list of supported Oracle Database releases, refer to [*Axway and third-party software support*](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm).

-   To support unicode characters in filenames and directories, the database should use AL32UTF8 encoding.

-   SecureTransport can connect to an external Oracle database over a plain or secure connection.
    Starting with SecureTransport 5.5-20201029, the external database server’s certificates that contain `keyUsage` extensions MUST also have the `digitalSignature` indicator enabled. This affects both secure and non-secure connections.

-   The Oracle database can use, but does not require, the Real Application Clusters (RAC) option.

-   SecureTransport can use, but does not require, more than one Oracle database to store its data.

-   Settings and parameters as follows:
    -   Redo log groups: 3
    -   Redo log file size: 500 MB (For more about redo log file use, see *SecureTransport 5.5 Capacity Planning Guide*)
    -   Gather optimizer statistics: Weekly or with any 10 percent change in the record count.
    -   `DB_CACHE_SIZE`: 1 GB or larger. You should set this as high as possible to improve performance.
    -   `OPEN_CURSORS`: at least 1000
    -   `SHARED_POOL_SIZE`: 150 MB per node in the cluster
    -   `PROCESSES`: 1000 or more

    <!-- -->

    -   For the external Oracle database, `hibernate.c3p0.max_size` and `hibernate.c3p0.min_size` is specified in `<FILEDRIVEHOME>/conf/configuration.xml`. The default value for `hibernate.c3p0.max_size` is 8 for each component, while the default value for `hibernate.c3p0.min_size` varies depending on the component. These two configuration items specify the connection pool size per component.

-   The database must have the following tablespaces defined:

    -   `ST_DATA` – configuration, such as account, sites, and certificates
    -   `ST_FILETRACKING` – file tracking tables
    -   `ST_SERVERLOG` – server log tables

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When you direct log data to separate databases, you must define the <code>ST_FILETRACKING</code> tablespace in the database for the transfer log and the <code>ST_SERVERLOG</code> tablespace in the database for the server log.         </td>
      </tr>
</table>

      
    Set `AUTOEXTEND ON` for all tablespaces and datafiles.  
    See *SecureTransport 5.5 Capacity Planning Guide* for information you can use to set initial sizes for the tablespaces. Give the user unlimited quota on all tablespaces.

-   The database must have a user defined who have been granted the following system privileges:  
    
    -   `CREATE OPERATOR`
    -   `CREATE PROCEDURE`
    -   `CREATE SEQUENCE`
    -   `CREATE SESSION`
    -   `CREATE TABLE`

      
    
    These privileges can be granted through a role or, preferably, directly. There are a few restrictions in the use of roles: 
    -   UPDATES\_DB\_LOG table is not populated, therefore logging for DB errors during installation or upgrade is limited
    -   To install updates, the `update.sh` script should be run with an additional [argument](https://docs.axway.com/bundle/SecureTransport_55_UpgradeGuide_allOS_en_HTML5/page/Content/UpgradeGuide/upgrade/Upgrading_SecureTransport_on_a_Unix_based_platform.htm).
    -   Transfer Log Maintenance and Log Entry Maintenance applications fail to export old partitions with "ORA-31623: a job is not attached to this session via the specified handle" error.

-   The default tablespace for the database user must be `ST_DATA`.

During the installation, you need the following information:

-   Host name, IP address, or SCAN name of the database server in case Oracle RAC is utilized
-   Listener port number
-   Database user name and password
-   Service name
-   If the database is used over secure connection, you will also need the database server certificate signer or JKS keystore which contains it in order to trust the connection. In addition, the optional parameter **Distinguished Name (DN)** can be provided and installer will verify the provided information against the database certificate's DN. If it is not provided, the installer will not check the certificate DN and will trust any.

**Related topics:**

-   [Data pump database management system](data_pump_database_management)
-   [Requirements for Microsoft SQL Server databases](../requirements_for_sql_databases)
