{
    "title": "DNS settings",
    "linkTitle": "DNS settings",
    "weight": "340"
}Try the following procedures to verify that your DNS settings are not causing performance to deteriorate.

Verify that the DNS settings for the servers are correct by using `nslookup` in Windows or UNIX-based systems. If the `nslookup` returns an error you need to reconfigure your DNS settings. If `nslookup` times out, make sure that the firewall allows port 53 UDP/TCP.

Reverse DNS lookups are used to resolve an IP address into a fully qualified domain name. The domain name is used for logging purposes and for applying access rules that specify a host name instead of an IP address. Reverse DNS lookups might cause server performance to deteriorate since a series of requests through the DNS name server tree is made each time.  
To disable reverse DNS lookups for the FTP, HTTP, and SSH servers:

1.  Open the SecureTransport Administration Tool in a web browser and log in as the administrator.
2.  Select **Setup > Miscellaneous**.
3.  For **Reverse DNS Lookups**, choose `Reverse DNS lookups disabled`.
4.  Click **Apply**.

To disable DNS lookups for Administration Tool server:

1.  Open the SecureTransport Administration Tool in a web browser and log in as the administrator.
2.  Select **Operations > Server Configuration**.
3.  Search for the `Admin.ReverseDNSLookup` system configuration parameter.
4.  Click the Edit icon (![](SaveIcon_13x13.png)) in the **Edit** column, type `Off` in the **Value** column, and click the Save icon (![](SaveIcon_13x13.png)) in the **Edit** column.
5.  Restart the server.

If you need to use reverse DNS lookups, make sure that the DNS path is not blocked by a firewall. Firewalls can block the DNS path when SecureTransport is in the peripheral network (DMZ). Try one of the following workarounds to allow access through the firewall:

-   Allow SecureTransport access to port 53 TCP/UDP.
-   Include a hosts file entry for every computer using the Administration Tool.
-   Connect to the Administration Tool through a proxy, and put a host file entry for just the proxy.

In some cases, SecureTransport performs NIS lookups for users and groups, even when real users are disabled in SecureTransport. If there is a large number of users defined in NIS, server performance can deteriorate. To work around the issue, take the computer out of NIS.

**Related topics:**

-   [Evaluate performance issues](../t_st_evaluate_performance_issues)
-   [Firewall issues](../t_st_firewall_issues)
-   [Other services using to much CPU or memory](../t_st_other_services_using_to_much_cpu_memory)
-   [Installation on network drive](../t_st_installation_on_network_drive)
-   [Debug log output slows computer](../t_st_debug_log_output_slows_computer)