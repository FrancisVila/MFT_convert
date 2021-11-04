{
    "title": "Use the operating system to monitor SecureTransport processes",
    "linkTitle": "Use the operating system to monitor SecureTransport processes",
    "weight": "180"
}As an alternative to the Monitor server, you can monitor the state of specific processes using operating system tools.

There are two categories of processes, those that implement file transfer and related functions and those that implement the administrative functions. You need to know their process IDs to monitor them.

The following topics describe the file transfer and admin processes:

-   <a href="#File" class="MCXref xref">File transfer processes</a>
-   <a href="#Admin" class="MCXref xref">Admin processes</a>

**Related topics:**

-   <a href="#" class="MCXref xref">Manage server operations</a>
-   <a href="#" class="MCXref xref">Manage the FTP server</a>
-   <a href="#" class="MCXref xref">Manage the HTTP server</a>
-   <a href="#" class="MCXref xref">Manage the AS2 server</a>
-   <a href="#" class="MCXref xref">Manage the SSH server</a>
-   <a href="#" class="MCXref xref">Manage the PeSIT server</a>
-   <a href="#" class="MCXref xref">Manage the Transaction Manager server</a>
-   <a href="#" class="MCXref xref">Manage the Proxy server on SecureTransport Edge</a>
-   <a href="../t_st_monitorserver" class="MCXref xref">Monitor server</a>

<span id="File"></span>

## File transfer processes

For file transfer, there are six parent processes to monitor:

-   java – AS2 proxy server
-   java – FTP server
-   java – HTTP server
-   java – PeSIT server
-   java – SSH server
-   java – Transaction Manager server
-   mysqld – Embedded database server, when used

The first five processes all interact with the Transaction Manager server.

The process IDs for each for these processes can be found in `<FILEDRIVEHOME>/var/run`. The files are called:

-   `as2d.pid`
-   `ftpd.pid`
-   `httpd.pid`
-   `pesitd.pid`
-   `sshd.pid`
-   `tm-java.pid`
-   `db.pid`

<span id="Admin"></span>

## Admin processes

For administration functions, there is one parent processes to monitor:

-   java – Tomcat Admin server

It interacts with the file transfer processes by manipulating configuration and performing signaling.

The process ID for this process can be found in `<FILEDRIVEHOME>/var/run/admin/tomcat.pid`.
