{
    "title": "Messages and codes   ",
    "linkTitle": "Messages and codes",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

Gateway generates log messages that provide information about the processes and events that occur on the Gateway.

<span id="Log_message_structure"></span>

## Structure of log messages

Each message is made up of three parts, each part displayed in a separate column:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Column</p>         </th>
<th class="HeadD-Column1-Header1"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Time stamp (when the message was printed)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message identification</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Message text</p>         </td>
      </tr>
   </tbody>
</table>

The message identification items are displayed in two formats, depending on the user interface used. However, the message text does not change.

### Message identification (column 2)

Messages are identified in a character string that comprises the following elements:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>         </th>
<th class="HeadD-Column1-Header1"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Message number</p>         </td>
         <td><p>Expressed using three bytes</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway module (or process)</p>         </td>
         <td><p>The name of the Gateway module or process at the source of this message. This name is abbreviated to one of:</p>
<ul>
<li>FPSIT (PeSIT protocol)</li>
<li>FTP (FTP protocol)</li>
<li>HTTP (HTTP protocol)</li>
<li>SMTP (SMTP protocol)</li>
<li>POP3 (POP3 protocol)</li>
<li>SFTP (SFTP protocol)</li>
<li>ODT (OFTP protocol)</li>
<li>PEL (PEL protocol)</li>
<li>JCT (Job Control Table)</li>
<li>NET (Network module)</li>
<li>SNAC (SNA LU 6.2 module)</li>
<li>SUP (Supervisor module)</li>
<li>PCNX (Protocol connection - customization through the <span class="code">cgate_log_level</span> configuration variable)</li>
<li>TSD (TCP Server Daemon)</li>
<li>VFD (Virtual file and directory access)</li>
<li>SECS (Security errors)</li>
<li>EXT (Exit)</li>
<li>USR (User)</li>
<li>CHK (Monitor checking)</li>
<li>NOT (Notif)</li>
<li>SR (Statistics and script resolution modules)</li>
<li>INT (Payload or Data integrity)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Message Severity</p>         </td>
         <td><ul>
<li>S = Success</li>
<li>I = Information</li>
<li>W = Warning</li>
<li>E = Error</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Event Name</p>         </td>
         <td><p>A character string that abbreviates the name of the associated event. There is a one-to-one correspondence between message names and code numbers.</p>         </td>
      </tr>
   </tbody>
</table>

In the GUI, the Gateway module name, the code number and the type of message are concatenated. The message name is not displayed.

#### Example:

Depending on the interface, PEL information message number 131, named CONN\_REQ, is displayed in one of the following formats:

-   &lt;time stamp> 131 PEL I CONN\_REQ &lt;text>
-   &lt;time stamp> PEL131I &lt;text>

### Message text (column 3)

The text of the message comprises a generic component. In turn, this component contains a (variable) number of context-dependent parameters.

### Examples of message text

<table>
         
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Code</p>         </th>
<th class="HeadE-Column1-Header1"><p>Module</p>         </th>
<th class="HeadE-Column1-Header1"><p>Type</p>         </th>
<th class="HeadE-Column1-Header1"><p>Message name</p>         </th>
<th class="HeadD-Column1-Header1"><p>Message text</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>048</p>         </td>
         <td><p>SUP</p>         </td>
         <td><p>I</p>         </td>
         <td><p>KEY</p>         </td>
         <td><p>key=%1, site=%2</p>         </td>
      </tr>
      <tr>
         <td><p>101</p>         </td>
         <td><p>NET</p>         </td>
         <td><p>I</p>         </td>
         <td><p>CONN_REQ</p>         </td>
         <td><p>(%1) outgoing connection request [dest_address="%2"]</p>         </td>
      </tr>
      <tr>
         <td><p>045</p>         </td>
         <td><p>PEL</p>         </td>
         <td><p>E</p>         </td>
         <td><p>ABORT_IND</p>         </td>
         <td><p>%1(%2) [%3] transfer aborted. reason=%4</p>         </td>
      </tr>
   </tbody>
</table>

Each instance of a message replaces the context-dependent variables by their values before writing the message in the log file. In the example messages shown in the table above, variables are designated by the percentage symbol (%), followed by a digit that represents the rank of the parameter in the message.

Related topics

[Log files](../transfers_start_here/monitoring_transfers_start_here/log_files)

[Access Management (AM)](access_management_(am))

[EDI Errors](edi_errors)

[Exits (EXT)](exits_(ext))

[File Transfer Protocol (FTP)](file_transfer_protocol_(ftp))

[FTP Reply Codes](ftp_reply_codes)

[Hypertext Transfer Protocol (HTTP)](hypertext_transfer_protocol_(http))

[JMS](jms_messages)

[Job Control Table (JCT)](job_control_table_(jct))

[LU 6.2 SNA Network (SNAC)](lu6.2_sna_network_(snac))

[Axway Messaging connector routing (XMSC)](xms_routing)

[MGET and MPUT messages (MXF)](mget_and_mput_messages_(mxf))

[Monitor Checking (CHK)](monitor_checking_(chk))

[Network Module (NET and NDSP)](network_module_(net_and_ndsp))

[OFTP (Odette) protocol (ODT)](odette_protocol_(odt))

[PEL protocol (PEL)](pel_protocol_(pel))

[PeSIT HS protocol (FPSIT)](pesit_hs_protocol_(fpsit))

[POP3](pop3)

[Process Monitoring (GC)](process_monitoring_(gc))

[Protocol Connection (PCNX)](protocol_connection_(pcnx))

[Reason Codes and Messages](reason_codes_and_messages)

[Routing (NOTIF)](routing_(notif))

[Routing Axway Messaging (RXMS)](routing_xms_messages_(rxms))

[Rule table evaluation](rule_table_evaluation)

[SECS messages](secs_messages)

[Simple Mail Transfer Protocol (SMTP)](simple_mail_transfer_protocol_(smtp))

[SSH File Transfer Protocol (SFTP)](ssh_file_transfer_protocol_(sftp))

[Statistics and Script Resolution Modules (SR STATS)](statistics_and_script_resolution_modules_(sr_stats))

[Supervisor Module (SUP)](supervisor_module_(sup))

[SWIFTNet (SNET)](swiftnet_messages_(snet))

[TCP Server Daemon (TSD)](tcp_server_daemon_(tsd))

[Time Driver (TDRV)](time_driver_(tdrv))

[Trade messages (TRADE)](trade_messages)

[Trading Partner Management (TPM)](trading_partner_management_(tpm))

[User Request (USR)](user_request_(usr))

[VFD Errors](vfd_errors)

[X.400 (X420)](x400_messages)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
