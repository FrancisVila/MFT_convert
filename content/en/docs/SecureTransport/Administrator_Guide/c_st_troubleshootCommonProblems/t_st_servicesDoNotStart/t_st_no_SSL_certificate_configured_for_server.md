{
    "title": "No SSL certificate configured for the server",
    "linkTitle": "No SSL certificate configured for the server",
    "weight": "250"
}Verify that the SSL certificate configured for the server has not expired. If the certificate is valid, use the following procedure to make sure that the SSL certificate is properly configured for the server that is not starting.

1.  Select **Operations > Server Control**.
2.  For each server, select an appropriate certificate alias from the **SSL Key Alias** list.
3.  At the bottom of the page, click **Update**.
4.  Restart each server for which you changed the certificate.

In a synchronized configuration, the certificate aliases must match on the primary and the secondary nodes, or after synchronizing, the link between the server and the certificate is broken.

**Related topics:**

-   [Conflicting port numbers](../c_st_conflicting_port_numbers)
-   [Incorrect host name and IP address in the host file](../c_st_incorrect_host_name_ip_in_host_file)
