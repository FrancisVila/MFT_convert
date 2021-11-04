{
    "title": " Shared Storage",
    "linkTitle": "Shared storage",
    "weight": "100"
}Cluster environments of any type in an Enterprise or a Standard Cluster require Shared storage.

For more information about Standard and Enterprise Cluster models, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

## Shared storage definition and configuration in SecureTransport

Since the data in the Shared Storage is used by all cluster nodes, they must have identical rights and simultaneous read/write access, while also providing consistency between the users’ files.

Shared Storage must be mounted to the same location on all servers.

When creating a user account, the user’s home folder must be the full path to the Shared Storage folder.

## Setting up cluster with shared storage for the home folders of the user accounts

**Windows**

If the account home folder prefix is on a shared network, specify a real user that has access to it. You must either use SecureTransport impersonation functionality or use permissions sufficient for the network share to be accessed by local system users. The real user must be part of the domain, not a local user for one of the cluster nodes; otherwise the other nodes in the cluster cannot impersonate it to access the shared location.

For more information about creating and configuring a real user in Windows, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

**Linux**

All user accounts must have access to the shared storage folder.

For more information about creating and configuring a real user in Linux, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.
