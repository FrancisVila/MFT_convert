{
    "title": "Connectivity",
    "linkTitle": "Connectivity",
    "weight": "260"
}Communication issues can arise when IP addresses are not recognized properly. Use the following procedures to check your connectivity settings.

-   Make sure that the correct IP addresses are listed for the {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge in the `hosts` file. For details, see <a href="../../t_st_servicesdonotstart/c_st_incorrect_host_name_ip_in_host_file#Appendix_Troubleshooting_4259246568_1017841" class="MCXref xref">Incorrect host name and IP address in the host file</a>.
-   Make sure that the network zones on the {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge are correct and consistent.
-   Make sure that the {{< SecureTransport/componentshortname >}} Server is listed as an allowed server on the {{< SecureTransport/componentshortname >}} Edge.
-   Make sure that the `Streaming.TrustedAliases` server configuration parameter is set correctly. For more information, see <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#Secure" class="MCXref xref">Secure the communication between the TM server and the protocol servers</a>.
-   Make sure that the firewall is configured correctly. For more information on configuring the firewall, see <a href="../../../c_st_firewallsettings#Appendix_Firewall_Settings_3020346255_1032350" class="MCXref xref">Firewall settings</a>.

**Related topics:**

-   <a href="../c_st_clocks_out_of_sync" class="MCXref xref">Clocks out of sync</a>
-   <a href="../c_st_trust_establishment_issues" class="MCXref xref">Trust establishment issues</a>
