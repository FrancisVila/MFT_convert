{
    "title": "Outgoing connections",
    "linkTitle": "Outgoing connections",
    "weight": "300"
}You can proxy outgoing connections using a SOCKS5 proxy running on a SecureTransport Edge or an HTTP proxy. You configure the use of a proxy by defining one or more network zones and making a selection in the transfer site. See [Manage the communication across Transaction Manager, protocol and proxy servers](../../../c_st_setup/c_st_networkzones/t_st_networkzones) and the procedures for defining AS2, FTP, HTTP, PeSIT, and SSH transfer sites.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">By default, when a proxy is configured, direct connections from the SecureTransport Backend are not permitted even in when the proxy is unreachable. To change the default behavior, set <code>Direct.Connection.When.Proxy.Down</code> server configuration parameter to <strong>true</strong>. For information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters" xrefformat="{paratext}">View and change server configuration parameters</a>.         </td>
      </tr>
</table>

If server-initiated transfers being performed using FTP(S) are passing through the SOCKS5 proxy, increase the value of the `Socks.Idle.Timeout` server configuration parameter on the SecureTransport Edge from 600000 to 7200000 milliseconds. This prevents the FTP control connection from timing out during the transfer. You must restart the SOCKS5 proxy server for this change to take effect.

**Related topics:**

-   [Transfer mode for server-initiated transfers](../c_st_transfer_mode_for_server-initiated_transfers)
-   [Transfer multiple files](../c_st_transfer_multiple_files)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Authentication](../r_st_authentication)
-   [Server authentication](../c_st_server_authentication)
-   [Limitations](../c_st_limitations)
-   [Encryption and server-initiated transfers](../c_st_encryption_server-initiated_transfers)
