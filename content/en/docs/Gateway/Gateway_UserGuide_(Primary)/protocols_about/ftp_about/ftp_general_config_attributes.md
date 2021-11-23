{
    "title": "General FTP command attributes",
    "linkTitle": "General FTP command attributes",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Protocols

## General FTP commands

This topic introduces the attributes for general FTP commands. This command information applies to submitting a Transfer Request in either client or server mode.

### Using FTP commands to define session attributes

To transfer a file, you must define the session attributes. The three standard commands for setting FTP session attributes are:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FTP Command         </th>
<th class="HeadE-Column1-Header1">Options         </th>
<th class="HeadD-Column1-Header1">Comments         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TYPE</p>
<p>Use this command to define the transfer mode (data conversion mode for transmission)</p>         </td>
         <td><p><strong>S</strong>(tream) (<em>default</em>)</p>         </td>
         <td><p>Gateway establishes a new data connection for each transfer</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">B</span>(lock)</p>         </td>
         <td><p>In both of these modes, Gateway keeps the data connection open, depending on the FTP response code that the Responder sends at the end of each transfer</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">C</span>(ompressed)</p>         </td>
      </tr>
      <tr>
         <td><p>MODE</p>
<p>Use this command to define data code</p>         </td>
         <td><p><span style="font-weight: bold;">A</span>(SCII)</p>         </td>
         <td><p>In virtual directories you can access ASCII Transfer Requests using the existing <em>FTP_A</em> and <em>FTP_E</em> Applications for local text files in ASCII</p>         </td>
      </tr>
      <tr>
         <td><p><strong>E</strong>(BCDIC)</p>         </td>
         <td><p>In virtual directories you can access EBCDIC Transfer Requests</p>
<p>Gateway automatically converts EBCDIC (network) to ASCII (local)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>I</strong>(MAGE)</p>         </td>
         <td><p>In virtual directories you can access binary, ASCII, and EBCDIC Transfer Requests using the existing <em>FTP_B</em> for IMAGE type files</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">STRU</span> = file structure</p>
<p>Use this command to define data representation</p>         </td>
         <td><p><span style="font-weight: bold;">F</span>(ile) (default)</p>         </td>
         <td><p>File is a continuous sequence of data bytes</p>         </td>
      </tr>
      <tr>
         <td><p><strong>R</strong>(ecord structure</p>         </td>
         <td><p>File consists of sequential records</p>         </td>
      </tr>
   </tbody>
</table>

**Note:** PAGE structure representation is not available in Gateway.

#### Summary of session attributes

The way that data is encoded depends on how you combine commands, as shown in the following table. FTP commands that define session attributes include the following:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FTP command         </th>
<th class="HeadE-Column1-Header1">Gateway command parameters         </th>
<th class="HeadD-Column1-Header1">Define this parameter in         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MODE</p>         </td>
         <td><p><strong>-data_code (-dc)</strong></p>         </td>
         <td><p>Application (<em>Data code</em>)</p>
<p>Transfer Request (<em>Data code</em>)</p>         </td>
      </tr>
      <tr>
         <td><p>TYPE</p>         </td>
         <td><p><strong>-trans_mode (-trm)</strong></p>         </td>
         <td><p>Remote Site (<em>Transfer mode</em>)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>-rec_fmt (-rf)</strong></p>
<p>Values are:</p>
<ul>
<li>F (Fixed)</li>
<li>FT (Fixed Text)</li>
<li>V (Variable)</li>
<li>VT (Variable Text)</li>
<li>S (Stream)</li>
</ul>         </td>
         <td><p>Transfer Request <em>(Record format)</em></p>         </td>
      </tr>
      <tr>
         <td><p>STRU</p>         </td>
         <td><p><strong>-ftp_data_struct</strong></p>         </td>
         <td><p>Remote Site (<em>Data structure</em>)</p>         </td>
      </tr>
   </tbody>
</table>

### Using the SYST command

To identify a Gateway server, an FTP client can send the <span class="code">**SYST**</span> command, and recognizes a Gateway server by its response to this command.

A Gateway server responds to a <span class="code">**SYST**</span> command by:

"215 &lt;UNIX XFB/&lt;Operating\_System\_type>"

For example:

"UNIX XFB/UNIX" or "UNIX XFB/NT"

Many applications or Web browsers work better when the FTP server is a UNIX system. Therefore, the UNIX system has been chosen as representative of all implementations of the FTP protocol, irrespective of the actual operating system.

The first UNIX label specifies the format to use with the <span class="code">**LIST**</span> command. The last one gives the real operating system type.

**Note:** When a Gateway FTP client receives an Axway MFT system type in response to a <span class="code">**SYST**</span> command, it sends specific information using a <span class="code" style="font-weight: bold;">SITE</span> command before transferring a file.

### Using the SITE command

To send specific commands to a Gateway FTP server, you can use the <span class="code" style="font-weight: bold;">SITE</span> command.

The syntax of the <span class="code" style="font-weight: bold;">SITE</span> command is:

SITE &lt;sp> &lt;Command\_1> &lt;sp> &lt;Param\_1>\[;...;&lt;Command\_n> &lt;sp> &lt;Param\_n>\]

The following table lists available <span class="code">SITE</span> commands:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span class="code">SITE</span> command         </th>
<th class="HeadD-Column1-Header1">Function         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>P_CLIENT</p>         </td>
         <td><p>Client Type</p>         </td>
      </tr>
      <tr>
         <td><p>P_ORG</p>         </td>
         <td><p>Originator Site name</p>         </td>
      </tr>
      <tr>
         <td><p>P_DEST</p>         </td>
         <td><p>Destination Site name (can be used for routing a transfer)</p>         </td>
      </tr>
      <tr>
         <td><p>P_RECFMT</p>         </td>
         <td><p>Format or record (F (Fixed) or V (Variable))</p>         </td>
      </tr>
      <tr>
         <td><p>P_LRECL</p>         </td>
         <td><p>Logical record length in bytes</p>         </td>
      </tr>
      <tr>
         <td><p>P_APPLI</p>         </td>
         <td><p>Name of Application to use</p>         </td>
      </tr>
      <tr>
         <td><p>P_MSG</p>         </td>
         <td><p>User message</p>         </td>
      </tr>
      <tr>
         <td><p>FTPCS</p>         </td>
         <td><p>FTPCS client version number. Prompts the Axway MFT FTP server to return the whole list of authorized commands/ parameters.</p>         </td>
      </tr>
   </tbody>
</table>

If one of these special commands was already sent in the Transfer Request, only the other commands are sent to the server.

The FTP client can use a <span class="code">**SITE P\_APPLI**</span> command to use a specific Application on the server Site. An Application that you specify via the <span class="code">**SITE P\_APPLI**</span> command takes priority over one defined in the Remote Site or Transfer Request.

<span style="font-weight: bold;">Note:</span> Remote Applications must have the same <span class="code">xfer\_data\_code</span> (transmission mode) value as in the current FTP session attribute (ASCII, EBCDIC, IMAGE).

### Pre- and post-transfer end response timers

In STREAM mode, the Gateway FTP server can never guarantee that an incoming transfer is finished gracefully. The only way it can detect an error during such a transfer, and so avoid routing the file if it is required, is to receive an <span class="code" style="font-weight: bold;">ABORT</span> command.

However, the reception of an <span class="code" style="font-weight: bold;">ABORT</span> command can occur before or after the transfer is finished (for example, in STREAM mode, the data session is closed). To detect as many error conditions as possible, the following response timers are available in Responder/Receiver mode for STREAM mode / FILE structure sessions:

-   <span class="code" style="font-weight: bold;">pre\_resp\_timer:</span> indicates the waiting period allowed between detecting the data closure and sending the transfer end response (226 Requested file action successful) to the client.
-   <span class="code" style="font-weight: bold;">post\_resp\_timer:</span> indicates the waiting period allowed between sending the transfer end response and validating the transfer.

You can designate the waiting period for these two timers in the configuration file, with the <span class="code">pre\_resp\_timer</span> and <span class="code">post\_resp\_timer</span> fields of the FT\_FTP entity. Any timer set to 0 is ignored, that is, it is not started, and the process goes directly to the next step.

If the Gateway Responder receives an <span class="code" style="font-weight: bold;">ABORT</span> command or a control session closure during one of these allowed waiting periods, it aborts the transfer. If it receives any command other than <span class="code" style="font-weight: bold;">ABORT</span>, it stops both timers and validates the transfer.

#### FTP transfer scenarios

Since Gateway *must* be able to detect that a transfer is invalid to avoid routing it, clients that do not send <span class="code" style="font-weight: bold;">ABORT</span> commands should not use Gateway to route transfers. Many FTP clients never send <span class="code" style="font-weight: bold;">ABORT</span> commands, even if the user explicitly requests a transfer abort. However, when a client sends a file to Gateway in STREAM mode and FILE structure, there is no way for the server to detect that the partner aborted the transfer.

### FTP commands for directory management

To manage files on a Gateway FTP server, you can use the following standard FTP commands:

-   <span class="code">MKD</span> (make directory)
-   <span class="code">RMD</span> (remove directory) you can only delete empty directories
-   <span class="code">DELE</span> (delete file)
-   <span class="code">RNFR</span> and <span class="code">RNTO</span> (rename file)

You must have specific rights to use these commands. In addition, these commands only apply to Real File Directories (RFD).

Related topics

[Using FTP in Initiator mode](../ftp_initiator_mode)

[Using FTP in Responder mode](../ftp_responder_mode)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
