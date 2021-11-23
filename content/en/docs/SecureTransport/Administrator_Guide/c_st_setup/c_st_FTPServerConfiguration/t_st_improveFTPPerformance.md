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

-   [FTP server messages](../t_st_ftpservermessages)
-   [Set up FTP active mode](../t_st_ftpactivemode)
-   [Set up FTP passive mode](../t_st_ftppassivemode)
-   [FTP server limitations](../r_st_ftpserverlimitations)
-   [Increase the timeout for large files using server-initiated transfer](../t_st_increaseftptimeout)
