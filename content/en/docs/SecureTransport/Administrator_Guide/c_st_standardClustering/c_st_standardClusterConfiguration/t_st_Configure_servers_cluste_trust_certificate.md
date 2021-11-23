{
    "title": "Configure servers in a cluster to trust a certificate",
    "linkTitle": "Configure servers in a cluster to trust a certificate",
    "weight": "140"
}In a cluster environment, the CA that issued the certificate must be trusted by all servers in the cluster. Refer to the procedure below. The self-signed certificates used to sign the server certificates during the installation of the servers also need to be configured across the servers. If the signing certificates for the {{< SecureTransport/componentshortname  >}} servers are issued by different CAs, configure each server with the root CA certificate of that CA.

1.  On primary server, export the CA certificate to a local file using the *Trusted CAs* page.
2.  Copy the certificate file with the CA certificate from the primary server to the secondary server and import the certificate using the *Trusted CAs* page.
3.  On secondary server, export the CA certificate to a local file using the *Trusted CAs* page.
4.  Copy the certificate file with the CA certificate from the secondary server to the primary server and import the certificate using the *Trusted CAs* page.
5.  Bounce both servers. For instructions, see [Limit FTP login failures](../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_miscellaneousoptions#Limit).

**Related topics:**

-   [Set up an active/active cluster](../t_st_setup_active-active_cluster)
-   [Specify the cluster connection timeout](../t_st_specify_cluster_connection_timeout)
-   [Set up an active/passive cluster](../t_st_setup_active-passive_cluster)
