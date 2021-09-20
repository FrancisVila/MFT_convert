{
    "title": "Firewall issues",
    "linkTitle": "Firewall issues",
    "weight": "350"
}To eliminate any possible firewall settings that can affect performance, check the following:

-   Make sure the ports SecureTransport uses are set correctly. If your firewall uses passive mode, make sure that you are using Clear Command Channel (CCC) or Firewall Friendly mode.
-   Verify that no other applications are experiencing problems with the firewall.
-   The Transaction Manager has a timeout value that allows connections to close before the firewall can close them. Make sure the timeout setting in `<FILEDRIVEHOME>/brules/conf/brules.xml` on the SecureTransport Server is a lower value than the timeout setting for the firewall. Look for the following setting in the Event Monitor element in the file:  
    `<!-- single simple value, timeout in seconds -->`  
    `<client timeout="900"/>`
      
    Change the setting to be smaller than the value of the firewall timeout.

**Related topics:**

-   [Evaluate performance issues](../t_st_evaluate_performance_issues)
-   [DNS settings](../t_st_dns_settings)
-   [Other services using to much CPU or memory](../t_st_other_services_using_to_much_cpu_memory)
-   [Installation on network drive](../t_st_installation_on_network_drive)
-   [Debug log output slows computer](../t_st_debug_log_output_slows_computer)
