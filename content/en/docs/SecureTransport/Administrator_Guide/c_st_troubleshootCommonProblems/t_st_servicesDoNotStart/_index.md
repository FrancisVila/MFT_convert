{
    "title": "Servers do not start",
    "linkTitle": "Services do not start",
    "weight": "230"
}If a {{< SecureTransport/componentshortname  >}} protocol or TM server does not start, check the following topics to troubleshoot the problem. Make sure you check each item in the order listed.

1.  **SSL Certificate** – Verify that the SSL certificate is properly configured for the server.
2.  **Conflicting Port Numbers** – Verify that the port number assigned to the server is not in use elsewhere.
3.  **Host Name** – Look in the server host file for an entry for each host name with the correct IP address.

The following topics provide lists of what to check for when servers do not start:

-   [No SSL certificate configured for the server](t_st_no_ssl_certificate_configured_for_server) - Provides how-to instructions for verifying that an SSL certificate is configured for the server.
-   [Conflicting port numbers](c_st_conflicting_port_numbers) - Provides how-to instructions for verifying port assignments and eliminating conflicting port assignments.
-   [Incorrect host name and IP address in the host file](c_st_incorrect_host_name_ip_in_host_file) - Provides how-to instructions for verifying IP address and host name assignments.
