{
    "title": "LDAP connections, binds, and searches",
    "linkTitle": "LDAP connections, binds, and searches",
    "weight": "280"
}To configure backup LDAP servers in case a server is not accessible or not responding, you can list two or more LDAP servers for any domain. SecureTransport attempts to connect to the servers and bind to their LDAP databases in the order you specify in the server list. SecureTransport uses the first LDAP database it can bind to. If SecureTransport does not find a record for the user in the first available LDAP database, it does not try to connect to other servers in the sequence. So for each login attempt, SecureTransport searches at most one LDAP database in a domain.

You can configure SecureTransport to bind to an LDAP database anonymously or using a bind DN and password.

To locate a DN in the LDAP database, SecureTransport searches using partial DN information and the user’s common name (CN), unique identifier (UID), or Active Directory account name (sAMAccountName). You must define the base DN as required by the server and select the search attribute. You can also define an alias query that is a filter that uses values from an email address used as a login user name.
