{
    "title": "Address configuration for Remote Sites",
    "linkTitle": "Address configuration",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

This topic provides additional information about address configuration for Gateway partners. In the GUI, you enter this information in the <span style="font-weight: bold;">Network address</span> tab of the <span style="font-style: italic;">New Remote Site</span> window. The parameters required depend on your network interface:

-   [TCP/IP](#TCP_IP)
-   [SNA LU 6.2](#SNA_LU62)

<span id="TCP_IP"></span>

## Configuring Remote Sites for TCP/IP

To create a Remote Site that uses TCP/IP, you supply the remote machine name (if using a name server) or its IP address (such as 193.56.234.50), and the port number on which the remote file transfer protocol is listening.

For example, create a Remote Site using the following command:

peladm create\_site   -pr PHSE  -a REMOTE\_PHSE\_TCP  -pi RPT0

                     -ct TCP  -dest\_address 193.56.234.50/22200

This command creates a destination Site with the following properties:

-   Protocol = PeSIT E (<span class="code">-pr PHSE</span>)
-   Alias name = REMOTE\_PHSE\_TCP (<span class="code">-a REMOTE\_PHSE\_TCP</span>)
-   Protocol identifier = RPT0 (<span class="code">-pi RPT0</span>)

To access this Site, Gateway:

-   Uses TCP/IP network (<span class="code">-ct TCP</span>)
-   Calls the IP address 193.56.234.50 on port number 22200

The partner application must be running on a platform with this IP address and listening to this port number.

<span id="RAS"></span>

### Configuring Remote Sites for RAS

For Windows platforms only.

In Gateway, each remote partner participating in a file transfer must be defined as a Remote Site object.

To define a Remote Site as an RAS server, you must complete the TCP/IP address field in Remote Site definition in the following format:

-   <span style="font-weight: bold;">Network type</span> = TCP
-   <span style="font-weight: bold;">Network address</span> = \[destination\] nnn.nnn.nnn.nnn
-   <span style="font-weight: bold;">Port</span> = mmmm

where \[destination\] is a section name in the RASPPP.INI file and nnn.nnn.nnn.nnn is the called TCP/IP host address. For example:

-   <span style="font-weight: bold;">Network type</span> = TCP
-   <span style="font-weight: bold;">Network address</span> = \[PARIS\] 172.20.102.33
-   <span style="font-weight: bold;">Port</span> = 2345

<span id="CAPI"></span>

### 

<span id="SNA_LU62"></span>

## Configuring Remote Sites for SNA LU 6.2

To create a Remote Site accessible over SNA LU 6.2, set the <span style="font-weight: bold;">Network type</span> to <span style="font-weight: bold;">LU 6.2</span>.

The field Machine name is used to define the <span style="font-style: italic;">CPI-C side information</span>. Note that in some SNA access methods, <span style="font-style: italic;">CPI-C side information</span> is referred to as <span style="font-style: italic;">CPI-C symbolic destinations</span>.

The field <span style="font-weight: bold;">LU: Local</span> contains the Logical Unit for the local partner.

For example, create a Remote Site using the following command:

peladm create\_site   -pr PHSE  -a REMOTE\_LU  -pi RPX0

                     -ct LU62  -dest\_address TOMVS@IPASOPL1@0

This command creates a destination Site with the following properties:

-   Protocol = PHSE (<span class="code">-pr PHSE</span>)
-   Alias name = REMOTE\_LU (<span class="code">-a REMOTE\_LU</span>)
-   Protocol identifier = RPX0 (<span class="code">-pi RPX0</span>)

To access this Site, Gateway:

-   Uses the SNA network (<span class="code">-ct LU62</span>)
-   Calls the address TOMVS@IPASOPL1@0 (<span class="code">-dest\_address TOMVS@IPASOPL1@0</span>)

You must define the corresponding and related SNA configuration parameters in the SNA configuration database of your system before you create the Gateway Sites that use these parameters.

#### For Windows users

Every partner involved in a file transfer must be defined in Gateway. To identify a Remote Site as the LU 6.2 partner, the Site definition must include the following parameters:

-   Network type: LU 6.2
-   Machine: xxxxxxxx

where xxxxxxx is a CPI-C symbolic destination defined in the SNA configuration database.

Specify the <span style="font-style: italic;">CPI-C symbolic destination</span> name in the <span style="font-weight: bold;">Destination</span> field in the Gateway Remote Site definition. It identifies the SNA resources to use to connect to the Site.

In addition, if you are using PEL protocol over SNA LU 6.2 with the remote partner, the acknowledgment window must be greater than 0. If you are using PeSIT HS protocol over SNA LU 6.2, the acknowledgment window must be 1.

Also refer to [Configuring protocols: SNA LU 6.2](../../../../configuration_start_here/config_protocols_about/config_sna_lu_6_2#CPI-C_Symbolic_Destination).

#### For UNIX users

On most UNIX systems, you can define CPI-C information profiles that group all SNA parameter values required to establish connections to the Remote Site.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
