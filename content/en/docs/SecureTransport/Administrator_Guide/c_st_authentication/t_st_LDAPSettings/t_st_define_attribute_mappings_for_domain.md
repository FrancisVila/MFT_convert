{
    "title": "Define attribute mappings for a domain",
    "linkTitle": "Define attribute mappings for a domain",
    "weight": "350"
}For information about how SecureTransport uses the default attribute mappings, see [LDAP logins](../../c_st_ldap_logins).

The session variables available depend on the attribute mappings:

-   The following session variables are always available: `STSESSION_LDAP_AUTH_BY_EMAIL`, `STSESSION_LDAP_DN, STSESSION_LDAP_DOMAIN_ID`, and `STSESSION_LDAP_DOMAIN_NAME`.
-   To enable `STSESSION_LDAP_fdxGid`, `STSESSION_LDAP_fdxHomeDir`, `STSESSION_LDAP_fdxShell`, `STSESSION_LDAP_fdxUid`, and `STSESSION_LDAP_fdxUserType`, select **Map to Schema** for the corresponding default attribute.
-   If you do not select **Map to Schema** for any custom mappings, all LDAP attributes are mapped to session variables named `LDAP_DIR_` followed by the attribute name.
-   If you add a custom mapping, only those attributes added with **Map to Schema** selected are mapped to session variables named `LDAP_DIR_` followed by the attribute name.

A multivalued LDAP attribute is mapped to several session variables. To use a multivalued LDAP variable, map it and check the SecureTransport session for the names of the session variables.

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click the domain name in the Domains List to open the *LDAP Domain* page.
2.  Under *Attributes List*, for each SecureTransport attribute that will be mapped from an LDAP attribute, select **Map to Schema** to enable an attribute mapping.

You can modify a default attribute mapping.

1.  Click the Edit icon (![Edit](SaveIcon_13x13.png)) in the **Edit** column.
2.  Type the new value in the **LDAP Attribute Name** column.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

You can define a mapping for a custom LDAP attribute.

1.  Click **New Attribute**.  
    SecureTransport adds a line to the *Attributes List*.
2.  Type the **Description**, **ST Attribute Name**, and **LDAP Attribute Name**.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.
4.  Select **Map to Schema** to enable the mapping.

To delete a custom attribute mapping, click **X** in the first column of the table.

**Related topics:**

-   [Create an LDAP domain](../t_st_create_domain)
-   [Define LDAP search criteria for a domain](../t_st_define_ldap_search_criteria_for_domain)
-   [Define LDAP user settings for a domain](../t_st_define_ldap_user_settings_for_domain)
-   [Manage DN filters for a domain](../t_st_manage_dn_filters_for_domain)
-   [Manage DN filters](../t_st_add_dn_filter)
-   [Define Address Book settings for a domain](../t_st_define_ab_settings_for_domain)
-   [Edit a domain](../t_st_edit_domain)
-   [Delete domains](../t_st_delete_domains)
-   [Configure default domains](../t_st_configure_default_domains)
-   [LDAP domains example](../c_st_ldap_domains_example)
-   [Secure LDAP](../c_st_secure_ldap)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)