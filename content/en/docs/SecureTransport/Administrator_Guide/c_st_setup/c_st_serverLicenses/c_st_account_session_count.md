{
    "title": "Account session count",
    "linkTitle": "Account session count",
    "weight": "200"
}The number of accounts in the core server license controls the number of connections allowed to the server. An account license is considered in use when a user logs in. A license is also considered in use when used for a site that is initiating transfers. The license is considered in use for 60 days after the initial login or site transfer. The Folder Monitor, AS2 receiving, and asynchronous AS2 MDN receiving are excluded from license counting.

Account licenses apply to all protocols. To limit the number of concurrent users who can connect to the {{< SecureTransport/componentshortname  >}} FTP and HTTP servers, see [User limits](../../../c_st_accesscontrol/c_st_userlimits#AccessMenu_3475920566_1011758).

> **Note:**
>
> SecureTransport does not perform DNS lookups. Therefore a single site referred to in one place by name and another place by IP address is counted as two sites.

**Related topics:**

-   [Ad hoc user licenses](../c_st_adhoc_user_licenses)
-   [Updating SecureTransport licenses](../t_st_serverlicenses)
