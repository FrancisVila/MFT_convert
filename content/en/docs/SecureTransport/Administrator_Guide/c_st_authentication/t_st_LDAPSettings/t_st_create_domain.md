{
    "title": "Create an LDAP domain",
    "linkTitle": "Create an LDAP domain",
    "weight": "320"
}When you create a domain, you must give it a name and specify at least one LDAP server.

1.  Select **Authentication > LDAP Domains**.  
    The *LDAP Domains* page is displayed.

2.  Click **New Domain**.  
    The *New LDAP Domain* page is displayed.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Settings</em> pane is only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>). For information on defining Address Book settings for a domain, refer to <a href="../t_st_define_ab_settings_for_domain">Define Address Book settings for a domain</a>. For information on the Address Book LDAP source, refer to <a href="../../../c_st_setup/address_book/ab_sources">LDAP source</a>.         </td>
      </tr>
</table>

3.  Type a **Domain Name**. The user must specify this name in the login name, *domain\_name*/*user\_name*, to select this domain if it is not configured as a default domain on *LDAP Domains* page.

4.  Type a **Description** for your use.

5.  Under *LDAP Servers*, click **New Server**.  
    A line is added to the *Servers List*.

6.  In the **Server** field, type the host name or IP address of the LDAP server.

7.  In the **Port** field type the LDAP port number for the server. The default is 389.

8.  To test the connection to the LDAP server, click the icon in the column after the **Server** column.

9.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the **Edit** column.

10. Add backup LDAP servers, if any, to the *Servers List*.

11. To change the order SecureTransport tries the servers, click **Reorder**, update the numbers in the **Order** column, and click **Save**.

12. Under *LDAP Servers*, complete the following fields:  
    

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
         <td>Protocol Version         </td>
         <td>Select the LDAP protocol version.         </td>
         <td>2 or 3         </td>
      </tr>
      <tr>
         <td>Encryption         </td>
         <td>Enable  Secure LDAP, also know as LDAP over SSL or LDAPS.         </td>
         <td>None, TLS, or StartTLS (for LDAP protocol 3 )         </td>
      </tr>
      <tr>
         <td>Verify Certificate Chain         </td>
         <td>Configure whether <span>SecureTransport</span> implicitly trusts the LDAP servers in this domain or verifies the LDAP server certificates.         </td>
         <td>See <a href="#secure">Create an LDAP domain</a>.         </td>
      </tr>
      <tr>
         <td>Enable LDAP Referrals         </td>
         <td>Configure whether <span>SecureTransport</span> allows the LDAP server to refer a request to another LDAP server.         </td>
         <td>This option is required when the LDAP directory tree is distributed over a group of servers.         </td>
      </tr>
      <tr>
         <td>Enable Anonymous Binds         </td>
         <td>Configure whether <span>SecureTransport</span> uses a Bind DN to access to the LDAP server.         </td>
         <td>
            <p>You can select this option when LDAP servers supports anonymous binding.</p>
            <p>If this option is not selected, the <strong>Bind DN</strong> field is required.</p>
         </td>
      </tr>
      <tr>
         <td>Bind DN         </td>
         <td>Type the distinguished name of a user who is allowed access to the LDAP directory for user lookups.         </td>
         <td>
            <p>For authorization purposes, this field is case sensitive.</p>
            <p>If <strong>Enable Anonymous Binds</strong> is not selected, this field is required.</p>
         </td>
      </tr>
      <tr>
         <td>Use Bind DN Password         </td>
         <td>If a password is required to bind to the directory service on the LDAP server, select <strong>Use Password</strong> and enter the password in the fields provided.         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>LDAP Common Case         </td>
         <td>
            <p>Configure whether and how <span>SecureTransport</span> changes the case of the user name it receives from the LDAP database.</p>
         </td>
         <td>
            <p>None, Lower, or Upper.</p>
            <p>If the value is Lower or Upper, <span>SecureTransport</span> maps the case of all letters in the user name to the case you specify.</p>
         </td>
      </tr>
   </tbody>
</table>

13. Click **Save.**

For information on the Address Book LDAP source, refer to [LDAP source](../../../c_st_setup/address_book/ab_sources).

**Related topics:**

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
-   [LDAP and Active Directory configuration](../c_st_ldap_active_directory_configuration)
