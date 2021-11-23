{
    "title": "New Remote Site: X.400 tab",
    "linkTitle": "X.400 tab",
    "weight": "320"
}{{< Gateway/componentlongname  >}}: Managing Partners

The Remote Site contains information on how to communicate with a remote Message Transfer Agent (MTA) or a Message Store (MS) mailbox.

P7 is the name of the protocol used to access a Message Store (MS) client from a User Agent (UA).

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Version</p>         </td>
         <td><p>Select:</p>
<ul>
<li>MTA</li>
<li>MSP7</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Password</strong>         </td>
      </tr>
      <tr>
         <td><p>Set Password</p>         </td>
         <td><p>Opens a dialog box to set the password.</p>
<p>For MTA:</p>
<p>Password that the local MTA uses to access the remote MTA.</p>
<p>For MSP7:</p>
<p>Password that the MS uses to authenticate itself. The MS in the connection-accept response sends the password and the P7-client validates the password before initiating any operations. Default: No authentication.</p>         </td>
      </tr>
      <tr>
         <td><strong>Set password to check</strong>         </td>
         <td><p>For MTA:</p>
<p>Password that the remote MTA uses to access the local MTA.</p>
<p>For MSP7:</p>
<p>Password used by the P7-client to authenticate itself. The client at connection establishment sends the password and the MS validates the password before it accepts the connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Communication parameters</p>
<p>These parameters identify the Service Access Points for the different communication layers.</p>
<p>You must specify at least one of these parameters. Typically the TSAP is used.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <code>'7C,A2'</code>.</p>         </td>
      </tr>
      <tr>
         <td><p>PSAP</p>         </td>
         <td><p>Presentation Service Access Point.</p>
<p>This parameter defines the OSI address for the net, transport, session, and presentation layer.</p>         </td>
      </tr>
      <tr>
         <td><p>SSAP</p>         </td>
         <td><p>Session Service Access Point.</p>
<p>This parameter defines the SSAP. Maximum 16 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>TSAP *</p>         </td>
         <td><p>Transport Service Access Point.</p>
<p>This parameter defines the TSAP. Maximum 20 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Routing...</p>         </td>
         <td><p>MTA only</p>
<p>Click <strong>Routing...</strong>. Refer to <a href="#olh_routing">Routing parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Scheduling...</p>         </td>
         <td><p>MSP7 only</p>
<p>Click <span style="font-weight: bold;">Scheduling...</span>. Refer to <a href="#olh_scheduling">Scheduling parameters</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced...</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Advanced...</span>.</p>
<p>For MTA-type Remote Sites, refer to <a href="#olh_advanced_mta">Advanced parameters (MTA)</a>.</p>
<p>For MSP7-type Remote Sites, refer to <a href="#olh_advanced_msp7">Advanced parameters (MSP7)</a>.</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Mandatory parameter

## Additional parameters for MTA-type Remote Sites

<span id="olh_routing"></span>

### Routing parameters

1.  Complete the fields of the <span style="font-style: italic;">Routing</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Routing O/R address *</p>         </td>
         <td><p>When there is no explicit information on where to route a message, the destination address is matched against any defined remote MTA routing address and the one which gives the best match is used.</p>         </td>
      </tr>
      <tr>
         <td><p>Edit...</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Edit...</span> to configure the <a href="../../../../configuration_start_here/config_protocols_about/x400_or_address">O/R address</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Clear</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Clear</span> to delete the displayed O/R address.</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Mandatory parameter

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_mta"></span>

### Advanced parameters (MTA)

1.  Complete the fields of the <span style="font-style: italic;">Advanced</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Version 84</p>         </td>
         <td><p>Typically the MTA version is greater than 84. If the version is 84, select this option.</p>         </td>
      </tr>
      <tr>
         <td><p>RTS X.410 mode</p>         </td>
         <td><p>Typically, a version 84 system uses RTS X.410 mode whereas non-84 systems do not use RTS X.410 mode.</p>
<p>Specify this option as appropriate.</p>         </td>
      </tr>
      <tr>
         <td><p>External name</p>         </td>
         <td><p>To have more than one remote MTA with the same MTA name, it is important to specify an external name that is to be used when contacting the MTA (MTA-MTA protocol). The MTA name specified in the X.400 MTA dialog is used locally and must be unique, whereas several MTAs can have the same external name. If no external name is specified, the MTA name specified in the X.400 MTA dialog is used.</p>         </td>
      </tr>
      <tr>
         <td><p>ADMD</p>         </td>
         <td><p>If you complete this parameter, the specified ADMD name is put in the originator's address if ADMD is set to an asterisk (*) when sending messages to this MTA. The reason for allowing this is that some ADMDs require the ADMD field to be set to their ADMD name when sending messages to that particular ADMD. The specified ADMD name is only substituted if the ADMD attribute in the O/R address of the originator is set to (*).</p>
<p><span style="font-weight: bold;">Note:</span> ADMD substitutions should only be used when you communicate with multiple ADMDs, and only if the ADMD requires that its ADMD name be used when contacting it.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

## Additional parameters for MSP7-type Remote Sites

<span id="olh_scheduling"></span>

### Scheduling parameters

These parameters are used for the polling of external MS mailboxes.

