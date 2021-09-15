{
    "title": "Connectivity",
    "linkTitle": "Connectivity",
    "weight": "270"
}Communication issues can arise when IP addresses are not recognized properly. Use the following procedures to check your connectivity settings.

-   Make sure that the correct IP addresses are listed for the SecureTransport Server and SecureTransport Edge in the `hosts` file. For details, see [Incorrect host name and IP address in the host file](../../t_st_servicesdonotstart/c_st_incorrect_host_name_ip_in_host_file).
-   Make sure that the network zones on the SecureTransport Server and SecureTransport Edge are correct and consistent.
-   Make sure that the SecureTransport Server is listed as an allowed server on the SecureTransport Edge.
-   Make sure that the `Streaming.TrustedAliases` server configuration parameter is set correctly. For more information, see [Secure the communication between the TM server and the protocol servers](../../../c_st_setup/c_st_networkzones/t_st_networkzones).
-   Make sure that the firewall is configured correctly. For more information on configuring the firewall, see [Firewall settings](../../../c_st_firewallsettings).

**Related topics:**

-   [Clocks out of sync](../c_st_clocks_out_of_sync)
-   [Trust establishment issues](../c_st_trust_establishment_issues)
