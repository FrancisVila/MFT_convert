{
    "title": "Conflicting port numbers",
    "linkTitle": "Conflicting port numbers",
    "weight": "270"
}Make sure the port number assigned to the server is not in use elsewhere, such as the operating system SSH server using port 22. To check the port, open the SecureTransport Administration Tool and select **Operations &gt; Server Control**. Verify that the ports assigned to the FTP Server, the HTTP server, the AS2 Server, the SSH server, and the PeSIT Server are not in use by other servers.

**Related topics:**

-   [No SSL certificate configured for the server](../t_st_no_ssl_certificate_configured_for_server)
-   [Incorrect host name and IP address in the host file](../c_st_incorrect_host_name_ip_in_host_file)
