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
-   <a href="../c_st_secure_ldap" class="MCXref xref">Secure LDAP</a>
-   <a href="../c_st_ldap_active_directory_configuration" class="MCXref xref">LDAP and Active Directory configuration</a>
