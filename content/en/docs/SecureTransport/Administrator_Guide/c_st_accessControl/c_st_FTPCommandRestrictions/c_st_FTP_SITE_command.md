{
    "title": "FTP SITE command",
    "linkTitle": "FTP SITE command",
    "weight": "260"
}Some FTP `SITE` commands that SecureTransport accepts are handled differently than the other FTP commands. The `SITE VERS`, `SITE AUTH` and `SITE FEAT` commands are not listed even though SecureTransport accepts those commands. Those commands must always be allowed, because Axway Secure Client depends on the responses of those commands to determine the capabilities of SecureTransport Server. SecureTransport restricts the `SITE HELP` command based on the setting for the `HELP` command.

**Related topic:**

-   [Manage FTP command restrictions](../t_st_ftpcommandrestrictions)
