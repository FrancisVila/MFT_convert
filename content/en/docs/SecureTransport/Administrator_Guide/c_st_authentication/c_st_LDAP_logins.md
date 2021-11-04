{
    "title": "LDAP logins",
    "linkTitle": "LDAP logins",
    "weight": "280"
}If you configure and enable LDAP, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses it as follows when users log in:

If the user includes a domain name in the login name, *domain\_name*/*user\_name*, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> attempts to connect the LDAP servers configured for the named domain. If the first server <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> connect to has record for the user, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> use it. If not, the login fails.

If the user does not include a domain name in the login name, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can still find the authentication information and user attributes in the LDAP databases of the default domains in the order on the *LDAP Domains* page. Depending on whether or not LDAP authentication is required, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> also searches other databases:

1.  If LDAP authentication is optional, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> searches the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> database before it searched the LDAP databases in the default domains.
2.  If the user specified by the login name is not in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> database and login name and password match, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> searches the databases of the LDAP servers configured for the default domains in the order on the *LDAP Domains* page.
3.  If LDAP authentication is optional and the authentication information is not in any of the databases of the LDAP servers in the default domains, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> searches the operating system if real users are enabled.

If <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not find the user name in one of these locations, the login fails.

When <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> finds an LDAP entry for the user name, it uses the password from the entry to authenticate the user. If authentication fails, the login fails.

-   **User ID** (UID) (UNIX-based systems only) – `fdxUid`. This is the numeric value required by the UNIX system to identify the user. This is not the LDAP attribute `UID`, which represents an LDAP unique identifier.
-   **Group ID** (GID) – `fdxGid`
-   **Home folder** (HomeDir) – `fdxHomeDir`
-   **User type** – `fdxUserType`
-   **User shell** (UNIX-based systems only) – `fdxShell`
-   **System user** (Windows only) – `fdxSysUser`. This is name of a local or domain user of the Windows server. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses this user's credentials to access the Windows files in the session. If this is a real user, you must add the user to a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> password vault before you specify the user as the System User in an LDAP record or as the default system user for a domain. See <a href="../../c_st_advancedaccountadministration/c_st_systemusers/t_st_passwordfiles#Add" class="MCXref xref">Add a user to a password vault</a>.
-   **Login by email** – `fdxAuthByEmail`. If this is enabled, the user can login using an email address as well as a user name if the login by email is enabled in the LDAP domain and the email attribute of the LDAP record has the correct value.

If the LDAP record <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> finds does not include some of the user attributes, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses any enabled attributes maps, any enabled user type ranges, any enabled home folder entries, and the configured defaults for the domain to set the attributes. If any required attribute information is not available or not valid, the login fails.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> performs the following actions to set the user attributes and other required session information:

1.  Sets all attributes from LDAP record values based on any enabled attribute maps. For configuration, see <a href="../t_st_ldapsettings/t_st_define_attribute_mappings_for_domain#Define" class="MCXref xref">Define attribute mappings for a domain</a>.
2.  On UNIX-based systems, if the `fdxUserType` attribute is not set and there is an applicable entry in the *User Type Ranges* page, sets the user type based on the value of the user ID. For configuration, see <a href="../t_st_ldapusertype#LDAP_3833293101_1025306" class="MCXref xref">LDAP user type ranges</a>.
3.  For attributes that are not set, applies the default values for the domain. For configuration, see <a href="../t_st_ldapsettings/t_st_define_ldap_user_settings_for_domain#Define2" class="MCXref xref">Define LDAP user settings for a domain</a>.
4.  Sets the user class. See <a href="../../c_st_accesscontrol/c_st_userclasses#AccessMenu_3475920566_1017158" class="MCXref xref">User classes</a>.
5.  Checks any enabled DN filters configured for the domain. You can use DN filters to permit access to only certain sub-trees of the LDAP directory structure within the domain. If there is an enabled DN filter for the user class set in the previous step or for all users, denoted by asterisk (`*`), the DN from the LDAP record must match one of those filters. If there are enabled DN filters for the user class or for all users and no filter matches, the login fails. See <a href="../t_st_ldapsettings/t_st_manage_dn_filters_for_domain#Manage" class="MCXref xref">Manage DN filters for a domain</a>.
6.  If the `fdxHomeDir` attribute is not set, sets it based on the user class using the entries in the *Home Folder* page. For configuration, see <a href="../t_st_ldaphomefolders#LDAP_3833293101_1025358" class="MCXref xref">LDAP home folders</a>.
7.  Use the alphabetically first applicable account template. If there is an applicable account template, the values from the template replace any value already set. For details, see <a href="../../c_st_advancedaccountadministration/c_st_accounttemplates/c_st_account_templates_external_users#Advanced_Accounts_2036285406_1103710" class="MCXref xref">Account templates and external users</a>.

If, after this process, any required user attributes are not set because there is no enabled attribute map, because the LDAP value for an enabled attribute map is not present in the LDAP record, or because the value was not set by a later step, the login fails.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> real users authenticated using LDAP have the following limitations:

-   They cannot use certificate authentication.
-   They cannot change their passwords using a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> client.
-   You can only subscribe them to an application if you do it in an account template or create a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> account that stores its password in the LDAP record.

To configure Active Directory in a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> LDAP domain, see <a href="../t_st_ldapsettings/c_st_ldap_active_directory_configuration#LDAP" class="MCXref xref">LDAP and Active Directory configuration</a>.
