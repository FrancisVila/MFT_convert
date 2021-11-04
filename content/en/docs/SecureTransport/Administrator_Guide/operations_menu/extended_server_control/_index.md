{
    "title": "Server control",
    "linkTitle": "Server Control",
    "weight": "80"
}**<a href="../" class="MCXref xref">Operations</a> &gt; Server Control**

The *Server Control* page is the entry point for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> administrators on successful login. Here you view and manage all protocol servers, the TM server and the Monitor server of your system.

Server control is available on both <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server and <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Edge.

In this topic you will learn about:

-   <a href="#Server2" class="MCXref xref">Server Control: Protocol servers</a>
-   <a href="#Server6" class="MCXref xref">Server Control: Folder Monitor</a>
-   <a href="#Server7" class="MCXref xref">Server Control: Scheduler</a>
-   <a href="#Server3" class="MCXref xref">Server Control: Transaction Manager server</a>
-   <a href="#Server4" class="MCXref xref">Server Control: Monitor server</a>
-   <a href="#Server" class="MCXref xref">Server status indicators</a>
-   <a href="#Server5" class="MCXref xref">Server Control on SecureTransport Edge</a>

<span id="Server2"></span>

## Server Control: Protocol servers

The protocol servers (also called daemons) you can manage on the *Server Control* page are: *FTP*, *HTTP*, *AS2*, *SSH* and *PeSIT*.

Each daemon is represented by a dedicated panel. The daemon's settings and status, as well as the available management actions are located in the panel header. From here, you can edit the daemon settings and perform actions like start and stop the daemon or adding a new server.

For each server, the panel displays current *Status*, basic configuration options, including listener port and key alias. You can also perform certain actions, like start and stop a server, or changing server configuration, distributed in dedicated controls, as follows:

-   the "gear" icon![](/Images/SecureTransport/gearwheel-icon.png)allows you to edit the configuration parameters of the corresponding server
-   the "play" icon(![](/Images/SecureTransport/play-icon.png) when server stopped) interchanges with the "stop" icon (![](/Images/SecureTransport/stop-icon.png) when server running); these controls apply the corresponding action to the selected server only

The following topics provide more details on adding and editing server daemons with the respective protocol:

-   <a href="ext_servercontrol-add-ftp" class="MCXref xref">Manage the FTP server</a>
-   <a href="ssh-daemon-conf/ext_servercontrol-add-ssh" class="MCXref xref">Manage the SSH server</a>
-   <a href="ext_servercontrol-add-http" class="MCXref xref">Manage the HTTP server</a>
-   <a href="ext_servercontrol-add-as2" class="MCXref xref">Manage the AS2 server</a>
-   <a href="ext_servercontrol-add-pesit" class="MCXref xref">Manage the PeSIT server</a>
-   <a href="advanced-server-config" class="MCXref xref">Advanced protocol server configuration</a>

### Disabling protocol servers

When you disable any of the component servers using the Administration Tool, the scripts used to run the servers from the command line are renamed with the .`disable` extension. To disable a server clear the check box for that server. Once the servers are enabled, the files are restored to the original name. For example, if you disable the FTP server, the script `start_ftpd` is renamed to `start_ftpd.disable`. Once you select the enable check box and start the server using the Administration Tool, the script name returns to `start_ftpd`. All utility scripts are located in the `<FILEDRIVEHOME>/bin` directory.

<span id="Server6"></span>

## Server Control: Folder Monitor

Folder Monitor is available only on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and is dependent on the value of the `FolderMonitor.enable` Server configuration option. Its dedicated pane allows you to see its *Status* and to *Start* the FM (when not running) or *Stop* the FM (when running).

<span id="Server7"></span>

## Server Control: Scheduler

Scheduler is available only on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and is dependent on the value of the `Scheduler.enable` Server configuration option.
Its dedicated pane allows you to see its *Status* and to *Start* theScheduler (when not running) or *Stop* the Scheduler (when running).

> **Note:**
>
> The Scheduler.enable and FolderMonitor.enable server configuration options do not start or stop the respective cluster services; they only enable or disable the service. When Transaction Manager is running and Folder Monitor/Scheduler is disabled from the Server Configuration (the respective configuration parameter is set to false), the service runs in the background but does not do any job (schedule events or pull files). Folder Monitor/Scheduler is running and functional only when the Transaction Manager is started, and Folder Monitor/Scheduler is started and enabled from the Server Configuration.

<span id="Server3"></span>

## Server Control: Transaction Manager server

The Transaction Manager (TM) server connects to the ports specified in the network zones. Its dedicated pane allows you to see its *Status* and to *Start* the TM (when not running) or *Stop* the TM (when running).

For more information, see <a href="../../c_st_setup/c_st_networkzones#SetupMenu_1217491348_1149202" class="MCXref xref">Communication across Transaction Manager, protocol, and proxy servers</a>.

> **Note:**
>
> There is no TM panel in the Server Control page on SecureTransport Edge.

<span id="Server4"></span>

## Server Control: Monitor server

The Monitor Server uses the `monitord` monitoring service to perform periodical checks and identify if the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers are functional or not. Its dedicated pane allows you to see its *Status* and to *Start* the TM (when not running) or *Stop* the TM (when running).

For more information, see <a href="t_st_monitorserver" class="MCXref xref">Monitor server</a>.

<span id="Server"></span>

## Server status indicators

The table below lists the various status options available from the *Server Control* page and when <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays that status.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Status         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Used during:         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Running</strong><br />
(displayed in green)         </td>
         <td>The server is running normally.         </td>
         <td>Normal operation         </td>
      </tr>
      <tr>
         <td><strong>Running</strong><br />
(displayed in blue)         </td>
         <td>An HTTP or FTP server suspension is pending, with the server suspension information displayed below.         </td>
         <td>Scheduled suspensions         </td>
      </tr>
      <tr>
         <td><strong>Not Running</strong><br />
(displayed in red)         </td>
         <td>The server is stopped.         </td>
         <td>Disabled or stopped servers         </td>
      </tr>
      <tr>
         <td><strong>Suspend</strong><br />
(displayed in red)         </td>
         <td>The HTTP or FTP server is scheduled to <span>suspend</span> in the near future. The HTTP or FTP server is running, but does not allow transfers. Users can still connect and get messages.         </td>
         <td>Temporary <span>suspensions</span>, such as for maintenance         </td>
      </tr>
   </tbody>
</table>

<span id="Server5"></span>

## Server Control on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge

On the *Server Control* page for a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, there is no *TM Server* pane because the Transaction Manager does not run on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, but you can configure the port for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge proxy server.

On the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, specify the port for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> proxy server. The proxy port is used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to handle outgoing connections passed through a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge. The default is port number 1080.

1.  On the *Server Control* page, under **Proxy Server**, enter a value in the **Proxy Port** field.
2.  Click **Start**.

> **Note:**
>
> By default, SecureTransport Edge uses a cipher strength of AES 256 for communication between its protocol servers and the TM Server on the SecureTransport Servers. To change the cipher suites enabled, edit the TransactionManager.Listeners.Ssl.enabledCipherSuites server configuration parameter. For valid values, see the cipher suites listed for transfers using AS2, FTPS, HTTPS, and PeSIT over secured socket in Advertised ciphers and cipher suites.
