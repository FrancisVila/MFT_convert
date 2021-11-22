{
    "title": "LDAP home folders",
    "linkTitle": "LDAP home folders",
    "weight": "300"
}You can define entries in the *Home Folder* page that {{< SecureTransport/componentshortname  >}} uses to set the home folder (`fdxHomeDir` attribute) for an LDAP user when the attribute is not set by the other actions listed in <a href="../c_st_ldap_logins#LDAP" class="MCXref xref">LDAP logins</a>. If there is an entry for the user's user class or for all users, {{< SecureTransport/componentshortname  >}} uses the configured prefix. For example, if the prefix is `/home/users/partners` and the user name is `suplco`, {{< SecureTransport/componentshortname  >}} set the home folder to `/home/users/partners/suplco`.

When {{< SecureTransport/componentshortname  >}} is running under Windows, you can use a local file path, such as `D:\home\users\partners` or a UNC path for a share such as `\\NAS2\home\users\partners`. The permissions for the share must permit the {{< SecureTransport/componentshortname  >}} Administration Tool service, which runs on Windows with a local system user as its owner, to create the folder. If the permissions granted for the share are not sufficient to create the subfolder for the LDAP user’s home folder, {{< SecureTransport/componentshortname  >}} refuses the connection.

> **Note:**
>
> Because operating systems do not accept angle brackets (&lt; >) and quotation marks (") in file names, LDAP users with any of those characters in their user name cannot log in to SecureTransport and get a default home directory. You must map such users to a properly configured account template.

You can define a user class based on values from the LDAP entry. See <a href="../../c_st_accesscontrol/c_st_userclasses#AccessMenu_3475920566_1017158" class="MCXref xref">User classes</a>.

If there is no entry for the user class, {{< SecureTransport/componentshortname  >}} uses the entry for all users indicated by an asterisk (`*`) in the **User Class** field.

For more information about how {{< SecureTransport/componentshortname  >}} uses the entries on the *Home Folder* page during LDAP logins, see <a href="../c_st_ldap_logins#LDAP" class="MCXref xref">LDAP logins</a> In particular, if there is an applicable account template, the home folder defined in the account template replaces any home folder set from configuration on the *Home Folders* page.

The following topics describe managing LDAP home folders:

-   <a href="t_st_create_home_folder_entry" class="MCXref xref">Create a home folder entry</a> - Provides how-to instructions for creating a home folder entry.
-   <a href="t_st_enable_disable_home_folder_entries" class="MCXref xref">Enable or disable home folder entries</a> - Provides how-to instructions for enabling or disabling home folder entries.
-   <a href="t_st_edit_home_folder_entry" class="MCXref xref">Edit a home folder entry</a> - Provides how-to instructions for editing a home folder entry.
-   <a href="t_st_delete_home_folder_entries" class="MCXref xref">Delete home folder entries</a> - Provide how-to instructions for deleting home folder entries.
