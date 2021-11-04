{
    "title": "Change the package manager base folder",
    "linkTitle": "Change the package manager base folder",
    "weight": "160"
}To change the package manager base folder on a root installation:

1.  Log on to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server as root.
2.  Stop all SecureTransport protocol servers and services.
3.  If the new folder is on a network share, so that LDAP users can access the package manager base folder, mount the new network share on which the new package manager base folder is located using the default UID and GID specified in LDAP domain page for those users.
4.  Copy the package manager base folder to its new location.
5.  Delete the old package manager base folder.
6.  So that references to the old package manager base folder still work, create a symbolic link that points to the new package manager base folder at the location of the old package manager base folder with the same names as the old package manager base folder.
7.  Start the database and the Administration Tool service.
8.  In the Administration Tool, change the **Package Manager Base Folder** field to reference the new package manager base folder.
9.  Start the remaining SecureTransport services and protocol servers.

> **Note:**
>
> You can make a package manager base folder stored on a network share accessible for users of only one LDAP domain.

**Related topic:**

-   <a href="../../../applications/applicationspackageretentionmaintenance" class="MCXref xref">Package Retention Maintenance application</a>
