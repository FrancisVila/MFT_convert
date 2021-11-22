{
    "title": "LDAP and Active Directory configuration",
    "linkTitle": "LDAP and Active Directory configuration",
    "weight": "430"
}If you use LDAP with Active Directory, you must consider the following requirements for the LDAP server configuration in {{< SecureTransport/componentshortname  >}}:

-   Under LDAP Searches:
    -   Specify a CN value in the **Base DN** field (for example, `cn=users`). The CN value is required for {{< SecureTransport/componentshortname >}} LDAP authentication to work, even though the OpenLDAP `ldapsearch` command generically does not require it when run from a command line interface.
    -   Select **Common Name (cn)** or **SAM-Account-Name (sAMAccountName)** for the **Search Attribute**. Use the SAM-Account-Name parameter instead of the CN parameter to log in using the Windows domain login name.
-   TLS is only supported in Windows Server 2003 Active Directory or later.
-   Disable **Anonymous Binds**.

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
-   <a href="../c_st_secure_ldap" class="MCXref xref">Secure LDAP</a>
