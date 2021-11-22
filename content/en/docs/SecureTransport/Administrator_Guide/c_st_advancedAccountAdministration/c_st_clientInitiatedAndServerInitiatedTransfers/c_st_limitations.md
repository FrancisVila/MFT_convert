{
    "title": "Limitations",
    "linkTitle": "Limitations",
    "weight": "320"
}{{< SecureTransport/componentshortname  >}} has the following limitations for server‑initiated transfers:

-   {{< SecureTransport/componentshortname >}} Server supports server-initiated transfers over HTTP only to remote sites running on another {{< SecureTransport/componentshortname >}} Server.
-   Server-initiated transfers over FTPS from a streaming configuration with {{< SecureTransport/componentshortname >}} Edge to remote sites support only passive connection mode.
-   When performing server-initiated uploads using the SSH protocol SecureTransport cannot always identify the remote operating system when the remote SSH server has version 3 or less.  
    For ASCII mode SSH transfers, if the remote SSH server supports the newline (newline@vandyke.com) extension, SecureTransport correctly converts the end-of-line characters of the file.  
    If the remote SSH server does not support the newline extension, SecureTransport can be configured to convert the end-of-line characters during server-initiated uploads based on the value of server configuration parameters. If the value of the `Ssh.EndOfLineConversion.enabled` server configuration parameter is true, SecureTransport uses the value of the `Ssh.EndOfLineConversion.type` server configuration parameter as the end-of-line sequence. Valid values are: `0x0A` (LF), `0x0D` (CR), and `0x0D0A` (CRLF). By default, the value of `Ssh.EndOfLineConversion.enabled` is `false` and the value of `Ssh.EndOfLineConversion.type` is `0x0D0A`.  
    Whether or not the remote SSH server supports the newline extension, the remote server sees these transfers as BINARY mode.  
    In all other cases of ASCII mode SSH server-initiated uploads and downloads, SecureTransport cannot identify the correct end-of-line characters to use. SecureTransport performs these transfers in BINARY mode and indicates this on the *File Tracking* page.
-   The name of a file processed by a Folder Monitor transfer site cannot contain two or more of the following characters in sequence: `< > | : ? " * / \ % [ ] ~` (at the beginning of the file only).

**Related topics:**

-   <a href="../c_st_transfer_mode_for_server-initiated_transfers" class="MCXref xref">Transfer mode for server-initiated transfers</a>
-   <a href="../c_st_transfer_multiple_files" class="MCXref xref">Transfer multiple files</a>
-   <a href="../c_st_configure_retry_parameters_for_server-initiated_transfers" class="MCXref xref">Configure retry parameters for server-initiated transfers</a>
-   <a href="../c_st_outgoing_connections" class="MCXref xref">Outgoing connections</a>
-   <a href="../r_st_authentication" class="MCXref xref">Authentication</a>
-   <a href="../c_st_server_authentication" class="MCXref xref">Server authentication</a>
-   <a href="../c_st_encryption_server-initiated_transfers" class="MCXref xref">Encryption and server-initiated transfers</a>
