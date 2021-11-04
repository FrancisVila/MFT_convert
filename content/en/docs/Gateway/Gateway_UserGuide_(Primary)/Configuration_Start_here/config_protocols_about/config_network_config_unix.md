{
    "title": "Network configuration for UNIX platforms",
    "linkTitle": "Network configuration: UNIX",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

This topic provides information about configuring protocols on UNIX platforms for the following network interfaces:

-   [TCP/IP](#TCP_IP)
-   [SNA LU 6.2](#SNA_LU62)

<span id="TCP_IP"></span>

## TCP/IP

Gateway supports TCP/IP transport for the following protocols:

-   FTP
-   HTTP
-   SFTP
-   SMTP
-   POP3
-   EDIINT
-   RosettaNet
-   PeSIT
-   OFTP (Odette)
-   PEL

To use TCP/IP transport with a protocol, you must indicate:

-   The hostname (or IP address)
-   The port number to use to route incoming calls to that protocol

Assign a different port number to each Gateway protocol configured for TCP/IP. Make sure that no other application running on your system uses these port numbers.

It is recommended that you select port numbers within the range 5000...32760. Each value must be used once only on the system. If you are currently using an X11 graphic display on your system, or intend to do so, do not select port number 6000 since the X Server uses this port number to listen to X client connections.

For more information, refer to the <span style="font-style: italic;"><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> Configuration Guide (UNIX)</span>.

<span id="SNA_LU62"></span>

## SNA LU 6.2

Gateway support for LU 6.2 communications is not available on LINUX platforms.

A separate Gateway process handles each LU 6.2 session. Gateway starts processes that handle requester sessions. For server sessions, you must define transaction programs (TP) in the LU 6.2 sub-system. This sub-system is responsible for starting a Gateway LU 6.2 server process on each incoming connection.

For more information, refer to the <span style="font-style: italic;"><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> Configuration Guide (UNIX)</span>.

Related topics

[Configuring protocols](../config_protocols)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
