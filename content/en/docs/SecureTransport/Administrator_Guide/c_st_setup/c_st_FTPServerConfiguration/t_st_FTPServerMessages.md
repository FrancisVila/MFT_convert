{
    "title": "FTP server messages",
    "linkTitle": "FTP server messages",
    "weight": "120"
}FTP server messages are messages displayed to users at the startup of an FTP session. Two types of startup FTP server messages are available:

-   [Create or edit the server connect message](#create)
-   [Create or edit the server ready message](#create_edit)

Users might or might not see FTP server messages, depending on the software they use to connect to SecureTransport. Most FTP client applications display these messages, but they are not displayed on browser clients. Users downloading a single file by URL from a browser might not see these messages.

Startup messages are displayed while a connection to the server is being established, prior to any login prompt. A message is displayed to the user when the connection is established. A server ready message also be displayed when SecureTransport is ready to accept a login. The default message displays the host name of the server and the server version, but this can be overridden.

## <span id="Create"></span>Create or edit the server connect message

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *Server Start up Messages:*  
    
    1.  Select **Enable Message on FTP Server Connect** to display a message to users logging onto SecureTransport through the FTP Server. By default, this option is not selected.
    2.  In the **FTP Connect Message** field, type the message you want to be displayed when a user connects to the SecureTransport Server
3.  Click **Save** to apply the changes.

## <span id="Create_edit"></span>Create or edit the server ready message

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *Server Start up Messages:*
    1.  Select **Enable Message on FTP Server ready** to display a message indicating that the server is ready to accept logins. By default, this option is not selected.
    2.  In the **FTP Ready Message** field, type the message you want to be displayed when the server is ready.
3.  Click **Save** to apply the changes.

 

**Related topics:**

-   [Set up FTP active mode](../t_st_ftpactivemode)
-   [Set up FTP passive mode](../t_st_ftppassivemode)
-   [FTP server limitations](../r_st_ftpserverlimitations)
-   [Improve FTP performance on a multi-homed system](../t_st_improveftpperformance)
-   [Increase the timeout for large files using server-initiated transfer](../t_st_increaseftptimeout)
