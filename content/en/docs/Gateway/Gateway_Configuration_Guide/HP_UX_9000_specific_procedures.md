{
    "title": "HP UX 9000 specific procedures",
    "linkTitle": "HP UX 9000 specific procedures",
    "weight": "30"
}{
"title": "AIX specific procedures",
"linkTitle": "AIX specific procedures",
"weight": "20"
}This chapter provides information specific to AIX platforms.
## Basics

<table>
   <tbody>
      <tr>
         <td><p><strong>Options available with AIX systems</strong></p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for AIX supports COMMUNICATION SERVER 5 SNA LU 6.2 Services through the CPIC programming interface.</p>         </td>
      </tr>
   </tbody>
</table>

## TCP/IP network interface configuration
To work with TCP/IP, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires the following information:
- The \*\*local port numbers\*\* where <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> listens in order to receive incoming connections.
You must assign a different port number to each configured file transfer protocol. Make sure that these port numbers are not currently in use, and that no application on the system will try to use them during operation. It is recommended that you select port numbers in the range \*\*5000\*\* to \*\*65000\*\*. Configure the port numbers in the configuration menu and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.
- Either a \*\*host name\*\* or \*\*IP address\*\* to use as authoritative host for incoming connections.
Use one of the following:
- The host name of the local machine
- The looped address (localhost or 127.0.0.1)
- An empty address
<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Site objects group all parameters that apply to outgoing connections. For each remote machine and each configured file transfer protocol, you must create a Site object where you supply the TCP/IP address and port number that the remote machine expects for that protocol. To create <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Sites, use either the Windows GUI or the peladm line command.
### Example
The following example creates a Site using the command <span class="code">peladm create\\\_site</span> for a Site in PHSE protocol at dotted IP address <span class="bold_in_para">193.56.234.50</span> and port number <span class="bold_in_para">22001</span>:
peladm create\_site  -pr PHSE  -a SITE1  -pi SITE1
                    -da 193.56.234.50/22001
You can specify either the host name (when using DNS facilities), or the IP dotted address (such as 193.56.234.50) as the IP destination address fields for Sites to which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> connects over TCP/IP.
## LU 6.2 network interface configuration
### Basics

<table>
   <tbody>
      <tr>
         <td><p>Hardware and software prerequisites</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> can communicate over LU 6.2 conversations using either SNA SERVER version 3 or COMMUNICATION SERVER version 5 SNA sub-systems.</p>         </td>
      </tr>
      <tr>
         <td><p>Configuring <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for CS5</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires AIX operating system version 5.1 or higher to support COMMUNICATION SERVER 5.</p>         </td>
      </tr>
   </tbody>
</table>

### Configuring SNA connectivity
A complete description of SNA connectivity configuration is beyond the scope of this document. Configurations can vary greatly depending on the topology of the SNA network. You can use the X-motif user interface <span class="bold_in_para">xsnaadmin</span> to configure SNA connectivity on your system.
To configure SNA connectivity, you define the following SNA configuration items:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">SNA configuration item         </th>
<th class="HeadD-Column1-Header1">Definition (xsnaadmin menu items)         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>local node</p>
<p>(characteristics)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>Node parameters</p>         </td>
      </tr>
      <tr>
         <td><p>port</p>
<p>(for each hardware interface)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>New Port</p>         </td>
      </tr>
      <tr>
         <td><p>link station</p>
<p>(for each adjacent host)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>Link Station</p>         </td>
      </tr>
   </tbody>
</table>

