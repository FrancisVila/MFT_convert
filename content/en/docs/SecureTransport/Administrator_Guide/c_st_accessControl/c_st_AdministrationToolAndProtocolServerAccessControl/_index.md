{
    "title": "Protocol server access control",
    "linkTitle": "Protocol server access control",
    "weight": "240"
}You can limit access to the {{< SecureTransport/componentshortname  >}} Administration Tool, FTP, and HTTP servers to specified hosts by defining access rules.

When a client attempts to connect to the {{< SecureTransport/componentshortname  >}} Administration Tool or either of the protocol servers, the server looks up the address and, if reverse DNS lookup is enabled, the host name of the computer the client is connecting from and for protocol servers, the user class and applies the access rules to allow or deny access.

If your {{< SecureTransport/componentshortname  >}} deployment includes {{< SecureTransport/componentshortname  >}} Edge servers in a peripheral network (DMZ) and if you need different Administration Tool access control for administrators who use the Administration Tool for {{< SecureTransport/componentshortname  >}} Edge and for {{< SecureTransport/componentshortname  >}} Server, you can configure Administration Tool access control differently.

Configure protocol server access control on {{< SecureTransport/componentshortname  >}} Server only.

> **Note:**
>
> Protocol server access restrictions do not work for SiteMinder logins.

The following topics describe access rule ordering and provide how-to instructions for enabling host names for access control and managing protocol server access:

-   [Access rule order](c_st_access_rule_order) - Describes the access rule order and provides configuration information for access rule ordering.
-   [Enable host names for access control](t_st_enablehostnamesforaccesscontrol) - Provides how-to instructions for enabling host names for access control.
-   [Manage protocol server access](t_st_administrationtoolandprotocolserveraccess) - Provides how-to instructions for managing protocol server access.
