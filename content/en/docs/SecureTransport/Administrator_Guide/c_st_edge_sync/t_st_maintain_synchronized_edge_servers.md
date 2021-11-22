{
    "title": "Maintain synchronized SecureTransport Edge servers",
    "linkTitle": "Maintain synchronized SecureTransport Edge servers",
    "weight": "160"
}As long as your synchronized {{< SecureTransport/componentshortname  >}} Edge servers meet the requirements for
synchronization, you can make changes to the group, such as:

-   Change the primary server (manually failing over the primary server to another
    server or restoring a server to its role as primary server)
-   Add a server
-   Remove a server

The key requirement is that the `<FILEDRIVEHOME>/lib/admin/config/servers`
configuration file is correct and identical on all servers and that only the primary server
has a `<FILEDRIVEHOME>/var/tmp/sentinel_primary` file.

1.  Stop all the {{< SecureTransport/componentshortname >}} Edge servers.
2.  If you are adding or removing a secondary server, update the
    `<FILEDRIVEHOME>/lib/admin/config/servers` file on the primary server and copy
    the servers file to all the {{< SecureTransport/componentshortname >}} Edge server systems.
3.  If you are changing the primary server, list it as the first line in the
    `<FILEDRIVEHOME>/lib/admin/config/servers` file on the primary server, copy the
    `servers` file to all the {{< SecureTransport/componentshortname >}} Edge server systems, delete the
    `<FILEDRIVEHOME>/var/tmp/sentinel_primary` file on the previous primary server,
    and create the `<FILEDRIVEHOME>/var/tmp/sentinel_primary` file on the new
    primary server.
4.  Restart all the {{< SecureTransport/componentshortname >}} Edge servers.
5.  Log in to the Administration Tool and
    manually synchronize the servers.
