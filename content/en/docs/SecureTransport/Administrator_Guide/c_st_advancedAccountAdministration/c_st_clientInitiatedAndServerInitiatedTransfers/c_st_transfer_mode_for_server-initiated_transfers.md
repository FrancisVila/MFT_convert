{
    "title": "Transfer mode for server-initiated transfers",
    "linkTitle": "Transfer mode for server-initiated transfers",
    "weight": "270"
}Transfer mode for server-initiated transfers is determined by protocol and file content type.

For AS2, transfer mode is always binary. For all other protocols, including FTP(S), HTTP(S), and SFTP, SecureTransport uses the content-type of the file name to determine whether a transfer is text (ASCII) or binary (IMAGE).

If the content type is `text`, the file is transferred as text. If the content-type is not text, the file is transferred as binary.

Content-type is determined based on the file's extension. The default mapping for file name extension to content-type is stored in the file, `<FILEDRIVEHOME>/conf/mime.types`. Use the *Server Configuration* page to edit this file to change or add entries.

**Related topics:**

-   [Transfer multiple files](../c_st_transfer_multiple_files)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Outgoing connections](../c_st_outgoing_connections)
-   [Authentication](../r_st_authentication)
-   [Server authentication](../c_st_server_authentication)
-   [Limitations](../c_st_limitations)
-   [Encryption and server-initiated transfers](../c_st_encryption_server-initiated_transfers)
