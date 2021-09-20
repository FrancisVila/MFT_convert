{
    "title": "What information is synchronized",
    "linkTitle": "What information is synchronized",
    "weight": "140"
}SecureTransport
Edge synchronization moves configuration data from the primary
SecureTransport Edge server to all the SecureTransport Edge secondary servers only. SecureTransport does not support moving
data from secondary servers to the primary server or from
the primary server to selected secondary servers.

The following information is synchronized dynamically from the primary SecureTransport Edge server to the secondary SecureTransport Edge servers when you change it on the
primary server:

-   All server configuration parameters that are not local to the server

The following information is also synchronized during manual synchronization:

-   All configuration files listed in the `<FILEDRIVEHOME>/conf/sync.conf` file
-   All database tables listed in the `<FILEDRIVEHOME>/conf/sync_tables.conf` file

The files listed in `<FILEDRIVEHOME>/conf/sync.excl` are not copied from the primary to the secondary server.
