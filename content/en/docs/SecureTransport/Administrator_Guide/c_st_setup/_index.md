{
    "title": "Setup",
    "linkTitle": "Setup",
    "weight": "60"
}The following set of topics provides detailed SecureTransport configuration and setup information:

-   [Certificates](c_st_certificates): types, import and export, generating certificates and certificate signing requests.
-   [PGP key encryption and signing](c_st_pgpkey)
-   [Configure FTP server messages and modes](c_st_ftpserverconfiguration)
-   [Configure HTTP server messages](httpserverconfiguration)
-   [Configure AS2 server settings](t_st_as2serverconfiguration)
-   [Configure Administration Tool server settings](t_st_administrationtoolserverconfiguration_new)
-   [PeSIT server configuration settings](t_st_pesitserverconfiguration)
-   [Configure adhoc file transfers](t_st_adhocconfiguration)
-   [Configure your database](c_st_database)
-   [Integrate Axway Sentinel](c_st_sentinelintegration)
-   [Server licenses](c_st_serverlicenses)
-   [Configure FTP command log](t_st_ftpcommandlogconfiguration)
-   [Configure FTP command log](t_st_ftpcommandlogconfiguration)
-   [Configure transfer log](t_st_transferlogconfiguration)
-   [Configure holiday schedule](t_st_holidayschedule)
-   [Mail templates](t_st_mailtemplates)
-   [Configure miscellaneous settings](c_st_miscellaneousconfiguration)
-   [ICAP settings](t_st_icap_settings)
-   [Transaction Manager](c_st_tm_settings): import, export, enable, disable rules packages; install agents and functions.
-   [File archiving](c_st_file_archiving)
-   [Communication across Transaction Manager, protocol, and proxy servers](c_st_networkzones)
-   [Configure SecureTransport Back End to Edge streaming communication](t_st_stream_edge_backend)
-   [Address Book](address_book)

## Log in to the SecureTransport Administration Tool

To log in to the SecureTransport Administration Tool through a web browser, take the following steps. For a list of supported web browsers, see [Axway and third-party software support](../overview5/r_st_axway_and_third-party_software_support).

1.  Open the web browser.
2.  Type the URL for the Administration Tool as follows:  
    `https://<host>:port`
      
    where `<host>` is the host name, FQDN or IP of the computer running SecureTransport and `port` is the administration port number entered during installation. The default port number is 444 for root installations. When SecureTransport is installed as non-root, the default port is 8444.
3.  Following the instructions for your browser, add a certificate exception for the SecureTransport instance if needed.  
    The login page is displayed.
4.  Type the administrator name and password. The default user name is `admin` and the default password is `admin`.
5.  Click **Log In**.

If an error occurs when logging into the Administration Tool, SecureTransport prompts you to type the name and password again.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using the Administration Tool, make sure that your browser does not block pop-up windows for <span>SecureTransport</span>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot open Administration tool in multiple browser tabs/windows that share the same session.         </td>
      </tr>
</table>

For more information about administrator login, see [Administrator login options](../c_st_authentication/c_st_login_settings) and [Manage administrator accounts](../c_st_advancedaccountadministration/c_st_manageadministratoraccounts).
