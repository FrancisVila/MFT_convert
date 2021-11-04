{
    "title": "Outgoing connections",
    "linkTitle": "Outgoing connections",
    "weight": "290"
}You can proxy outgoing connections using a SOCKS5 proxy running on a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge or an HTTP proxy. You configure the use of a proxy by defining one or more network zones and making a selection in the transfer site. See <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#SetupMenu_1217491348_1149202" class="MCXref xref">Manage the communication across Transaction Manager, protocol and proxy servers</a> and the procedures for defining AS2, FTP, HTTP, PeSIT, and SSH transfer sites.

> **Note:**
>
> By default, when a proxy is configured, direct connections from the SecureTransport Backend are not permitted even in when the proxy is unreachable. To change the default behavior, set Direct.Connection.When.Proxy.Down server configuration parameter to true. For information on changing server configuration parameters, refer to View and change server configuration parameters.

If server-initiated transfers being performed using FTP(S) are passing through the SOCKS5 proxy, increase the value of the `Socks.Idle.Timeout` server configuration parameter on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge from 600000 to 7200000 milliseconds. This prevents the FTP control connection from timing out during the transfer. You must restart the SOCKS5 proxy server for this change to take effect.

**Related topics:**

-   <a href="../c_st_transfer_mode_for_server-initiated_transfers" class="MCXref xref">Transfer mode for server-initiated transfers</a>
-   <a href="../c_st_transfer_multiple_files" class="MCXref xref">Transfer multiple files</a>
-   <a href="../c_st_configure_retry_parameters_for_server-initiated_transfers" class="MCXref xref">Configure retry parameters for server-initiated transfers</a>
-   <a href="../r_st_authentication" class="MCXref xref">Authentication</a>
-   <a href="../c_st_server_authentication" class="MCXref xref">Server authentication</a>
-   <a href="../c_st_limitations" class="MCXref xref">Limitations</a>
-   <a href="../c_st_encryption_server-initiated_transfers" class="MCXref xref">Encryption and server-initiated transfers</a>
