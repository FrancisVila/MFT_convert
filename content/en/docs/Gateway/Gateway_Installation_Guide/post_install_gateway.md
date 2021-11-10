{
    "title": "Post-installation",
    "linkTitle": "Post-installation",
    "weight": "80"
}After installing Gateway you can:

-   [Integrate PassPort](#integrating_passport). This is mandatory if you chose to use <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> with Gateway.
-   [Start or stop the server.](#starting_server) In order to configure and work with Gateway.
-   [Install Gateway Navigator](../install_gateway_navigator): Navigator allows you to control your Gateway servers remotely through a management UI.

<span id="integrating_passport"></span>

## Integrating PassPort

### About

After installing Gateway and <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>, but before starting the Gateway server for the first time:

-   Set up a user as a Gateway administrator in <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>
-   Log in as the Gateway administrator

### Prerequisites

-   Start PassPort.
-   Connect to PassPort via a browser by entering the PassPort URL, which has the format: `https://PassPortServerHost:PassPortServerPort/ui`
-   The `PassPortServerHost` and `PassPortServerPort` are the same values defined during installation.
-   An SMTP server has been set up in PassPort

**Note**: Contact the PassPort administrator if you have problems.

1.  Log in to the PassPort user interface. Select the domain **System:Administration**. The initial username and password for the default PassPort administrative user are **system** and **System01**. For security reasons, it is recommended to change this password as soon as possible.
2.  Select **Access** **&gt;** **Components** in the user interface to open the AM components area.
3.  Click the **Import CSD** icon to import the Gateway CSD file. The file, named `CSDGateway.xml`, must be accessible on your network. The file is in the directory where you installed Gateway at `[Gateway installation directory]\extras\passport`.  
    **Note**: the default domain is **Synchrony** and it contains the default **Users** organization.
4.  On the same menu, select **Access** > **Components** > **Gateway**. An instance name **default** has been imported. This may not match the instance name that the Gateway assigned itself during installation. You must make sure PassPort and Gateway are synchronized with the instance name. For example, create a **gatewayInstance** instance and make sure that the Gateway used the same value as Passport.
5.  Add the domain **Synchrony** to the active **gatewayInstance**.
6.  Select **Access > Users and organizations**. Select the **Users** organization under the **Synchrony** domain and add a user. For example, **Admin**. Use a valid e-mail address because the initial user password is sent to this address. Before clicking **OK** to add the user, set the status to **active**. PassPort then sends an e-mail message informing the user of the initial password.
7.  Select **Access** **&gt; Authorization > Predefined roles** to display a list of roles. These roles are system defaults or have been imported from CSD files.
8.  Select the **Admin** role of the Gateway component, click the **Users** tab and click **Add users to role** to assign the user added to this predefined role.

If RMA is installed:

1.  Import into PassPort AM the Roles defined inside the newly installed file: <span class="code">{ROOTFOLDER of RMA SERVER}/conf/passport/rma\_csd.xml</span>. For detailed information, refer to *Gateway User Guide >* [Importing required data into PassPort](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/Products/RMA/Administration/t_fex_asp_rma_access_ctrl.htm).
2.  Inside PassPort AM, as administrator, grant RMA roles to the previously defined user\[s\].

<span id="starting_server"></span>

## Starting and stopping the server

This section explains how to start and stop after <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> installation and how to check which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> processes are running. The procedures to follow depend on your operating system:

-   [Windows](#Windows)
-   [UNIX](#UNIX)

<span id="Windows"></span>

### Controlling <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> on Windows

After installation, you can either [start
<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> manually](#Starting_manually), or let it to start
automatically on system startup if set to do so. To start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> automatically,
you must have [installed <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>
as a system service](#Installing_as_system_service).

To start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, enter the command: <span class="code">gatestart</span>

To stop <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, enter the command: <span class="code">gatestop</span>

#### Starting and stopping <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> manually

To start and stop <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> manually, use the commands available in the Windows <span style="font-weight: bold;">Start</span> menu or by command line.

<span id="Starting_manually"></span>

#### Starting <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

To start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, from the Windows <span style="font-weight: bold;">Start</span> menu, click the **Start Gateway** icon:

<span style="font-weight: normal;">You can also start Gateway by command line. Open **Programs &gt; Axway Software &gt; Axway \[ProjectName\] &gt; Gateway &gt; Command Prompt**</span>

<span style="font-weight: normal;">Or, open a command prompt and execute the shell script profile.bat (located by default in </span><span style="font-weight: normal;">&lt;`Gateway installation directory>/run_time/etc/profile.bat`).</span>

<span style="font-weight: normal;">To start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, enter the command:</span>`gatestart`

<span id="Stopping_manually"></span>

#### Stopping <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

To stop Gateway from the Windows <span style="font-weight: bold;">Start</span> menu, click the **Stop Gateway** icon:

**Programs &gt; Axway Software &gt; Axway \[ProjectName\] &gt; Gateway &gt; Stop Gateway**

<span style="font-weight: normal;">You can stop Gateway by command line. <span style="font-weight: normal;">Open **Programs &gt; Axway Software &gt; Axway \[ProjectName\] &gt; Gateway &gt; Command Prompt**</span></span>

<span style="font-weight: normal;"><span style="font-weight: normal;">Or, open a command prompt and execute the shell script profile.bat (located by default in </span><span style="font-weight: normal;">&lt;`Gateway installation directory>/run_time/etc/profile.bat`)</span>.</span>

To stop Gateway, enter the command: `gatestop`

> **Note:**
>
> Stop (or disconnect) Gateway Navigator before you stop the Gateway server.

### <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as a system service

Install <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> as a system service if you want:

-   To start <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> automatically on system startup
-   <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> to run across sessions

**Note**: If <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> has been started as system service, it must be stopped either via the
<span style="font-weight: bold;">Services</span> option in the Control Panel or using the **`net stop`** command.

<span id="Installing_as_system_service"></span>

#### Installing <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as a system service

If you did not install <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as a system service during
the installation, proceed as follows:

To install <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as a system service, you must have administrator
rights and carry out the following steps:

1.  From the Windows <span style="font-weight: bold;">Start</span>
    menu, select:<span style="font-weight: bold;">  
    Programs > Axway Software > Axway \[ProjectName\] > Gateway > Command
    Prompt</span>  
    to open an MS-DOS command prompt session.
2.  Enter <span style="font-weight: bold;font-family: 'Courier New', monospace;">pelinst
    service-name dir-path user-name password</span>

where:

> -   <span style="font-family: 'Courier New', monospace;">service-name</span>
>     is the system service name (mandatory)
> -   <span style="font-family: 'Courier New', monospace;">dir-path</span>
>     is the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> base directory (mandatory)
> -   <span style="font-family: 'Courier New', monospace;">user-name</span>
>     is the user account under which the service runs
> -   <span style="font-family: 'Courier New', monospace;">password</span>
>     is the associated account password

For example:

pelinst
Axway Gateway &lt;Gateway installation directory> .\\administrator
secret

1.  Specify the user name in the format <span style="font-family: 'Courier New', monospace;">domain\\username</span>
    or .<span style="font-family: 'Courier New', monospace;">\\username</span>.(optional)
2.  Specify
    the password.

If you choose not to specify a user name and password,
the default <span style="font-family: 'Courier New', monospace;">SYSTEM</span>
is used. A message indicates whether the service is successfully
created or an error occurred. If an error occurs, refer to Microsoft Windows documentation
for details.

#### Configuring <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> system service

As with any system service, you can configure the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>
system service via the <span style="font-weight: bold;">Services</span>
option in the Control Panel.

1.  From the Windows <span style="font-weight: bold;">Start</span>
    menu, select <span style="font-weight: bold;">Settings</span>.
2.  Select the <span style="font-weight: bold;">Control
    Panel</span> program folder.
3.  Select <span style="font-weight: bold;">Administrative
    Tools</span>.
4.  Select <span style="font-weight: bold;">Services</span>.
5.  Select the <span style="font-family: Verdana, sans-serif;"><span style="font-family: Calibri;"><span class="code">&lt;service name></span> service</span> (<span style="font-family: Calibri;">for example</span> </span><span style="font-weight: bold;font-family: 'Courier New', monospace;">Axway
    Gateway</span><span style="font-family: Verdana, sans-serif;">) <span style="font-family: Calibri;">and</span></span>
    select <span style="font-weight: bold;">Start</span> or <span style="font-weight: bold;">Properties</span>.

You can then define the startup type and the account information under
which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> will run.

If the startup type is:

-   <span style="font-weight: bold;">Automatic</span>:
    The service starts automatically on system startup
-   <span style="font-weight: bold;">Manual</span>:
    You must use a Windows command to start and stop the service.  
    For example:<span style="font-family: 'Courier New', monospace;font-weight: bold;">  
    </span><span class="code">net start &lt;Gateway service name></span><span style="font-weight: bold;font-family: 'Courier New', monospace;">  
    </span><span class="code">net stop &lt;Gateway service name></span>

Refer to the Microsoft Windows documentation for details.

#### Removing<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> from system service

The standard uninstall procedure provided by the Axway Installer
does not remove any system services installed in this way.

To remove <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> from the system service base:

1.  Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> if it
    is running.
2.  From the Windows <span style="font-weight: bold;">Start</span>
    menu, select:<span style="font-weight: bold;">  
    Programs > Axway Software > Axway \[ProjectName\] > Gateway > Command
    Prompt</span>  
    to open an MS-DOS command prompt session.
3.  Enter <span style="font-family: 'Courier New', monospace;font-weight: bold;">pelinst
    service-name remove</span>

A message indicates whether the service was successfully
removed or whether an error occurred. If an error occurs, refer to Microsoft
Windows documentation for details.

### Checking <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> processes on Windows

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is composed of a group of related executable programs.

The programs activated at startup depend on the options chosen in the
configuration menu. After startup, you can view the list of programs that
are activated.

From the Windows <span style="font-weight: bold;">Start</span> menu,
select:

Programs &gt; Axway Software &gt; Axway \[ProjectName\] &gt; Gateway &gt; Process List

You can also run the **gatestatus** command. For more information refer to the *[Gateway User Guide](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm)*.

<span id="UNIX"></span>

### Controlling <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> on UNIX

Before using <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> program files, set the product environment for your UNIX session.

Execute the Shell script <span style="font-family: 'Courier New', monospace;font-weight: bold;">profile</span>, located by default in:

$ . <span style="font-family: 'Courier New', monospace;">&lt;Gateway installation directory></span>/run\_time/etc/profile

The <span style="font-weight: bold;font-family: 'Courier New', monospace;">gatestart</span> and <span style="font-family: 'Courier New', monospace;font-weight: bold;">gatestop</span> utilities enable you to start and stop <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> in the UNIX environment.

#### Starting <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

To start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, enter the command:

$ gatestart

#### Stopping <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

To stop <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, enter the command:

$ gatestop

## Checking <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> processes on UNIX

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is composed of a group of related executable programs.
The programs activated at startup depend on the options chosen in the
configuration menu.

After entering the command <span style="font-weight: bold;font-family: 'Courier New', monospace;">gatestart</span>
or <span style="font-family: 'Courier New', monospace;font-weight: bold;">gatestop</span>,
you can check that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> processes have correctly started
or stopped.

To view the list of programs that are activated, enter the command:

$
ps –e | grep -E “ p\_| q\_| h\_| notif| ipelapi”

When <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is started, the <span style="font-weight: bold;font-family: 'Courier New', monospace;">ps</span>
(or Process List) command must show a supervisor process (<span style="font-family: 'Courier New', monospace;">p\_sup</span>)
and a system process (<span style="font-family: 'Courier New', monospace;">p\_sys</span>).

Other processes are launched depending on the networks, protocol resources used and product options (for example, <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SentinelName variable">Sentinel</span>).

## Starting and stopping the RMA Server

This section explains how to use the RMA housekeeping scripts and how to purge log, audit and trace files if they become too large.

### About RMA housekeeping scripts

All the RMA scripts are located in the <span class="code">&lt;GATEWAY\_INSTALL\_DIR>/bin</span> directory.

These scripts include the housekeeping scripts that enable you to start, stop and check the current status of the RMA Server. The housekeeping scripts do not require any parameters.

### Running the RMA housekeeping scripts

1.  Go to the <span class="code">&lt;GATEWAY\_INSTALL\_DIR>/bin</span> directory.
2.  Run the script for your OS:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th rowspan="2" class="HeadE-Column1-Header1">Task         </th>
<th colspan="2" class="HeadD-Column1-Header1">Command         </th>
      </tr>
      <tr>
<th class="HeadE-Column1-Header1">on Windows         </th>
<th class="HeadD-Column1-Header1">on UNIX         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Start RMA Server         </td>
         <td><span class="code" style="font-weight: bold;">rmaStart.bat</span>         </td>
         <td><span class="code" style="font-weight: bold;">rmaStart.sh</span>         </td>
      </tr>
      <tr>
         <td>Stop RMA Server         </td>
         <td><span class="code" style="font-weight: bold;">rmaStop.bat</span>         </td>
         <td><span class="code" style="font-weight: bold;">rmaStop.sh</span>         </td>
      </tr>
      <tr>
         <td>Check status of RMA Server         </td>
         <td><span class="code" style="font-weight: bold;">rmaStatus.bat</span>         </td>
         <td><span class="code" style="font-weight: bold;">rmaStatus.sh</span>         </td>
      </tr>
   </tbody>
</table>

After starting the RMA Server you can check that it is fully booted by consulting the server <span class="code">rma.log</span> file, located in the <span class="code">&lt;FEX\_RMA\_INSTALL\_DIR>/logs</span> directory.

### Installing (or removing) the RMA Server Windows service

To install the RMA Server Windows service, run the script <span class="code">&lt;InstallationDir>/RMAServer/service/installRMA.bat</span>.

To remove the RMA Server Windows service, run the script <span class="code">&lt;InstallationDir>/RMAServer/service/removeRMA.bat</span>.

### Starting and stopping the RMA Server in Windows service mode

If, during installation, FEX RMA was installed as a Windows service, you can start and stop the RMA Server as follows.

#### Starting the RMA Server

1.  From the Windows **Start** menu , select **Settings > Control Panel > Administrative Tools > Services**.  
    Windows displays the *Services* window.
2.  Scroll down the Services list and right-click the FEX RMA service.
3.  From the context menu, select **Start**.

Alternatively, run the script <span class="code">&lt;InstallationDir>/RMAServer/service/startRMA.bat</span>.

#### Stopping the RMA Server

1.  From the Windows **Start** menu , select **Settings > Control Panel > Administrative Tools > Services**.  
    Windows displays the *Services* window.
2.  Scroll down the Services list and right-click the FEX RMA service.
3.  From the context menu, select **Stop**.

Alternatively, run the script <span class="code">&lt;InstallationDir>/RMAServer/service/stopRMA.bat</span>.

### Purging log, audit and trace files

Log, audit and trace files can become quite large after time. You can delete the following files if you no longer need the information:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type of file         </th>
<th class="HeadE-Column1-Header1">File name         </th>
<th class="HeadD-Column1-Header1">Location         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>RMA Server log         </td>
         <td><span class="code">rma.log</span>         </td>
         <td><span class="code">&lt;GATEWAY_INSTALL_DIR&gt;/logs</span>         </td>
      </tr>
      <tr>
         <td>RMA command line log         </td>
         <td><span class="code">rma_cmdline.log</span>         </td>
         <td><span class="code">&lt;GATEWAY_INSTALL_DIR&gt;/logs</span>         </td>
      </tr>
      <tr>
         <td>Audit         </td>
         <td><span class="code">audit.log</span>         </td>
         <td><span class="code">&lt;GATEWAY_INSTALL_DIR&gt;/logs</span>         </td>
      </tr>
   </tbody>
</table>

## Using <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

Refer to the *[Gateway User Guide](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm)* for information about configuring and using <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.

Related topics

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
