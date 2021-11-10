{
    "title": "HTTP: Configuring the environment",
    "linkTitle": "Configuring HTTP",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About HTTP configuration](#About_HTTP_configuration)

[HTTP configuration](#Configuration)

[Configuring HTTP security](#Configuring_HTTP_security)

<span id="About_HTTP_configuration"></span>

## About HTTP configuration

Before creating a transfer, you must configure a specific HTTP Application and Sites if they do not exist. In both client and server mode, you must define at least one each of the following Gateway objects:

-   <span style="font-weight: bold;">Local Site</span>  
    During installation, Gateway creates a default Local Site corresponding to the alias name and protocol identifier you supplied at that time. It is the default Local Site for all the protocols supplied by the product, including HTTP.
-   <span style="font-weight: bold;">Remote Site</span>  
    Define your partner Site and communication attributes in the Remote Site object.
-   <span style="font-weight: bold;">Application</span>  
    A default Application object is delivered for each data code.

You can create these objects either via the GUI or the <span class="code" style="font-weight: bold;">peladm</span> online command.

<span id="Configuration"></span>

## HTTP configuration

### Creating a Site object

A transfer begins with the physical connection of two Sites. In Gateway the terms *Initiator* and *Responder* are used in place of the standard HTTP terms *Client* and *Server*.

The Responder Site responds to the connection request from the Initiator Site. During the connection phase:

-   The Initiator sends its identification
-   If the Responder is an Axway MFT product, it checks the Initiator identification in the Remote Site attributes

The HTTP protocol allows data transfer in both directions: the Site sending the data is the Sender, the other is the Receiver. A given Site can have the following roles:

-   Initiator/Sender
-   Initiator/Receiver
-   Responder/Sender
-   Responder/Receiver

Gateway references a Site by its protocol identifier. For each Axway MFT product, you can define as many Local and Remote Sites as needed. The Local Site is defined by the <span style="font-weight: bold;">Partner local alias</span> (<span class="code" style="font-weight: bold;">-partner\_loc\_alias</span>) attribute in the Remote Site object, or by the default Local Site name (defined during the installation).

It is possible to use the same Site for simultaneous file transfers in both directions.

### Defining Remote Site parameters

Use the Remote Site to:

-   Provide the network address and SAP of the partner
-   Select the method to use for the identification phase, and information relevant to this method (user name and password for the login method)
-   Define the Application selection method if it is not defined in the Transfer Request

If you do not define a parameter, Gateway uses default values from the operator interface or from the internal default attributes.

The following table summarizes the possible roles the Remote Site should have to perform specific actions.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Action         </th>
<th class="HeadE-Column1-Header1">If RS represents:         </th>
<th class="HeadD-Column1-Header1">Then it must be defined as:         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Send a file from your Local Site</p>         </td>
         <td><p>Destination</p>         </td>
         <td><p>Receiver</p>         </td>
      </tr>
      <tr>
         <td><p>Receive a file</p>         </td>
         <td><p>Partner</p>         </td>
         <td><p>Sender</p>         </td>
      </tr>
   </tbody>
</table>

The parameters representing the mode and action of the Remote Site (**init\_sender**, **init\_receiver**, **resp\_sender**, **resp\_receiver**) are all set to *Yes* (*Y*) by default.

If you do not specify a group when creating a Remote Site, **GDDEFAULT** is the group name associated with the Site by default. The group name of the Remote Site and Application must be the same.

<span id="Creating_an_Application"></span>

### Creating an Application

The Application object manages transfer and file attributes such as record format and padding.

HTTP uses the default FTP Application, *FTP\_B*, which should not be modified.

<span id="Configuring_HTTP_security"></span>

## Configuring HTTP security

TLS and SSL protocols are fully supported by both HTTP client and server and their use is completely transparent for the HTTP protocol. To implement security, you must:

-   Select the option TLS/SSL in the configuration of the protocol.
-   Create security objects:
    -   Network Profile (netprof) for the client
    -   TLS Security Profile (sprof)
    -   Certificate

The use of TLS or SSL with Web browsers consists in replacing *http://server.com* with *https://server.com* in the browser navigation bar.

Related topics

[About Site objects](../../../managing_partners_start_here/sites_start_here)

[Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list)

[About Applications](../../../transfers_start_here/parameters_start_here/applications_start_here)

[Using HTTP in client mode](http_using_in_client_mode.htm)

[Using HTTP in server mode](http_using_in_server_mode.htm)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
