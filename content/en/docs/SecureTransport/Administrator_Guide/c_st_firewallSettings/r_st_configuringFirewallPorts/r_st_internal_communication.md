{
    "title": "Internal SecureTransport communication",
    "linkTitle": "Internal SecureTransport communication",
    "weight": "330"
}-   7800 thorough 7802 – Hibernate second-level cache
-   8005 – Tomcat shutdown
-   8006 – AS2 shutdown
-   8009 – Tomcat JK connector
-   33060 – MySQL or MariaDB database
-   44431 – Standard Cluster (SC) server synchronization and heartbeat

Ports used for communication outside the firewall (for the servers that you plan to use), might need firewall rules set up so that they are accessible only from certain subnets. For example, allowing internal users to connect using both plain and secure HTTP, while requiring external users to use HTTPS, by opening port 80 only for a certain subnet, while keeping 443 open unconditionally.)

**Related topics:**

-   [Communication between the outside and SecureTransport Edge](../r_st_communication_between_outside)
-   [Communication between SecureTransport Server and SecureTransport Edge](../r_st_communication_between)
-   [Communication between SecureTransport Server and an internal network](../r_st_communication_between_server_internal_network)
