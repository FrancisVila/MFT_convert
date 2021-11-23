{
    "title": "Secure LDAP",
    "linkTitle": "Secure LDAP",
    "weight": "420"
}For secure communication between {{< SecureTransport/componentshortname  >}} and an LDAP server to work correctly, a trust must be established between the two parties.

When **Verify Certificate Chain** is selected, {{< SecureTransport/componentshortname  >}} must trust the CA certificates used to sign the LDAP servers' certificate for encrypted connections. You must add these certificates to the {{< SecureTransport/componentshortname  >}} trusted certificate store. For more information, see [Import a local certificate](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#Import).

SSL and TLS support have the following limitations based on the SSL protocol and TLS LDAP server implementation:

-   {{< SecureTransport/componentshortname >}} cannot connect to the i-Planet Directory Server, v5.0 using TLS. {{< SecureTransport/componentshortname >}} fails to connect after a few minutes, displays an error message in the client , and makes an entry in its server log.
-   The OpenLDAP server might incorrectly report an error when closing a TLS connection. The TLS connection closes properly even though the error is reported.

**Related topics:**

-   [Create an LDAP domain](../t_st_create_domain)
-   [Define LDAP search criteria for a domain](../t_st_define_ldap_search_criteria_for_domain)
-   [Define LDAP user settings for a domain](../t_st_define_ldap_user_settings_for_domain)
-   [Define attribute mappings for a domain](../t_st_define_attribute_mappings_for_domain)
-   [Manage DN filters for a domain](../t_st_manage_dn_filters_for_domain)
-   [Manage DN filters](../t_st_add_dn_filter)
-   [Define Address Book settings for a domain](../t_st_define_ab_settings_for_domain)
-   [Edit a domain](../t_st_edit_domain)
-   [Delete domains](../t_st_delete_domains)
-   [Configure default domains](../t_st_configure_default_domains)
-   [LDAP domains example](../c_st_ldap_domains_example)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)
