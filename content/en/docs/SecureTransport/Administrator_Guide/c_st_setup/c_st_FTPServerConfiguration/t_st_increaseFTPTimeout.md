{
    "title": "Increase the time-out for large files using server-initiated transfer",
    "linkTitle": "Increase the time-out for large files using server-initiated transfer",
    "weight": "170"
}When sending 1.5 GB or larger files, the default timeout settings might be too low and SecureTransport might throw an exception error. You can increase the timeout settings for the FTP(S) and HTTP(S).

1.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `OutboundConnections.connectTimeout` and `OutboundConnections.receiveTimeout` parameters.  
    The default value for each parameter is 25 seconds.
3.  Set the value of each parameter to the amount of time it takes to upload the file in seconds. For example, if the file takes 20 minutes to upload, then increase the value of each parameter to 1200 seconds or higher.
4.  Restart the TM Server on all servers in your cluster.

**Related topics:**

-   [FTP server messages](../t_st_ftpservermessages)
-   [Set up FTP active mode](../t_st_ftpactivemode)
-   [Set up FTP passive mode](../t_st_ftppassivemode)
-   [FTP server limitations](../r_st_ftpserverlimitations)
-   [Improve FTP performance on a multi-homed system](../t_st_improveftpperformance)
