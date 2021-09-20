{
    "title": "User limits",
    "linkTitle": "User limits",
    "weight": "260"
}Use user limit entries to limit the number of concurrent users who can connect to the SecureTransport FTP and HTTP servers. The limit you define applies to each protocol server, if you limit the users from a user class to 10, 10 users can connect concurrently to the FTP server and 10 can connect to the HTTP server. You can also specify a time range and days of the week to apply the limit.

If your SecureTransport deployment includes SecureTransport Edge servers in a peripheral network (DMZ) and if you need different user limits for users who connect using SecureTransport Edge and using SecureTransport Server, you can configure user limits differently. For example, you can allow access to users who connect to SecureTransport Server from your internal network during a time you restrict access to users who connect using SecureTransport Edge.

SecureTransport applies all user limits defined for all users or for the user class that the user is in. If no user limit applies to the user, the user can connect to the FTP and HTTP servers. However, connections might be limited by licenses or hardware or network capacity.

User limits do not apply to protocol servers other than FTP and HTTP.

The following topic describes how to manage user limits:

-   [Manage user limits](t_st_userlimits) - Provide how-to instructions for managing user limits.
