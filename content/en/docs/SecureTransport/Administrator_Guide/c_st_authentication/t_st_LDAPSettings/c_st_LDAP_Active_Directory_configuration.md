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
-   [Secure LDAP](../c_st_secure_ldap)
