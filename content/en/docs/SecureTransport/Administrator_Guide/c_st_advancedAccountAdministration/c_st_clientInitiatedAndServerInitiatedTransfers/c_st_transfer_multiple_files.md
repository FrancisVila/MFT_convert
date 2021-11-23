{
    "title": "Transfer multiple files",
    "linkTitle": "Transfer multiple files",
    "weight": "270"
}{{< SecureTransport/componentshortname  >}} allows a server-initiated transfer job to process a single file, a set of multiple files specified using wildcards in the file name, or a directory.

> **Note:**
>
> Except for Folder Monitor type applications, wildcards in directory names and recursive directory traversal are not supported.

A single transfer request for transferring multiple files is defined at the beginning of the transfer process only. If the number of files happens to change during the transfer process, these changes are not reflected and the transfer of these additional/missing files or directories fails.

The {{< SecureTransport/componentshortname  >}} system keeps track of the status of all the individual transfers. If a transfer fails, it is rescheduled for a later point in time until the retry limit value is exceeded.

**Related topics:**

-   [Transfer mode for server-initiated transfers](../c_st_transfer_mode_for_server-initiated_transfers)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Outgoing connections](../c_st_outgoing_connections)
-   [Authentication](../r_st_authentication)
-   [Server authentication](../c_st_server_authentication)
-   [Limitations](../c_st_limitations)
-   [Encryption and server-initiated transfers](../c_st_encryption_server-initiated_transfers)
