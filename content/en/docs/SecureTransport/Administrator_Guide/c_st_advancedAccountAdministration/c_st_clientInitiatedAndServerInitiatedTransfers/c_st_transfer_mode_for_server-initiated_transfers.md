{
    "title": "Transfer mode for server-initiated transfers",
    "linkTitle": "Transfer mode for server-initiated transfers",
    "weight": "260"
}Transfer mode for server-initiated transfers is determined by protocol and file content type.

For AS2, transfer mode is always binary. For all other protocols, including FTP(S), HTTP(S), and SFTP, {{< SecureTransport/componentshortname  >}} uses the content-type of the file name to determine whether a transfer is text (ASCII) or binary (IMAGE).

If the content type is `text`, the file is transferred as text. If the content-type is not text, the file is transferred as binary.

Content-type is determined based on the file's extension. The default mapping for file name extension to content-type is stored in the file, `<FILEDRIVEHOME>/conf/mime.types`. Use the *Server Configuration* page to edit this file to change or add entries.

**Related topics:**

-   <a href="../c_st_transfer_multiple_files" class="MCXref xref">Transfer multiple files</a>
-   <a href="../c_st_configure_retry_parameters_for_server-initiated_transfers" class="MCXref xref">Configure retry parameters for server-initiated transfers</a>
-   <a href="../c_st_outgoing_connections" class="MCXref xref">Outgoing connections</a>
-   <a href="../r_st_authentication" class="MCXref xref">Authentication</a>
-   <a href="../c_st_server_authentication" class="MCXref xref">Server authentication</a>
-   <a href="../c_st_limitations" class="MCXref xref">Limitations</a>
-   <a href="../c_st_encryption_server-initiated_transfers" class="MCXref xref">Encryption and server-initiated transfers</a>
