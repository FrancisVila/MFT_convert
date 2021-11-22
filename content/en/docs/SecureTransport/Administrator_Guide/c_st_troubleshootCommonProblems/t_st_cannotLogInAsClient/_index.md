{
    "title": "Cannot log in as a client",
    "linkTitle": "Cannot log in as a client",
    "weight": "240"
}If you attempt to login to {{< SecureTransport/componentshortname  >}} and the login fails despite using a correct user name and password, try the following topics to troubleshoot the problem. Make sure that you check each item in the order listed.

1.  **License Issues** – Verify that the required licenses are installed and current.
2.  **Connection to Server** – Verify that the client system can communicate with the server and that no other client is experiencing a problem.
3.  **Authentication** – Check the LDAP or SiteMinder settings.
4.  **LDAP** – Verify that the LDAP configuration is set correctly.
5.  **Unable to use file system commands such as ls** – make sure that you have plenty of hard drive space available.
6.  **Unable to log in to {{< SecureTransport/componentshortname >}} Edge, but can log in to {{< SecureTransport/componentshortname >}} Server** – Make sure that the certificates for Edge and Server match.
7.  **Client certificate authentication fails** – Make sure that you do not have two Root CA certificates in the "Trusted Certificates" keystore with an identical DN specified.
8.  **Logged in to client with reduced functionality** – Make sure that you are using the required browser and that the required features are installed and enabled.
9.  **Session terminates due to CSRF protection** – Add the client to the white list.

The following topics provide procedures for troubleshooting client log in problems:

-   <a href="t_st_license_issues" class="MCXref xref">License issues</a> - Provides how-to procedures for troubleshooting license issues.
-   <a href="t_st_connectivity_to_server_failed" class="MCXref xref">Connectivity to server failed</a> - Provides how-to procedures for troubleshooting connectivity issues.
-   <a href="t_st_siteminder_issues" class="MCXref xref">SiteMinder issues</a> - Provides how-to procedures for troubleshooting SiteMinder issues.
-   <a href="c_st_ldap_issues" class="MCXref xref">LDAP issues</a> - Provides how-to procedures for troubleshooting LDAP issues.
-   <a href="c_st_file_system_commands_not_functional" class="MCXref xref">File system commands not functional</a> - Provides how-to procedures for troubleshooting file system command functionality issues.
-   <a href="c_st_cannot_log_edge" class="MCXref xref">Cannot log in to SecureTransport Edge</a> - Provides how-to procedures for troubleshooting {{< SecureTransport/componentshortname >}} Edge log in issues.
-   <a href="c_st_client_certificate_authentication_fails" class="MCXref xref">Client certificate authentication fails</a> - Provides how-to procedures for troubleshooting client certificate authentication issues.
-   <a href="c_st_session_terminates_due_to_csrf_protection" class="MCXref xref">Session terminates due to CSRF protection</a> - Provides how-to procedures for troubleshooting session termination issues due to CSRF protection.
