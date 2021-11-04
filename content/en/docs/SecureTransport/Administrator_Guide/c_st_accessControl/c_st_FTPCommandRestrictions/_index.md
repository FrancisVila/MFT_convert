{
    "title": "FTP command restrictions",
    "linkTitle": "FTP command restrictions",
    "weight": "230"
}The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> FTP server uses a number of standard and extended FTP commands. You can restrict individual FTP commands for specified user classes. By default, the page includes entries that allow all listed commands for all users.

To allow an FTP command for some users and restrict it for others, create two or more entries and reorder them so that the more restrictive rule comes before the less restrictive rules.

If your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment includes <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers in a peripheral network (DMZ) and if you need different restrictions for users who connect using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, you can configure FTP command restrictions differently.

The following topics describe the FTP SITE command and the how-to instructions for managing FTP command restrictions:

-   <a href="c_st_ftp_site_command" class="MCXref xref">FTP SITE command</a> - Describes the FTP SITE command.
-   <a href="t_st_ftpcommandrestrictions" class="MCXref xref">Manage FTP command restrictions</a> - Provides how-to instructions for managing FTP command restrictions.
