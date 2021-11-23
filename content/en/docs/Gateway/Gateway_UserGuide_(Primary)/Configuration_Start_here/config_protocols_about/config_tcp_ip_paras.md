{
    "title": "Configuring TCP/IP parameters",
    "linkTitle": "TCP/IP parameters",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Configuration

This topic describes how to configure TCP ports for a file transfer protocol.

In this version of Gateway you enter port information in the *Port specification in server mode* pane.

**Former syntax:** If you have upgraded from a previous version, Gateway attempts to convert all previous TCP port configuration information. In certain cases, this is not possible. If the port configuration information cannot be converted, Gateway displays the port configuration information in the <span style="font-weight: bold;">[Port specification using former syntax](#Former_syntax)</span> field.

[About TCP ports](#About_TCP_ports)

[Configuring TCP ports](#Configuring_TCP_ports)

[Port specification using former syntax](#Former_syntax)

<span id="About_TCP_ports"></span>

## About TCP ports

TCP port numbers must be in decimal format and unique on the operating system. The TCP port associates an incoming TCP/IP connection request with the appropriate file transfer Application.

Default values:

-   6310 for PEL
-   6320 for PeSIT HS D
-   6330 for PeSIT HS E
-   6360 for OFTP
-   6370 for FTP
-   6380 for HTTP
-   6321 for SFTP
-   6382 for AS2
-   6373 for AS3
-   6386 for RosettaNet HTTP

### Additional information for TCP port configuration with FTP (and AS3)

When using FTP (and AS3), you can specify the ports that are used for control sessions. Optionally, you can separately define the dynamic data sessions in order to control the range of ports available for a session. To do this, you need to define a port configuration block that lists the available ports for a specific type of session.

A port configuration block comprises:

-   For the server - a control session port followed by the range of data connection ports that are used in passive mode
-   For a client - the range of data connection ports that are used in active mode

<span id="Configuring_TCP_ports"></span>

## Configuring TCP ports

When you configure a file transfer protocol in the configuration menu, the <span style="font-style: italic;">Port specification in server mode</span> pane displays the current TCP port configuration.

To change the TCP port configuration:

1.  Either:
    -   Add a new port specification by clicking <span style="font-weight: bold;">New</span>, or
    -   Modify an existing port specification by selecting the required row and clicking <span style="font-weight: bold;">Modify</span>

      
    Gateway opens the <span style="font-style: italic;">SAP parameters</span> window.
2.  Specify the TCP port(s) in the <span style="font-style: italic;">[SAP parameters](../config_sap_parameters)</span> window.
3.  Click OK.

### Using TCP ports below number 1024

#### Introduction

Although it is strongly discouraged, it is possible to configure a product to bind explicitly to local TCP port numbers below 1024. This allows you, for example, to replace TCP services shipped with the Operating System by the equivalent service provided by the product. A typical usage of this feature could be to replace the O/S FTP server by configuring the product FTP listen port to value 21.

When doing so, you must ensure that the corresponding O/S TCP service is disabled prior to starting the product.

TCP ports below 1024 (i.e. in the range 1-1023) are called privileged ports. Applications that use such port numbers are required to run under the root account (or to be allowed to switch to this account) for the O/S to accept socket systems services that set up the local end-points.

Allowing an application to run either permanently or temporarily as root can be achieved in two different ways, as follows:

-   Start the application under the root account.
-   Make root the owner of the executable files(s) and set the `suid` attribute bit for the file(s).

#### Recommended method

For the product to operate with privileged local TCP ports, we recommend using the "`suid bit`" method over the "start under root account" method. This ensures that the product runs by default under the user account switching to root only for socket system services that require such a privilege. These system services include:

-   `bind()`: Binds local address + port number pair to a socket.
-   `listen()`: Establishes the queue of incoming calls on a bound socket allowing connections from clients to be accepted.
-   `connect()`: Connect to a remote server.

#### Operating system dependencies

Some UNIX systems may allow the listen() service to succeed under a normal user account when the local end-point is bound to a privileged port, some others may require the application to run under the root account in the same situation. This difference may exist for the connect() system service. Since such a difference does not appear to be clearly documented, the product performs these system services under the root account when the local end-point is applied to a privileged TCP port.

Another difference applies to dynamically linkable libraries. Some UNIX systems may require all DLLs linked by the `suid` executable to be seen from the default library path.

#### Configuration

The executable files that may bind sockets to privileged local TCP ports include:

-   `p_tsd` : Generic TCP server daemon. This executable is started when the product is configured for dynamic TCP servers.
-   `p_ftpsock`: FTP protocol file transfer program.
-   `p_httpsock`: HTTP protocol file transfer program.

These files are located in the sub-directory `bin` of the product installation home directory.

Depending on the actual configuration of privileged ports and/or the use of dynamic servers or not, only part of those files may have to be set as `suid` from root. You may not, for example, set the `suid` bit for file transfer programs that are not configured for privileged local ports.

To allow a program to start as root, the following attribute changes are to be performed under the root account (example for file `bin/p_ftpsock`):

1.  Set owner root for the file: <span class="code">chown root bin/p\_ftpsock</span>.
2.  Set the `suid` bit on exec : `chmod +s bin/p_ftpsock`.

Depending on your UNIX O/S visibility requirements for dynamically linkable libraries, all such libraries needed for the executable must be set as visible giving the default library patch. This can be achieved using logical links as follows (example for the file <span class="code">obj/libtftools.so</span>):

-   Create a logical link to `libtftools.a in /usr/lib`:

`` ln -s `pwd`/obj/libtftools.a /usr/lib/libtftools.so ``

#### Sample configuration scripts.

A sample shell script that performs the required operations for all files that may have to bind sockets to privileged local ports is supplied. The pathname is <span class="code">run\_time/etc/socksuid.sh</span>.

This shell script can only succeed when run under the root account. It does not check the actual product configuration but performs all operations for both FTP and HTTP protocols to be allowed to bind to local privileged ports. This script is provided as an example. System administrators may check their content prior to running it and optionally comment-out any command that is not needed depending on the actual product configuration.

For example, if only FTP is configured for privileged local ports, all lines involving files for other protocols should be commented-out. To allow the installation of patches and service packs, the script has rollback support. This option requires the name of the user that owns the product installation (the file owner prior to running the script). In this situation, the script must also be run under the root account.

#### Under the hood.

This section describes how the product interacts with the different uids attached to a `suid` process when local privileged ports have been configured. These brief explanations are intended for security analyzing.

The program detects that it has been started from a non-root user account and `set-uid` to root by the condition of having the effective `user_id` equal to zero and the real `user_id` different from zero.

Since, by default, all the resources it may have to create must be owned by the `<real user-id>`, this program sets the `<effective user-id>` to the value of the <span class="code">&lt;real user-id></span> as soon as possible. This happens immediately after the main entry point. It has the advantage of preventing security problems since the program then runs with a non-root `<effective user_id>` value.

Due to the product having been configured to use privileged TCP port values, it may be necessary to switch the `<effective user-id>` to root (i.e . zero). For the attachment of such a port to be made possible, the following algorithm is used:

##### LISTEN to a privileged port

1.  Try to switch `<effective user-id>` to root (zero).
2.  Create a socket (using the socket() system service).
3.  Build the address argument to use on "bind" using the priviledged port value.
4.  Bind the socket and listen to it (using the bind() system service, then the listen() system service in this order).
5.  Revert the `<effective user-id>` to the `<real user-id>` value.

##### CONNECT from a privileged port (local port):

1.  Try to switch `<effective user-id>` to root (zero).
2.  Create a socket (using the socket() system service).
3.  Build the address argument to use on "bind" using the privileged port value.
4.  Bind the socket and connect to a remote (using the bind() system service, then the connect() system service in this order).
5.  Revert the `<effective user-id>` to the `<real user-id>` value.

Care has been taken for the program to ensure that (5) will executed when (1) succeeds.

Technically, the program uses the setreuid() system service in a way that ensures that either the `<saved user-id>` or the `<effective user-id>` is set to `<root user-id>` at any time, for the `<effective user-id>` to remain changeable to &lt;root user-id> when required (and switched back to `<real user-id value>` as soon as it is no longer required).

As a result, when `suid-root` starts, the program is basically running by default with `<effective user-id>` set to the value of the `<real user-id>`, and will switch temporarily the `<effective user-id>` to root only when it is required. Such behavior minimizes security issues and ensures that all other resources are created and/or accessed under the `<real user-id>` account (i.e. `<effective user-id>` set to `<real user-id>`.

<span id="Former_syntax"></span>

## Port specification using former syntax

This section describes the TCP port configuration displayed in the <span style="font-weight: bold;">Port specification using former syntax</span> field.

This field is only displayed if:

-   You configured TCP ports in a previous version of Gateway
-   You have upgraded to this version of Gateway
-   Gateway cannot convert the TCP port configuration information

### TCP port configuration using former syntax

If a protocol listens on more than one port, the port numbers are specified as follows:

-   single port: nnnn
-   list of ports: mmmm nnnn pppp
-   range of ports: mmmm:nnnn

A list of ports is separated by commas:

<span style="font-weight: bold;">     Addr1/Port1,Addr2/Port2, Addr3/Port3</span>

where <span style="font-weight: bold;">Addr(n)</span> designates an IP address and <span style="font-weight: bold;">Port(n)</span> designates a port specification. If you do not specify the address, the value of the IP address is taken.

For example:

<span style="font-weight: bold;">     9950</span>

<span style="font-weight: bold;">     9900 9920 9930</span>

     20000,1.72.10.5/21000:21002

### TCP port configuration with FTP using former syntax

The format and rules listed below define one, or several, port configuration blocks Ps(Ps1:Ps2)  (Pc1:Pc2)...

where:

-   Ps = port used for server control sessions
-   Ps(n) = range of ports used for data connections in server passive mode
-   Pc(n)= range of ports used for data connections in client active mode

The following conventions are used when specifying control session ports in FTP:

-   A space is used between the port configuration blocks, for example between <span style="font-weight: bold;">Ps(Ps1:Ps2)</span> and <span style="font-weight: bold;">(Pc1:Pc2)</span>
-   No space is used between the server port and the port range listed in parentheses, <span style="font-weight: bold;">Ps(Ps1:Ps2)</span>
-   No space is used for a range of ports for a session in parentheses <span style="font-weight: bold;">(Pc1:Pc2)</span>
-   Client ports, which are used in the active mode, are not attached to a control session port

### Examples using former syntax

#### Example 1: Classic configuration

This example displays a simple and effective FTP port configuration. Note the spaces between block units.

6370(8000:8010)  6470(8000:8010)  (8000:8010)

-   6370 = server listening port for FTP control sessions
-   6470 = secondary listening port, for example for an SSL secured session
-   (8000:8010) = this port range is used for data connections in server passive mode attached to a session established on port 6370 or 6470, as well as data connections in client active mode

#### Example 2

This example displays an alternate use of port configuration blocks.

6370(8000:8010)  6470(8011:8020)  (8021:8030)

-   6370 = server listening port for FTP control sessions
-   (8000:8010) = port range for data connections in server passive mode, attached to a session established on port 6370
-   6470 = secondary listening port, for example for an SSL secured session
-   (8011:8020) = secondary port range for data connections in server passive mode, attached to a session established on port 6470
-   (8021:8030) = range of ports for data connections in client active mode

#### Example 3

It is important to note in this example that there is a space between the listening port and the data connection port range. This space separates the two elements into two block entities, so that the range is a separate block and not the range for port 6370.

6370  (8021:8030)

-   6370 = server listening port for FTP control sessions. Note that when in passive mode, the server listens on any port for data sessions
-   (8021:8030) = range of ports for data connections in client active mode

Related topics

[TCP advanced options](../config_tcp_adv_options)

[Configuring protocols](../config_protocols)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
