{
    "title": "Managing transfers",
    "linkTitle": "Managing transfers",
    "weight": "90"
}{{< Gateway/componentlongname  >}}: Managing Transfers

<span id="About"></span>

## About transfers and transfer requests

Gateway processes file Transfers. A *file Transfer* is a set of processes that results in the exchange of files between two computers. In a transfer, one computer is the sender, the other is the receiver. The sender and receiver are linked together by a network. A file Transfer consists of sending:

-   The file
-   All related technical parameters associated with the file. For example: connected partners, local file storage format, and so on.

### Transfer types

Gateway enables you to submit three types of Transfer:

-   [Transfer Requests](submitting_transfer_requests_start_here/working_with_transfers_(gui)) – transfers a file between two computers
-   [acknowledgment Message Requests](submitting_transfer_requests_start_here/working_with_ack_messages) – returns an acknowledgment for a transfer
-   [Application Message Requests](submitting_transfer_requests_start_here/working_with_appli_messages) – enables you to send a limited-length text message via the PeSIT protocol

### Transfer objects

Gateway provides a set of objects that enable you to create and define the characteristics of a Transfer. To create a Transfer you choose the objects useful for your Transfer and enter the object property values that define the processing that you require.

To execute a Transfer, you need:

-   A *Transfer Request*
-   A pair of *Site* objects

You may require additional objects to define additional transfer characteristics, depending on the nature of the Transfer and the context in which you want to execute it. For example, to handle any incoming connection request, you also need a *CGate* definition.

The following table lists the Gateway objects you can use to manage Transfers and summarizes the way you can use them.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Object</p>         </th>
<th class="HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="HeadD-Column1-Header1"><p>Refer to</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="Application"></span>Application</p>         </td>
         <td><p>To process files during transfer, Gateway requires information about the file characteristics.</p>
<p><strong>Application</strong> objects define:</p>
<ul>
<li>Local file attributes, such as record format and length, local directory for received files and so on</li>
<li>Transferred file attributes, such as data code, record length, compression and so on</li>
</ul>
<p>You can enter values for certain Application object parameters directly in the Transfer Request.</p>
<p>If you set the same parameters values in both the Transfer Request and the Application object, the Transfer Request parameter values override the Application parameter values.</p>         </td>
         <td><p><a href="parameters_start_here/applications_start_here">About Applications</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="ConnectionGate"></span>Connection Gate/ Connection Gate Group</p>         </td>
         <td><p>Before Gateway can accept protocol connections from external entities, the access permissions and connection characteristics must be defined for the entity.</p>
<p>The <span style="font-weight: bold;">Connection Gate</span> object enables you to attribute permission to connect to Gateway and exchange files with it. It also controls the connecting-client access to files stored in the <a href="virtual_file_directory_start_here">Virtual File Directory</a>.</p>         </td>
         <td><p><a href="../managing_partners_start_here/cgates_start_here">About CGates and CGateGroups</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="Decision_Rule"></span>Decision Rule</p>         </td>
         <td><p>You can optionally configure Gateway to process the files it handles according to pre-set criteria.</p>
<p><span style="font-weight: bold;">Decision Rules</span> objects determine the processing for the current transfer based on a set of conditions that Gateway applies to the transfer. If all conditions specified in the Decision Rule match the parameters defined in the transfer, Gateway applies the specified execution type (for example, execute Perl script, redirect to Axway Integrator, and so on).</p>         </td>
         <td><p><a href="../managing_events_start_here">Managing Events on Gateway</a></p>         </td>
      </tr>
      <tr>
         <td><p>Diffusion List</p>         </td>
         <td><p><span style="font-weight: bold;">Diffusion List</span> objects enable you to transmit a Transfer Request to multiple destination Sites.</p>
<p>You apply a Diffusion List object by first creating the Diffusion List object, and then selecting the Diffusion List object as a Transfer Request parameter.</p>         </td>
         <td><p><a href="../managing_partners_start_here/diffusion_lists_start_here">About Diffusion Lists</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="Model"></span>Model</p>         </td>
         <td><p>A <span style="font-weight: bold;">Model</span> is a template of a Transfer Request that groups a set of common parameters to apply to multiple Transfer Requests. Models accelerate and simplify the process of defining Transfer Requests.</p>
