{
    "title": "FTP server messages",
    "linkTitle": "FTP server messages",
    "weight": "110"
}FTP server messages are messages displayed to users at the startup of an FTP session. Two types of startup FTP server messages are available:

-   <a href="#Create" class="MCXref xref">Create or edit the server connect message</a>
-   <a href="#Create_edit" class="MCXref xref">Create or edit the server ready message</a>

Users might or might not see FTP server messages, depending on the software they use to connect to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Most FTP client applications display these messages, but they are not displayed on browser clients. Users downloading a single file by URL from a browser might not see these messages.

Startup messages are displayed while a connection to the server is being established, prior to any login prompt. A message is displayed to the user when the connection is established. A server ready message also be displayed when <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is ready to accept a login. The default message displays the host name of the server and the server version, but this can be overridden.

<span id="Create"></span>

## Create or edit the server connect message

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *Server Start up Messages:*  
    1.  Select **Enable Message on FTP Server Connect** to display a message to users logging onto <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> through the FTP Server. By default, this option is not selected.
    2.  In the **FTP Connect Message** field, type the message you want to be displayed when a user connects to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server
3.  Click **Save** to apply the changes.

<span id="Create_edit"></span>

## Create or edit the server ready message

1.  Select **Setup > FTP Settings** to open the *FTP Settings* page.
2.  Under *Server Start up Messages:*
    1.  Select **Enable Message on FTP Server ready** to display a message indicating that the server is ready to accept logins. By default, this option is not selected.
    2.  In the **FTP Ready Message** field, type the message you want to be displayed when the server is ready.
3.  Click **Save** to apply the changes.

 

**Related topics:**

-   <a href="../t_st_ftpactivemode" class="MCXref xref">Set up FTP active mode</a>
-   <a href="../t_st_ftppassivemode" class="MCXref xref">Set up FTP passive mode</a>
-   <a href="../r_st_ftpserverlimitations" class="MCXref xref">FTP server limitations</a>
-   <a href="../t_st_improveftpperformance" class="MCXref xref">Improve FTP performance on a multi-homed system</a>
-   <a href="../t_st_increaseftptimeout" class="MCXref xref">Increase the timeout for large files using server-initiated transfer</a>
