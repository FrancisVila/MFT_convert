{
    "title": "Protected folders and accounts",
    "linkTitle": "Protected folders and accounts",
    "weight": "270"
}SecureTransport maintains a list of directories which you should not use for home folders for user or service accounts. This type of directory is called a *protected folder*. Protected folders are identified by a specific prefix in the path. The following table lists the prefixes used by default.

Virtual accounts can be purged using SecureTransport, provided these accounts are not in a protected folder.

SecureTransport provides the following precautions that are built-in to prevent accidental or malicious account deletion:

-   Paths are converted to equivalent paths without any "." or ".." directories.
-   The user home folder cannot directly, or indirectly through a symbolic link, refer to any of the protected directories.
-   If the entry for a user home folder is not a directory, it is not purged.
-   If the user home folder begins with any of the protected home folder prefixes, the account is not purged.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Platform</th>
         <th>Protected home folder prefixes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td> AIX, Linux, <span>Axway</span> Appliance         </td>
         <td><code>/audit /bin /boot /dev <br/>/etc /kernel /lib /lpp <br/>/mnt /modules /net /opt <br/>/platform /proc /root <br/>/sbin /stand /sys /tftp <br/>/usr /var /vol</code>
         </td>
      </tr>
      <tr>
         <td>Windows (in Cygwin Format)         </td>
         <td>(none)         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can add to the list of protected folders by modifying the <code>UnsafePaths</code> server configuration option. When adding a folder name that contains spaces, use quotes around the path so the entire path is recognized, for example, <code>"/user 1/"</code>. Do not remove any of the default protected folder prefix. Make the change on all servers in your Standard Cluster (SC) or Enterprise Cluster (EC).         </td>
      </tr>
</table>

**Related topics:**

-   [Create a user account](../t_st_create_user_account)
-   [Change how long user account information is cached in memory](../t_st_change_how_long_user_account_information_is_cached)
-   [Disable or enable a user account](../t_st_disable_enable_user_account)
-   [Lock or unlock a user account](../t_st_lock_unlock_user_account)
-   [Manage user account passwords](../t_st_manage_user_account_passwords)
-   [Edit user account settings](../t_st_edit_user_account_settings)
-   [Delete user accounts](../t_st_delete_user_accounts)
-   [Delete and purge a user account](../t_st_delete_purge_user_account)
-   [Export a single user account](../t_st_export_single_user_account)
-   [Unlicensed users](../t_st_unlicensed_users)
