{
    "title": "Backup remote sites for SWIFTNet",
    "linkTitle": "Implementing SWIFTNet exchanges",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About backup Remote Sites for SWIFTNet](#about)

<a href="#Backup" class="MCXref xref">Backup site hierarchy limitation</a>

[Defining a backup Site](#defining)

[Starting and stopping SWIFTNet Remote Sites](#starting_and_stopping)

[Transfer behavior](#transfer_behavior)

[Static and Dynamic backup](#static_and_dynamic)

<span id="about"></span>

## About backup Remote Sites for SWIFTNet

To ensure service continuity, you can define backup Sites for use with SWIFTNet transfers. If a transfer to a SWIFTNet Remote Site (the nominal Site) fails, for example if the connection with SWIFTNet is lost, Gateway will use the backup Site as an alternative.

Gateway can only use a backup Site if it is active. Depending on your requirements, you can start and stop backup Sites. If a transfer cannot be sent to the nominal Site or to a backup Site, it remains in the TO\_BEGIN state until the connection with SWIFTNet is available.

<span id="Backup"></span>

## Backup site hierarchy limitation

The backup Site hierarchy is limited to one. This means <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> does not support a chain of backup Sites (more than one element in chain when the backup also has set a backup Site). Selecting a Site as backup for more than one nominal Sites is not supported.

One SWIFTNet remote sites can have up to 4 backup Sites selected.

See <a href="../swiftnet_input_channels/swiftnet_filtering_duplicates#Dynamica" class="MCXref xref">Dynamically filtering duplicates for queues and output channels</a>

<span id="defining"></span>

## Defining a backup Site

Define the backup Site when *creating* or *modifying* the nominal SWIFTNet Remote Site. You specify the alias of the backup Site in the nominal Site.

<span style="font-weight: bold;">Prerequisite:</span> The backup Site must exist (create the backup Site first).

To modify the nominal SWIFTNet Remote Site and define the backup Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Partner Management > Sites**
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  Right-click the name of the Remote Site for which you want to modify the Site attributes and select <span style="font-weight: bold;">Modify...</span> .  
    Gateway displays the *Remote Site* editing window.
4.  Click the <span style="font-weight: bold;">[SWIFTNet](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_swiftnet_tab)</span> tab.  
    The currently selected backup Sites are displayed in the Backup Sites list.
5.  Click the **Change…** button next to the **Backup Sites** list.
6.  In the newly created window, you can select up to 4 Sites as backup Sites.  
    Click **OK** to save the current selection and return to the Remote Site editing window.
7.  Click **OK**.

Alternatively, use one of the following online commands:

• `peladm create_site  -a ABCD  -bks “BKPSITE1 BKPSITE2” ` (create nominal Site)

•`  peladm update_site  -a ABCD  -bks “BKPSITE1 BKPSITE2”    `(update nominal Site)

Up to 4 backup Sites can be specified for a remote Site. Gateway checks that the specified backup Site aliases exists.

<span id="starting_and_stopping"></span>

## Starting and stopping SWIFTNet Remote Sites

<span style="font-weight: bold;">Note:</span> After restarting Gateway, all SWIFTNet Remote Sites are automatically started if both Initiator and Responder modes are set.

### Stopping a SWIFTNet Remote Site

To stop a SWIFTNet Remote Site:

1.  Right-click the name of the Site.
2.  Deselect <span style="font-weight: bold;">Initiator mode (dynamic)</span>.  
    You may need to wait for up to 30 seconds for the Site to stop.  
    After stopping a Site, all client and server processes are stopped.

Alternatively, use the online command:

pelctl stop\_site  -a ABCD  -im

### Starting a SWIFTNet Remote Site

To start a SWIFTNet Remote Site:

1.  Right-click the name of the Site.
2.  Select <span style="font-weight: bold;">Initiator mode (dynamic)</span>.  
    You may need to wait for up to 30 seconds for the Site to start.  
    After starting a Site, all server processes are started. If required, client processes are started, to start acquiring queues.

Alternatively, use the online command:

pelctl start\_site  -a ABCD  -im

### Auto Deactivate

You can set a SWIFTNet Remote Site to automatically deactivate after a maximum number of attempts

-   by configuring \[monitor\]stop\_site\_on\_max\_retry\_reached parameter with peluconf command,
-   or from Gateway Navigator

See section
Configuring Gateway parameters
&gt;
<a href="../../../configuration_start_here/config_gateway_paras#Advanced_parameters" class="MCXref xref">Advanced parameters and Trace levels</a>

### Number of retries

The <span class="code">swift\_job\_retry\_count\_max</span> parameter in the <span class="code">conffile</span> controls the number of retries in the case of a connection error with SAG. The value of this parameter is taken into account by the client and server processes. You can modify the value of this parameter if required by editing the <span class="code">[pelsetup.def](../../../configuration_start_here/t_gw_config_conffile_paras_modify)</span> file.

<span style="font-weight: bold;">Example:</span> If the connection to SAG is broken, the client/server process retries to establish the connections as many times as specified by this parameter.

<span id="transfer_behavior"></span>

## Transfer behavior

Consider a configuration with two SWIFTNet Sites:

-   Nominal Site
-   Backup Site

In this example, the following possible cases of transfer behavior exist:

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Case         </th>
<th class="HeadE-Column1-Header1">Nominal Site         </th>
<th class="HeadE-Column1-Header1">Backup Site         </th>
<th class="HeadD-Column1-Header1">Transfer behavior         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Inactive</p>         </td>
         <td><p>None</p>         </td>
         <td><p>The transfer remains in the TO_BEGIN state.</p>
<p>If you want the transfer to change to the CANCELED state, specify the latest start date when submitting the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Inactive</p>         </td>
         <td><p>Defined (in nominal Site) and <span style="font-weight: bold;">active</span></p>         </td>
         <td><p>The transfer is made directly to the backup Site.</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Inactive</p>         </td>
         <td><p>Defined (in nominal Site) and <span style="font-weight: bold;">inactive</span></p>         </td>
         <td><p>Same behavior as case 1.</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Inactive</p>         </td>
         <td><p>Defined (in nominal Site) but the backup Site no longer exists because it has been deleted</p>         </td>
         <td><p>Same behavior as case 1.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="static_and_dynamic"></span>

## Static and Dynamic backup

Two types of backup situation exist:

### Static backup

When a transfer is launched on the nominal Site but the Site is not active, the transfer is automatically started on the backup Site.

**Prerequisites:** The nominal Site has a backup Site and the backup Site is active.

### Dynamic backup

When a transfer is launched on the nominal Site and the maximum number of retries<span class="code"> retry\_count\_max (-rc\_max)</span> for this transfer has been reached, the transfer is automatically started on the backup Site.

**Prerequisites:** The nominal Site has a backup Site and the backup Site is active.

Related topics

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../swiftnet_connector/swiftnet_configuring)

[About Site objects](../../../managing_partners_start_here/sites_start_here)

[Modifying conffile parameters](../../../configuration_start_here/t_gw_config_conffile_paras_modify)

[SWIFTNet queues and output channels](../swiftnet_input_channels/swiftnet_output_channels)

[SWIFTNet queue sharing](../swiftnet_input_channels/swiftnet_queue_sharing)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
