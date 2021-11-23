{
    "title": "FTP command restrictions",
    "linkTitle": "FTP command restrictions",
    "weight": "230"
}The {{< SecureTransport/componentshortname  >}} FTP server uses a number of standard and extended FTP commands. You can restrict individual FTP commands for specified user classes. By default, the page includes entries that allow all listed commands for all users.

To allow an FTP command for some users and restrict it for others, create two or more entries and reorder them so that the more restrictive rule comes before the less restrictive rules.

If your {{< SecureTransport/componentshortname  >}} deployment includes {{< SecureTransport/componentshortname  >}} Edge servers in a peripheral network (DMZ) and if you need different restrictions for users who connect using {{< SecureTransport/componentshortname  >}} Edge and using {{< SecureTransport/componentshortname  >}} Server, you can configure FTP command restrictions differently.

The following topics describe the FTP SITE command and the how-to instructions for managing FTP command restrictions:

-   [FTP SITE command](c_st_ftp_site_command) - Describes the FTP SITE command.
-   [Manage FTP command restrictions](t_st_ftpcommandrestrictions) - Provides how-to instructions for managing FTP command restrictions.
