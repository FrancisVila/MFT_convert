{
    "title": "FTP: Configuring the environment",
    "linkTitle": "Configuring the FTP environment",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About FTP configuration](#About_the_FTP_configuration)

[Creating an Application](#creating_Application)

[Creating a Site object](#Creating_a_Site_object)

[Configuring FTP security](#Configuring_FTP_security)

<span id="About_the_FTP_configuration"></span>

## About FTP configuration

Before creating a transfer, you must define specific FTP Applications and Sites if they do not already exist. At least one of the each of the following objects must be defined:

-   <span style="font-weight: bold;">Application</span>  
    A default Application object is supplied for each data code: FTP\_A, FTP\_B, FTP\_E.
-   <span style="font-weight: bold;">Local Site</span>  
    Gateway creates a default Local Site during installation, that corresponds to the alias name and protocol identifier supplied at that time. It is the default Local Site for all the protocols supplied by the product, including FTP.
-   <span style="font-weight: bold;">Remote Site</span>  
    Define your partner Site and communication attributes in the Remote Site object. You can use a default Template Site, TFTP, to create a dynamic site.

Create these objects using the GUI or the <span class="code" style="font-weight: bold;">peladm</span> online command.

<span id="creating_Application"></span>

## Creating an Application

The Application object manages transfer and file attributes such as record format and padding.

Gateway provides three default Applications for FTP transfers. You must use a specific Application for each FTP type:

-   FTP\_A: for ASCII type files
-   FTP\_B: for IMAGE type files (same as BINARY)
-   FTP\_E: for EBCDIC type files

#### Application parameters

Refer to [Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui)) for detailed information about Application parameters.

<span id="Creating_a_Site_object"></span>

## Creating a Site object

A transfer begins with the physical connection of two Sites. In Gateway, the terms Initiator and Responder are used in place of the standard FTP terms Client and Server. The Initiator Site sends the connection request to which the Responder Site responds.

During the connection phase, the Initiator sends its identification. If the Responder is an Axway MFT product, it checks the Initiator identification in the Remote Site attributes.

The FTP protocol allows data transfer in both directions: the Site sending the data is the Sender, the other is the Receiver. A given Site can have the following roles:

-   Initiator/Sender
-   Initiator/Receiver
-   Responder/Sender
-   Responder/Receiver

The table below summarizes the possible roles for the Remote Site.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Action you want to perform:</p>         </th>
<th class="HeadE-Column1-Header1"><p>The Remote Site represents:</p>         </th>
<th class="HeadD-Column1-Header1"><p>Then it is defined as:</p>         </th>
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

The parameters representing the mode and action of the Remote Site (<span class="code">-init\_sender</span>, <span class="code">-init\_receiver</span>, <span class="code">-resp\_sender</span>, <span class="code">-resp\_receiver</span>) are all set to Yes (Y) by default when you use command lines.

For each Axway MFT product, you can define as many Local and Remote Sites as needed, each referenced by a unique protocol identifier. The Local Site is defined by the <span style="font-weight: bold;">Partner local alias</span> (<span class="code">-partner\_loc\_alias</span>) attribute in the Remote Site object, or by the default Local Site name (defined during the installation).

You can use the same Site for simultaneous file transfers in both directions.

### Defining Remote Site parameters

Use the Remote Site to:

-   Provide the network address and SAP (port) of the partner
-   Select the method to use for the identification phase, and information required for this method (for example, user name and password)
-   Obtain the Application selection method if it is not defined in the Transfer Request

#### Remote Site parameters

Refer to [Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list) for details of the parameters to set when creating a Remote Site.

#### Defaults

If you do not define a parameter, Gateway uses default values from the operator interface or from the internal default attributes.

If you do not specify a group when creating a Remote Site, Gateway assigns the group <span style="font-weight: bold;">GDDEFAULT</span> to the Site by default. The group name of the Remote Site and Application must be the same.

#### Example


    peladm create_site  –alias ftppartner  –protocol FTP
       -comments "FTP Remote Site"  -ct TCPIP
       -dest_address hostname/21  -1_id username  -1_pswd password

#### Anonymous Site

In the server database, you can define a Remote Site object without a password, named <span style="font-weight: bold;">ANONYMOUS</span>. This object accepts the connection from any incoming host, regardless of the password provided. The server implementation of FTP asks the Remote Site for a password and traces it in the log file before allowing the connection.

<span id="Configuring_FTP_security"></span>

## Configuring FTP security

### Using FTP with SSL/TLS

You can configure Gateway to handle incoming connections in either <span style="font-style: italic;">implicit</span> or <span style="font-style: italic;">explicit</span> mode. You can also implement FTP security in a Gateway client in either of these modes. By default, Gateway uses TLS in implicit mode.

#### Implicit mode:

-   Connection occurs on a secure port
-   Control session opens directly in SSL or TLS

#### Explicit mode:

-   Connection occurs on an unencrypted port
-   Decision to launch the SSL/TLS layer is negotiated once the session is established

Set the following three parameters in the TLS Profile (<span style="font-weight: bold;">sprof</span>) to define the connection mode:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>TLS Profile parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Connection securing mode</p>
<p><span class="code">-ft_sec_option</span></p>         </td>
         <td><p>Defines whether to implement security implicitly or explicitly. The possible values are:</p>
<ul>
<li>implicit (default)</li>
<li>explicit</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Global session policy</p>
<p><span class="code">-ft_session_policy</span></p>         </td>
         <td><p>Determines whether or not the control session must be secured but are only available in explicit mode. Prohibiting security is equivalent to deactivating it. The possible values are:</p>
<ul>
<li>mandatory</li>
<li>optional (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FTP data session policy</p>
<p><span class="code">-ft_data_policy</span></p>         </td>
         <td><p>Defines whether the data sessions must be secured. The possible values are:</p>
<ul>
<li>mandatory</li>
<li>optional (default)</li>
<li>disabled</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Notes:</span> The distinction between SSL and TLS is made during negotiation of the protocol version.

The cipher suites that you specify in the TLS Profile define the level of security.

Related topics

[About FTP](../)

[Working with Local Sites](../../../managing_partners_start_here/sites_start_here/managing_local_sites)

[Working with Local Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Site objects: Parameters List](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list)

[Working with Applications](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_(gui))

[Working with Applications (command line)](../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli)

[Executing a basic FTP transfer](../../../transfer_examples/transfer_example_ftp)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
