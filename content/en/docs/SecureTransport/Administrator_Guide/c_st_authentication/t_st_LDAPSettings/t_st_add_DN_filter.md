{
    "title": "Manage DN filters",
    "linkTitle": "Manage DN filters",
    "weight": "360"
}The following topics describe how to manage DN filters:

-   <a href="#Add" class="MCXref xref">Add a DN filter</a>
-   <a href="#Enable" class="MCXref xref">Enable or disable a DN filter</a>
-   <a href="#Edit" class="MCXref xref">Edit a DN filter</a>
-   <a href="#Delete" class="MCXref xref">Delete a DN filter</a>

**Related topics:**

-   <a href="../t_st_create_domain" class="MCXref xref">Create an LDAP domain</a>
-   <a href="../t_st_define_ldap_search_criteria_for_domain" class="MCXref xref">Define LDAP search criteria for a domain</a>
-   <a href="../t_st_define_ldap_user_settings_for_domain" class="MCXref xref">Define LDAP user settings for a domain</a>
-   <a href="../t_st_define_attribute_mappings_for_domain" class="MCXref xref">Define attribute mappings for a domain</a>
-   <a href="../t_st_manage_dn_filters_for_domain" class="MCXref xref">Manage DN filters for a domain</a>
-   <a href="../t_st_define_ab_settings_for_domain" class="MCXref xref">Define Address Book settings for a domain</a>
-   <a href="../t_st_edit_domain" class="MCXref xref">Edit a domain</a>
-   <a href="../t_st_delete_domains" class="MCXref xref">Delete domains</a>
-   <a href="../t_st_configure_default_domains" class="MCXref xref">Configure default domains</a>
-   <a href="../c_st_ldap_domains_example" class="MCXref xref">LDAP domains example</a>
-   <a href="../c_st_secure_ldap" class="MCXref xref">Secure LDAP</a>
-   <a href="../c_st_ldap_active_directory_configuration" class="MCXref xref">LDAP and Active Directory configuration</a>

<span id="Add"></span>

## Add a DN filter

Use the following procedure to add a DN filter.

1.  If you do not have the *New LDAP Domain* page open, select **Authentication > LDAP Domains** and click the domain name in the Domains List to open the *LDAP Domain* page.
2.  Under *DN Filter List*, click **New Filter**.  
    A line is added to the *DN Filters List*.
3.  In the **DN Filter** field, type a regular expression to match against the DN retrieved from the LDAP database. To specify only a portion of a DN, use wild cards. For example, to allow access to users from the organization acme, enter`.*O=acme.*` in this field. For more information about regular expressions supported by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, see <a href="../../../c_st_regularexpressions#Appendix_Reg_Ex_3207565968_1044920" class="MCXref xref">Regular expressions</a>.
4.  In the **User Class** field, select a user class to apply the DN filter only to users in that class or asterisk (`*`) to apply the DN filter to all users.
5.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

The status of the new DN filter is Disabled.

<span id="Enable"></span>

## Enable or disable a DN filter

Use the following procedure to enable or disable a DN filter.

-   In the entry in the *DN Filter List*, click **Enable** or **Disable**.  
    The Status column is updated.

<span id="Edit"></span>

## Edit a DN filter

Use the following procedure to edit a DN filter.

1.  In an entry in the *DN Filter List*, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column.
2.  Make the required changes to the fields in the entry.
3.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

<span id="Delete"></span>

## Delete a DN filter

Use the following procedure to delete a DN filter.

-   In the entry in the *DN Filter List*, click **X** in the first column.  
    The entry is removed from the list.
