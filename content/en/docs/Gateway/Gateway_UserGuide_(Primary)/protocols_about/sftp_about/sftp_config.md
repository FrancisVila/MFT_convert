{
    "title": "Configuring SFTP",
    "linkTitle": "Configuring SFTP",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About SFTP configuration](#About_SFTP_configuration)

[Defining a Remote Site (-remote\_agent)](#Defining_Remote_Site)

[Creating a Transfer Request](#Creating_a_Transfer_Request)

<span id="About_SFTP_configuration"></span>

## About SFTP configuration

To send and receive transfers via SFTP and perform processing on these transfers, you must configure the following elements in Gateway:

-   Remote Site
-   Network Profile
-   SSH Profile
-   Transfer Request

You can use the following default objects supplied in Gateway.

-   Local Site
-   Application

Configuration of the SFTP Remote Site and Transfer Request are described in this section. For more information on creating a Network profile and an SSH profile, see the [Security guide](#).

<span id="Defining_Remote_Site"></span>

## Defining a Remote Site (-remote\_agent)

The Remote Site represents an SFTP client or server. You must define at least one Remote Site for each remote SFTP partner.

The SFTP Remote Site can have the following roles:

-   Responder/Receiver
-   Responder/Sender
-   Initiator/Receiver
-   Initiator/Sender

The following table summarizes the elements you define for Remote Responder and Remote Initiator Sites.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>         </th>
<th class="HeadE-Column1-Header1"><p>Remote Responder Site</p>         </th>
<th class="HeadD-Column1-Header1"><p>Remote Initiator Site</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local SSH profile</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>User name and password</p>         </td>
         <td><p>YES</p>
<p>Send, if requested by the Remote Server</p>         </td>
         <td><p>YES</p>
<p>Check, if requested by the Remote Client</p>         </td>
      </tr>
      <tr>
         <td><p>Local private key alias, your certificate alias, or both, to authenticate your Gateway to the Server</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Key or certificate parameters</p>         </td>
         <td><p>YES</p>
<p>Use to authenticate the server</p>         </td>
         <td><p>YES</p>
<p>Use to authenticate the client</p>         </td>
      </tr>
      <tr>
         <td><p>Default location of files to be sent or received</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
   </tbody>
</table>

Refer to [Remote Site: SFTP tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_sftp_tab) for information on the specific SFTP parameters to use.

<span id="Creating_a_Transfer_Request"></span>

## Creating a Transfer Request

To send or receive a file you must also create a Transfer Request, either via the GUI or using the <span class="code">peltrans</span> command. The syntax is:

**peltrans** &lt;argument> value &lt;argument> value &lt;argument> value

Command arguments are parameters, each of which is followed by the corresponding value. Parameters are prefixed by the "<span class="code">-</span>" character, and most have abbreviated names.

The <span class="code">peltrans</span> parameters specifically relevant to SFTP are given in the following table.

### SFTP relevant Transfer Request parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use this parameter to:</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-type (-ty)</p>         </td>
         <td><p>TRANS</p>
<p>DIR</p>         </td>
         <td><p>Request and format a list of available transfers</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_type (-dt)</p>         </td>
         <td><p>LONG</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-dir_name (-dn)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Define the location of a remote file</p>         </td>
      </tr>
      <tr>
         <td><p>-ftp_command (-ftpc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Send commands to remote server using <span class="code">QUOTE</span> or <span class="code">SITE</span> command</p>         </td>
      </tr>
      <tr>
         <td><p>-newline_convention</p>         </td>
         <td><p>(no default)</p>         </td>
         <td><p>Set the end-of-line code, depending on the remote system type. This parameter is valid for text file transfers in both send and receive mode. Although this parameter is also available in the Remote Site definition, the Transfer Request parameter takes priority.</p>
<p>Enter one of the following values:</p>
<ul>
<li><strong>U</strong> for UNIX</li>
<li><strong>W</strong> for Windows</li>
<li>Blank for Undefined</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Executing an SFTP transfer](../../../transfer_examples/transfer_example_sftp)

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
