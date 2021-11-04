{
    "title": "Using RAS ",
    "linkTitle": "Using RAS",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

For Windows platforms only.

This topic describes how to use Microsoft Remote Access Service Networking (RAS) with Gateway.

[Enabling RAS](#Enabling)

[Customizing RASPPP.ini](#Customizing_RASPPP_ini)

[How Gateway makes a connection using RAS](#How_GW_makes_RAS_connection)

[Common errors and troubleshooting](#Troubleshooting)

<span id="Enabling"></span>

## Enabling RAS

One of the network interfaces supported by Gateway is the dial-up connection. This facility is implemented using Microsoft Remote Access Service Networking (RAS) on Windows platforms.

To enable this facility in Gateway:

1.  Install MS dial-up networking service.
2.  Define remote PPP servers in MS dial-up networking phone book.
3.  Configure Gateway file transfer protocols with TCP/IP networking.
4.  [Customize the Gateway <span class="code">RASPPP.ini</span> file](#Customizing_RASPPP_ini).
5.  Configure Gateway Remote Sites to use RAS connections.  
    Refer to [Site objects: Address configuration for Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/site_objects_address_config#RAS).

<span id="Configuring_RAS"></span>

### Configuring RAS

For details on how to install RAS and add RAS phone book entries, refer to the Microsoft RAS documentation.

For each remote PPP server, define an RAS networking phone book entry. This entry contains parameters such as phone line number, modem and server settings.

<span id="Customizing_RASPPP_ini"></span>

## Customizing RASPPP.ini

Gateway uses a text file named <span class="code">RASPPP.INI</span> (in the usual Windows INI file format) to bind itself to the RAS service. In the <span class="code">RASPPP.INI</span> file, each remote PPP server is defined as an INI file section.

During Gateway installation, a default <span class="code">RASPPP.INI</span> is copied to the <span class="code">&lt;Gateway installation directory>\\run\_time\\etc\\</span> directory. Customize this file depending on your RAS configuration before you run Gateway.

#### Sample RASPPP.INI file


    ;
    ; See <Gateway installation directory>\help\srvcfgen.hlp for more information
    ;
    ;==================================================================================
    ;
    ; [*links*] section for internal usage
    ;
    ; Max= maximum simultaneous RAS connections (decimal value, default is 4)
    ; Share= share RAS link with other applications (boolean: 0=NO, 1=YES, default is 0)
    ; KeepAlive= keep connection active on end of transfer (boolean: 0=NO, 1=YES, default is 0)
    ; Force= close all connections on program exit (boolean: 0=NO, 1=YES, default is 0)
    ;
    ;==============================================================================
    [*links*]
     
    Max=4
    Share=1
    KeepAlive=0
    Force=0
    ;==============================================================================
    ; User section Samples:
    :
    ; [Destination]
    ; LinkEntry= RAS networking phone book entry name (mandatory)
    ; Phoneno= phone number (optional if Linkentry is specified)
    ; Server= server where user credentials are to be validated (optional)
    ; USERNAME= logon user name (optional for NT, mandatory for W9.x)
    ; PASSWORD= logon user password (optional for NT, mandatory for W9.x)
    ;
    ; =============================================================================
     
    [PARIS]
    linkentry=PARIS
    Phoneno=
    Server=
    USERNAME=DUPONT
    PASSWORD=BONJOUR
     
    [LONDON]
    linkentry=
    Phoneno=
    Server=
    USERNAME=SMITH
    PASSWORD=HELLO

Each section is defined with the following parameters:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>[xxxxxxx]</p>         </td>
         <td><p>INI file section header. It represents an RAS destination for Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Linkentry</p>         </td>
         <td><p>Mandatory</p>
<p>RAS phone book entry to use.</p>         </td>
      </tr>
      <tr>
         <td><p>Phoneno</p>         </td>
         <td><p>Optional</p>
<p>Phone number to dial. If you do not specify this parameter, the parameter defined in RAS phone book entry is used. For purposes of consistency, it is recommended that you leave this parameter blank and use the RAS phone book entry definition.</p>         </td>
      </tr>
      <tr>
         <td><p>Username</p>         </td>
         <td><p><span style="font-style: italic;">Mandatory on Windows 9.x, optional on Windows NT</span></p>
<p>Login user name for the remote host. If not specified, the current login credentials are used.</p>         </td>
      </tr>
      <tr>
         <td><p>Password</p>         </td>
         <td><p>Mandatory on Windows 9.x, optional on Windows NT</p>
<p>Login user password for the remote host. If not specified, the current login credentials are used.</p>         </td>
      </tr>
      <tr>
         <td><p>Server</p>         </td>
         <td><p>Windows NT only</p>
<p>Optional</p>
<p>Computer where login credentials are validated. If not specified, the dialed-up PPP server is used.</p>         </td>
      </tr>
   </tbody>
</table>

Apart from the destination sections(s), <span class="code">RASPPP.INI</span> also has a <span class="code">\[\*links\*\]</span> section, where parameters governing the program behavior are defined.

\[\*links\*\]

Max=4

Share=0

KeepAlive=0

Force=0

where:

-   <span style="font-weight: bold;">\[\*links\*\]</span> is a reserved system section
-   <span style="font-weight: bold;">Max</span> = Maximum number of simultaneous RAS connections.  
    A decimal value up to 64. Default = 4.
-   <span style="font-weight: bold;">Share</span> = Share RAS connections with other applications. A Boolean value:
    -   <span style="font-weight: bold;">0 = NO</span> (default): If <span style="font-weight: bold;">Share=0</span> and the required port (modem) is in use by another application, the connection request is refused.
    -   <span style="font-weight: bold;">1 = YES</span>: If <span style="font-weight: bold;">Share=1</span>, the connection is considered valid and the file transfer is carried out over this pre-established link. You should only select this option if the external application and Gateway share the same PPP server.
-   <span style="font-weight: bold;">KeepAlive</span> = Keep the RAS connection open after file transfer. A Boolean value:
    -   <span style="font-weight: bold;">0 = NO</span> (default): If <span style="font-weight: bold;">KeepAlive=0</span>, the connection is closed when the file transfer is ended.
    -   <span style="font-weight: bold;">1 = YES</span>: If <span style="font-weight: bold;">KeepAlive=1</span>, the connection remains open until the end of the program or until it is terminated by an external factor. A connection is closed if, and only if, it was opened by Gateway. So even if KeepAlive=1, connections opened by an external application are never closed on end of transfer.
-   <span style="font-weight: bold;">Force</span> = Close all active connections on program exit. A Boolean value:
    -   <span style="font-weight: bold;">0 = NO</span> (default): If <span style="font-weight: bold;">Force=0</span>, only connections that were opened by Gateway are closed.
    -   <span style="font-weight: bold;">1 = YES</span>: If <span style="font-weight: bold;">Force=1</span>, all active connections are closed on program exit (including those established by a foreign application).

<span id="How_GW_makes_RAS_connection"></span>

## How Gateway makes a connection using RAS

When you initiate an outgoing TCP/IP transfer, the software checks the destination network address. If it begins with \[xxxxxxxx\], an RAS destination is assumed. \[xxxxxxxx\] is extracted and used to retrieve further information from <span class="code">RASPPP.INI</span>. The Linkentry, Username and Password are then passed to RAS networking to dial up the remote PPP server. If the dial-up succeeds, or the connection was already established and is still active, subsequent TCP/IP transfers are performed on this connection. If it fails, the connection request is refused. When a transfer is ended, the connection reference count is updated. If no connection reference is active, the RAS connection is closed. (Assume KeepAlive=0).

This algorithm allows for multiple parallel TCP/IP transfers over an RAS connection. The RAS connection can also be established outside Gateway, as long as it designates the same PPP server as that expected by Gateway. In this case, it is also the responsibility of this foreign application to maintain and terminate the RAS connection. If the foreign application closes the RAS connection while the Gateway transfer is still in progress, the transfer is aborted.

<span id="Troubleshooting"></span>

## Common errors and troubleshooting

#### RAS never dials, in spite of a network address starting with \[xxxxxxxx\]

Check that <span class="code">RASAPI32.DLL</span> is on the Windows system directory and is accessible. This is the system DLL that Gateway uses to access RAS services. Its absence disables RAS features in Gateway.

If <span class="code">RASAPI32.DLL</span> is present, check that the <span class="code">p\_ras\_cfg</span> environment variable points to a correct <span class="code">RASPPP.INI</span> file (by default and unless otherwise modified, <span class="code">p\_ras\_cfg = &lt;Gateway installation directory>\\run\_time\\etc\\RASPPP.INI</span>). Then ensure that the requested \[xxxxxxxx\] exists and is defined with appropriate parameters.

If <span style="font-weight: bold;">Shared=0</span>, check that the port is not in use by another application.

Additional diagnostic messages are also available in the Gateway log file and standard error output file: <span class="code">&lt;Gateway installation directory>\\run\_time\\tmp\\TCP\_xxxx.out</span>.

#### RASDial / Cannot find phone book entry

Check that RAS networking is functioning correctly. Use the RAS networking dial-up dialog to start an RAS connection manually with the same RAS phone book entry as that defined in the &lt;linkentry=> parameter.

#### RASDial / Hardware failure in port or attached device

The modem may be out of service or off line.

#### RASDial / There is no dial tone

The modem may not be attached to the network.

#### RASDial / Line is busy

The line called is busy or not responding.

#### RASDial / Your modem (or other connecting device) reported an error

The modem may be out of order. Turn the modem off and on again and then retry.

If there is dial-up tone but error persists, the remote PPP server may not be started.

#### RASDial / The port is already in use or is not configured for dial out

#### RASDial / The port is not available

The port is either already used by another application process or is not configured for outgoing connections. Check that the port is configured for outgoing calls. Multiple applications may share the same port (line), so the first case may not be an error.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
