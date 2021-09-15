{
    "title": "Define LDAP user settings for a domain",
    "linkTitle": "Define LDAP user settings for a domain",
    "weight": "340"
}SecureTransport uses these default values when the LDAP entry does not include the attribute and no mapping to the attribute is enabled in the *Default Attributes List*. For information, see [LDAP logins](../../c_st_ldap_logins).

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click the domain name in the Domains List to open the *LDAP Domain* page.

2.  Under *LDAP User Settings*, complete the following fields:  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
         <th>Valid values and notes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Default GID         </td>
         <td>The value for the <code>fdxGid</code> attribute (group ID) for the LDAP user.         </td>
         <td>
            <p>The default value is 10000.</p>
         </td>
      </tr>
      <tr>
         <td>Default UID         </td>
         <td>The value for the <code>fdxUid</code> attribute (user ID) for the LDAP user.         </td>
         <td>
            <p>UNIX-based systems only.</p>
            <p>The default value is 10000.</p>
         </td>
      </tr>
      <tr>
         <td>Default User Shell         </td>
         <td>The value for the <code>fdxShell</code> attribute (user shell) for the LDAP user.         </td>
         <td>
            <p>UNIX-based systems only.</p>
            <p>Valid user shell. The default value is <code>/bin/sh</code>.</p>
         </td>
      </tr>
      <tr>
         <td>Default User Type         </td>
         <td>The value for the <code>fdxUserType</code> attribute (user type) for the LDAP user.         </td>
         <td>
            <p><code>Real</code> or <code>Virtual</code>. The default value is <code>Virtual</code>.</p>
         </td>
      </tr>
      <tr>
         <td>Allow login by email         </td>
         <td>Controls whether the user can log in using an email address stored in the email attribute of the LDAP record.         </td>
         <td><code>Enabled</code> or <code>Disabled</code>. The default value is <code>Disabled</code>.         </td>
      </tr>
   </tbody>
</table>

3.  Click **Save**.

**Related topics:**

-   [Create an LDAP domain](../t_st_create_domain)
-   [Define LDAP search criteria for a domain](../t_st_define_ldap_search_criteria_for_domain)
-   [Define attribute mappings for a domain](../t_st_define_attribute_mappings_for_domain)
-   [Manage DN filters for a domain](../t_st_manage_dn_filters_for_domain)
-   [Manage DN filters](../t_st_add_dn_filter)
-   [Define Address Book settings for a domain](../t_st_define_ab_settings_for_domain)
-   [Edit a domain](../t_st_edit_domain)
-   [Delete domains](../t_st_delete_domains)
-   [Configure default domains](../t_st_configure_default_domains)
-   [LDAP domains example](../c_st_ldap_domains_example)
-   [Secure LDAP](../c_st_secure_ldap)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)
