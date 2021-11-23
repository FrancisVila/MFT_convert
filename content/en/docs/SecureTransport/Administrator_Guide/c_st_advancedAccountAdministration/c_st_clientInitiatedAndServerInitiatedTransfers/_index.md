{
    "title": "Client-initiated and server-initiated transfers",
    "linkTitle": "Client-initiated and server-initiated transfers",
    "weight": "240"
}You can use {{< SecureTransport/componentshortname  >}} to set up and execute server-initiated transfers. There are four types of transfers:

-   **Client-initiated downloads** – A client application "pulls" a file from the {{< SecureTransport/componentshortname >}} Server.
-   **Client-initiated uploads** – A client application "pushes" a file to the {{< SecureTransport/componentshortname >}} Server.
-   **Server-initiated downloads** – The {{< SecureTransport/componentshortname >}} Server "pulls" a file from a remote server.
-   **Server-initiated uploads** – The {{< SecureTransport/componentshortname >}} Server "pushes" a file to a remote server.

Client- and server-initiated transfers can be performed using any supported protocol. The protocol servers that handle client-initiated transfers run on the {{< SecureTransport/componentshortname  >}} Server or on the {{< SecureTransport/componentshortname  >}} Edge in the perimeter network (DMZ). The protocol clients that perform the server-initiated transfers run on the {{< SecureTransport/componentshortname  >}} Server in the Transaction Manager server JVM and can connect out through a SOCKS5 Proxy on a {{< SecureTransport/componentshortname  >}} Edge or through an HTTP proxy to a remote system. This allows the protocol clients to have direct access to the file system.

> **Note:**
>
> If the remote server certificate have a X509v3 Extended Key Usage extension configured, make sure it is set to 'TLS Web Server Authentication'. Server-initiated transfers will always fail if the remote server certificate is configured with a X509v3 Extended Key Usage extension of 'TLS Web Client Authentication'.

Server-initiated transfers can be triggered by any of the following events, depending on the configuration of the transfer:

-   A Folder Monitor
-   A scheduler
-   The arrival of a file

In addition to the protocols mentioned above, the Folder Monitor can be used for inbound and outbound file transfers.

-   For outbound transfers, {{< SecureTransport/componentshortname >}} can copy the files to a specified folder.
-   For inbound transfers, {{< SecureTransport/componentshortname >}} can monitor the folder for newly arrived files and use the event to trigger an application executing specific tasks.

Any server-initiated transfer requires an account to be subscribed to an application based on one of the application types: Standard Router, Site Mailbox, Shared Folder, Basic Application, File Transfer via File Service Interface, Human to System, or {{< SecureTransport/advancedrouting  >}}. For detailed information about application types and applications, see [Applications](../../applications).

> **Note:**
>
> When setting up a server-initiated outbound transfer, make sure that the target folder exists. SecureTransport does not create the target folder on the remote system automatically.

The following topics describe managing client-initiated and server-initiated transfers:

-   [Transfer mode for server-initiated transfers](c_st_transfer_mode_for_server-initiated_transfers) - Describes the transfer mode for server-initiated transfers.
-   [Transfer multiple files](c_st_transfer_multiple_files) - Describes transfers of single and multiple files.
-   [Configure retry parameters for server-initiated transfers](c_st_configure_retry_parameters_for_server-initiated_transfers) - Describes configuring the retry parameters for server-initiated transfers.
-   [Outgoing connections](c_st_outgoing_connections) - Describes the outgoing connections.
-   [Authentication](r_st_authentication) - Lists the authentication methods for connecting to a remote site for different protocols.
-   [Server authentication](c_st_server_authentication) - Describes server authentication.
-   [Limitations](c_st_limitations) - Lists the server‑initiated transfer limitations.
-   [Encryption and server-initiated transfers](c_st_encryption_server-initiated_transfers) - Describes using encryption with server-initiated transfers.
