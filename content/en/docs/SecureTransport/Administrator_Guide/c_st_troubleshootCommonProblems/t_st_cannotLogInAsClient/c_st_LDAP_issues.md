{
    "title": "LDAP issues",
    "linkTitle": "LDAP issues",
    "weight": "290"
}Common LDAP problems are incorrect LDAP configuration, incorrect service account credentials, and an inability to access LDAP through the firewall. Check the following setting in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool to troubleshoot problems:

-   Make sure that the credentials LDAP can search through are correct for each user unable to login from the client. If the users are connecting to an Active Directory (AD) LDAP server, the Bind DN and Password need to be specified. AD does not allow anonymous binds. Verify that the user has the correct user name and password and is entering the correct information into the client.
-   For Windows-based systems, make sure that the LDAP SysUser is set correctly to a local or domain user that has the necessary permissions on the directory. The LDAP SysUser must be present in the password vault.
-   Make sure that the correct LDAP port, generally 389 or 3268, is available to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> in the firewall.
-   Check that for each LDAP-based user, the settings allow the user to obtain the UID/GID (UNIX-based systems only), user type, and home directory either from the LDAP directory (using attribute mapping) or through the user defaults. Make sure that the user home directory exists and has the correct permissions. You can set up a login agent for this purpose.
-   Make sure that you use the correct LDAP Protocol version, and the LDAP server is the same version as the one selected in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool on the *LDAP Server* page.
-   Try using the `ldapsearch` command from the command line. If the command fails, you might have an incorrect search query or insufficient credentials.
-   If you are not using attribute mapping, make sure that the home directory exists in the LDAP User Default and that the entry is enabled. For more information, see <a href="../../../c_st_authentication/c_st_ldap_logins#LDAP" class="MCXref xref">LDAP logins</a>.

**Related topics:**

-   <a href="../t_st_license_issues" class="MCXref xref">License issues</a>
-   <a href="../t_st_connectivity_to_server_failed" class="MCXref xref">Connectivity to server failed</a>
-   <a href="../t_st_siteminder_issues" class="MCXref xref">SiteMinder issues</a>
-   <a href="../c_st_file_system_commands_not_functional" class="MCXref xref">File system commands not functional</a>
-   <a href="../c_st_cannot_log_edge" class="MCXref xref">Cannot log in to SecureTransport Edge</a>
-   <a href="../c_st_client_certificate_authentication_fails" class="MCXref xref">Client certificate authentication fails</a>
-   <a href="../c_st_session_terminates_due_to_csrf_protection" class="MCXref xref">Session terminates due to CSRF protection</a>
