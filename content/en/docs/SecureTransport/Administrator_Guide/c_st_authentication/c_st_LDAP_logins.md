{
    "title": "LDAP logins",
    "linkTitle": "LDAP logins",
    "weight": "290"
}If you configure and enable LDAP, SecureTransport uses it as follows when users log in:

If the user includes a domain name in the login name, *domain\_name*/*user\_name*, SecureTransport attempts to connect the LDAP servers configured for the named domain. If the first server SecureTransport connect to has record for the user, SecureTransport use it. If not, the login fails.

If the user does not include a domain name in the login name, SecureTransport can still find the authentication information and user attributes in the LDAP databases of the default domains in the order on the *LDAP Domains* page. Depending on whether or not LDAP authentication is required, SecureTransport also searches other databases:

1.  If LDAP authentication is optional, SecureTransport searches the SecureTransport database before it searched the LDAP databases in the default domains.
2.  If the user specified by the login name is not in the SecureTransport database and login name and password match, SecureTransport searches the databases of the LDAP servers configured for the default domains in the order on the *LDAP Domains* page.
3.  If LDAP authentication is optional and the authentication information is not in any of the databases of the LDAP servers in the default domains, SecureTransport searches the operating system if real users are enabled.

If SecureTransport does not find the user name in one of these locations, the login fails.

When SecureTransport finds an LDAP entry for the user name, it uses the password from the entry to authenticate the user. If authentication fails, the login fails.

-   **User ID** (UID) (UNIX-based systems only) – `fdxUid`. This is the numeric value required by the UNIX system to identify the user. This is not the LDAP attribute `UID`, which represents an LDAP unique identifier.
-   **Group ID** (GID) – `fdxGid`
-   **Home folder** (HomeDir) – `fdxHomeDir`
-   **User type** – `fdxUserType`
-   **User shell** (UNIX-based systems only) – `fdxShell`
-   **System user** (Windows only) – `fdxSysUser`. This is name of a local or domain user of the Windows server. SecureTransport uses this user's credentials to access the Windows files in the session. If this is a real user, you must add the user to a SecureTransport password vault before you specify the user as the System User in an LDAP record or as the default system user for a domain. See [Add a user to a password vault](../../c_st_advancedaccountadministration/c_st_systemusers/t_st_passwordfiles).
-   **Login by email** – `fdxAuthByEmail`. If this is enabled, the user can login using an email address as well as a user name if the login by email is enabled in the LDAP domain and the email attribute of the LDAP record has the correct value.

If the LDAP record SecureTransport finds does not include some of the user attributes, SecureTransport uses any enabled attributes maps, any enabled user type ranges, any enabled home folder entries, and the configured defaults for the domain to set the attributes. If any required attribute information is not available or not valid, the login fails.

SecureTransport performs the following actions to set the user attributes and other required session information:

1.  Sets all attributes from LDAP record values based on any enabled attribute maps. For configuration, see [Define attribute mappings for a domain](../t_st_ldapsettings/t_st_define_attribute_mappings_for_domain).
2.  On UNIX-based systems, if the `fdxUserType` attribute is not set and there is an applicable entry in the *User Type Ranges* page, sets the user type based on the value of the user ID. For configuration, see [LDAP user type ranges](../t_st_ldapusertype).
3.  For attributes that are not set, applies the default values for the domain. For configuration, see [Define LDAP user settings for a domain](../t_st_ldapsettings/t_st_define_ldap_user_settings_for_domain).
4.  Sets the user class. See [User classes](../../c_st_accesscontrol/c_st_userclasses).
5.  Checks any enabled DN filters configured for the domain. You can use DN filters to permit access to only certain sub-trees of the LDAP directory structure within the domain. If there is an enabled DN filter for the user class set in the previous step or for all users, denoted by asterisk (`*`), the DN from the LDAP record must match one of those filters. If there are enabled DN filters for the user class or for all users and no filter matches, the login fails. See [Manage DN filters for a domain](../t_st_ldapsettings/t_st_manage_dn_filters_for_domain).
6.  If the `fdxHomeDir` attribute is not set, sets it based on the user class using the entries in the *Home Folder* page. For configuration, see [LDAP home folders](../t_st_ldaphomefolders).
7.  Use the alphabetically first applicable account template. If there is an applicable account template, the values from the template replace any value already set. For details, see [Account templates and external users](../../c_st_advancedaccountadministration/c_st_accounttemplates/c_st_account_templates_external_users).

If, after this process, any required user attributes are not set because there is no enabled attribute map, because the LDAP value for an enabled attribute map is not present in the LDAP record, or because the value was not set by a later step, the login fails.

SecureTransport real users authenticated using LDAP have the following limitations:

-   They cannot use certificate authentication.
-   They cannot change their passwords using a SecureTransport client.
-   You can only subscribe them to an application if you do it in an account template or create a SecureTransport account that stores its password in the LDAP record.

To configure Active Directory in a SecureTransport LDAP domain, see [LDAP and Active Directory configuration](../t_st_ldapsettings/c_st_ldap_active_directory_configuration).