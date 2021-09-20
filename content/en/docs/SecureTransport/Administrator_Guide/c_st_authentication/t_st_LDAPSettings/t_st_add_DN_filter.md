{
    "title": "Manage DN filters",
    "linkTitle": "Manage DN filters",
    "weight": "370"
}The following topics describe how to manage DN filters:

-   [Add a DN filter](#add)
-   [Enable or disable a DN filter](#enable)
-   [Edit a DN filter](#edit)
-   [Delete a DN filter](#delete)

**Related topics:**

-   [Create an LDAP domain](../t_st_create_domain)
-   [Define LDAP search criteria for a domain](../t_st_define_ldap_search_criteria_for_domain)
-   [Define LDAP user settings for a domain](../t_st_define_ldap_user_settings_for_domain)
-   [Define attribute mappings for a domain](../t_st_define_attribute_mappings_for_domain)
-   [Manage DN filters for a domain](../t_st_manage_dn_filters_for_domain)
-   [Define Address Book settings for a domain](../t_st_define_ab_settings_for_domain)
-   [Edit a domain](../t_st_edit_domain)
-   [Delete domains](../t_st_delete_domains)
-   [Configure default domains](../t_st_configure_default_domains)
-   [LDAP domains example](../c_st_ldap_domains_example)
-   [Secure LDAP](../c_st_secure_ldap)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)

## <span id="Add"></span>Add a DN filter

Use the following procedure to add a DN filter.

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click the domain name in the Domains List to open the *LDAP Domain* page.
2.  Under *DN Filter List*, click **New Filter**.  
    A line is added to the *DN Filters List*.
3.  In the **DN Filter** field, type a regular expression to match against the DN retrieved from the LDAP database. To specify only a portion of a DN, use wild cards. For example, to allow access to users from the organization acme, enter`.*O=acme.*` in this field. For more information about regular expressions supported by SecureTransport, see [Regular expressions](../../../c_st_regularexpressions).
4.  In the **User Class** field, select a user class to apply the DN filter only to users in that class or asterisk (`*`) to apply the DN filter to all users.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

The status of the new DN filter is Disabled.

## <span id="Enable"></span>Enable or disable a DN filter

Use the following procedure to enable or disable a DN filter.

-   In the entry in the *DN Filter List*, click **Enable** or **Disable**.  
    The Status column is updated.

## <span id="Edit"></span>Edit a DN filter

Use the following procedure to edit a DN filter.

1.  In an entry in the *DN Filter List*, click the Edit icon (![Edit](SaveIcon_13x13.png)) in the **Edit** column.
2.  Make the required changes to the fields in the entry.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

## <span id="Delete"></span>Delete a DN filter

Use the following procedure to delete a DN filter.

-   In the entry in the *DN Filter List*, click **X** in the first column.  
    The entry is removed from the list.
