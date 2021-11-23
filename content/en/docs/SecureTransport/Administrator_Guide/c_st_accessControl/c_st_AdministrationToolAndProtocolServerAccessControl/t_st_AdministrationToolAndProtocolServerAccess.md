{
    "title": "Manage protocol server access",
    "linkTitle": "Manage protocol server access",
    "weight": "280"
}Define any number of rules in the *Admin Access Control* page control access to the {{< SecureTransport/componentshortname  >}} Administration Tool. Define any number of rules in the *Server Access Control* page to control access to the FTP and HTTP servers.

The following topics provide how-to instructions for managing protocol server access:

-   [Add an access rule](#Add)
-   [Enable or disable an access rule](#Enable)
-   [Edit an access rule](#Edit)
-   [Delete an access rule](#Delete)
-   [Change the order that rules are applied](#Change)
-   [Server access rules example](#Server)

**Related topics:**

-   [Access rule order](../c_st_access_rule_order)
-   [Enable host names for access control](../t_st_enablehostnamesforaccesscontrol)

<span id="Add"></span>

## Add an access rule

Use the following procedure to add an access rule.

1.  Select **Access > Admin Access Control** or **Access > Server Access Control**.  
    The *Admin Access Control* or *Server Access Control* page is displayed.  
    The initial configuration allows access to the Administration Tool from all computers.
2.  Click **New Access Rule**. A new line is displayed in the list.
3.  In the **Rule** field, select an access permission. The types of access permissions available are:
    -   Allow Access From
    -   Deny Access From
4.  In the Address field, enter a host name, an IP address, or a value that represents a range of IP addresses to apply the rule. For valid IP addresses and values for IP address ranges, see [IP addresses and host names](../../../c_st_ipaddressesandhostnames).  
    Only one host name, IP address, or IP address range value is allowed. A host name pattern is not valid.
5.  For a server access rule, select a **User Class**. Asterisk (`*`) means all users.
6.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.  
    The status of a new entry is set to Disabled.

> **Note:**
>
> To cancel an add operation, select Access &gt; Admin Access Control or Access &gt; Server Access Control again.

<span id="Enable"></span>

## Enable or disable an access rule

Use the following procedure to enable or disable an access rule.

1.  Select **Access > Admin Access Control** or **Access > Server Access Control**.  
    The *Admin Access Control* or *Server Access Control* page is displayed.
2.  Select the check box for each rule to modify.
3.  Click **Enable** or **Disable**.  
    The icons in the **Rule** column change to indicate the status of the classes.

<span id="Edit"></span>

## Edit an access rule

Use the following procedure to edit an access rule.

1.  Select **Access > Admin Access Control** or **Access > Server Access Control**.  
    The *Admin Access Control* or *Server Access Control* page is displayed.
2.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) in the **Edit** column for the rule to edit.
3.  Make the required changes in the fields.
4.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an edit operation, select Access &gt; Admin Access Control or Access &gt; Server Access Control again.

<span id="Delete"></span>

## Delete an access rule

Use the following procedure to delete an access rule.

1.  Select **Access > Admin Access Control** or **Access > Server Access Control**.  
    The *Admin Access Control* or *Server Access Control* page is displayed.
2.  Select the check box for each rule to delete.
3.  Click **Delete**.
4.  Click **OK** in the confirmation dialog box.

<span id="Change"></span>

## Change the order that rules are applied

Use the following procedure to change the order that access rules are applied.

1.  Select **Access > Admin Access Control** or **Access > Server Access Control**.  
    The *Admin Access Control* or *Server Access Control* page is displayed.
2.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) to the right of the **Rule** list.
3.  Select a rule order. The available rule orders are:
    -   Deny then Allow
    -   Allow then Deny
4.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)) to the right of the **Rule** list.

<span id="Server"></span>

## Server access rules example

The following example uses an IP address pattern to specify a range of IP addresses as described in [IP addresses and host names](../../../c_st_ipaddressesandhostnames). It denies access to all computers except those in the 198.160.123 subnet.
