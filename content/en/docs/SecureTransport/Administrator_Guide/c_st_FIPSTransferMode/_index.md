{
    "title": "FIPS transfer mode",
    "linkTitle": "FIPS transfer mode",
    "weight": "210"
}For client-initiated file transfers using the AS2 (SSL), FTPS, HTTPS, PeSIT (SSL, legacy SSL), or SSH (SFTP and SCP) protocols, you can restrict the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> Server to use only FIPS certified cryptographic libraries. This requires the sender and the recipient (clients and partner servers) to use only approved algorithms, ciphers, and cipher suites and assures that the entire transfer is secure at FIPS 140-2 Level 1.

For a complete list of supported ciphers and algorithms that be used in FIPS mode, see <a href="r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.

> **Note:**
>
> Because Axway Secure Client firewall-friendly Tunnel Mode uses SSL v3, you cannot use it for FTPS in FIPS transfer mode.

For the relevant protocols, you can select **Enable FIPS Transfer Mode** in the *Server Control* page or the *Add Transfer Site* or *Edit Transfer Site* page.

As an administrator, you can customize the list of allowed TLS cipher suites or SSH ciphers and algorithms at the following levels:

-   per protocol server (in the server settings). For more information about client-initiated transfers, see <a href="../operations_menu/extended_server_control" class="MCXref xref">Server control</a>.  

    > **Note:**
    >
    > Enabling FIPS transfer mode for a protocol server causes transfers to fail if the client that uses that server does not provide the required FIPS cipher or cipher suite.

-   for server-initiated transfers through a specific transfer site (in the transfer site configuration)

-   for server-initiated transfers over a specific protocol (via dedicated server configuration options)  
    For more information about server-initiated transfers, see <a href="../accounts/transfersites/t_st_transfersites" class="MCXref xref">Manage transfer sites</a>.  

    > **Note:**
    >
    > Enabling FIPS Transfer Mode for an existing transfer site causes transfers to fail if the other server does not provide the required cipher or cipher suite.

    ## FIPS-certified cryptographic libraries

    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span><span class="mc-variable axway_variables.Component_Version variable">5.5</span> uses the following cryptographic library in FIPS transfer mode:

    -   BC-FJA (Bouncy Castle FIPS Java API) 1.0.2, FIPS 140-2 Certificate No. 3514
