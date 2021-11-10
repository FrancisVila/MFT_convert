{
    "title": "Configuring the RosettaNet environment",
    "linkTitle": "Configuring for RosettaNet",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[Prerequisites](#Prerequisites_RosettaNet)

[Required objects](#Required_objects_RosettaNet)

[Creating objects for RosettaNet transfers](#Creating_objects_for_RosettaNet_transfers)

<span id="Prerequisites_RosettaNet"></span>

## Prerequisites

Before you can send and receive transfers via RosettaNet and perform processing on these transfers, you need to:

-   Confirm that you have a TCP/IP connection, and that your business exchange partners are connected to the network at the time you initiate or expect to receive a file transfer or acknowledgment.
-   Activate the appropriate supporting protocol processes in the Gateway [configuration menu](../../../configuration_start_here/config_protocols_about/config_protocols).
-   Ensure that you have access to the necessary Public Key Infrastructure (PKI). Each exchange partner must possess the public certificate for the remote and local partner as well as the associated private key.
    See the *Security Guide > [Certificates and keys](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/certificates_and_keys_start_here.htm)* for further information (requires login).
-   With each business exchange partner, you establish a RosettaNet exchange contract known as a <span style="font-style: italic;">Trading Partner Agreement</span>. In a Trading Partner Agreement you mutually establish:
    -   RosettaNet identifiers, unique names for every exchange entity
    -   Target file directory locations for your exchanges
    -   Signing and encryption algorithms  
        When you configure your respective RosettaNet compliant applications, you must scrupulously respect the terms of your Trading Partner Agreement.

<span id="Required_objects_RosettaNet"></span>

## Required objects

You require a different set of objects depending on whether you are sending or receiving a transfer. A complete RosettaNet exchange normally comprises a request phase and a file transfer phase. Between these two phases, the initiator and responder machines trade roles. For this reason, whether Gateway is acting as initiator or responder in a RosettaNet exchange, you require the same set of objects to complete the file transfer/receipt transfer cycle.

### Sending transfers

To successfully initiate a RosettaNet transfer you require as a minimum the following Gateway objects:

-   Remote Site object: to specify transport layer characteristics of the remote machine to which you are sending a file or a receipt
-   Local Trading Partner object, to specify:
    -   Local identification
    -   Signing certificate and signing algorithm on emission
    -   Optionally, the encryption certificate necessary for decrypting the returned receipt
-   Remote Trading Partner object: to specify the remote compression, signature, encryption and encapsulation processes for the exchange with your business partner

### Receiving transfers

To successfully receive a RosettaNet transfer from a remote business partner, you require as a minimum the following Gateway objects:

-   Remote Site object: to specify transport layer characteristics of the remote machine from which you are receiving the file
-   Local Trading Partner object, to specify:
    -   Local identification
    -   Signing certificate and signing algorithm for controlling the message on reception
    -   Optionally, the encryption certificate necessary for encrypting the return receipt
-   Remote Trading Partner object: to specify the remote compression, signature, encryption and encapsulation processes for exchanges with your business partner
-   CGateGroup and CGate objects: to control the remote connection to your machine by your business partner for transfer of the file or receipt

<span id="Creating_objects_for_RosettaNet_transfers"></span>

## Creating objects for RosettaNet transfers

This section describes how to create the following objects for RosettaNet transfers:

-   Remote Site objects
-   Local Trading Partner objects
-   Remote Trading Partner objects
-   CGateGroup objects
-   CGate objects

### Creating a Remote Site object for RosettaNet transfers

The Remote Site object provides Gateway with information about the remote machine to which you are sending your RosettaNet messages and receipts.

You can create Remote Site objects in Gateway either via the GUI or using command line.

#### Using the GUI

To create a Remote Site object via the GUI:

1.  In the left pane of the GUI main window, click to expand the nodes:  
    **Partner Management > Sites**
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New Remote Site</span> window.
3.  In this window, enter values in the fields to define the characteristics of the [Remote Site](../../../managing_partners_start_here/sites_start_here/managing_remote_sites) object.

The following Remote Site attributes specifically concern RosettaNet Transfer Requests.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Tab</p>         </th>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Parameter value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>General</p>         </td>
         <td><p>Protocol</p>         </td>
         <td><p>Select the appropriate protocol:</p>
<ul>
<li><strong>RN_HTTP</strong></li>
<li><strong>RN_SMTP</strong></li>
<li><strong>RN_POP3</strong></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Using command line

To create a Remote Site object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_site](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_create_site)</span> command. The precise values you enter depend on your transfer requirements. The following parameters specifically concern RosettaNet Transfer Requests.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>RosettaNet-related value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-protocol (-pr)</span></p>         </td>
         <td><p>Specify one of the following protocols:</p>
<ul>
<li>RN_HTTP</li>
<li>RN_SMTP</li>
<li>RN_POP3</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Creating a Local Trading Partner object for RosettaNet transfers

The Local Trading Partner object provides Gateway with information about the RosettaNet compression, signature, encryption and encapsulation operations that you use to transfer your message. It also enables you to specify how to handle the acknowledgments returned by remote partners.

You can create Local Trading Partner objects in Gateway either via the GUI or using command line.

#### Using the GUI

To create a Local Trading Partner object via the GUI:

1.  In the left pane of the GUI main window, click to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">Trading Partner</span> window.  
    In this window, you define the characteristics of the Local Trading Partner object by entering values in the appropriate fields.  
    Refer to [Working with Trading Partner objects](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui)).

#### Using command line

To create a Local Trading Partner object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_tradepart](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli#peladm_create_tradepart)</span> command.

### Creating a Remote Trading Partner object for RosettaNet transfers

The Remote Trading Partner object provides Gateway with information about the compression, signature, encryption and encapsulation operations defined by the RosettaNet protocol.

You can create Remote Trading Partner objects in Gateway either via the GUI or using command line.

#### Using the GUI

1.  In the left pane of the GUI main window, click to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">Trading Partner</span> window.  
    In this window, you define the characteristics of the Remote Trading Partner object by entering values in the appropriate fields.  
    Refer to [Working with Trading Partner objects](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui)).

#### Using command line

To create a Remote Trading Partner object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_tradepart](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli#peladm_create_tradepart)</span> command.

### Creating a CGateGroup object for RosettaNet transfers

To receive RosettaNet messages or message receipts from a business partner on your local machine, you control remote connection attempts to your machine via the CGateGroup object and CGate object.

You can create CGateGroup and CGate objects in Gateway either via the GUI or using command line.

#### Using the GUI

To create a CGateGroup object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window. Complete this window to define the characteristics of your new CGateGroup.  
    Refer to [Working with CGates and CGateGroups](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui)).  
    In particular, when you create the CGateGroup, specify, in the <span style="font-weight: bold;">Protocol</span> field, the protocol that is used by the connecting partner:

