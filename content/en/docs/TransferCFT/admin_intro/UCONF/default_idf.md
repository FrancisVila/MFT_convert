{
    "title": "Deactivate the default IDF ",
    "linkTitle": "Deactivating the default IDF",
    "weight": "340"
}You can deactivate the usage of the default IDF defined in CFTPARM that is used when the IDF in SEND or RECV commands does not exist. In this case, transfers that use nonexistent IDFs will end in error.

To disable the use of the default IDF, set the UCONF value: <span class="code">cft.default\_idf.enable=no</span>

This value is taken into account after issuing a <span class="code">reconfig </span>command or a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> restart.