1.  Complete the fields of the <span style="font-style: italic;">Scheduling</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Monthly</p>         </td>
      </tr>
      <tr>
         <td><p>New</p>         </td>
         <td><p>Click this button to add Monthly scheduling parameters. Refer to <span style="font-style: italic;">Monthly scheduling parameters</span> below.</p>         </td>
      </tr>
      <tr>
         <td><p>Modify...</p>         </td>
         <td><p>Click this button to change Monthly scheduling parameters. Refer to <span style="font-style: italic;">Monthly scheduling parameters</span> below.</p>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>Click this button to delete the latest entry.</p>         </td>
      </tr>
      <tr>
         <td><p>Weekly</p>         </td>
      </tr>
      <tr>
         <td><p>New</p>         </td>
         <td><p>Click this button to add Weekly scheduling parameters. Refer to <span style="font-style: italic;">Weekly scheduling parameters</span> below.</p>         </td>
      </tr>
      <tr>
         <td><p>Modify...</p>         </td>
         <td><p>Click this button to change Weekly scheduling parameters. Refer to <span style="font-style: italic;">Weekly scheduling parameters</span> below.</p>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>Click this button to delete the latest entry.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="olh_scheduling_monthly"></span>Monthly scheduling parameters         </th>
      </tr>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Month</p>         </td>
         <td><p>Month of the polling sequence.</p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
      </tr>
      <tr>
         <td><p>From</p>         </td>
         <td><p>Start date of the monthly polling period.</p>         </td>
      </tr>
      <tr>
         <td><p>To</p>         </td>
         <td><p>Stop date of the monthly polling period.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Start time</p>         </td>
         <td><p>Time when the polling sequence begins.</p>         </td>
      </tr>
      <tr>
         <td><p>Stop time</p>         </td>
         <td><p>Time when the polling sequence ends.</p>         </td>
      </tr>
      <tr>
         <td><p>Frequency</p>         </td>
         <td><p>Length of time between mailbox polls. If set to zero, there is exactly one mailbox poll at start time.</p>         </td>
      </tr>
      <tr>
         <td><p>When you have finished, click <span style="font-weight: bold;">OK</span> to confirm the Monthly scheduling settings.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="olh_scheduling_weekly"></span>Weekly scheduling parameters         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Day</p>         </td>
      </tr>
      <tr>
         <td><p>From</p>         </td>
         <td><p>Start date of the weekly polling period.</p>         </td>
      </tr>
      <tr>
         <td><p>To</p>         </td>
         <td><p>Stop date of the weekly polling period.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Start time</p>         </td>
         <td><p>Time when the polling sequence begins.</p>         </td>
      </tr>
      <tr>
         <td><p>Stop time</p>         </td>
         <td><p>Time when the polling sequence ends.</p>         </td>
      </tr>
      <tr>
         <td><p>Frequency</p>         </td>
         <td><p>Length of time between mailbox polls. If set to zero, there is exactly one mailbox poll at start time.</p>         </td>
      </tr>
      <tr>
         <td><p>When you have finished, click <span style="font-weight: bold;">OK</span> to confirm the Weekly scheduling settings.</p>         </td>
      </tr>
   </tbody>
</table>

1.  When you have finished completing all scheduling parameters, click <span style="font-weight: bold;">OK</span> to confirm the settings.

<span id="olh_advanced_msp7"></span>

### Advanced parameters (MSP7)

1.  Complete the fields of the <span style="font-style: italic;">Advanced</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Time between submission</p>         </td>
         <td><p>Specifies the number of seconds between message submission. When the submission time event occurs, a check is made to see if the UA has any messages to be sent. If there are pending messages, a connection is established and all messages are sent. If this parameter is set to 0, the message submission will be done immediately after the UA has made a submission request.</p>
<p>Default value: 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Max inactivity time</p>         </td>
         <td><p>Specifies the number of seconds that the P7-client will keep an established MS connection up without any activity. If the parameter is set to 0, a connection is released as soon as all MS operations are made.</p>
<p>Default value: 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Max connection attempts</p>         </td>
         <td><p>Used by the P7-client when it fails to connect to the MS. The parameter states how many times a new connection attempt should be made before all messages waiting for submission will be returned to the UA as non-deliverable. Default value: 8.</p>         </td>
      </tr>
      <tr>
         <td><p>Time between connection attempts</p>         </td>
         <td><p>Used by the P7-client when it fails to connect to the MS. The parameter specifies the time, in seconds, that the P7-client should wait before it makes a new connection attempt. Default value: 60 seconds.</p>         </td>
      </tr>
      <tr>
         <td><p>Local TSAP</p>         </td>
         <td><p>Specifies the local TSAP. Maximum 20 characters. Default value: P7.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Poll at submission</p>         </td>
         <td><p>Specifies whether or not the P7-client is allowed to retrieve messages after message submission.</p>
<p>If selected, the P7-client is allowed to poll the Mailbox before the connection is released even if it is not yet time for the next mailbox poll.</p>
<p>Default value: selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Submit at poll</p>         </td>
         <td><p>Specifies whether or not the P7-client is allowed to submit messages after a mailbox poll.</p>
<p>If selected, the P7-client is allowed to submit messages before the connection is released even if it is not yet time for the next message submission.</p>
<p>Default value: selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Auto alert</p>         </td>
         <td><p>Determines whether or not the P7-client should request the auto alert functionality in the MS. The auto alert functionality enables the MS to immediately inform the P7-client that a new message or report has been entered into the users mailbox. When the P7-client receives an alert indication, it will immediately fetch the new message or report.</p>
<p><span style="font-weight: bold;">Note:</span> The alert indication is only sent on an existing connection initiated by the P7-client. The auto alert function is used only if the configuration parameter Max inactivity time is greater than 0.</p>
<p>If selected, the auto alert function is requested. If not selected, no auto alert function is requested.</p>
<p>Default value: Not selected.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the settings.

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[X.400 connector](../../../../connectors_about/x400_about/x400_connector)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
