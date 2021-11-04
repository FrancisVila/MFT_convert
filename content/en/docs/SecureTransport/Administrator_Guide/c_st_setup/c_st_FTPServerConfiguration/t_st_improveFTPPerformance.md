{
    "title": "Improve FTP performance on a multi-homed system",
    "linkTitle": "Improve FTP performance on a multi-homed system",
    "weight": "150"
}You can improve FTP performance by assigning an IP address to the server if you are using a multi-homed system.

1.  Select **Operations > Server Configuration**.
2.  In the *Server Configuration* page, search for the `Ftp.Host` parameter.
3.  Set the value of the parameter to the IP address for the server.
4.  Restart the FTP Server on all servers in your cluster.

**Related topics:**

-   <a href="../t_st_ftpservermessages" class="MCXref xref">FTP server messages</a>
-   <a href="../t_st_ftpactivemode" class="MCXref xref">Set up FTP active mode</a>
-   <a href="../t_st_ftppassivemode" class="MCXref xref">Set up FTP passive mode</a>
-   <a href="../r_st_ftpserverlimitations" class="MCXref xref">FTP server limitations</a>
-   <a href="../t_st_increaseftptimeout" class="MCXref xref">Increase the timeout for large files using server-initiated transfer</a>
