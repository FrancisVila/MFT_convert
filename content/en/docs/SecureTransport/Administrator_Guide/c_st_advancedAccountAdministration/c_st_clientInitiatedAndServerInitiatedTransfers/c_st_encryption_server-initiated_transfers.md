{
    "title": "Encryption and server-initiated transfers",
    "linkTitle": "Encryption and server-initiated transfers",
    "weight": "330"
}When {{< SecureTransport/componentshortname  >}} performs server-initiated transfers, it defines user classes by UID and GID only – no user name is specified. As a result, if you use `EncryptClass` for encrypting or decrypting transferred files and `EncryptClass` is defined only by user name, the following is true:

-   Encrypted files transferred using a server-initiated upload are decrypted before the start of the transfer.
-   Files transferred using a server-initiated download are transferred with encryption.

**Related topics:**

-   [Transfer mode for server-initiated transfers](../c_st_transfer_mode_for_server-initiated_transfers)
-   [Transfer multiple files](../c_st_transfer_multiple_files)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Outgoing connections](../c_st_outgoing_connections)
-   [Authentication](../r_st_authentication)
-   [Server authentication](../c_st_server_authentication)
-   [Limitations](../c_st_limitations)