These configuration parameters are stored in the <span class="code">/etc/sna/sna\\\_domn.cfg</span> file.
For a description of SNA connectivity parameters, refer to the related AIX Communication Server 5 documentation.
The following examples of a sample<span class="code"> sna\\\_domn.cfg</span> file illustrate some of the parameters involved in the SNA connectivity configuration data.
#### Example of local node configuration
&gt; \[define\_node\]
&gt; cp\_alias = PXRS10
&gt; description = ""
&gt; fqcp\_name = SOPRA.PXRS10
&gt; node\_type = NETWORK\_NODE
&gt; mode\_to\_cos\_map\_supp = NO
&gt; mds\_supported = YES
&gt; node\_id = &lt;0710000f>
&gt; max\_locates = 1500
&gt; dir\_cache\_size = 255
&gt; max\_dir\_entries = 0
&gt; locate\_timeout = 0
&gt; reg\_with\_nn = YES
&gt; reg\_with\_cds = YES
&gt; mds\_send\_alert\_q\_size = 100
&gt; cos\_cache\_size = 24
&gt; tree\_cache\_size = 40
&gt; tree\_cache\_use\_limit = 40
&gt; max\_tdm\_nodes = 0
&gt; max\_tdm\_tgs = 0
&gt; max\_isr\_sessions = 1000
&gt; isr\_sessions\_upper\_threshold = 900
&gt; isr\_sessions\_lower\_threshold = 800
&gt; isr\_max\_ru\_size = 16384
&gt; isr\_rcv\_pac\_window = 8
&gt; store\_endpt\_rscvs = NO
&gt; store\_isr\_rscvs = NO
&gt; store\_dlur\_rscvs = NO
&gt; dlur\_support = YES
&gt; pu\_conc\_support = YES
&gt; nn\_rar = 128
&gt; max\_ls\_exception\_events = 0
&gt; ms\_support = NORMAL
&gt; queue\_nmvts = YES
&gt; ptf\_flags = NONE
#### Example of link station definition
&gt; \[define\_qllc\_ls\]
&gt; ls\_name = LYRS04
&gt; description = ""
&gt; port\_name = QLLCP0
&gt; adj\_cp\_name = SOPRA.RS04
&gt; adj\_cp\_type = NETWORK\_NODE
&gt; dspu\_services = NONE
&gt; dspu\_name = &lt;0000000000000000>
&gt; dlus\_name = &lt;0000000000000000000000000000000000>
&gt; bkup\_dlus\_name = &lt;0000000000000000000000000000000000>
&gt; local\_node\_id = &lt;00000000>
&gt; adj\_node\_id = &lt;00000000>
&gt; vc\_type = SVC
&gt; address = 9690002
&gt; pvc\_id = 1
&gt; max\_send\_btu\_size = 265
&gt; ls\_attributes = SNA
&gt; cp\_cp\_sess\_support = YES
&gt; default\_nn\_server = YES
&gt; hpr\_supported = NO
&gt; auto\_act\_supp = NO
&gt; tg\_number = 0
&gt; limited\_resource = NO
&gt; solicit\_sscp\_sessions = NO
&gt; pu\_name = &lt;0000000000000000>
&gt; disable\_remote\_act = NO
&gt; link\_deact\_timer = 30
&gt; use\_default\_tg\_chars = YES
&gt; effect\_cap = 9600
&gt; connect\_cost = 0
&gt; byte\_cost = 0
&gt; security = SEC\_PUBLIC\_SWITCHED\_NETWORK
&gt; prop\_delay = PROP\_DELAY\_PKT\_SWITCHED\_NET
&gt; user\_def\_parm\_1 = 128
&gt; user\_def\_parm\_2 = 128
&gt; user\_def\_parm\_3 = 128
&gt; target\_pacing\_count = 7
&gt; ls\_role = USE\_PORT\_DEFAULTS
&gt; max\_ifrm\_rcvd = 0
&gt; dlus\_retry\_timeout = 0
&gt; dlus\_retry\_limit = 0
&gt; need\_vrfy\_fixup = NO
&gt; initially\_active = NO
&gt; react\_timer = 30
&gt; react\_timer\_retry = 65535
&gt; req\_rev\_charge = NO
&gt; loc\_wsize = 0
&gt; rem\_wsize = 0
&gt; retry\_limit = 2
&gt; retry\_timeout = 8
&gt; loc\_packet = DEFAULT
&gt; rem\_packet = DEFAULT
&gt; idle\_timeout = 48
&gt;  
&gt; cud =
&gt; rx\_thruput\_class = DEFAULT
&gt; tx\_thruput\_class = DEFAULT
&gt; cugo = NO
&gt; cug = NO
&gt; cug\_index = 0
&gt; nuid = &lt;&gt;
### Configuring APPC/CPIC resources
<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses the CPIC programming Interface to communicate over SNA networks. In CS5, this API is based on the APPC interface. The following APPC resources enable <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to operate with SNA:
- Local LU
- Partner LU (on remote node)
- Mode
- Remote Node (if needed)
- Transaction programs
- CPIC side information
You must define:
- At least one resource of each type (with the possible exception of Remote Node), to allow <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to operate as both initiator and responder
- CPIC-side information to allow <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to initiate connections to a remote machine
- A transaction program for PeSIT E protocol to allow the SNA sub-system to start the appropriate <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> program on incoming conversations
Use the following menu entries from <span class="bold_in_para">xsnaadmin</span> to configure these items:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Resource         </th>
<th class="HeadD-Column1-Header1">xsnaadmin menu items         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local LU</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Independent Local LU</p>         </td>
      </tr>
      <tr>
         <td><p>Remote Node</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Remote Node</p>         </td>
      </tr>
      <tr>
         <td><p>Partner LU</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Partner LU</p>
