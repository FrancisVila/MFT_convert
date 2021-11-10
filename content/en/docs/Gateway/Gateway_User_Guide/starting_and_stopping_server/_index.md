{
    "title": "Starting and stopping the server",
    "linkTitle": "Managing the server",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing the Server

[Server startup overview](#gw_server_startup_overview)

[Before you start the Gateway server](#before_starting_gw_server)

[Starting and stopping the Gateway server](#starting_and_stopping_gw_server)

[Starting and stopping the Navigator server](#starting_and_stopping_gui_server)

[Starting and stopping the Axway MFT Navigator server](#starting_and_stopping_command_line_server)

[After you start the Gateway server](#after_starting_gw_server)

[After you stop the Gateway server](#after_stopping_gw_server)

<span id="gw_server_startup_overview"></span>

## Server startup overview

Gateway is composed of a group of related executable programs. The programs activated at startup depend on the options chosen during installation and configuration.

#### UNIX environments

Specify whether or not the server daemons (for the Gateway user interface) are started at the same time as the product. By default, the server daemons start automatically.

#### Windows environments

Start Gateway in one of two ways:

-   Manually: select <span style="font-weight: bold;">Start</span> in the Gateway program folder created by the installation process
-   Automatically: configure Gateway as a service to automatically start on system start

After startup is completed, select <span style="font-weight: bold;">Process List</span> in the Gateway program folder to view the list of currently activated programs.

<span id="before_starting_gw_server"></span>

## Before you start the Gateway server

Before starting Gateway, check the network resources needed for communication between Gateway and its partners.

### IPC Queues

Gateway uses the OS's IPC queues for inter-process communication.

Refer to the *Installation Guide* &gt; *[Gateway kernel prerequisites](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/Installation/gateway_kernel_prereqs.htm)* for their configuring to avoid delays during high-load.

### TCP/IP subsystems

To check that you can reach remote systems from your computer, use the standard <span class="code" style="font-weight: bold;">ping</span> command with the hostname or IP address as argument. For more details, refer to the ping documentation supplied with your system.

### SNA LU 6.2 subsystems

To check the SNA configuration, activate each LU 6.2 connection that Gateway uses.

If you are unable to activate LU-LU sessions, check the LU 6.2 local and remote parameters.

If LU-LU sessions are activated, and the session establishment failed at file transfer time, check that:

-   The Remote Site is active, and
-   The mode and the transaction name requested in <span style="font-style: italic;">CPI symbolic destination</span> are defined in the Remote Site

If the problem persists, activate the audit function and the SNA trace.

<span id="starting_and_stopping_gw_server"></span>

## Starting and stopping the Gateway server

You do not have to initialize this version of Gateway. The Installer executes the <span class="code" style="font-weight: bold;">gateinit</span> command for you.

### Windows environments: Starting

To start Gateway, go to the Windows <span style="font-weight: bold;">Start</span> menu and select:

<span style="font-weight: bold;">Programs &gt; Axway Software &gt; Axway \[ProjectName\]&gt; Gateway &gt; Start Gateway</span>

You can configure Gateway to continue running between login sessions by installing it as a system service.

### Windows environments: Stopping

To stop Gateway, go to the Windows <span style="font-weight: bold;">Start</span> menu and select:

<span style="font-weight: bold;">Programs &gt; Axway Software &gt; Axway \[ProjectName\]&gt; Gateway &gt; Stop Gateway</span>

If you started Gateway as a system service, you must stop it via a Service applet in the Control Panel. Alternatively, use the <span class="code">net stop xxxxx</span> command.

The Axway MFT Navigator server and the Gateway GUI server stop at the same time as the product.

### UNIX environments: Starting and stopping

The <span class="code" style="font-weight: bold;">gatestart</span> and <span class="code" style="font-weight: bold;">gatestop</span> utilities enable you to start and stop Gateway in the UNIX environment.

Before using Gateway program files, set the product environment for your UNIX session.

Execute the Shell script <span class="code" style="font-weight: bold;">profile</span>, located by default in:

&lt;Gateway installation directory>/run\_time/etc

#### Starting

To start Gateway, enter the command:

gatestart

This command starts Gateway, and by extension, activates the tracking functions of the Mailbox. Use this command when Gateway is stopped.

<span style="font-weight: bold;">Note:</span> Do not use the<span class="code" style="font-weight: bold;"> pelmon start</span> command that was used in earlier versions of Gateway.

#### Stopping

To stop Gateway, enter the command:

gatestop

This command shuts down Gateway, and by extension, stops Mailbox tracking.

<span style="font-weight: bold;">Note:</span> Do not use the<span class="code" style="font-weight: bold;"> pelmon stop</span> command that was used in earlier versions of Gateway.

<span id="starting_and_stopping_gui_server"></span>

## Starting and stopping the Navigator server

In Windows and UNIX environments, the Gateway Navigator server (GUI server) starts and stops at the same time as Gateway.

<span id="starting_and_stopping_command_line_server"></span>

## Starting and stopping the Axway MFT Navigator server

The MFT Navigator server starts and stops at the same time as Gateway.

<span id="after_starting_gw_server"></span>

## After you start the Gateway server

After starting Gateway, check the Gateway processes.

### Windows environments

After startup is completed, select <span style="font-weight: bold;">Process List</span> in the Gateway program folder to view the list of currently activated programs.

### UNIX environments

#### Status

Use the <span class="code" style="font-weight: bold;">gatestatus</span> command to obtain the current status of Gateway, and by extension, the Mailbox.

<span style="font-weight: bold;">Note:</span> Do not use the <span class="code" style="font-weight: bold;">pelmon status</span> command that was used in earlier versions of Gateway.

For a list of possible responses, refer to [About `gatestatus` messages](c_gatestatus_messages).

#### Processes

After entering the <span class="code" style="font-weight: bold;">gatestart</span> or <span class="code" style="font-weight: bold;">gatestop</span> command, check that Gateway processes have correctly started or stopped.

Enter the command:

ps –e | grep -E " p\_| q\_| h\_| notif| ipelapi"

When Gateway is started, the <span class="code" style="font-weight: bold;">ps</span> (or Process List) command must show a supervisor process (<span class="code">p\_sup</span>) and a system process (<span class="code">p\_sys</span>).

Other processes are launched depending on the networks, protocol resources used and product options (for example, Sentinel).

#### For TCP/IP networks

Use the following commands to specify the appropriate protocol for the TCP/IP network.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Specifies the protocol for the TCP/IP network...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">p_as1pop3sock</span></p>         </td>
         <td><p>EDIINT AS1 POP3</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_as1smtpsock</span></p>         </td>
         <td><p>EDIINT AS1 SMTP</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_as2sock</span></p>         </td>
         <td><p>EDIINT AS2</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_as3sock</span></p>         </td>
         <td><p>EDIINT AS3</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_fsitsock</span></p>         </td>
         <td><p>PeSIT protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">clp_ftpsock</span></p>         </td>
         <td><p>FTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_fodtsock</span></p>         </td>
         <td><p>OFTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_fpelsock</span></p>         </td>
         <td><p>PEL protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_fhttpsock</span></p>         </td>
         <td><p>HTTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_fpop3sock</span></p>         </td>
         <td><p>POP3 protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_sftpsock</span></p>         </td>
         <td><p>SFTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p_smtpsock</span></p>         </td>
         <td><p>SMTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">h_trade_job</span></p>         </td>
         <td><p>S/MIME, AS1, AS2, AS3</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">         </th>
<th class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">         </th>
<th class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

#### For SNA networks

Use the following command to specify the appropriate protocol for the SNA network.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Specifies...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">p_fsit62</span></p>         </td>
         <td><p>the use of an SNA network with PeSIT protocol</p>         </td>
      </tr>
   </tbody>
</table>

Only the PeSIT E protocol is supported for SNA.

SNA processes are not started when you start Gateway. These processes are started when a connection occurs. For this reason, they are referred to as <span style="font-style: italic;">dynamic processes</span>.

Multiple processes for the same protocol can be displayed if several connections occur. These processes stop when the connections are dropped.

#### Message queues (UNIX environments)

Gateway uses message queues. In the UNIX environment, use the <span class="code" style="font-weight: bold;">ipcs</span> command to check that the message queues are started.

ipcs –q | grep &lt;OWNER>

<span id="after_stopping_gw_server"></span>

## After you stop the Gateway server

When you stop Gateway, you should also stop the list of processes being printed, and delete the message queues.

### Checking the status of processes

Process traces can be found in the folder <span class="code">p\_home\_dir/run\_time/tmp</span>. Select the file that corresponds to your process to view messages that describe why processes are not launched.

The following table lists the types of trace file (where XX is the PID number of the process).

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Trace file name</p>         </th>
<th class="HeadD-Column1-Header1"><p>Trace type</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">SUP-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>SUPERVISOR traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">SYS-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>SYSTEM traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_AS1_POP3-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>EDIINT AS1 POP3 protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_AS1_SMTP-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>EDIINT AS1 SMTP protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_AS2_X-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>EDIINT AS2 protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_AS3_X-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>EDIINT AS3 protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_PHSE-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>PeSIT E protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">FT_FTP-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>FTP protocol traces</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">TCP_PHSE-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>TCP traces with PeSIT E protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">TCP_FTP-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>TCP traces with FTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">PHECPICR.XX-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>SNA traces for outgoing call with PHSE protocol</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">PHECPICI.XX-&lt;timestamp&gt;-&lt;pid&gt;.out</span></p>         </td>
         <td><p>SNA traces for incoming call with PHSE protocol</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About gatestatus messages](c_gatestatus_messages)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
