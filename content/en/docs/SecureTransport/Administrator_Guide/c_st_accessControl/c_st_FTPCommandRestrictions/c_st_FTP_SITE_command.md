{
    "title": "FTP SITE command",
    "linkTitle": "FTP SITE command",
    "weight": "250"
}Some FTP `SITE` commands that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> accepts are handled differently than the other FTP commands. The `SITE VERS`, `SITE AUTH` and `SITE FEAT` commands are not listed even though <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> accepts those commands. Those commands must always be allowed, because <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Secure Client depends on the responses of those commands to determine the capabilities of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> restricts the `SITE HELP` command based on the setting for the `HELP` command.

**Related topic:**

-   <a href="../t_st_ftpcommandrestrictions" class="MCXref xref">Manage FTP command restrictions</a>
