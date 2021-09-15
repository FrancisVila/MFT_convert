{
    "title": "LDAP home folders",
    "linkTitle": "LDAP home folders",
    "weight": "310"
}You can define entries in the *Home Folder* page that SecureTransport uses to set the home folder (`fdxHomeDir` attribute) for an LDAP user when the attribute is not set by the other actions listed in [LDAP logins](../c_st_ldap_logins). If there is an entry for the user's user class or for all users, SecureTransport uses the configured prefix. For example, if the prefix is `/home/users/partners` and the user name is `suplco`, SecureTransport set the home folder to `/home/users/partners/suplco`.

When SecureTransport is running under Windows, you can use a local file path, such as `D:\home\users\partners` or a UNC path for a share such as `\\NAS2\home\users\partners`. The permissions for the share must permit the SecureTransport Administration Tool service, which runs on Windows with a local system user as its owner, to create the folder. If the permissions granted for the share are not sufficient to create the subfolder for the LDAP user’s home folder, SecureTransport refuses the connection.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Because operating systems do not accept angle brackets (<code>&lt; &gt;</code>) and quotation marks (<code>"</code>) in file names, LDAP users with any of those characters in their user name cannot log in to <span>SecureTransport</span> and get a default home directory. You must map such users to a properly configured account template.         </td>
      </tr>
</table>

You can define a user class based on values from the LDAP entry. See [User classes](../../c_st_accesscontrol/c_st_userclasses).

If there is no entry for the user class, SecureTransport uses the entry for all users indicated by an asterisk (`*`) in the **User Class** field.

For more information about how SecureTransport uses the entries on the *Home Folder* page during LDAP logins, see [LDAP logins](../c_st_ldap_logins) In particular, if there is an applicable account template, the home folder defined in the account template replaces any home folder set from configuration on the *Home Folders* page.

The following topics describe managing LDAP home folders:

-   [Create a home folder entry](t_st_create_home_folder_entry) - Provides how-to instructions for creating a home folder entry.
-   [Enable or disable home folder entries](t_st_enable_disable_home_folder_entries) - Provides how-to instructions for enabling or disabling home folder entries.
-   [Edit a home folder entry](t_st_edit_home_folder_entry) - Provides how-to instructions for editing a home folder entry.
-   [Delete home folder entries](t_st_delete_home_folder_entries) - Provide how-to instructions for deleting home folder entries.
