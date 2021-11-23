{
    "title": "Set up FTP passive mode",
    "linkTitle": "Set up FTP passive mode",
    "weight": "130"
}If an FTP client is behind a firewall that does not permit {{< SecureTransport/componentshortname  >}} to open a data port as required by active mode FTP, you use the passive mode options to configure the FTP server to accept passive mode FTP connections. You specify a passive mode base port and a number of ports that can be used for passive mode. Make sure the ports are accessible through the firewall. Do not use these ports for any other service.

The base port represents the number of the first port available for the FTP server to use for a passive mode data connection. The number of ports specifies how many open ports to allocate. For example, the base port is set to 10000 and the number of ports is set to 1024, the FTP server can use only the ports from 10000 to 11023 for passive mode data connections.

Specify ports for five times the expected number of concurrent connections based on the following considerations:

-   If the port range is too small or equal to the number of expected number of connections, a port to connect might not be available when needed. The operating system does not release a port immediately after a user disconnects, so the free port does not become available for another connection immediately. This can result in a failure when a new connection is attempted.
-   When most of the ports are used up and a new connection is attempted, the server scans for the next available port. This is resource intensive and can affect the performance of the server. With a large pool of ports, finding next available port is quicker and is less likely to affect the performance.

You can also set up passive address rules, which allow the {{< SecureTransport/componentshortname  >}} server to respond with the external address of the firewall instead of the internal address of the server when a FTP client issues the `PASV` (passive mode) command.

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *FTP Passive Mode*:  
    1.  Type the appropriate port number for the **Base Port**. This is the first port used.
    2.  Type the **Number Of Ports**. This value sets the range of ports available for use.
3.  The **Port End** field displays the number for the last port to use.
4.  Click **Save** to apply the changes.

The following sections provide how-to instructions for adding and editing a passive mode address rules and insuring that passive mode sessions are initiated on the correct system:

-   [Add passive mode address rules](#Add)
-   [Edit a passive mode address rule](#Edit)
-   [Assure that passive mode sessions are initiated on the correct system](#Assure)

<span id="Add"></span>

## Add passive mode address rules

1.  Under *Passive Mode Address Rules*, enter in the **User Class** field a pattern that matches the user classes for which this rule will be applied. Use question mark (`?`) to match one character and asterisk (`*`) to match any sequences of characters. For example, enter `*` to apply the rule to all user classes.
2.  Type the external address with which the FTP server should respond in the **Passive Address** field.
3.  Click **Add** to add the rule. To make the change permanent, click **Save**.

<span id="Edit"></span>

## Edit a passive mode address rule

1.  To change the **User Class**, **Passive Address** or **Status** of a rule, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) at the end of the rule.
2.  Make the required changes in the fields and click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)).
3.  To change the status of one or more rules or to remove a rule entirely, select in the left column each rule to modify.
4.  From the **Select Action** list, choose **Delete**, **Enable**, or **Disable** and click **Apply** to make the change.
5.  To make your updates on this page permanent, click **Save**.

<span id="Assure"></span>

## Assure that passive mode sessions are initiated on the correct system

When clients open passive mode sessions though a load balancer, a client communicating on the server assigned port might create a new session which opens a port on a different system than the originally contacted one. You can prevent this issue by configuring the load balancers and servers.

-   Set the load balancer to use "session sticky" mode. This ensures that the data-channel connection goes to the same system that serviced the control-channel connection.
-   Make sure to set a passive-mode address rule on all the {{< SecureTransport/componentshortname >}} Edge gateways or servers to return the external IP address of the load balancer in the response to the PASV command instead of the internal address of the {{< SecureTransport/componentshortname >}} Edge.

 

**Related topics:**

-   [FTP server messages](../t_st_ftpservermessages)
-   [Set up FTP active mode](../t_st_ftpactivemode)
-   [FTP server limitations](../r_st_ftpserverlimitations)
-   [Improve FTP performance on a multi-homed system](../t_st_improveftpperformance)
-   [Increase the timeout for large files using server-initiated transfer](../t_st_increaseftptimeout)
