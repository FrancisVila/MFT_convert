{
    "title": "Set up SecureTransport Edge servers for synchronization",
    "linkTitle": "Set up SecureTransport Edge servers for synchronization",
    "weight": "140"
}Use the following procedure to set up <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers for synchronization.

1.  Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge on the system that will be the primary
    server.
2.  Copy the `taeh` file from the `<FILEDRIVEHOME>/bin/` directory to
    all the other systems.
3.  Using the `taeh` file, install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge on the other systems.
4.  Add licenses for all servers. For instructions, refer to the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.
5.  Generate an internal CA on each server. For instructions, refer to the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.
6.  Exchange CA certificates between all servers in a Standard Cluster (SC) or Enterprise Cluster (EC). For details, refer to the
    procedures for exporting and importing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server CA certificates in the
    <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.
7.  On the primary and all secondary servers, list all the servers in the
    `<FILEDRIVEHOME>/lib/admin/config/servers` configuration file. List the primary
    server first and continue with the secondary servers.  
    Edit the file and add a line of following form for each server in a cluster:  
    `<host> https://<host>:<port>`  
    where:
    -   `<host>` is the FQDN or IP address of the system
    -   `https://<host>:<port>` is the URL of the Administration Tool on that
        system
    -   `<port>` is usually 444

      
    The two fields are separated by a tab character.  
    The `<FILEDRIVEHOME>/lib/admin/config/servers` file must be the same on all
    computer in your cluster. You can create it on the primary server and copy it to the
    others.
8.  On the primary server, create a file named
    `<FILEDRIVEHOME>/var/tmp/sentinel_primary`. This file is not used for integration with <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Sentinel. It is required whether or not Sentinel is used.  
    To create the file, you can use the `touch` command in UNIX or create an empty
    file with no file extension in Windows. The file must have 0 bytes.
9.  Log out of the primary <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge server and log in again. Make sure that the
    server is identified as the primary server and that the **Synchronize All** and **Bounce All** buttons are displayed.
10. Synchronize the secondary servers manually from the Administration Tool of the
    primary server.
11. On the primary server, either import an external CA or generate a local CA. For
    instructions, refer to the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.
    Dynamic synchronization copies the new CA to all servers in a cluster.
12. On the primary server, generate the server certificate required by your configuration
    and complete other configuration tasks.
