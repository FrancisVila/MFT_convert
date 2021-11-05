{
    "title": "Define Address Book settings for a domain",
    "linkTitle": "Define Address Book settings for a domain",
    "weight": "370"
}For information on LDAP Address Book sources, refer to <a href="#LDAP" class="MCXref xref">LDAP source</a>.

> **Note:**
>
> The Address Book Settings pane is only displayed if the Address Book feature is enabled (the value of the AddressBook.Enabled configuration option is set to true).

The following topics define Address Book LDAP searches and attribute mappings for a domain:

-   <a href="#Define" class="MCXref xref">Define Address Book LDAP searches for a domain</a>
-   <a href="#Define2" class="MCXref xref">Define Address Book attribute mappings for a domain</a>

**Related topics:**

-   <a href="../t_st_create_domain" class="MCXref xref">Create an LDAP domain</a>
-   <a href="../t_st_define_ldap_search_criteria_for_domain" class="MCXref xref">Define LDAP search criteria for a domain</a>
-   <a href="../t_st_define_ldap_user_settings_for_domain" class="MCXref xref">Define LDAP user settings for a domain</a>
-   <a href="../t_st_define_attribute_mappings_for_domain" class="MCXref xref">Define attribute mappings for a domain</a>
-   <a href="../t_st_manage_dn_filters_for_domain" class="MCXref xref">Manage DN filters for a domain</a>
-   <a href="../t_st_add_dn_filter" class="MCXref xref">Manage DN filters</a>
-   <a href="../t_st_edit_domain" class="MCXref xref">Edit a domain</a>
-   <a href="../t_st_delete_domains" class="MCXref xref">Delete domains</a>
-   <a href="../t_st_configure_default_domains" class="MCXref xref">Configure default domains</a>
-   <a href="../c_st_ldap_domains_example" class="MCXref xref">LDAP domains example</a>
-   <a href="../c_st_secure_ldap" class="MCXref xref">Secure LDAP</a>
-   <a href="../c_st_ldap_active_directory_configuration" class="MCXref xref">LDAP and Active Directory configuration</a>

<span id="Define"></span>

## Define Address Book LDAP searches for a domain

Use the following instructions to configure LDAP search settings for the Address Book feature.

> **Note:**
>
> All search operations performed via this source will be case insensitive and wild card searches will be supported at the end of the phrase; for example, (|(displayName=string\*)(ou=string\*)(mail=string\*)).

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click **New Domain** open the *New LDAP Domain* page.
2.  In the *Address Book Settings* pane under *LDAP Searches*, complete the following fields:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadE-Column1-Header1">Description         </th>
    <th class="HeadD-Column1-Header1">Valid values and notes         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>Base DN         </td>
             <td>Define the base DN for the searches         </td>
             <td><p>A valid DN, such as,</p>
    <p><code>OU=Sales</code>, <code>DC=ldaps1</code>, <code>DC=Example</code>, <code>DC=com</code></p>         </td>
          </tr>
          <tr>
             <td>Additional search query         </td>
             <td><p>Enter an LDAP query to specify the selection criteria for Address Book.</p>
    <p>The search behavior depends on the current selection of the <strong>Use only additional search query</strong> checkbox:</p>
    <ul>
    <li>If selected, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> executes the exact search query entered in the <strong>Additional search query</strong> field.</li>
    <li>If not selected, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> applies pre-defined filters that manage the LDAP server responses to the search query, entered in the <strong>Additional search query</strong> field, and executes the final query.</li>
    </ul>         </td>
             <td><p>Get all user entries with an email attribute and a surname equal to "smith":</p>
    <p><code>&amp;(sn=smith)(objectClass=user)(email=*)</code></p>
    <p>Get all entries:</p>
    <p><code>objectclass=*</code></p>         </td>
          </tr>
       </tbody>
    </table>
3.  Click **Save**.

<span id="Define2"></span>

## Define Address Book attribute mappings for a domain

> **Note:**
>
> Address Book supports only unique group names, so the LDAP server should not have two group entries with exact same value of the attribute which, is mapped to displayName.

> **Note:**
>
> Address Book classifies an entry as user or group based on the objectClass and objectCategory attribute values.

To map an Address Book attribute to a schema:

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click **New Domain** open the *New LDAP Domain* page.
2.  Under *Address Book Attributes List*, for each Address Book attribute that will be mapped from an LDAP domain attribute, select **Map to Schema** to enable an attribute mapping.

You can modify a default attribute mapping.

1.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column.
2.  Type the new value in the **LDAP Attribute Name** column.
3.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

You can define a mapping for a custom Address Book attribute.

1.  Click **New Attribute**.  
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> adds a line to the *Attributes List*.
2.  Type the **Description**, **Entity Attribute Name**, and **LDAP Attribute Name**.
3.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.
4.  Select **Map to Schema** to enable the mapping.

To delete a custom attribute mapping, click **X** in the first column of the table.
