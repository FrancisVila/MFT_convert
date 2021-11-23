{
    "title": "Client certificate authentication fails",
    "linkTitle": "Client certificate authentication fails",
    "weight": "320"
}If you have two Root CA certificates in the "Trusted Certificates" keystore with an identical DN specified, you might not be able to log into {{< SecureTransport/componentshortname  >}}. {{< SecureTransport/componentshortname  >}} searches for the first certificate that matches the DN of the Certificate Authority. If a match is found, then {{< SecureTransport/componentshortname  >}} does not continue to search. When two or more CA certificates with the same DN exist, the correct CA might never be selected.

Make sure that all CA certificates have unique DN values.

**Related topics:**

-   [License issues](../t_st_license_issues)
-   [Connectivity to server failed](../t_st_connectivity_to_server_failed)
-   [SiteMinder issues](../t_st_siteminder_issues)
-   [LDAP issues](../c_st_ldap_issues)
-   [File system commands not functional](../c_st_file_system_commands_not_functional)
-   [Cannot log in to SecureTransport Edge](../c_st_cannot_log_edge)
-   [Session terminates due to CSRF protection](../c_st_session_terminates_due_to_csrf_protection)
