{
    "title": "Incorrect host name and IP address in the host file",
    "linkTitle": "Incorrect host name and IP address in the host file",
    "weight": "270"
}Verify that the correct IP addresses are in the `hosts` file for each system running <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Look in the hosts file for an entry for each host name with the correct IP address. This file is located in the /`etc` directory on UNIX-based systems. The `hosts` file can be found in the `WINNT\System32\drivers` directory on Windows Server.

Entries in the hosts file have the following format:

`127.0.0.1 localhost.localdomain localhost`

If the entry is not present, create it. If there is an entry, make sure that it has the correct IP address listed. Entries should have the primary alias for each IP address first, followed by the aliases for all other interfaces. You should also verify that your DNS is set up correctly. For more information, see <a href="../../t_st_performanceissues/t_st_dns_settings#Appendix_Troubleshooting_4259246568_1030231" class="MCXref xref">DNS settings</a>.

**Related topics:**

-   <a href="../t_st_no_ssl_certificate_configured_for_server" class="MCXref xref">No SSL certificate configured for the server</a>
-   <a href="../c_st_conflicting_port_numbers" class="MCXref xref">Conflicting port numbers</a>
