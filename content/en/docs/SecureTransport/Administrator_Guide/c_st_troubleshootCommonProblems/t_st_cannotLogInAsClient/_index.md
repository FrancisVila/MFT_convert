{
    "title": "Cannot log in as a client",
    "linkTitle": "Cannot log in as a client",
    "weight": "250"
}If you attempt to login to SecureTransport and the login fails despite using a correct user name and password, try the following topics to troubleshoot the problem. Make sure that you check each item in the order listed.

1.  **License Issues** – Verify that the required licenses are installed and current.
2.  **Connection to Server** – Verify that the client system can communicate with the server and that no other client is experiencing a problem.
3.  **Authentication** – Check the LDAP or SiteMinder settings.
4.  **LDAP** – Verify that the LDAP configuration is set correctly.
5.  **Unable to use file system commands such as ls** – make sure that you have plenty of hard drive space available.
6.  **Unable to log in to SecureTransport Edge, but can log in to SecureTransport Server** – Make sure that the certificates for Edge and Server match.
7.  **Client certificate authentication fails** – Make sure that you do not have two Root CA certificates in the "Trusted Certificates" keystore with an identical DN specified.
8.  **Logged in to client with reduced functionality** – Make sure that you are using the required browser and that the required features are installed and enabled.
9.  **Session terminates due to CSRF protection** – Add the client to the white list.

The following topics provide procedures for troubleshooting client log in problems:

-   [License issues](t_st_license_issues) - Provides how-to procedures for troubleshooting license issues.
-   [Connectivity to server failed](t_st_connectivity_to_server_failed) - Provides how-to procedures for troubleshooting connectivity issues.
-   [SiteMinder issues](t_st_siteminder_issues) - Provides how-to procedures for troubleshooting SiteMinder issues.
-   [LDAP issues](c_st_ldap_issues) - Provides how-to procedures for troubleshooting LDAP issues.
-   [File system commands not functional](c_st_file_system_commands_not_functional) - Provides how-to procedures for troubleshooting file system command functionality issues.
-   [Cannot log in to SecureTransport Edge](c_st_cannot_log_edge) - Provides how-to procedures for troubleshooting SecureTransport Edge log in issues.
-   [Client certificate authentication fails](c_st_client_certificate_authentication_fails) - Provides how-to procedures for troubleshooting client certificate authentication issues.
-   [Session terminates due to CSRF protection](c_st_session_terminates_due_to_csrf_protection) - Provides how-to procedures for troubleshooting session termination issues due to CSRF protection.
