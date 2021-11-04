{
    "title": "Requirements for synchronization",
    "linkTitle": "Requirements for synchronization",
    "weight": "120"
}Cluster synchronization requires the following:

-   The `<FILEDRIVEHOME>/lib/admin/config/servers` configuration file is correct and
    identical on all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers.
-   The `<FILEDRIVEHOME>/var/tmp/sentinel_primary` file exists on the primary <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>
    Edge only.
-   A shared common secret file (named `taeh` file) is used on all servers.
-   Each server is hosted on a different computer or VM.
-   All servers use the same installation path.
-   All the servers are on the same LAN.
    -   The primary administrator user ID is the same on all servers and all have the same password.
-   The clocks are set to the same time on all servers.
-   The internal CAs on all servers is trusted by all other servers. Optionally, you can import
    the same internal CA on all servers.
-   All database settings are identical on all the computers that will be synchronized.
-   Only files used for server configuration are configured for synchronization.
-   All the server certificates are issued by a common CA.
