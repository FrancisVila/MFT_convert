{
    "title": "Configure retry parameters for server-initiated transfers",
    "linkTitle": "Configure retry parameters for server-initiated transfers",
    "weight": "280"
}When a server-initiated transfer fails, {{< SecureTransport/componentshortname  >}} can automatically retry the transfer. By default, {{< SecureTransport/componentshortname  >}} is configured to retry such a transfer five times at two-minute intervals. You can configure the retry count and interval by editing parameters on the *Server Configuration* page:

-   `EventQueue.maxRetryCount` – The number of times {{< SecureTransport/componentshortname >}} retries a transfer. The default value is `5`.
-   `EventQueue.retryDelayInterval` – The time in seconds that {{< SecureTransport/componentshortname >}} waits after a transfer fails before retrying it. The default value is `120`.
-   `EventQueue.internalRetryDelayInterval` – The time in seconds that {{< SecureTransport/componentshortname >}} waits when a transfer cannot be started (for example, because all outbound connection to an FTP server are in use) before retrying it. The default value is `120`.

**Related topics:**

-   <a href="../c_st_transfer_mode_for_server-initiated_transfers" class="MCXref xref">Transfer mode for server-initiated transfers</a>
-   <a href="../c_st_transfer_multiple_files" class="MCXref xref">Transfer multiple files</a>
-   <a href="../c_st_outgoing_connections" class="MCXref xref">Outgoing connections</a>
-   <a href="../r_st_authentication" class="MCXref xref">Authentication</a>
-   <a href="../c_st_server_authentication" class="MCXref xref">Server authentication</a>
-   <a href="../c_st_limitations" class="MCXref xref">Limitations</a>
-   <a href="../c_st_encryption_server-initiated_transfers" class="MCXref xref">Encryption and server-initiated transfers</a>
