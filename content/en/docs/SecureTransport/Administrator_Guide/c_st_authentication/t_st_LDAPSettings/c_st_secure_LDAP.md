{
    "title": "Secure LDAP",
    "linkTitle": "Secure LDAP",
    "weight": "420"
}For secure communication between <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and an LDAP server to work correctly, a trust must be established between the two parties.

When **Verify Certificate Chain** is selected, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> must trust the CA certificates used to sign the LDAP servers' certificate for encrypted connections. You must add these certificates to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> trusted certificate store. For more information, see <a href="../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#Import" class="MCXref xref">Import a local certificate</a>.

SSL and TLS support have the following limitations based on the SSL protocol and TLS LDAP server implementation:

-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> cannot connect to the i-Planet Directory Server, v5.0 using TLS. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> fails to connect after a few minutes, displays an error message in the client , and makes an entry in its server log.
-   The OpenLDAP server might incorrectly report an error when closing a TLS connection. The TLS connection closes properly even though the error is reported.

**Related topics:**

-   <a href="../t_st_create_domain" class="MCXref xref">Create an LDAP domain</a>
-   <a href="../t_st_define_ldap_search_criteria_for_domain" class="MCXref xref">Define LDAP search criteria for a domain</a>
-   <a href="../t_st_define_ldap_user_settings_for_domain" class="MCXref xref">Define LDAP user settings for a domain</a>
-   <a href="../t_st_define_attribute_mappings_for_domain" class="MCXref xref">Define attribute mappings for a domain</a>
-   <a href="../t_st_manage_dn_filters_for_domain" class="MCXref xref">Manage DN filters for a domain</a>
-   <a href="../t_st_add_dn_filter" class="MCXref xref">Manage DN filters</a>
-   <a href="../t_st_define_ab_settings_for_domain" class="MCXref xref">Define Address Book settings for a domain</a>
-   <a href="../t_st_edit_domain" class="MCXref xref">Edit a domain</a>
-   <a href="../t_st_delete_domains" class="MCXref xref">Delete domains</a>
-   <a href="../t_st_configure_default_domains" class="MCXref xref">Configure default domains</a>
-   <a href="../c_st_ldap_domains_example" class="MCXref xref">LDAP domains example</a>
-   <a href="../c_st_ldap_active_directory_configuration" class="MCXref xref">LDAP and Active Directory configuration</a>
