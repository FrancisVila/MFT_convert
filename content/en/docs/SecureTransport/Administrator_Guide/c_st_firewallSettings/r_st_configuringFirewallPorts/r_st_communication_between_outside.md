{
    "title": "Communication between the outside and SecureTransport Edge",
    "linkTitle": "Communication between the outside and SecureTransport Edge",
    "weight": "290"
}These ports must be opened on your external firewall to allow communication between the outside world and your proxy (SecureTransport Edge) server.

-   20 – FTP (secure and non-secure) active-mode data channel
-   21 – FTP (secure and non-secure) control channel (For secure connections, the firewall must allow bidirectional communication.)
-   22 – SSH (SFTP and SCP)
-   80 – HTTP
-   443 – HTTPS
-   444 – Administration Tool (HTTPS)
-   10080 – AS2 (non-SSL)
-   10443 – AS2 (SSL)
-   17617 – PeSIT (non-SSL)
-   17627 – PeSIT over secure socket (non–Transfer CFT compatible)
-   17637 – PeSIT over secure socket (CFT compatible)
-   19617 - PeSIT over pTCP plain socket
-   19627 - PeSIT over pTCP Secured Socket
-   User-defined range – FTP (secure and non-secure) passive-mode data channel

**Related topics:**

-   <a href="../r_st_communication_between" class="MCXref xref">Communication between SecureTransport Server and SecureTransport Edge</a>
-   <a href="../r_st_communication_between_server_internal_network" class="MCXref xref">Communication between SecureTransport Server and an internal network</a>
-   <a href="../r_st_internal_communication" class="MCXref xref">Internal SecureTransport communication</a>
