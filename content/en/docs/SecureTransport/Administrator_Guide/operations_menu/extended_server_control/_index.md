{
    "title": "Server Control",
    "linkTitle": "Server Control",
    "weight": "90"
}**[Operations](../) &gt; Server Control**

The *Server Control* page is the entry point for SecureTransport administrators on successful login. Here you view and manage all protocol servers, the TM server and the Monitor server of your system.

Server control is available on both SecureTransport Server and SecureTransport Edge.

In this topic you will learn about:

-   [Server Control: Protocol servers](#server2)
-   [Server Control: Folder Monitor](#server6)
-   [Server Control: Scheduler](#server7)
-   [Server Control: Transaction Manager server](#server3)
-   [Server Control: Monitor server](#server4)
-   [Server status indicators](#server)
-   [Server Control on SecureTransport Edge](#server5)

## <span id="Server2"></span>Server Control: Protocol servers

The protocol servers (also called daemons) you can manage on the *Server Control* page are: *FTP*, *HTTP*, *AS2*, *SSH* and *PeSIT*.

Each daemon is represented by a dedicated panel. The daemon's settings and status, as well as the available management actions are located in the panel header. From here, you can edit the daemon settings and perform actions like start and stop the daemon or adding a new server.

For each server, the panel displays current *Status*, basic configuration options, including listener port and key alias. You can also perform certain actions, like start and stop a server, or changing server configuration, distributed in dedicated controls, as follows:

-   the "gear" icon![](stop-icon.png)allows you to edit the configuration parameters of the corresponding server
-   the "play" icon(![](stop-icon.png) when server stopped) interchanges with the "stop" icon (![](stop-icon.png) when server running); these controls apply the corresponding action to the selected server only

The following topics provide more details on adding and editing server daemons with the respective protocol:

-   [Manage the FTP server](ext_servercontrol-add-ftp)
-   [Manage the SSH server](ssh-daemon-conf/ext_servercontrol-add-ssh)
-   [Manage the HTTP server](ext_servercontrol-add-http)
-   [Manage the AS2 server](ext_servercontrol-add-as2)
-   [Manage the PeSIT server](ext_servercontrol-add-pesit)
-   [Advanced protocol server configuration](advanced-server-config)

### Disabling protocol servers

When you disable any of the component servers using the Administration Tool, the scripts used to run the servers from the command line are renamed with the .`disable` extension. To disable a server clear the check box for that server. Once the servers are enabled, the files are restored to the original name. For example, if you disable the FTP server, the script `start_ftpd` is renamed to `start_ftpd.disable`. Once you select the enable check box and start the server using the Administration Tool, the script name returns to `start_ftpd`. All utility scripts are located in the `<FILEDRIVEHOME>/bin` directory.

## <span id="Server6"></span>Server Control: Folder Monitor

Folder Monitor is available only on SecureTransport Server and is dependent on the value of the `FolderMonitor.enable` Server configuration option. Its dedicated pane allows you to see its *Status* and to *Start* the FM (when not running) or *Stop* the FM (when running).

## <span id="Server7"></span>Server Control: Scheduler

Scheduler is available only on SecureTransport Server and is dependent on the value of the `Scheduler.enable` Server configuration option.
Its dedicated pane allows you to see its *Status* and to *Start* theScheduler (when not running) or *Stop* the Scheduler (when running).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">
<br/>The <code>Scheduler.enable</code> and <code>FolderMonitor.enable</code>   server configuration options do not start or stop the respective cluster services; they only enable or disable the service. When Transaction Manager is running and  Folder Monitor/Scheduler is disabled  from the Server Configuration (the respective configuration parameter is set to <code>false</code>), the service runs in the background but does not do any job (schedule events or pull files). Folder Monitor/Scheduler is running and functional only when the Transaction Manager is started, and Folder Monitor/Scheduler is started and enabled from the Server Configuration.         </td>
      </tr>
</table>

## <span id="Server3"></span>Server Control: Transaction Manager server

The Transaction Manager (TM) server connects to the ports specified in the network zones. Its dedicated pane allows you to see its *Status* and to *Start* the TM (when not running) or *Stop* the TM (when running).

For more information, see [Communication across Transaction Manager, protocol, and proxy servers](../../c_st_setup/c_st_networkzones).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">There is no TM panel in the <i>Server Control</i> page on <span>SecureTransport Edge</span>.         </td>
      </tr>
</table>

## <span id="Server4"></span>Server Control: Monitor server

The Monitor Server uses the `monitord` monitoring service to perform periodical checks and identify if the SecureTransport servers are functional or not. Its dedicated pane allows you to see its *Status* and to *Start* the TM (when not running) or *Stop* the TM (when running).

For more information, see [Monitor server](t_st_monitorserver).

## <span id="Server"></span>Server status indicators

The table below lists the various status options available from the *Server Control* page and when SecureTransport displays that status.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Status</th>
         <th>Description</th>
         <th>Used during:</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Running</strong>
<br/>(displayed in green)         </td>
         <td>The server is running normally.         </td>
         <td>Normal operation         </td>
      </tr>
      <tr>
         <td><strong>Running</strong>
<br/>(displayed in blue)         </td>
         <td>An HTTP or FTP server suspension is pending, with the server suspension information displayed below.         </td>
         <td>Scheduled suspensions         </td>
      </tr>
      <tr>
         <td><strong>Not Running</strong>
<br/>(displayed in red)         </td>
         <td>The server is stopped.         </td>
         <td>Disabled or stopped servers         </td>
      </tr>
      <tr>
         <td><strong>Suspend</strong>
<br/>(displayed in red)         </td>
         <td>The HTTP or FTP server is scheduled to <span>suspend</span> in the near future. The HTTP or FTP server is running, but does not allow transfers. Users can still connect and get messages.         </td>
         <td>Temporary <span>suspensions</span>, such as for maintenance         </td>
      </tr>
   </tbody>
</table>

## <span id="Server5"></span>Server Control on SecureTransport Edge

On the *Server Control* page for a SecureTransport Edge, there is no *TM Server* pane because the Transaction Manager does not run on the SecureTransport Edge, but you can configure the port for the SecureTransport Edge proxy server.

On the SecureTransport Edge, specify the port for the SecureTransport proxy server. The proxy port is used by SecureTransport Server to handle outgoing connections passed through a SecureTransport Edge. The default is port number 1080.

1.  On the *Server Control* page, under **Proxy Server**, enter a value in the **Proxy Port** field.
2.  Click **Start**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">By default, <span>SecureTransport</span> Edge uses a cipher strength of <code>AES 256</code> for communication between its protocol servers and the TM Server on the <span>SecureTransport</span> Servers. To change the cipher suites enabled, edit the <code>TransactionManager.Listeners.Ssl.enabledCipherSuites</code>	server configuration parameter. For valid values, see the cipher suites listed for transfers using AS2, FTPS, HTTPS, and PeSIT over secured socket in <a href="../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.         </td>
      </tr>
</table>
