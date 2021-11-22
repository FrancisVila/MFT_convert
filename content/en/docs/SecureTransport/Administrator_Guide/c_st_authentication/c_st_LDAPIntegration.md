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

-   <a href="../c_st_ldap_connections_binds_searches" class="MCXref xref">LDAP connections, binds, and searches</a> - Describes LDAP connections, binds, and searches.
-   <a href="../c_st_ldap_logins" class="MCXref xref">LDAP logins</a> - Describes LDAP logins and provides how-to instructions for logging into LDAP.
-   <a href="../t_st_ldapsettings" class="MCXref xref">LDAP domains</a> - Describes the LDAP domains.
-   <a href="../t_st_ldaphomefolders" class="MCXref xref">LDAP home folders</a> - Describes the LDAP home folders.
-   <a href="../t_st_ldapusertype" class="MCXref xref">LDAP user type ranges</a> - Describes the LDAP user type ranges.
