{
    "title": "License issues",
    "linkTitle": "License issues",
    "weight": "260"
}If you get an error indicating that the license is expired or that there is no license available for ad hoc users, verify that the license is installed and within the validity period. Use the following procedure to verify that your license is still valid.

To view server licenses:

1.  Open the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool and select **Setup > Server License**.
2.  Verify that the license is installed and not expired by checking the **Core Server License** for the FTP and HTTP servers, user accounts, and ad hoc users and the **Features License** for AS2, SSH, and Connect:Direct protocols and the SiteMinder feature.
3.  If your license has passed the expiration date, contact <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Global Support to renew it. For details, see <a href="##top" class="MCXref xref">Get more help</a>.

For each license type, the validity period is given in the **Valid from** and **Valid to** fields. Check the following items if your license is valid.

-   Make sure that you are using the correct IP address to connect to the server from the client.
-   Make sure that your server’s clock is set correctly.
-   If you experience a license error, log in to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool, select **Operations > Server Log**, and look in the following log entries for the exact error code and description.
    -   AS2: AS2D
    -   FTP or FTPS logins (secure or nonsecure): FTPD
    -   HTTP or HTTPS logins: HTTPD
    -   PeSIT transfer: TM
    -   SiteMinder: TM
    -   SSH: SSHD
    -   Transaction Manager: TM

**Related topics:**

-   <a href="../t_st_connectivity_to_server_failed" class="MCXref xref">Connectivity to server failed</a>
-   <a href="../t_st_siteminder_issues" class="MCXref xref">SiteMinder issues</a>
-   <a href="../c_st_ldap_issues" class="MCXref xref">LDAP issues</a>
-   <a href="../c_st_file_system_commands_not_functional" class="MCXref xref">File system commands not functional</a>
-   <a href="../c_st_cannot_log_edge" class="MCXref xref">Cannot log in to SecureTransport Edge</a>
-   <a href="../c_st_client_certificate_authentication_fails" class="MCXref xref">Client certificate authentication fails</a>
-   <a href="../c_st_session_terminates_due_to_csrf_protection" class="MCXref xref">Session terminates due to CSRF protection</a>
