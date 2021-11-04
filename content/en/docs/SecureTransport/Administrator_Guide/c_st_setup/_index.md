{
    "title": "Setup",
    "linkTitle": "Setup",
    "weight": "50"
}The following set of topics provides detailed <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> configuration and setup information:

-   <a href="c_st_certificates" class="MCXref xref">Certificates</a>: types, import and export, generating certificates and certificate signing requests.
-   <a href="c_st_pgpkey" class="MCXref xref">PGP key encryption and signing</a>
-   <a href="c_st_ftpserverconfiguration" class="MCXref xref">Configure FTP server messages and modes</a>
-   <a href="httpserverconfiguration" class="MCXref xref">Configure HTTP server messages</a>
-   <a href="t_st_as2serverconfiguration" class="MCXref xref">Configure AS2 server settings</a>
-   <a href="t_st_administrationtoolserverconfiguration_new" class="MCXref xref">Configure Administration Tool server settings</a>
-   <a href="t_st_pesitserverconfiguration" class="MCXref xref">PeSIT server configuration settings</a>
-   <a href="t_st_adhocconfiguration" class="MCXref xref">Configure adhoc file transfers</a>
-   <a href="c_st_database" class="MCXref xref">Configure your database</a>
-   <a href="c_st_sentinelintegration" class="MCXref xref">Integrate Axway Sentinel</a>
-   <a href="c_st_serverlicenses" class="MCXref xref">Server licenses</a>
-   <a href="t_st_ftpcommandlogconfiguration" class="MCXref xref">Configure FTP command log</a>
-   <a href="t_st_ftpcommandlogconfiguration" class="MCXref xref">Configure FTP command log</a>
-   <a href="t_st_transferlogconfiguration" class="MCXref xref">Configure transfer log</a>
-   <a href="t_st_holidayschedule" class="MCXref xref">Configure holiday schedule</a>
-   <a href="t_st_mailtemplates" class="MCXref xref">Mail templates</a>
-   <a href="c_st_miscellaneousconfiguration" class="MCXref xref">Configure miscellaneous settings</a>
-   <a href="t_st_icap_settings" class="MCXref xref">ICAP settings</a>
-   <a href="c_st_tm_settings" class="MCXref xref">Transaction Manager</a>: import, export, enable, disable rules packages; install agents and functions.
-   <a href="c_st_file_archiving" class="MCXref xref">File archiving</a>
-   <a href="c_st_networkzones" class="MCXref xref">Communication across Transaction Manager, protocol, and proxy servers</a>
-   <a href="t_st_stream_edge_backend" class="MCXref xref">Configure SecureTransport Back End to Edge streaming communication</a>
-   <a href="#" class="MCXref xref">Address Book</a>

## Log in to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool

To log in to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool through a web browser, take the following steps. For a list of supported web browsers, see <a href="../overview/r_st_axway_and_third-party_software_support#Introduction_3964627930_1066167" class="MCXref xref">Axway and third-party software support</a>.

1.  Open the web browser.
2.  Type the URL for the Administration Tool as follows:  
    `https://<host>:port`  
    where `<host>` is the host name, FQDN or IP of the computer running <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and `port` is the administration port number entered during installation. The default port number is 444 for root installations. When <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is installed as non-root, the default port is 8444.
3.  Following the instructions for your browser, add a certificate exception for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> instance if needed.  
    The login page is displayed.
4.  Type the administrator name and password. The default user name is `admin` and the default password is `admin`.
5.  Click **Log In**.

If an error occurs when logging into the Administration Tool, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> prompts you to type the name and password again.

> **Note:**
>
> When using the Administration Tool, make sure that your browser does not block pop-up windows for SecureTransport.

> **Note:**
>
> You cannot open Administration tool in multiple browser tabs/windows that share the same session.

For more information about administrator login, see <a href="../c_st_authentication/c_st_login_settings#Administ" class="MCXref xref">Administrator login options</a> and <a href="../c_st_advancedaccountadministration/c_st_manageadministratoraccounts#Advanced_Accounts_2036285406_1078374" class="MCXref xref">Manage administrator accounts</a>.