<p>Partner LU on Remote Node</p>         </td>
      </tr>
      <tr>
         <td><p>Modes</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>Modes</p>         </td>
      </tr>
      <tr>
         <td><p>Transaction Programs</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>Transaction Programs</p>         </td>
      </tr>
      <tr>
         <td><p>CPIC Side Info</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>CPIC</p>         </td>
      </tr>
   </tbody>
</table>

Local LU, partner LUs and mode definitions are stored in <span class="code">/etc/sna/sna\\\_node.cfg</span>.
Transaction Program definitions are stored in <span class="code">/etc/sna/sna\\\_tps</span>.
CPIC Side Info profiles are stored in <span class="code">/etc/sna/sna\\\_domn.cfg</span>.
#### Defining local LU
<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> can use a single local LU for both outgoing and incoming conversations. However, this type of configuration is not recommended.
For example, you can define sets of local LUs for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as follows:
- <span class="bold_in_para">LPHE</span>:local LU for both incoming and outgoing conversations
or
- <span class="bold_in_para">LPHEI</span>: local LU for incoming conversations only
- <span class="bold_in_para">LPHEO</span>: local LU for outgoing conversations only
#### Example of local LU definition
This is is an extract from <span class="code">/etc/sna/sna\\\_node.cfg</span>:
&gt; \[define\_local\_lu\]
&gt; lu\_alias = PHSEI
&gt; list\_name = ""
&gt; description = ""
&gt; lu\_name = PHSEI
&gt; lu\_session\_limit = 0
&gt; pu\_name = &lt;0000000000000000>
&gt; nau\_address = 0
&gt; default\_pool = NO
&gt; syncpt\_support = NO
&gt; lu\_attributes = NONE
&gt; sscp\_id = 0
&gt; disable = NO
&gt; sys\_name = ""
&gt; timeout = 60
&gt; back\_level = NO
#### Defining partner LU
You must define a partner LU for each <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Remote Site. To enable <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to connect to that Site, you must also create a CPIC side info profile that points to that partner LU. For more information on CPIC side info profile creation, see <a href="#CPIC_side_info_AIX" class="MCXref xref">Defining CPIC side info</a>. When you create a partner LU name, you supply the fully qualified partner LU name.
#### Example of partner LU definition
This is an extract from <span class="code">/etc/sna/sna\\\_node.cfg</span>:
&gt; \[define\_partner\_lu\]
&gt; plu\_alias = RS04
&gt; description = ""
&gt; fqplu\_name = SOPRA.RS04
&gt; plu\_un\_name = RS04
&gt; parallel\_sess\_supp = YES
&gt; appcip\_routing\_preference = NATIVE
&gt; max\_mc\_ll\_send\_size = 0
&gt; conv\_security\_ver = NO
#### Defining mode
You must define all modes used for LU 6.2 conversations on all nodes intended to communicate over LU 6.2 (local and remote nodes, as seen from the local machine). A simple LU 6.2 configuration for a monitor that uses the same mode for all LU 6.2 conversations is possible, but not required. When a single set of mode parameters is not suitable for all LU 6.2 conversations, you can create several modes.
#### Example of mode definition
This is an extract from <span class="code">/etc/sna/sna\\\_node.cfg</span>:
&gt; \[define\_mode\]
&gt; mode\_name = PHSEMODE
&gt; description = ""
&gt; max\_neg\_sess\_lim = 32767
&gt; plu\_mode\_session\_limit = 2
&gt; min\_conwin\_src = 1
&gt; min\_conloser\_src = 0
&gt; auto\_act = 0
&gt; receive\_pacing\_win = 4
&gt; max\_receive\_pacing\_win = 0
&gt; default\_ru\_size = YES
&gt; max\_ru\_size\_upp = 1024
&gt; max\_ru\_size\_low = 0
&gt; cos\_name = #CONNECT
<span id="CPIC_side_info_AIX"></span>
#### Defining CPIC side info
You must create a CPIC side info profile for each Remote Site to which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> may initiate LU 6.2 conversations. Apart from the CPIC side info profile, you must also create the corresponding Site object. You can create these objects in any order, but the CPIC side info profile that addresses a given Remote Site must exist when <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> attempts to connect to this Site.
The CPIC side info profile contains all information that a CPIC application requires to initiate an LU 6.2 conversation. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses the CPIC side info profile name as an object that fully addresses and qualifies the remote application.
For this reason, you supply the following information in each CPIC side info profile dedicated to <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>:
- Local LU alias
- Partner LU name
- Mode name
- TP (transaction program) name
#### Example of CPIC side info definition
This is an extract from <span class="code">/etc/sna/sna\\\_domn.cfg</span>:
&gt; \[define\_cpic\_side\_info\]
&gt; sym\_dest\_name = PHECPICI
&gt; description = ""
&gt; lu\_alias = PHSEI
&gt; partner\_lu\_name = PHSER
&gt; mode\_name = PHSEMODE
&gt; tp\_name\_type = APPLICATION\_TP
&gt; tp\_name = PHECPICR
&gt; conversation\_security\_type = NONE
&gt; security\_user\_id = ""
&gt; security\_password = ""
#### Defining TP (Transaction Program)
For each incoming conversation intended for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, the SNA sub-system is expected to start an appropriate <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> application program. You first create a Transaction Program profile for the PeSIT E protocol.
You define Transaction Program profiles as follows:
1. The USERID and GROUP fields must match the user-id and group-id used to install and start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.
2. Set the TYPE field to NON-QUEUED.
3. Complete the PATH field with the absolute path of the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> application program that corresponds to the targeted file transfer protocol.
4. The ENVIRONMENT field must set APPCTPN to the corresponding TP name.
If for example, the TP name is PHECPICR, this field must contain APPCTPN=PHECPICR.
#### Example of Transaction Program definition
This is an extract from <span class="code">/etc/sna/sna\\\_tps</span>:
&gt; \[PHECPICR\]
&gt; LUALIAS = ""
&gt; DESCRIPTION = ""
&gt; USERID = portpel
&gt; GROUP = Gateway
&gt; TIMEOUT = 0
&gt; TYPE = NON-QUEUED
&gt; STYLE = EXTENDED
&gt; PATH = /portage\_Gateway/users/portpel/T6342/bin/PHECPICR
&gt; ENV = APPCTPN=PHECPICR
### Summary of SNA installation for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>
#### Configuring and checking SNA system resources
The SNA configuration procedure using the <span class="bold_in_para">xsnaadmin</span> interface is as follows:
1. Configure SNA connectivity on the local machine:
- The node
- One port for each hardware interface used for SNA
- One link station per remote machine
2. Check that you can activate all links. If not, check the SNA log and trace files.
The cause may be incorrect configuration on a remote machine.
3. Configure the local LUs, partner LUs and possibly remote NODEs that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> will use.
4. Use the appropriate <span class="bold_in_para">xsnaadmin</span> command to establish LU-LU sessions manually.
Fix any problems on the local and remote machines that may prevent LU-LU sessions from being established.
5. Create all other configuration objects that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires (that is, Modes, CPIC Side Information Profile, and Transaction Programs).
#### Configuring and checking <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> resources for SNA
1. Configure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to enable the SNA option for the PeSIT E protocol.
2. Stop and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> using the appropriate commands.
3. Create a Remote Site for each remote system that expects to accept SNA conversations initiated by the local <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.
This Remote Site contains the corresponding CPIC side info profile name as the destination address field. Create the Remote Site using either the Windows GUI or the <span class="bold_in_para">peladm</span> command.
4. To check each Remote Site configured for SNA/LU 6.2, submit a Transfer Request addressed to that Site.
If a problem occurs that prevents the file transfer from processing normally, enable the trace mode for that Site and set up the trace and log facility in the SNA sub-system. This will produce outputs that may help track the problem.
 
Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:
- \[Installation\](/bundle/Gateway\_6173\_InstallationGuide\_allOS\_en\_HTML5/page/Content/start\_page.htm) -- \[User\](/bundle/Gateway\_6173\_UsersGuide\_allOS\_en\_HTML5/page/Content/start\_page.htm) -- \[Unix Configuration\](/bundle/Gateway\_6173\_ConfigurationGuide\_UNIX\_en\_HTML5/page/Content/start\_page.htm) -- \[Upgrade\](/bundle/Gateway\_6173\_UpgradeGuide\_allOS\_en\_HTML5/page/Content/start\_page.htm) -- \[Interoperability\](/bundle/Gateway\_6173\_InteroperabilityGuide\_allOS\_en\_HTML5/page/Content/start\_page.htm) -- \[Security\](/bundle/Gateway\_6173\_SecurityGuide\_allOS\_en\_HTML5/page/Content/start\_page.htm), requires login -- \[Release Notes\](/bundle/Gateway\_6173\_ReleaseNotes\_allOS\_en\_HTML5/page/Content/Gateway\_ReleaseNotes\_allOS\_en.htm)
