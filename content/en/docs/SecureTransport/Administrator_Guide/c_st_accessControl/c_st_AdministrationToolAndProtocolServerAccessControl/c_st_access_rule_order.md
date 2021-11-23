{
    "title": "Access rule order",
    "linkTitle": "Access rule order",
    "weight": "260"
}You set the order that the server applies the access rules. Using rule order and multiple rules, you can implement detail access control.

If you select *Allow then Deny* rule order, the server denies access to a computer if:

-   It is not explicitly specified in an allow rule  
    or
-   It is explicitly specified in a deny rule.

With *Allow then Deny*, if the IP address or host name of a computer is not specified in either an allow rule or a deny rule, the server denies access. So, the default is no access.

A more general deny rule overrides a more specific allow rule, so to allow access from an entire subnet or range of IP addresses and deny access from specific hosts, select *Allow then Deny* and define an allow rule for the subnet or range of IP addresses and deny rules for each host.

> **Note:**
>
> Be careful not to deny access to the Administration Tool from all computers. If you select Allow then Deny rule order and delete all admin access control rules, no computer can access the Administration Tool. If this happens, contact Axway Global Support.

If you select *Deny then Allow* rule order, the Administration Tool server allows access to a computer if:

-   It is not explicitly specified in a deny rule  
    or
-   It is explicitly specified in an allow rule.

With *Deny the Allow*, if the IP address or host name of a computer is not specified in either an allow rule or a deny rule, the server allows access. So, the default is access.

A more general allow rule overrides a more specific deny rule, So to deny access from an entire subnet or range of IP addresses and allow access from specific hosts, select *Deny the Allow* and define an deny rule for the subnet or range of IP addresses and allow rules for each host.

**Related topics:**

-   [Enable host names for access control](../t_st_enablehostnamesforaccesscontrol)
-   [Manage protocol server access](../t_st_administrationtoolandprotocolserveraccess)
