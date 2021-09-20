{
    "title": "Define Address Book settings for a domain",
    "linkTitle": "Define Address Book settings for a domain",
    "weight": "380"
}For information on LDAP Address Book sources, refer to [LDAP source](../../../c_st_setup/address_book/ab_sources).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Settings</em> pane is only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>).         </td>
      </tr>
</table>

The following topics define Address Book LDAP searches and attribute mappings for a domain:

-   [Define Address Book LDAP searches for a domain](#define)
-   [Define Address Book attribute mappings for a domain](#define2)

**Related topics:**

-   [Create an LDAP domain](../t_st_create_domain)
-   [Define LDAP search criteria for a domain](../t_st_define_ldap_search_criteria_for_domain)
-   [Define LDAP user settings for a domain](../t_st_define_ldap_user_settings_for_domain)
-   [Define attribute mappings for a domain](../t_st_define_attribute_mappings_for_domain)
-   [Manage DN filters for a domain](../t_st_manage_dn_filters_for_domain)
-   [Manage DN filters](../t_st_add_dn_filter)
-   [Edit a domain](../t_st_edit_domain)
-   [Delete domains](../t_st_delete_domains)
-   [Configure default domains](../t_st_configure_default_domains)
-   [LDAP domains example](../c_st_ldap_domains_example)
-   [Secure LDAP](../c_st_secure_ldap)
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)

## <span id="Define"></span>Define Address Book LDAP searches for a domain

Use the following instructions to configure LDAP search settings for the Address Book feature.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">All search operations performed via this source will be case insensitive and wild card searches will be supported at the end of the phrase; for example, <code>(|(displayName=string*)(ou=string*)(mail=string*))</code>.         </td>
      </tr>
</table>

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click **New Domain** open the *New LDAP Domain* page.

2.  In the *Address Book Settings* pane under *LDAP Searches*, complete the following fields:  
    

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
         <td>Base DN         </td>
         <td>Define the base DN for the searches         </td>
         <td>
            <p>A valid DN, such as, </p>
            <p><code>OU=Sales</code>, <code>DC=ldaps1</code>, <code>DC=Example</code>, <code>DC=com</code></p>
         </td>
      </tr>
      <tr>
         <td> Additional search query         </td>
         <td>
            <p>Enter an LDAP query to specify the  selection criteria for Address Book.  </p>
            <p>The search behavior depends on the current selection of the <strong>Use only additional search query</strong> checkbox:</p>
            <ul>
               <li>If selected,  <span>SecureTransport</span> executes the exact search query  entered in the  <strong>Additional search query</strong> field.               </li>
               <li>If  not selected, <span>SecureTransport</span> applies pre-defined filters that manage the  LDAP server responses to the search query, entered in the  <strong>Additional search query</strong> field, and executes the final query.               </li>
            </ul>
         </td>
         <td>
            <p>Get all user entries with an email attribute and a surname equal to "smith":</p>
            <p><code>&amp;(sn=smith)(objectClass=user)(email=*)</code>
</p>
            <p>Get all entries:</p>
            <p><code>objectclass=*</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

3.  Click **Save**.

## <span id="Define2"></span>Define Address Book attribute mappings for a domain

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Address Book supports only unique group names, so the LDAP server should not have two group entries with exact same value of the attribute which, is mapped to <code>displayName</code>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Address Book classifies an entry as user or group based on the <code>objectClass</code> and <code>objectCategory</code> attribute values.         </td>
      </tr>
</table>

To map an Address Book attribute to a schema:

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click **New Domain** open the *New LDAP Domain* page.
2.  Under *Address Book Attributes List*, for each Address Book attribute that will be mapped from an LDAP domain attribute, select **Map to Schema** to enable an attribute mapping.

You can modify a default attribute mapping.

1.  Click the Edit icon (![Edit](SaveIcon_13x13.png)) in the **Edit** column.
2.  Type the new value in the **LDAP Attribute Name** column.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

You can define a mapping for a custom Address Book attribute.

1.  Click **New Attribute**.  
    SecureTransport adds a line to the *Attributes List*.
2.  Type the **Description**, **Entity Attribute Name**, and **LDAP Attribute Name**.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.
4.  Select **Map to Schema** to enable the mapping.

To delete a custom attribute mapping, click **X** in the first column of the table.