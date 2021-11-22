{
    "title": "FTP SITE command",
    "linkTitle": "FTP SITE command",
    "weight": "250"
}Some FTP `SITE` commands that {{< SecureTransport/componentshortname  >}} accepts are handled differently than the other FTP commands. The `SITE VERS`, `SITE AUTH` and `SITE FEAT` commands are not listed even though {{< SecureTransport/componentshortname  >}} accepts those commands. Those commands must always be allowed, because {{< SecureTransport/companyname  >}} Secure Client depends on the responses of those commands to determine the capabilities of {{< SecureTransport/componentshortname  >}} Server. {{< SecureTransport/componentshortname  >}} restricts the `SITE HELP` command based on the setting for the `HELP` command.

**Related topic:**

-   <a href="../t_st_ftpcommandrestrictions" class="MCXref xref">Manage FTP command restrictions</a>
