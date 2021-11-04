{
    "title": "About configuring protocols ",
    "linkTitle": "Configuring protocols",
    "weight": "120"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

<span id="Supported_protocols"></span>

## Supported protocols and network interfaces

Gateway supports the following file transfer protocols and associated network interfaces:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>File transfer protocol</p>         </th>
<th class="HeadD-Column1-Header1"><p>Network interface</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>PEL         </td>
         <td>TCP/IP, SNA, PAD         </td>
      </tr>
      <tr>
         <td>PeSIT HS (D and E)         </td>
         <td>TCP/IP, SNA         </td>
      </tr>
      <tr>
         <td>OFTP (Odette)         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>FTP         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>SMTP         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>POP3         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>SFTP         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>AS1         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>AS3         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>RosettaNet         </td>
         <td>TCP/IP         </td>
      </tr>
      <tr>
         <td>X.400 (X.420)         </td>
         <td>TCP/IP         </td>
      </tr>
   </tbody>
</table>

### Network interfaces

A file transfer protocol stack needs at least one network transport interface. You can, however, associate a file transfer protocol with more than one network interface.

If you are using a UNIX platform, refer to [Network configuration for UNIX platforms](config_network_config_unix).

To configure Gateway to communicate using a specific protocol and network interface, refer to [Configuring protocols](config_protocols).

Related topics

[Configuring protocols](config_protocols): The <span style="font-weight: bold;">Internet protocols</span> and <span style="font-weight: bold;">Legacy protocols</span> parameters of the configuration menu.

[Configuring protocols: TCP/IP parameters](config_tcp_ip_paras): How to specify the TCP port when completing the <span style="font-weight: bold;">Port specification using former syntax</span> field.

[Configuring protocols: SAP parameters](config_sap_parameters)

[Configuring protocols: FTP options](config_ftp_options)

[Configuring protocols: HTTP options](config_http_options)

[Configuring protocols: TCP advanced options](config_tcp_adv_options)

[Configuring protocols: SNA LU 6.2](config_sna_lu_6_2): How to use the SNA LU 6.2 network interface.

[Configuring protocols: Using RAS](config_ras): How to use Microsoft RAS (Remote Access Service Networking) <span style="font-style: italic;">Windows platforms only</span>.

[Configuring protocols: Network configuration for UNIX platforms](config_network_config_unix): Introduction to configuring protocols on UNIX platforms for different network interfaces.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
