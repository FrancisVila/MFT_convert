{
    "title": "Limitations",
    "linkTitle": "Limitations",
    "weight": "330"
}SecureTransport has the following limitations for server‑initiated transfers:

-   SecureTransport Server supports server-initiated transfers over HTTP only to remote sites running on another SecureTransport Server.
-   Server-initiated transfers over FTPS from a streaming configuration with SecureTransport Edge to remote sites support only passive connection mode.
-   When performing server-initiated uploads using the SSH protocol SecureTransport cannot always identify the remote operating system when the remote SSH server has version 3 or less.  
    For ASCII mode SSH transfers, if the remote SSH server supports the newline (newline@vandyke.com) extension, SecureTransport correctly converts the end-of-line characters of the file.  
    If the remote SSH server does not support the newline extension, SecureTransport can be configured to convert the end-of-line characters during server-initiated uploads based on the value of server configuration parameters. If the value of the `Ssh.EndOfLineConversion.enabled` server configuration parameter is true, SecureTransport uses the value of the `Ssh.EndOfLineConversion.type` server configuration parameter as the end-of-line sequence. Valid values are: `0x0A` (LF), `0x0D` (CR), and `0x0D0A` (CRLF). By default, the value of `Ssh.EndOfLineConversion.enabled` is `false` and the value of `Ssh.EndOfLineConversion.type` is `0x0D0A`.  
    Whether or not the remote SSH server supports the newline extension, the remote server sees these transfers as BINARY mode.  
    In all other cases of ASCII mode SSH server-initiated uploads and downloads, SecureTransport cannot identify the correct end-of-line characters to use. SecureTransport performs these transfers in BINARY mode and indicates this on the *File Tracking* page.
-   The name of a file processed by a Folder Monitor transfer site cannot contain two or more of the following characters in sequence: `< > | : ? " * / \ % [ ] ~` (at the beginning of the file only).

**Related topics:**

-   [Transfer mode for server-initiated transfers](../c_st_transfer_mode_for_server-initiated_transfers)
-   [Transfer multiple files](../c_st_transfer_multiple_files)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Outgoing connections](../c_st_outgoing_connections)
-   [Authentication](../r_st_authentication)
-   [Server authentication](../c_st_server_authentication)
-   [Encryption and server-initiated transfers](../c_st_encryption_server-initiated_transfers)
