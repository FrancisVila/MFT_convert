{
    "title": "SWIFTNet input channels",
    "linkTitle": "Store&Forward",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About SWIFTNet input channels](#about)

[Creating input channels](#creating_input_channels)

[Specifying the input channel in the Remote Site](#specifying)

[More information](#more_info)

<span id="about"></span>

## About SWIFTNet input channels

Input channels are designed to guarantee that the store-and-forward traffic sent to the SWIFT network respects a particular sequence.

SWIFT 7.0 only supports the sending of *Interact* messages through input channels.

It is not necessary to use input channels if the business applications exchanging messages already support the exchange of non-sequenced traffic.

<span id="creating_input_channels"></span>

## Creating input channels

Gateway automatically creates a default input channel for the BIC. If required, create additional input channels using the <span class="codeBold_in_para">pelctl create\_input\_channel</span> command. Make sure that you respect the SWIFT naming conventions for input channels. For example, input channel names must be in lower case. Gateway does not check or correct the name or case of the channel. If the name is not SWIFT-compliant it will be rejected by SWIFT.

It is possible to restrict the creation of input channels. If user security is activated, only a user who has administrator control of the Remote Site used for the creation will be able to create the input channel.

### Security considerations relating to input channels

See *Security Guide &gt; Security best practices &gt; [Identified threats and possible mitigations](##identified_threats_and_possible_mitigations)* for further information (requires login).

<span id="pelctl_create_input_channel"></span>

### Creating an input channel using command line


    pelctl create_input_channel

       -input_channel (-ic) CHANNELNAME
       -site (-si) SITENAME
       -wait

### pelctl  create\_input\_channel parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-input_channel (-ic)</p>         </td>
         <td><p>The name of the input channel</p>         </td>
      </tr>
      <tr>
         <td><p>-site (-si)</p>         </td>
         <td><p>Remote Site used to create the input channel</p>         </td>
      </tr>
      <tr>
         <td><p>-wait</p>         </td>
         <td><p><em>Optional</em></p>
<p>Wait for SWIFT to process the channel creation request.</p>
<p>If the channel creation fails, an error is displayed.</p>         </td>
      </tr>
   </tbody>
</table>

### Example 1

Create an input channel for BIC bankfrpp:

pelctl create\_input\_channel -input\_channel bankfrpp\_sample –site SWNET\_EP1

This request should be successful.

### Example 2

Attempt to create the following input channel and wait for the reply:

pelctl create\_input\_channel -input\_channel BankfrpP\_sAmple -site SWNET\_EP1 -wait

The creation of this channel is refused by SWIFT (input channel name must be lower case).

Error message:

pelctl create\_input\_channel: bad request

<span id="pelctl_open_input_channel"></span>

### Opening an input channel using command line

You should open an input channel from the command line if you added it in the Site before creating it and the Site is not able to open it.

You can force the input channel to open if there were some errors at normal opening. This mode allows the channel to be opened even if it has not been properly closed or it is locked.


    pelctl  open_input_channel

       -site (-si) SITENAME
       -input_channel_window (-icw) 1...12
       -input_channel_force (-icf) { (Y) | N }

### pelctl  open\_input\_channel parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-site (-si)</p>         </td>
         <td><p>The Site where the input channel is defined.</p>         </td>
      </tr>
      <tr>
         <td><p>-input_channel window(-icw)</p>         </td>
         <td><p>The size of the input channel window. See SWIFT documentation for more information.</p>         </td>
      </tr>
      <tr>
         <td><p>-input channel force (-icf)</p>         </td>
         <td><p><em>Optional</em></p>
<p>Force the opening of the input channel.</p>
<p>Possible values:</p>
<ul>
<li><span class="codeBold_in_para">Y</span> (yes)</li>
<li><span class="codeBold_in_para">N</span> (no)</li>
</ul>
<p>If set to <span class="bold_in_para">Y</span>, the open is successful even if the input channel is already open.</p>         </td>
      </tr>
   </tbody>
</table>

### Example

pelctl open\_input\_channel –site SWIFT7 -input\_channel\_window 20

<span id="pelctl_close_input_channel"></span>

### Closing an input channel using command line

The command line enables you to close the input channel without stopping the Site.


    pelctl  close_input_channel

       -site (-si) SITENAME

### pelctl  close\_input\_channel parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-site (-si)</p>         </td>
         <td><p>The Site where the input channel is defined.</p>         </td>
      </tr>
   </tbody>
</table>

### Example

pelctl close\_input\_channel –site SWIFT7

<span id="pelctl_delete_input_channel"></span>

### Deleting an input channel using command line


    pelctl  delete_input_channel

       -input_channel (-ic) CHANNELNAME
       -site (-si) SITENAME
       -wait

### pelctl  delete\_input\_channel parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-input_channel (-ic)</p>         </td>
         <td><p>The name of the input channel</p>         </td>
      </tr>
      <tr>
         <td><p>-site (-si)</p>         </td>
         <td><p>The site where the input channel is defined.</p>         </td>
      </tr>
      <tr>
         <td><p>-wait</p>         </td>
         <td><p><em>Optional</em></p>
<p>Wait for SWIFT to process the request.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="specifying"></span>

## Specifying the input channel in the Remote Site

You specify the input channel to be used in the Remote Site. A Remote Site can use only one input channel at a time. If you want to use more than one input channel, use a separate Remote Site for each one. To guarantee the correct ordering of messages, an input channel cannot be used by several Remote Sites at the same time.

By default, the input channel is opened in force mode. This mode allows the channel to be opened even if it has not been properly closed or it is locked.

A window size is provided as a parameter of the open input channel request. However, only the parameter provided in the reply will be the one used by SWIFT.

### Specifying the input channel using the Gateway GUI

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">New</span> to display the <span style="font-style: italic;">New Remote Site</span> window.
3.  Complete the fields on the <span style="font-weight: bold;">[General](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab. In the <span style="font-weight: bold;">Protocol</span> field, make sure you select <span style="font-weight: bold;">SWIFTNet</span>.
4.  Complete the fields on the <span style="font-weight: bold;">[Options](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_options_tab)</span> tab.
5.  On the <span style="font-weight: bold;">[SWIFTNet](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_swiftnet_tab)</span> tab, select the **SnF** sub-tab and complete the **Input Channel** field.
6.  Click <span style="font-weight: bold;">OK</span>.  
    Gateway creates a new Remote Site with the specified characteristics.

### Specifying the input channel using online commands

Create a Remote Site using the <span class="code" style="font-weight: bold;">[<span class="code" style="font-weight: bold;">peladm create\_site</span>](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_create_site)</span> online command.


    peladm create_site

       -input_channel (-ic)
       -input_channel_window (-icw) 1...12
       -input_channel_force (-icf) { (Y) | N }

For details of parameters, refer to the table below.

<span id="swift_ip_ch_paras"></span>

### Remote Site parameters specific to SWIFTNet input channels

In this table, the corresponding field name (if available) in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-input_channel (-ic)</p>
<p>Input Channel</p>         </td>
         <td><p>The name of the input channel.</p>
<p><strong>Note:</strong> The input channel must already exist! First create the channel using the <span class="codeBold_in_para">pelctl create_input_channel</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p>-input_channel_force (-icf)</p>         </td>
         <td><p><em>Optional</em></p>
<p>Force the opening of the input channel.</p>
<p>Possible values:</p>
<ul>
<li><span class="codeBold_in_para">Y</span> (yes)</li>
<li><span class="codeBold_in_para">N</span> (no)</li>
</ul>
<p>Default = <span class="codeBold_in_para">Y</span>.</p>
<p>You should normally need to change the default value.</p>         </td>
      </tr>
      <tr>
         <td><p>-input_channel_window (-icw)</p>         </td>
         <td><p><em>Optional</em></p>
<p>The proposed input channel window size.</p>
<p>You can specify a value when opening an input channel. However, only the value provided in the reply will be the one used by SWIFT.</p>
<p>Normally you do not need to change the default value. Only specify the window size if you want to restrict the value.</p>
<p>Possible values: 1 - 12. Default = 12</p>         </td>
      </tr>
   </tbody>
</table>

For details of all other Remote Site parameters, refer to [Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list).

### Example


    peladm create_site  -input_channel CHANNELNAME  -input_channel_window 8

## Updating the input channel in the Remote Site

This section explains how to update an input channel in the Remote Site.

### Updating the input channel using the Gateway GUI

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  In the right pane, right-click the name of the Remote Site for which you want to modify the input channel. Select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Remote Site</span> editing window.
4.  On the <span style="font-weight: bold;">[SWIFTNet](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_swiftnet_tab)</span> tab, select the **SnF** sub-tab and modify the **Input Channel** field.
5.  Click <span style="font-weight: bold;">OK</span>.

### Updating the input channel using online commands

Use the [<span class="code" style="font-weight: bold;">peladm update\_site</span>](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_delete_site) command to update the input channel specified in the Remote Site.


    peladm update_site

       -input_channel (-ic)
       -input_channel_window (-icw) 1...12
       -input_channel_force (-icf) { (Y) | N }

For details of parameters, refer to the table [above](#swift_ip_ch_paras).

## Sending messages using input channels

Gateway manages the order in which traffic is sent. Messages are automatically assigned a sequence number based on the order of the creation of the transfers.

This ordering is guaranteed for all transfers using the same priority.

An InterAct Store and Forward message will automatically use the input channel from its Remote Site if it has been specified.

A Remote Site using an input channel can still handle real time and FileAct transfers. It is however advisable to use a separate Remote Site since the ordering of the InterAct Store and Forward messages can slow down the processing of the rest of the traffic.

It is still possible to send InterAct Store and Forward traffic without using input channels through a Remote Site where such a channel has not been specified.

Input channel ordering will work with PassPort or a user exit as long as the Transfer Request contains enough information to identify an InterAct Store and Forward transfer.

### Example

Enter:

peltrans -type MSG -snd\_msg XXX -ap FTP\_B -tradeoa L\_TRADE -tradeda TRADE\_IA\_ST -da SWIFT\_EP1

Gateway returns:

18

Enter:

peldsp display\_trans –i 18

Gateway returns:

\[…\]

x\_full\_state='ENDED'

\[…\]

x\_sequence\_number=’2’

x\_ic\_name=’bankfrpp\_sample’

x\_snf\_input\_time='0124:2011-06-21T15:49:29'

## Resolving gaps

A *gap* exists when the sequencing of the accepted transfers is not contiguous. A gap is created when a transfer using an input channel is rejected by SWIFT. This case is also likely to occur when Gateway is stopped while exchanges are being made using the input channel.

Transfers that have sequence numbers higher than the gap are accepted as long as the window of the input channel allows this. However, until the gap is resolved, such outgoing transfers remain in a non-final state and have an empty SnFInputTime.

It is therefore very important to avoid creating gaps by checking the validity of the transfers or to resolve the gaps as quickly as possible.

#### Example

Send a transfer using input channels, check SnFInputTime, sequence number and input channel for ended transfers.

When a transfer using an input channel is canceled, a gap resolution process is launched based on the sequence number attached to the transfer.

Gateway will also try to resolve gaps if they are detected as a result of opening an input channel.

#### Example

Send 3 transfers configured so that the 1st is accepted by SWIFT, the 2nd is rejected and 3rd is accepted. Then cancel transfer 2. A gap resolution process is launched. Check the message log. Transfer 3 should be ended with an SnF Input Time at the end of the gap resolution.

## Closing input channels

An input channel is automatically closed when you stop a Site (using the <span class="code"><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#pelctl_stop_site" class="codeBold_in_para">pelctl stop_site</a></span> command) or when you stop Gateway. However, when you stop Gateway, there is no guarantee that it will have the time to close the input channel.

The closure of an input channel is only accepted if there is no gap. It is however possible to re-open an existing opened input channel which has gaps.

The command line enables you to close the input channel without stopping the Site.

<span id="more_info"></span>

## More information

For more information about SWIFTNet input channels, refer to the SWIFT official documentation.

Related topics

[SWIFTNet connector](../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../swiftnet_connector/swiftnet_configuring)

[Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list)

[SWIFTNet (SNET) log messages](../../../log_messages_about/swiftnet_messages_(snet))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
