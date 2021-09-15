{
    "title": "Check Point firewall is not configured for bidirectional transfers",
    "linkTitle": "Check Point firewall is not configured for bidirectional transfers",
    "weight": "300"
}The symptoms of incorrectly configured bidirectional FTP transfers include:

-   The error message `message_info violated unidirectional connection` in the Check Point log viewer
-   Bidirectional FTP data connections getting dropped

These symptoms can occur because bidirectional FTP data connections are not allowed by default. Bidirectional FTP data connections are not considered as safe since the data connection is interactive and the connection changes the basic way FTP works.

Check Point firewalls need to be configured to use bidirectional transfers. In the Check Point NG firewall (AI R55 and higher), set the FTP connection to FTP\_BASIC. This allows bidirectional communications and sets the firewall to allow commands not terminated with a new line.

**Related topics:**

-   [Firewall rules prevent the port from opening](../c_st_firewall_rules_prevent_port_from_opening)
-   [Passive port range is not defined in the firewall](../c_st_passive_port_range_is_not_defined_in_firewall)