-   **RN\_HTTP**
-   **RN\_SMTP**
-   **RN\_POP3**

#### Using command line

To create a CGateGroup object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_cgategroup](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli/working_with_cgategroups_cli#peladm_create_cgategroup)</span> command.

To enable the reception of a connection based on a RosettaNet protocol, in the <span class="code" style="font-weight: bold;">protocol</span> attribute of this command, enter one of the following values to specify the RosettaNet protocol format used by your remote partner for the acknowledgment transfer:

-   RN\_HTTP
-   RN\_SMTP
-   RN\_POP3

### Creating a CGate object for RosettaNet transfers

To specify the login name and password requirements for AS1 or AS2 connections to your local machine, create a CGate in the CGateGroup you created in the previous section.

You can create CGate objects in Gateway either via the GUI or using command line.

#### Using the GUI

To create a CGate object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">CGate</span> node.
3.  Select the CGateGroup created in the previous section.
4.  Right-click the CGateGroup, and from the context menu that appears, select <span style="font-weight: bold;">New > CGate...</span>.  
    Gateway displays the <span style="font-style: italic;">New CGate</span> window. Complete this window to define the characteristics of your new CGate.  
    Use the CGate object to define login requirements and directories with associated directory access rights for AS2 (HTTP) and AS3 (FTP) based transfers.  
    Refer to [Working with CGates and CGateGroups](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui)).

#### Using command line

To create a CGate object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_cgate](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli#peladm_create_cgate)</span> command.

Use the CGate object to define login requirements and directories with associated directory access rights for RN\_HTTP based transfers.

Related topics

[About RosettaNet](../)

[Working with Trading Partner objects](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))

[Working with Trading Partner objects (command line)](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli)

[Using RosettaNet](../rosettanet_using)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
