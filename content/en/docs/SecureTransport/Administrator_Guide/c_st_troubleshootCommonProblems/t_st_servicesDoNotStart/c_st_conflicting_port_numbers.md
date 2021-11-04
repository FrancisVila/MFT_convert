{
    "title": "Conflicting port numbers",
    "linkTitle": "Conflicting port numbers",
    "weight": "260"
}Make sure the port number assigned to the server is not in use elsewhere, such as the operating system SSH server using port 22. To check the port, open the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool and select **Operations &gt; Server Control**. Verify that the ports assigned to the FTP Server, the HTTP server, the AS2 Server, the SSH server, and the PeSIT Server are not in use by other servers.

**Related topics:**

-   <a href="../t_st_no_ssl_certificate_configured_for_server" class="MCXref xref">No SSL certificate configured for the server</a>
-   <a href="../c_st_incorrect_host_name_ip_in_host_file" class="MCXref xref">Incorrect host name and IP address in the host file</a>
