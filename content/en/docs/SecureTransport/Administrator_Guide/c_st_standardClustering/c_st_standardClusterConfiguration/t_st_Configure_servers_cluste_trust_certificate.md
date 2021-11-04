{
    "title": "Configure servers in a cluster to trust a certificate",
    "linkTitle": "Configure servers in a cluster to trust a certificate",
    "weight": "140"
}In a cluster environment, the CA that issued the certificate must be trusted by all servers in the cluster. Refer to the procedure below. The self-signed certificates used to sign the server certificates during the installation of the servers also need to be configured across the servers. If the signing certificates for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers are issued by different CAs, configure each server with the root CA certificate of that CA.

1.  On primary server, export the CA certificate to a local file using the *Trusted CAs* page.
2.  Copy the certificate file with the CA certificate from the primary server to the secondary server and import the certificate using the *Trusted CAs* page.
3.  On secondary server, export the CA certificate to a local file using the *Trusted CAs* page.
4.  Copy the certificate file with the CA certificate from the secondary server to the primary server and import the certificate using the *Trusted CAs* page.
5.  Bounce both servers. For instructions, see <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_miscellaneousoptions#Limit" class="MCXref xref">Limit FTP login failures</a>.

**Related topics:**

-   <a href="../t_st_setup_active-active_cluster" class="MCXref xref">Set up an active/active cluster</a>
-   <a href="../t_st_specify_cluster_connection_timeout" class="MCXref xref">Specify the cluster connection timeout</a>
-   <a href="../t_st_setup_active-passive_cluster" class="MCXref xref">Set up an active/passive cluster</a>
