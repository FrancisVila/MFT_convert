{
    "title": "Protocol server access control",
    "linkTitle": "Protocol server access control",
    "weight": "240"
}You can limit access to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool, FTP, and HTTP servers to specified hosts by defining access rules.

When a client attempts to connect to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool or either of the protocol servers, the server looks up the address and, if reverse DNS lookup is enabled, the host name of the computer the client is connecting from and for protocol servers, the user class and applies the access rules to allow or deny access.

If your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment includes <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers in a peripheral network (DMZ) and if you need different Administration Tool access control for administrators who use the Administration Tool for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, you can configure Administration Tool access control differently.

Configure protocol server access control on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server only.

> **Note:**
>
> Protocol server access restrictions do not work for SiteMinder logins.

The following topics describe access rule ordering and provide how-to instructions for enabling host names for access control and managing protocol server access:

-   <a href="c_st_access_rule_order" class="MCXref xref">Access rule order</a> - Describes the access rule order and provides configuration information for access rule ordering.
-   <a href="t_st_enablehostnamesforaccesscontrol" class="MCXref xref">Enable host names for access control</a> - Provides how-to instructions for enabling host names for access control.
-   <a href="t_st_administrationtoolandprotocolserveraccess" class="MCXref xref">Manage protocol server access</a> - Provides how-to instructions for managing protocol server access.
