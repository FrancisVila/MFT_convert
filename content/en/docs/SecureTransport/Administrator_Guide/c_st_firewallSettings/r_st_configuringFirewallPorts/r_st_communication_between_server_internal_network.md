{
    "title": "Communication between SecureTransport Server and an internal network",
    "linkTitle": "Communication between SecureTransport Server and an internal network",
    "weight": "310"
}All of the ports used for communication between the outside and {{< SecureTransport/componentshortname  >}} Edge can be used for user connections originating within your internal network. The following ports might be used for interfacing with infrastructure components:

-   389 or 3268 – LDAP
-   1305 – {{< SecureTransport/companyname >}} Sentinel
-   1344 - ICAP
-   1433 - Microsoft SQL Server database (default)
-   1521 – Oracle database (default)
-   44441 – SiteMinder Accounting
-   44442 – SiteMinder Authentication
-   44443 – SiteMinder Authorization

**Related topics:**

-   [Communication between the outside and SecureTransport Edge](../r_st_communication_between_outside)
-   [Communication between SecureTransport Server and SecureTransport Edge](../r_st_communication_between)
-   [Internal SecureTransport communication](../r_st_internal_communication)
