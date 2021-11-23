{
    "title": "LDAP domains example",
    "linkTitle": "LDAP domains example",
    "weight": "410"
}This example illustrates a scenario with three LDAP domains, one each for Engineering, Operations, and Security. The configuration has the following features:

-   Each domain has a primary LDAP server and backup LDAP server.
-   The Engineering and Operations domains are default domains. Users with login credentials in those LDAP databases do not need to specify a domain to log in.
-   The Engineering domain is searched first. Users who have the same login credentials in both the Engineering and Operations domain will get the attributes stored in the entry in the Engineering domain unless they specify the Operations domain when they log in.
-   The Security domain is not a default domain. Users with login credentials in the Security domain LDAP database must specify a domain name to log in.

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
-   [Secure LDAP](../c_st_secure_ldap)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)
