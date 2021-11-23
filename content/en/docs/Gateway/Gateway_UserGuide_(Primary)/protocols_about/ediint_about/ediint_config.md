{
    "title": "Configuring and using EDIINT",
    "linkTitle": "Configuring and using EDIINT",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Protocols

[Configuring Gateway for EDIINT](#Configuring_Gateway)

[Creating objects for EDIINT transfers](#Creating_objects)

[Using EDIINT on Gateway](#Using_EDIINT)

<span id="Configuring_Gateway"></span>

## Configuring Gateway for EDIINT

### Prerequisites

Before you can send and receive transfers via EDIINT and perform processing on these transfers, you need to:

-   Confirm that you have a TCP/IP connection, and that your business exchange partners are connected to the network at the time you initiate or expect to receive a file transfer or acknowledgment
-   Activate the appropriate supporting protocol processes in the [configuration menu](../../../configuration_start_here/config_protocols_about/config_protocols)
-   Ensure that you have access to the necessary Public Key Infrastructure (PKI). Each exchange partner must possess the public certificate for the remote and local partner as well as the associated private key.
    See *Security Guide > [Certificates and keys](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/certificates_and_keys_start_here.htm)* for further information (requires login).
-   With each business exchange partner, you establish an EDI exchange contract known as a *Trading Partner Agreement*. In a Trading Partner Agreement you mutually establish:
    -   your EDI identifiers, unique names for every exchange entity
    -   the services you want to apply to your exchanges: signing, encryption, compression, and receipt management
    -   target file directory locations for your exchanges
    -   signing and encryption algorithms
    -   for AS2, synchronization or non-synchronization of receipt emissions

      
    When you configure your respective EDIINT compliant applications, you must scrupulously respect the terms of your Trading Partner Agreement.

### Required objects

You require a different set of objects depending on whether you are sending or receiving a transfer. A complete EDIINT exchange normally comprises a file transfer phase and a receipt transfer phase. Between these two phases, the initiator and responder machines trade roles. For this reason, whether Gateway is acting as initiator or responder in an EDIINT exchange, you require the same set of objects to complete the file transfer/receipt transfer cycle.

#### Sending transfers

To successfully initiate an EDIINT transfer you require as a minimum the following Gateway objects:

-   [Remote Site object](#Creating_remote_site_EDIINT)  
    to specify transport layer characteristics of the remote machine to which you are sending a file or a receipt
-   [Local Trading Partner object](#Creating_local_TP_EDIINT)  
    to specify:
    -   local identification
    -   the signing certificate and signing algorithm on emission
    -   optionally, the encryption certificate necessary for decrypting the returned receipt
-   [Remote Trading Partner object](#Creating_remote_TP_EDIINT)  
    to specify the remote compression, signature, encryption and encapsulation processes for the exchange with your business partner.

#### Receiving transfers

To successfully receive an EDIINT transfer from a remote business partner, you require as a minimum the following Gateway objects:

-   [Remote Site object](#Creating_remote_site_EDIINT)  
    to specify transport layer characteristics of the remote machine from which you are receiving the file
-   [Local Trading Partner object](#Creating_local_TP_EDIINT)  
    to specify:
    -   local identification
    -   the signing certificate and signing algorithm for controlling the message on reception
    -   optionally, the encryption certificate necessary for encrypting the return receipt
-   [Remote Trading Partner object](#Creating_remote_TP_EDIINT)  
    to specify the remote compression, signature, encryption and encapsulation processes for exchanges with your business partner.
-   [CGateGroup and CGate objects](#Creating_CGate_EDIINT)  
    to control the remote connection to your machine by your business partner for transfer of the file or receipt

#### Additional required objects

The above objects take into account only the basic objects necessary for the transfer. Depending on your transfer type and business context, you will require additional Gateway objects to process incoming files. These objects can include, for example, VFD or RFD objects, SSL/TLS security objects, Decision Rule objects, and so on.

<span id="Creating_objects"></span>

## Creating objects for EDIINT transfers

As described in the previous section, you must create a certain number of Gateway objects before you can use Gateway to send and receive files via EDIINT:

-   [Remote Site objects](#Creating_remote_site_EDIINT)
-   [Local Trading Partner objects](#Creating_local_TP_EDIINT)
-   [Remote Trading Partner objects](#Creating_remote_TP_EDIINT)
-   [CGate objects](#Creating_CGate_EDIINT)

<span id="Creating_remote_site_EDIINT"></span>

### Creating a Remote Site object for EDIINT transfers

The Remote Site object provides Gateway with information about the remote machine to which you are sending your EDIINT messages and receipts.

You can create Remote Site objects in Gateway either via the GUI or command line.

#### Using command line

To create a Remote Site object via command line, use the `peladm create_site` command. The parameter values depend on your transfer requirements.

The following `peladm create_site` parameters specifically concern EDIINT transfers.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">EDIINT-related value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><code>-protocol (-pr)</code></p>         </td>
         <td><p>Specify one of the following protocols:</p>
<ul>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>AS2</li>
<li>AS3</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Using the GUI

To create a Remote Site object via the GUI:

1.  In the left pane of the GUI main window, click to expand the nodes:  
    **Partner Management > Sites**
2.  Right-click the **Remote Site** sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New Remote Site</span> window.  
    Define the characteristics of the Remote Site object by entering values in the fields. Refer to [Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites).

The following Remote Site parameters specifically concern EDIINT transfers.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Tab         </th>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>General</strong></p>         </td>
         <td><p><strong>Protocol</strong></p>         </td>
         <td><p>Select the appropriate protocol:</p>
<ul>
<li><strong>AS1_POP3</strong></li>
<li><strong>AS1_SMTP</strong></li>
<li><strong>AS2</strong></li>
<li><strong>AS3</strong></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Creating_local_TP_EDIINT"></span>

### Creating a Local Trading Partner object for EDIINT transfers

The Local Trading Partner object provides Gateway with information about the EDIINT compression, signature, encryption and encapsulation operations that you use to transfer your message. It also enables you to specify how to handle the acknowledgments returned by remote partners.

You can create Local Trading Partner objects in Gateway either via the GUI or command line.

#### Using command line

To create a Local Trading Partner object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_tradepart](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli#peladm_create_tradepart)</span> command.

#### Using the GUI

To create a Local Trading Partner object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays a context menu.
3.  Select <span style="font-weight: bold;">New</span>.  
    Gateway displays a context menu.
4.  Select the type of partner:
    -   AS1 partner
    -   AS2 partner
    -   AS3 partner

<span id="Creating_remote_TP_EDIINT"></span>

### Creating a Remote Trading Partner object for EDIINT transfers

The Remote Trading Partner object provides Gateway with information about the compression, signature, encryption and encapsulation operations defined by the EDIINT protocol.

You can create Remote Trading Partner objects in Gateway either via the GUI or command line.

#### Using command line

To create a Remote Trading Partner object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_tradepart](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli#peladm_create_tradepart)</span> command.

#### Using the GUI

To create a Remote Trading Partner object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays a context menu.
3.  Select <span style="font-weight: bold;">New</span>.  
    Gateway displays a context menu.
4.  Select the type of partner:
    -   AS1 partner
    -   AS2 partner
    -   AS3 partner

      
    Gateway displays the <span style="font-style: italic;">Trading Partner</span> window.  
    In this window, you define the characteristics of the Remote Trading Partner object by entering values in the appropriate fields. Refer to [Working with Trading Partner objects](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui)).

<span id="Creating_CGate_EDIINT"></span>

### Creating a CGateGroup object for EDIINT transfers

To receive EDIINT messages or message receipts from a business partner on your local machine, you control remote connection attempts to your machine via the CGateGroup object and CGate object.

You can create CGateGroup and CGate objects in Gateway either via the GUI or command line.

#### Using command line

To create a CGateGroup object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_cgategroup](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli/working_with_cgategroups_cli#peladm_create_cgategroup)</span> command.

To enable the reception of a connection based on an EDIINT protocol, in the <span class="code" style="font-weight: bold;">protocol</span> attribute of this command, enter one of the following values to specify the EDIINT protocol format used by your remote partner for the acknowledgment transfer:

-   <span class="code">AS2</span>
-   <span class="code">AS3</span>

#### Using the GUI

To create a CGateGroup object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window. Complete this window to define the characteristics of your new CGateGroup.  
    Refer to [Working with CGates and CGateGroups](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui)).  
    In particular, when you create the CGateGroup, in the <span style="font-weight: bold;">Protocol</span> field, specify the protocol that is used by the connecting partner:
    -   AS2
    -   AS3

Next, create a CGate as described in the following section.

### Creating a CGate object for EDIINT transfers

To specify the login name and password requirements for AS1 or AS2 connections to your local machine, create a CGate in the CGateGroup you created in the previous section.

You can create CGate objects in Gateway either via the GUI or command line.

#### Using command line

To create a CGate object via command line, use the <span class="code" style="font-weight: bold;">[peladm create\_cgate](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli#peladm_create_cgate)</span> command.

Use the CGate object to define login requirements and directories with associated directory access rights for AS2 (HTTP) and AS3 (FTP) based transfers.

#### Using the GUI

To create a CGate object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGateGroup</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>.  
    Gateway displays the <span style="font-style: italic;">New CGate</span> window. Complete this window to define the characteristics of your new CGate.  
    Use the CGate object to define login requirements and directories with associated directory access rights for AS2 (HTTP) and AS3 (FTP) based transfers. Refer to [Working with CGates and CGateGroups](../../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui)).

<span id="Using_EDIINT"></span>

## Using EDIINT on Gateway

When you have carried out the configuration, confirmed your network connection and created the necessary objects, you can then:

-   Submit a Transfer Request to send a file to a business partner via EDIINT, optionally requesting a receipt
-   Receive EDIINT messages from remote business partners, and generate and return receipts to the sending partner

Related topics

[Overview: Trading Partners](../../../ov_gateway/ov_trading_partners)

[About EDIINT](../)

[Working with Trading Partner objects](../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))

[Transfer Examples: EDIINT AS2 transfer](../../../transfer_examples/transfer_example_ediint_as2)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
