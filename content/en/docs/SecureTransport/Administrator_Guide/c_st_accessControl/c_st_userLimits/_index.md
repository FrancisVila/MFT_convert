{
    "title": "User limits",
    "linkTitle": "User limits",
    "weight": "250"
}Use user limit entries to limit the number of concurrent users who can connect to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> FTP and HTTP servers. The limit you define applies to each protocol server, if you limit the users from a user class to 10, 10 users can connect concurrently to the FTP server and 10 can connect to the HTTP server. You can also specify a time range and days of the week to apply the limit.

If your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment includes <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers in a peripheral network (DMZ) and if you need different user limits for users who connect using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, you can configure user limits differently. For example, you can allow access to users who connect to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server from your internal network during a time you restrict access to users who connect using <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> applies all user limits defined for all users or for the user class that the user is in. If no user limit applies to the user, the user can connect to the FTP and HTTP servers. However, connections might be limited by licenses or hardware or network capacity.

User limits do not apply to protocol servers other than FTP and HTTP.

The following topic describes how to manage user limits:

-   <a href="t_st_userlimits" class="MCXref xref">Manage user limits</a> - Provide how-to instructions for managing user limits.
