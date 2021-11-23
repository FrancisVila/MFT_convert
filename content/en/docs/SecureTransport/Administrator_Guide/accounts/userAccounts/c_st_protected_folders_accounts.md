{
    "title": "Protected folders and accounts",
    "linkTitle": "Protected folders and accounts",
    "weight": "260"
}{{< SecureTransport/componentshortname  >}} maintains a list of directories which you should not use for home folders for user or service accounts. This type of directory is called a *protected folder*. Protected folders are identified by a specific prefix in the path. The following table lists the prefixes used by default.

Virtual accounts can be purged using {{< SecureTransport/componentshortname  >}}, provided these accounts are not in a protected folder.

{{< SecureTransport/componentshortname  >}} provides the following precautions that are built-in to prevent accidental or malicious account deletion:

-   Paths are converted to equivalent paths without any "." or ".." directories.
-   The user home folder cannot directly, or indirectly through a symbolic link, refer to any of the protected directories.
-   If the entry for a user home folder is not a directory, it is not purged.
-   If the user home folder begins with any of the protected home folder prefixes, the account is not purged.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Platform         </th>
<th class="HeadD-Column1-Header1">Protected home folder prefixes         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>AIX, Linux, {{< SecureTransport/companyname  >}} Appliance         </td>
         <td><code>/audit /bin /boot /dev /etc /kernel /lib /lpp /mnt /modules /net /opt /platform /proc /root /sbin /stand /sys /tftp /usr /var /vol</code>         </td>
      </tr>
      <tr>
         <td>Windows (in Cygwin Format)         </td>
         <td>(none)         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> You can add to the list of protected folders by modifying the UnsafePaths server configuration option. When adding a folder name that contains spaces, use quotes around the path so the entire path is recognized, for example, "/user 1/". Do not remove any of the default protected folder prefix. Make the change on all servers in your Standard Cluster (SC) or Enterprise Cluster (EC).

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
