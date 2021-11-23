{
    "title": "LDAP integration",
    "linkTitle": "LDAP integration",
    "weight": "260"
}You can configure {{< SecureTransport/componentlongname  >}} to use Lightweight Directory Access Protocol (LDAP) servers to authenticate users and provide information it uses to set up the user session.

The {{< SecureTransport/componentshortname  >}} LDAP integration includes:

-   Support for LDAP versions 2 and 3.
-   Support for Secure LDAP, also know as LDAP over SSL/TLS or LDAPS.
-   Search over multiple LDAP domains that provide authentication information and user attributes for different groups of users.
-   Multiple, redundant LDAP servers in a domain for backup when an LDAP server is down or inaccessible.
-   One or more default LDAP domains that {{< SecureTransport/componentshortname >}} searches when a user does not specify a domain name on login.

> **Note:**
>
> You cannot configure both LDAP integration and SiteMinder integration.

The following topics provide LDAP connections, binds, and searches information and logins, agents, domains, home folders, and use type ranges for LDAP:

-   [LDAP connections, binds, and searches](../c_st_ldap_connections_binds_searches) - Describes LDAP connections, binds, and searches.
-   [LDAP logins](../c_st_ldap_logins) - Describes LDAP logins and provides how-to instructions for logging into LDAP.
-   [LDAP domains](../t_st_ldapsettings) - Describes the LDAP domains.
-   [LDAP home folders](../t_st_ldaphomefolders) - Describes the LDAP home folders.
-   [LDAP user type ranges](../t_st_ldapusertype) - Describes the LDAP user type ranges.
