{
    "title": "License issues",
    "linkTitle": "License issues",
    "weight": "260"
}If you get an error indicating that the license is expired or that there is no license available for ad hoc users, verify that the license is installed and within the validity period. Use the following procedure to verify that your license is still valid.

To view server licenses:

1.  Open the {{< SecureTransport/componentshortname >}} Administration Tool and select **Setup > Server License**.
2.  Verify that the license is installed and not expired by checking the **Core Server License** for the FTP and HTTP servers, user accounts, and ad hoc users and the **Features License** for AS2, SSH, and Connect:Direct protocols and the SiteMinder feature.
3.  If your license has passed the expiration date, contact {{< SecureTransport/companyname >}} Global Support to renew it. For details, see [Get more help](#top).

For each license type, the validity period is given in the **Valid from** and **Valid to** fields. Check the following items if your license is valid.

-   Make sure that you are using the correct IP address to connect to the server from the client.
-   Make sure that your server’s clock is set correctly.
-   If you experience a license error, log in to the {{< SecureTransport/componentshortname >}} Administration Tool, select **Operations > Server Log**, and look in the following log entries for the exact error code and description.
    -   AS2: AS2D
    -   FTP or FTPS logins (secure or nonsecure): FTPD
    -   HTTP or HTTPS logins: HTTPD
    -   PeSIT transfer: TM
    -   SiteMinder: TM
    -   SSH: SSHD
    -   Transaction Manager: TM

**Related topics:**

-   [Connectivity to server failed](../t_st_connectivity_to_server_failed)
-   [SiteMinder issues](../t_st_siteminder_issues)
-   [LDAP issues](../c_st_ldap_issues)
-   [File system commands not functional](../c_st_file_system_commands_not_functional)
-   [Cannot log in to SecureTransport Edge](../c_st_cannot_log_edge)
-   [Client certificate authentication fails](../c_st_client_certificate_authentication_fails)
-   [Session terminates due to CSRF protection](../c_st_session_terminates_due_to_csrf_protection)
