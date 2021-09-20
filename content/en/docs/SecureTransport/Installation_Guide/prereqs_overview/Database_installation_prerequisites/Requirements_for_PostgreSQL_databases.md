{
    "title": "Requirements for PostgreSQL databases",
    "linkTitle": "Requirements for PostgreSQL databases",
    "weight": "120"
}For a complete list of supported PostgreSQL versions, refer to [*Axway and third-party software support*](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm).

SecureTransport can connect to an external PostgreSQL database over a plain or secure connection.
Starting with SecureTransport 5.5-20201029, the external database server’s certificates that contain `keyUsage` extensions MUST also have the `digitalSignature` indicator enabled. This affects both secure and non-secure connections.

-   Server
    requirements:
    -   physical or virtual server with 8 vCPUs or more
    -   64 GB RAM on the server (we assume the server will be used only for PostgreSQL) or more
-   Parameters as follows:
    -   `max_connections`: 1000
    -   `shared_buffers`– 1/4 of the available RAM
    -   `effective_cache_size`– 3/4 of the available RAM
    -   `maintenance_work_mem`– at least 512MB
    -   `work_mem`– half of the available RAM
    -   `autovacuum` should be turned on
-   Tablespace requirements:  
    The following tablespaces have to be created:
    -   `st_data` – configuration, such as account, sites, and certificates
    -   `st_filetracking` – file tracking tables
    -   `st_serverlog` – server log tables

      
    
    All three tablespaces should be created on fast disks (preferably SSDs) on location with enough free space to handle at least the predicted SecureTransport workload multiplied by two.
-   User/login/role requirements:
      
    <span id="role_requirements"></span>The role, which will be used for SecureTransport, should be created with the `LOGIN` privilege.
    The user/login/role must be granted `CREATE `privileges on the above three tablespaces.
-   Database requirements:  
    
    -   Database should be created with (default) tablespace `st_data`.
    -   The owner of the database should be the above mentioned user/login/role.

During the installation, you need the following information:

-   Host name or IP address
-   Listener port number
-   Database user name and password
-   If the database is used over secure connection, you will also need the public key of the database server certificate.

**Related topics:**

-   [Install SecureTransport](../../../install_overview)
