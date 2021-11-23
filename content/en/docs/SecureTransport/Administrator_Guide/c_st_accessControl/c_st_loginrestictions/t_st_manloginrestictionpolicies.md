{
    "title": "Create Login Restriction Policy entries",
    "linkTitle": "Create Login Restriction Policy entries",
    "weight": "300"
}The following topics provide the instructions for creating and editing Login Restriction Policies. The instructions for adding, editing, enabling, disabling, and deleting policy rules are also provided.

-   [Create a Login Restriction Policy](#Creating)
-   [Edit a Login Restriction Policy](#Editing)
-   [Add a policy rule](#Adding)
-   [Edit a policy rule](#Editing2)
-   [Enable, disable or delete a policy rule](#Enabling)

**Related topic:**

-   [Manage Login Restriction Policies](../t_st_manloginrestictions)

<span id="Creating"></span>

## Create a Login Restriction Policy

Use the following instructions to create a Login Restriction Policy:

1.  Click **New Login Restriction Policy** on the *Login Restriction Policies for End Users* page.  
    The New Login Restriction Policy entry page is displayed.

2.  Enter a **Policy Name**.

3.  Select a **Policy Type**.  
    If the selected Login Restriction Policy Type is `ALLOW_THEN_DENY`, then login access is **denied** by default unless some **ALLOW** rule matches and no **DENY** rule matches.  
    If the selected Login Restriction Policy Type is `DENY_THEN_ALLOW`, then login access is **allowed** by default unless some **DENY** rule matches and no **ALLOW** rule matches.

4.  (Optional) **Assign Business Units** to the Login Restriction Policy.

5.  (Optional) Enter a **Policy Description**.

6.  (Optional) Set **Additional attributes**: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition).

7.  Add Policy Rules to the Login Restriction Policy. See [Add a policy rule](#Adding).  

    > **Note:**
    >
    > Policy Rules are enabled by default.

8.  Click **Save Policy**.

<span id="Editing"></span>

## Edit a Login Restriction Policy

Use the following instructions to edit an existing Login Restriction Policy:

1.  Click on the Policy Name to edit the selected Login Restriction Policy on the *Login Restriction Policies for End Users* page.  
    The *Edit Login Restriction Policy entry* page will be displayed.
2.  Make the desired edits to the selected Login Restriction Policy.  
    See [Create a Login Restriction Policy](#Creating).
3.  Click **Save Policy**.

<span id="Adding"></span>

## Add a policy rule

Use the following instructions to add a policy rule to Login Restriction Policy.

1.  Click **New Rule**.  
    The **New Rule** fields open on *List of Rules* pane.

2.  Enter a policy rule **Name**.

3.  Select a policy rule **Type**.  
    If `Allow` is selected, the policy rule is set to **Allow** the Client Address.  
    If `Deny` is selected, the policy rule is set to **Deny** the Client Address.

4.  Enter a **Client Address** for the policy rule. Valid client address types are:
    -   **Allow All**: Use asterisk (\*) to allow all client addresses.
    -   **IPv4 address**: Use an exact IPv4 to specify a single host.
    -   Examples:
    -   `172.23.34.45`; `127.0.0.1`;
    -   **IPv6 address**: Use an exact IPv6 to specify a single host (two colons (::) can represent one sequence of zero bits).
    -   Examples:
    -   `FC00:1234:56:0:0:0:AB:EF`; `FC00:1234:56::AB:EF`; `::1`
    -   **IPv4 CIDR**: Classless Inter-Domain Routing (CIDR) notation specifies an IPv4 address and a number of significant bits separated by a slash (`/`). Use CIDR notation to represent a range of IP addresses.
    -   Examples:
    -   `172.23.34.0/24` represents `172.23.34.0` through `172.23.34.255`
    -   **IPv6 CIDR**: Classless Inter-Domain Routing (CIDR) notation specifies an IPv6 address and a number of significant bits separated by a slash (/). Use CIDR notation to represent a range of IP addresses.
    -   Examples:
    -   `FC00:1234:56::/120` represents `FC00:1234:56::` through `FC00:1234:56::FF`
    -   **Specific host name**: Use a literal host name to represent a single host where host names are valid. The host name must resolve to a valid IPv4 or IPv6 address.
    -   Example:
    -   `appserver.example.com`
    -   **Wild-carded host name using the character \* as wildcard**: Use a host name pattern that uses asterisk (`*`) to represent one or more characters. The pattern specifies any host whose name matches.
    -   Examples:
    -   `*.example.com`; `example.*`

5.  (Optional) Enter an **Expression** for the policy rule.  
    Specify an expression using {{< SecureTransport/securetransportname >}} expression language. Use the following named variable sets:

    -   `${sess['variable']}`
    -   `${env['variable']}, ${stenv['variable']}, or ${stenv.variable}`

      
    If such expression is specified, then a rule will be considered to match if both client address matches and expression evaluates to true.  
    If such expression is not specified then it is not taken into account. Just the client address is considered.  
    Example:  
    `${stenv.loginname =='user1'}`  
      
    You can create a rule that limits the possible concurrent open sessions by a user. To do this, you must use the `currentSessions`variable and evaluate it against the threshold value you set in your rule.  
    Example:  
    `${currentSessions <= 3}` - this example puts a session limit of up to 3 current sessions per user  

    > **Note:**
    >
    > To restrict user logins to a specific Edge server or a network zone, we can use two variables:

    -   The `DXAGENT_CLIENTADDR` variable effectively represents an Edge server hostname (or an IP address depending on the network setup) and is always present when connecting through an Edge server. It can be used in LRP expressions as `{stenv.clientaddr} or ${sess.clientaddr}`.  
    -   When connecting through an Edge server, the value of the `DXAGENT_EDGEID` variable is taken from the configuration option `EdgeId`. This configuration option is defined by a SecureTransport administrator and is valid for FTP and HTTP daemons only. It can be used in LPR expressions as `{stenv.edgeid} or ${sess.edgeid}`.  

    When a user logs in through the Private zone (that is through Backend protocol daemons), these variables are not available in the environment, and in this case the only valid expression is `${empty sess.clientaddr} or ${empty sess.edgeid}`.  
    You may use custom HTTP headers in LRP expressions, where the name of the HTTP header must be capitalized and all dashes must be replaced by underescores.  
    For example: ${env\['DXAGENT\_HTTP\_X\_FORWARDED\_FOR'\] == '10.10.10.10'}  

6.  (Optional) Enter a **Description** for the policy rule.

7.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon.

<span id="Editing2"></span>

## Edit a policy rule

Use the following instructions to edit a policy rule:

1.  Click the **Edit** (![](/Images/SecureTransport/EditIcon2.png)) icon for the policy rule.
2.  Make the desired changes to the policy rule. See [Add a policy rule](#Adding).
3.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon.

<span id="Enabling"></span>

### Enable, disable or delete a policy rule

Select one or more policy rules to enable using the **Policy Rule** checkboxes.

-   Click **Enable** to enable the selected policies.
-   Click **Disable** to disable the selected policies.
-   Click Delete and confirm your choice to delete selected policies.
