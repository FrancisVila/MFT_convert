{
    "title": "Encryption and server-initiated transfers",
    "linkTitle": "Encryption and server-initiated transfers",
    "weight": "330"
}When <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> performs server-initiated transfers, it defines user classes by UID and GID only – no user name is specified. As a result, if you use `EncryptClass` for encrypting or decrypting transferred files and `EncryptClass` is defined only by user name, the following is true:

-   Encrypted files transferred using a server-initiated upload are decrypted before the start of the transfer.
-   Files transferred using a server-initiated download are transferred with encryption.

**Related topics:**

-   <a href="../c_st_transfer_mode_for_server-initiated_transfers" class="MCXref xref">Transfer mode for server-initiated transfers</a>
-   <a href="../c_st_transfer_multiple_files" class="MCXref xref">Transfer multiple files</a>
-   <a href="../c_st_configure_retry_parameters_for_server-initiated_transfers" class="MCXref xref">Configure retry parameters for server-initiated transfers</a>
-   <a href="../c_st_outgoing_connections" class="MCXref xref">Outgoing connections</a>
-   <a href="../r_st_authentication" class="MCXref xref">Authentication</a>
-   <a href="../c_st_server_authentication" class="MCXref xref">Server authentication</a>
-   <a href="../c_st_limitations" class="MCXref xref">Limitations</a>
