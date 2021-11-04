{
    "title": "New Remote Site: General tab",
    "linkTitle": "General tab",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Alias</p>         </td>
         <td><p>Enter the Remote Site alias.<br />
Maximum: 31 alphanumeric characters.</p>
<p><span style="font-weight: bold;">Note:</span> When creating PassPort (TPM) Template Sites, the alias is limited to 23 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Select one of the following protocols:</p>
PeSIT D
PeSIT E
<strong>OFTP</strong> – then select the protocol version:
<ul>
<li><strong>R1.2</strong></li>
<li><strong>R1.3</strong></li>
<li><strong>R1.4</strong></li>
<li><strong>R2.0</strong></li>
</ul>
FTP
HTTP
FTP/HTTP
POP3
SMTP
SFTP
<span style="font-weight: bold;">PEL</span> – then select the protocol version:
<ul>
<li><strong>No</strong> = no value</li>
<li><strong>HV</strong> = High Value</li>
<li><strong>TR</strong> = Trailer</li>
<li><strong>HV/TR</strong> = High Value and Trailer</li>
<li><strong>CRC</strong> = Cyclic Redundancy Code</li>
</ul>
AS1_POP3
AS1_SMTP
AS2
AS3
RosettaNet_HTTP
RosettaNet_SMTP
RosettaNet_POP3
SWIFTNet
JMS
X.400
<p>When you select a protocol, the set of available tabs changes dynamically.</p>
<p><strong>Note:</strong> If you are using SWIFTNet, refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring#Creating_remote_site_object_for_SWIFTNet">Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol identifier</p>         </td>
         <td><p>Not for all protocols</p>
<p>Enter the Remote Site protocol name.<br />
Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Group name</p>         </td>
         <td><p>Enter a group name for this Site. Note that the Site must belong to the same group as the Application used for a given Transfer. Default = GDEFAULT.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer owner</p>         </td>
         <td><p>Enter the Transfer owner name to assign to Transfer Requests created by Gateway. For example, when Gateway receives an incoming Transfer that must be routed, it automatically creates an outgoing Transfer Request.</p>
<p>The user that you specify has all the usual Transfer access rights.</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Partner local alias</p>         </td>
         <td><p>Enter the Local Site alias to use during the connection phase.<br />
Maximum: 31 alphanumeric characters.</p>
<p>If you do not enter a value in this field, Gateway uses the default Local Site specified in the configuration menu.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description for the object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory for received files</p>         </td>
         <td><p>Enter the name of the directory where the received files are stored.<br />
Maximum: 127 alphanumeric characters.</p>
<p>If you also specify a received file directory in the Application object, the Application definition takes precedence.</p>         </td>
      </tr>
      <tr>
         <td><p>Role</p>         </td>
         <td><p>Select one or more of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Initiator/Sender</span></li>
<li><span style="font-weight: bold;">Initiator/Receiver</span></li>
<li><span style="font-weight: bold;">Responder/Sender</span> (mandatory for POP3 protocol)</li>
<li><span style="font-weight: bold;">Responder/Receiver</span> (mandatory for SMTP protocol)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Initialization mode</p>         </td>
         <td><p>Initialization attributes for the Site. On startup, the Site functions in the modes that you specify here.</p>
<p>Select one or more of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Initiating Site</span></li>
<li><span style="font-weight: bold;">Responding Site</span> (mandatory for POP3 and SMTP)</li>
<li><span style="font-weight: bold;">Trace</span></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About Site objects](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