<p>To use a Model, you:</p>
<ul>
<li>Create the Model object</li>
<li>Select the Model object as a Transfer Request parameter</li>
</ul>
<p>You can enter values for certain Model object parameters directly in the Transfer Request.</p>
<p>If you set the same parameters values in both the Transfer Request and the Model object, the Transfer Request parameters values override the Model parameter values.</p>         </td>
         <td><p><a href="parameters_start_here/models_start_here">About Models</a></p>         </td>
      </tr>
      <tr>
         <td><p>Security</p>         </td>
         <td><p><strong>Security</strong> objects provide added security for user access and for TLS and SSH file transfers. Security objects include:</p>
For user access security:
<ul>
<li>User definitions and Profiles</li>
</ul>
For file transfers:
<ul>
<li>Certificates and keys</li>
<li>Network Profiles</li>
<li>TLS and SSH Security Profiles</li>
</ul>         </td>
         <td><p>See <em><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm">Security guide</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Site"></span>Site</p>         </td>
         <td><p>Every file exchange involves a sending and receiving partner. <span style="font-weight: bold;">Site</span> objects represent these partners.</p>
<p>A Site object can represent a Local or Remote partner.</p>
<p>Typically the Local Site object defines characteristics of the machine that hosts the Gateway.</p>
<p>The Remote Site object defines the following parameters for the remote partner:</p>
<ul>
<li>Protocol used for exchanges with this partner</li>
<li>Role: responder or initiator, file sender or receiver</li>
<li>Connection information (max number of connections to / from this Site, and so on)</li>
<li>Network type used for connections (TCP/IP, LU 6.2)</li>
<li>Network security information</li>
<li>Protocol-specific parameters</li>
</ul>
<p>Once you have created a Site you can select the Site as a transfer partner in a Transfer Request.</p>
<p>If a Remote Site definition does not exist, when processing a Transfer Request, Gateway can create a dynamic Site.</p>         </td>
         <td><p><a href="../managing_partners_start_here/sites_start_here">About Site objects</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="Transfer_Request"></span>Transfer Request</p>         </td>
         <td><p>To create a transfer with Gateway you create a <span style="font-weight: bold;">Transfer Request</span>.</p>
<p>A Transfer Request defines the set of parameters required to submit a file transfer:</p>
<ul>
<li>Name of file to transfer</li>
<li>Physical file attributes</li>
<li>Compression or encryption options</li>
<li>Behavior in case of transfer failure</li>
<li>Transfer scheduling, restarting and routing</li>
</ul>
<p>A Transfer Request can collect and reuse the parameters that you may have defined in other Gateway objects, such as the <em>Model</em>, the <em>Remote Site</em> and the <em>Application</em>.</p>
<p>If you set values for the same parameters in both the Transfer Request and other objects, the Transfer Request parameter values override the other object parameter values.</p>         </td>
         <td><p><a href="submitting_transfer_requests_start_here">Submitting Transfers</a></p>         </td>
      </tr>
   </tbody>
</table>

#### Groups

Most Gateway objects have a field called "group", that can be used as a namespace. Groups apply in a number of use cases:

-   Mandatory: an application object used for an inbound transfer must be in the same group as its origin site object
-   Mandatory: an application object used for an outbound transfer must be in the same group as its destination site object
-   It is possible to give the same name to different applications, on condition they belong to different groups
-   For ssh key objects, when performing authentication, a site can be used to represent a remote peer presenting distinct keys to authenticate with Gateway's SFTP server. In this case, all partners key can be grouped and the site having the protocol identifier equal to that peer login name would point to that group via the 'remote\_public\_key\_group' attribute.

Related topics

[Overview: File Transfers and Transfer Requests](../ov_gateway/ov_file_transfers)

[Submitting Transfers](submitting_transfer_requests_start_here)

[About Virtual File Directories](virtual_file_directory_start_here)

[Parameters (Applications and Models)](parameters_start_here)

[Monitoring Transfers](monitoring_transfers_start_here)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
