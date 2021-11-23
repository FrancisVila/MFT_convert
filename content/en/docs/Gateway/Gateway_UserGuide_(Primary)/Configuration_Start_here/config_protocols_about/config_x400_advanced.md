{
    "title": "Configuring protocols: X.400 advanced settings",
    "linkTitle": "X.400 advanced settings",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Configuration

This topic lists the X.400 advanced parameters that you can modify in the *Advanced settings* windows. Gateway opens one of these windows if you click any of the *Advanced settings* buttons when configuring the X.420 protocol.

[Advanced server ports settings](#olh_advanced_server_ports)

[Advanced OSITP settings](#olh_advanced_ositp)

[Advanced MTA settings](#olh_advanced_mta)

[Advanced MTC settings](#olh_advanced_mtc)

[Advanced MS settings](#olh_advanced_ms)

[Advanced UA settings](#olh_advanced_ua)

<span id="olh_advanced_server_ports"></span>

## Advanced server ports settings

1.  Complete the fields of the *Advanced server ports settings* window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Sys starter port</p>         </td>
         <td><p>This port is used by the X.400 system starter.</p>
<p>Choose any free port.</p>         </td>
      </tr>
      <tr>
         <td><p>OSI TP port</p>         </td>
         <td><p>This port is used by X.400 internal processes.</p>
<p>Choose any free port.</p>         </td>
      </tr>
      <tr>
         <td><p>RFC 1006 port</p>         </td>
         <td><p>This port is used to listen for incoming external IP connections from peer MTAs.</p>
<p>Choose any free port.</p>         </td>
      </tr>
      <tr>
         <td><p>X.420 UA port</p>         </td>
         <td><p>This internal port is used by the Gateway X.420 facility to communicate with the X.400 subsystem.</p>
<p>Choose any free port.</p>         </td>
      </tr>
      <tr>
         <td><p>X.435 UA port</p>         </td>
         <td><p>This internal port is used by the Gateway X.435 facility to communicate with the X.400 subsystem.</p>
<p>Choose any free port.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Host name</strong></p>         </td>
         <td><p>This value must match a local IP address.</p>
<p>Typical value: 127.0.0.1 or localhost.</p>
<p>Maximum: 64 alphanumeric characters.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_ositp"></span>

## Advanced OSITP settings

1.  Complete the fields of the <span style="font-style: italic;">Advanced OSITP settings</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Max transport connections</p>         </td>
         <td><p>Maximum number of transport connections that the transport module accepts.</p>
<p>The memory required for transport connections is:</p>
<p>Max transport connections * Buffer size.</p>
<p>Memory is reserved for each new transport connection at connection time. If memory cannot be reserved, the connection is not established.</p>
<p>Default value 32.</p>         </td>
      </tr>
      <tr>
         <td><p>Max network connections</p>         </td>
         <td><p>Maximum number of network connections the transport module can handle.</p>
<p>Default value 32.</p>         </td>
      </tr>
      <tr>
         <td><p>Max connection response time (ms)</p>         </td>
         <td><p>Maximum time (in milliseconds) that the transport module waits for a connection response service primitive from the transport user to a previous issued connect indication service primitive.</p>
<p>Default value 500 000 ms.</p>         </td>
      </tr>
      <tr>
         <td><p>TS1 time (ms)</p>         </td>
         <td><p>Time (in milliseconds) to wait for an answer to a transport Connect Request. If an answer is not received within this time, the network connection is disconnected.</p>
<p>Default value 1 200 000 ms.</p>         </td>
      </tr>
      <tr>
         <td><p>Buffer size (B)</p>         </td>
         <td><p>Memory size, in bytes, that each transport connection may use for TPDU (Transport Protocol Data Unit) buffers.</p>
<p>Default value 24 000 bytes.</p>         </td>
      </tr>
      <tr>
         <td><p>Max TPDU size (B)</p>         </td>
         <td><p>Maximum TPDU size (in bytes) that is proposed on an outgoing connect request.</p>
<p>Default value 2048 bytes.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

 

<span id="olh_advanced_mta"></span>

## Advanced MTA settings

1.  Complete the fields of the <span style="font-style: italic;">Advanced MTA settings</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Delivery period (s)</p>         </td>
         <td><p>Defines how frequently the MTA process should check the UA in-queues. If an incoming message is not read by the receiving UA, the MTA removes the message from the UA delivery queue and sends a non-delivery report message to the sender, if requested.</p>         </td>
      </tr>
      <tr>
         <td><p>Poll period (s)</p>         </td>
         <td><p>Frequency (in seconds) that the MTA should poll its in-queue. Messages from UAs and the MTC process are put in the in-queue. The poll period is used only when the queue is empty. If the queue is not empty, all messages are processed before polling is restarted.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer time (s)</p>         </td>
         <td><p>Maximum time (in seconds) that it may take for a message to be transmitted between two MTAs. If the time is exceeded, the transmission is considered to have failed and the connection is released.</p>         </td>
      </tr>
      <tr>
         <td><p>Reload configuration at startup</p>         </td>
         <td><p>Determines whether the configuration should always be reloaded at start-up.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_mtc"></span>

## Advanced MTC settings

1.  Complete the fields of the <span style="font-style: italic;">Advanced MTC settings</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Max connect attempts</p>         </td>
         <td><p>Defines how many times the MTC process should try to connect to an MTA before giving up. If the connection fails, a non-delivery message is sent to the UA that had this MTA as destination for messages. If the parameter is set to 0 or 1, only one attempt is made.</p>
<p>Default value: 3.</p>         </td>
      </tr>
      <tr>
         <td><p>Max attempt timer (s)</p>         </td>
         <td><p>When a connection attempt fails, this value specifies the time (in seconds) to wait before attempting to connect again.</p>
<p>Default value: 30.</p>         </td>
      </tr>
      <tr>
         <td><p>Max in connections</p>         </td>
         <td><p>The maximum number of simultaneous incoming connections that are accepted by the MTC. If this value is reached, any new connection is rejected with a reason code indicating temporary congestion.</p>
<p>Default value: 6.</p>         </td>
      </tr>
      <tr>
         <td><p>Max out connections</p>         </td>
         <td><p>The maximum number of simultaneous outgoing connections that are established by the MTC.</p>
<p>Default value: 2.</p>
<p>Refer to the Note above, under <span style="font-weight: bold;">Max in connections</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Max message queued</p>         </td>
         <td><p>The maximum number of messages that can be queued for the local MTA routing.</p>
<p>If this level is reached, a new incoming connection is rejected with a code indicating temporary congestion.</p>
<p>Default value: 512.</p>         </td>
      </tr>
      <tr>
         <td><p>RTS window size</p>         </td>
         <td><p>Specifies the number of checkpoints that can be transmitted without receiving an acknowledgment from the remote MTA. Checkpoints are used to synchronize a sending MTA with a receiving MTA. This value must be larger than 0.</p>
<p>Default value: 3.</p>         </td>
      </tr>
      <tr>
         <td><p>RTS checkpoint size</p>         </td>
         <td><p>Specifies the maximum amount of data that can be transmitted between two checkpoints. Valid values are within the range of 0 to 100 KB.</p>
<p>0 means that check pointing is disabled.</p>
<p>Default value: 1.</p>         </td>
      </tr>
      <tr>
         <td><p>Keep delivery reports time (h)</p>         </td>
         <td><p>This parameter instructs the MTC process not to discard delivery reports when the maximum number of connection attempts has been reached. Typically, when the MTC process fails to connect to a remote MTA, that is, does not make a connection after the configured number of attempts:</p>
<ul>
<li>All messages, notifications, and reports are removed from the message out-queue</li>
<li>A non-delivery report is sent for all messages and UA notifications, and</li>
<li>All reports are discarded</li>
</ul>
<p>If this option is used, all reports are kept in the message out-queue, and the MTC process keeps trying to connect to the remote MTA once every hour. The value of the hours argument specifies the number of hours during which the MTC process attempts to re-send delivery reports.</p>
<p>The value must be a whole number greater than zero.</p>         </td>
      </tr>
      <tr>
         <td><p>Keep notifications time (h)</p>         </td>
         <td><p>This parameter instructs the MTC process not to remove any X.420 notifications from the message out-queue when the maximum number of connection attempts has been reached. Typically, when the MTC process fails to connect to a remote MTA, that is, does not make the connection after the configured number of attempts:</p>
<ul>
<li>All messages, notifications, and reports are removed from the message out-queue</li>
<li>A non-delivery report is sent for all messages and notifications, and</li>
<li>All reports are discarded</li>
</ul>
<p>If this option is used, all X.420 notifications sent from the local UAs are kept in the message out-queue, and the MTC process keeps trying to connect to the remote MTA once every hour. The value of the argument specifies the number of hours during which the MTC process attempts to re-send notifications.</p>
<p>The value must be a whole number greater than zero.</p>         </td>
      </tr>
      <tr>
         <td><p>Min transfer speed (byte/s)</p>         </td>
         <td><p>This parameter is used to specify the lowest network transfer speed that can be expected. The process to calculate maximum transfer times uses this value. A message transfer is aborted if the maximum transfer time is exceeded.</p>
<p><span style="font-weight: bold;">Note:</span> This option should be used only when there is a problem with transfer timeouts and the value should never be increased.</p>
<p>Default value: 200 bytes/sec.</p>         </td>
      </tr>
      <tr>
         <td><p>Use RTS recovery</p>         </td>
         <td><p>Use this parameter to determine whether recovery should be carried out on broken connections or not.</p>
<p>Note that recovery is rarely used.</p>
<p>Default value: No recovery.</p>         </td>
      </tr>
      <tr>
         <td><p>Dialog mode</p>         </td>
      </tr>
      <tr>
         <td><p>Use</p>         </td>
         <td><p>Specifies whether messages may be sent in both directions on the same connection between two MTAs.</p>
<p>Select one of:</p>
<ul>
<li><span style="font-weight: bold;">Monolog:</span> one direction (default)</li>
<li><span style="font-weight: bold;">Two way alternate:</span> both directions (rarely used)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_ms"></span>

## Advanced MS settings

1.  Complete the fields of the <span style="font-style: italic;">Advanced MS client settings</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Max message size (B)</p>         </td>
         <td><p>Sets the maximum size on messages retrieved from the MS. If a message with a size larger than this value is found in the MS it is deleted from the Message Store (MS)</p>         </td>
      </tr>
      <tr>
         <td><p>Message fetch limit</p>         </td>
         <td><p>Maximum number of messages fetched in one MS poll. This functionality can be used to flow-control at peak hours. When the size is 0, no messages are retrieved. This can be useful when you want to test the MS connection without retrieving any messages.</p>         </td>
      </tr>
      <tr>
         <td><p>Min transfer speed (b/s)</p>         </td>
         <td><p>Specifies the lowest network transfer speed that can be expected. This value is used to calculate maximum transfer times. A message transfer is aborted if the maximum transfer time is exceeded.</p>         </td>
      </tr>
      <tr>
         <td><p>Transport class</p>         </td>
         <td><p>Transport class proposed at the establishment of a connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Time to keep sending notifications (h)</p>         </td>
         <td><p>This parameter instructs the MS client not to remove any X.420 notifications from the message out-queue when the maximum number of connection attempts has been reached. Normally, when the MS client fails to connect to a remote MS, that is, does not make the connection after the configured number of attempts:</p>
<ul>
<li>All messages and notifications are removed from the message out-queue.</li>
<li>An internal non-delivery report is sent for all messages and notifications.</li>
</ul>
<p>If this parameter is used, all X.420 notifications sent from the local UAs are kept in the message out-queue, and the MS client keeps trying to connect to the remote MS once every hour. The value of this field specifies the number of hours during which the MS client attempts to re-send notifications.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_ua"></span>

## Advanced UA settings

1.  Complete the fields of the <span style="font-style: italic;">Advanced X.420 UA settings</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Allow anonymous addressing</p>         </td>
         <td><p>If you select this option, the UA accepts messages coming from a sender with an OR-address that does not match any of the X.420 remote users.</p>         </td>
      </tr>
      <tr>
         <td><p>Notifications expected within (m)</p>         </td>
         <td><p>The time (in minutes) within which notifications are expected, if notifications have been requested. If this time is exceeded for a transfer for which notifications are requested, the original message is marked NACKED.</p>
<p>Default value: 1380 minutes.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

Related topics

[Configuring connectors](../../config_connectors)

[Configuring Gateway for X.400](../../../connectors_about/x400_about/x400_configuring)

[About X.400](../../../connectors_about/x400_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
