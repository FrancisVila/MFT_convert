{
    "title": "Using FTP in Responder mode ",
    "linkTitle": "Using FTP in Responder  mode",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

## FTP transfers in Responder mode

After [configuring the Remote Site and Application for FTP](../ftp_config) you can submit a Transfer Request.

There are certain parameters that Gateway only uses in Responder mode. The following parameters are set on the Responder side, or can be sent to Gateway by standard FTP clients communicating with a Gateway server.

### Using an Application

#### Responder/Receiver mode

The function used to transmit the Application name is defined in the <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) field of the Remote Site object. Three methods are available for the Responder to retrieve the Application name for an incoming transfer:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Method</p>         </th>
<th class="HeadD-Column1-Header1"><p>Element used by FTP server as Application name</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>File name (AIF)</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>User message field (AIM)</p>         </td>
         <td><p><span style="font-style: italic;">User message</span> field, that the client provides in the <span class="code">SITE P_MSG</span> command argument.</p>
<p>If this command is not provided before the transfer command (<span class="code">STOR</span> or <span class="code">STOU</span>), the Application name remains void and the transfer is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>User exit (AIE)</p>         </td>
         <td><p>The corresponding exit function.</p>
<p>If it is not provided, the FTP client can force its value by sending the <span class="code">SITE P_APPLI</span> command. If this command is not provided before the transfer command (<span class="code">STOR</span> or <span class="code">STOU</span>), the FTP server uses the default Application name for the current session type:</p>
<ul>
<li>FTP_A for an ASCII session</li>
<li>FTP_E for an EBCDIC session</li>
<li>FTP_B for a binary (image) session</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

The resulting Application name must correspond to an existing Application and must not be void. Otherwise the Transfer Request is rejected.

#### Responder/Sender mode

When you define an Application in Responder/Sender mode, the transfer characteristics must match the FTP session attributes asked for by the Remote Site. Otherwise the Receiver cannot open the file.

<span id="Transferring_files_to_and_from_virtual_directories"></span>

## Transferring files to and from virtual directories

In virtual directories, Gateway only provides a logical view of a file. Since the physical files stored on the product host machine are referenced in the corresponding Transfer Request, they cannot be accessed directly. Therefore, retrieving or sending a file depends on a successful Transfer Request to Gateway.

An FTP transfer is identified by its protocol name. For security reasons, the protocol file names managed by Gateway are logical file names which FTP clients are only able to view and browse.

### Sending a file

The Transfer Request submitted to Gateway defines the logical file name (protocol file name) and physical file name (file component).

### Receiving a file

The client defines the logical file name and Gateway automatically assigns the physical file name.

<span style="font-weight: bold;">Notes:</span>

-   In real directories, the protocol file name is its physical name.
-   You can influence the FIFO behavior for the <span class="code" style="font-weight: bold;">RETR</span>, <span class="code" style="font-weight: bold;">STOR</span>, <span class="code" style="font-weight: bold;">MDTM</span> and <span class="code" style="font-weight: bold;">SIZE</span> FTP commands when they are used in combination with file name duplication (if the VFD allows it) with the <span class="code">ftp\_vfd\_fifo</span> parameter. Refer to [Advanced parameters and Trace levels](../../../configuration_start_here/config_gateway_paras#Advanced_parameters).

<span id="FTP_file_transfer__peltrans_command"></span>

## FTP file transfer: peltrans command parameters

The following table is a partial list of Transfer Request parameters and their default values. The parameters described here are either specific FTP parameters, or parameters that have a particular meaning when used in an FTP transfer. For the complete list of parameters and their possible values refer to [Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list).

#### Responder/Sender mode: Transfer Request parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Keyword names (*)</p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use the parameter to:</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-route_from_xfer (-rfx)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Activate a link between the incoming transfer and the outgoing one.</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Define the transmission mode: <span style="font-weight: bold;">R</span> in Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Define the transmission direction: <span style="font-weight: bold;">O</span> in Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>
<p>-file_component (-fc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Define protocol file name and to select the physical file to send (mandatory fields).</p>         </td>
      </tr>
      <tr>
         <td><p>-permanent (-perm)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Set Transfer Request availability to permanent.</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviated keyword names in parentheses

### Storing and retrieving FTP transferred files

#### Virtual File Directory (VFD)

Gateway always uses the VFD in FTP Responder mode. In virtual directories, the real file name is never used for:

-   <span class="code">STOR</span>, <span class="code">STOU</span> commands on the client side
-   <span class="code">RETR</span> on the server side

Consequently, you must specify the <span style="font-weight: bold;">protocol file name</span> to send files in both Initiator and Responder modes.

The protocol file name provided in LIST format in virtual directories, is <span class="code">sXXX.filename</span>, where:

-   <span class="code">XXX</span> is the <span class="code">xfer\_ident</span> field of the transfer
-   <span class="code">filename</span> is the protocol file name given in either the Transfer Request or the <span class="code">STOR</span> or <span class="code">STOU</span> command

The Mailbox entries are available either through this name, or just the protocol file name.

#### Gateway file filter and list query

As a virtual directory and a file name are sometimes insufficient to describe a Mailbox entry, Gateway provides an advanced file filter feature for use in <span class="code">RETR</span>, <span class="code">STOR</span>, <span class="code">STOU</span>, <span class="code">MDTM</span>, <span class="code">SIZE</span> and <span class="code">LIST</span> commands. This filter replaces the file name in these commands.

For example, the command:

RETR filename

can be replaced with:

RETR name=filename

A file filter is a string containing field=value pairs, separated either by space or "&" characters. Accepted values for fields are given in the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Accepted values</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>name</p>         </td>
         <td><p>A regular expression that matches paths and protocol file names, or an <span style="font-style: italic;">xfer_ident</span> format (<span style="font-style: italic;">s&lt;xfer_ident&gt;.&lt;proto_filename&gt;</span>).</p>         </td>
      </tr>
      <tr>
         <td><p>direction</p>         </td>
         <td><p>IN, OUT, or BOTH (not case-sensitive)</p>         </td>
      </tr>
      <tr>
         <td><p>date</p>         </td>
         <td><p>The date of the transfer, in the following format: <span style="font-style: italic;">YYYYMMDDhhmmss</span></p>
<ul>
<li>Date fields (year, month, day of month) can be separated by a "/" character.</li>
<li>Time fields (hours, minutes, and seconds) can be separated by ":" characters.</li>
</ul>
<p>Time can be provided without a date. The current day is then considered as the default date.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">end_before</span> or <span style="font-weight: bold;">endbefore</span></p>         </td>
         <td><p>All transfers requested or performed later than the given date, are not selected. The value is in date format.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">start_after</span> or <span style="font-weight: bold;">startafter</span></p>         </td>
         <td><p>All transfers requested or performed earlier than the given date, are not selected. The value is in date format.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">origin</span> or <span style="font-weight: bold;">org</span></p>         </td>
         <td><p>Originator Site</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">destination</span> or <span style="font-weight: bold;">dest</span></p>         </td>
         <td><p>Destination Site</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>List of states in Gateway format.</p>
<p>Each selected Transfer Request has one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">mvs_state</span> or <span style="font-weight: bold;">mvsstate</span></p>         </td>
         <td><p>List of states in MVS format.</p>
<p>Each selected Transfer Request has one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">ftpcs_state</span> or <span style="font-weight: bold;">ftpcsstate</span></p>         </td>
         <td><p>List of states in Axway EndPoint FTPCS format.</p>
<p>Each selected Transfer Request has one of the given states. The FTPCS state is the concatenation of the state in Gateway format and the state in InterPel MVS format.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">local_ident</span> or <span style="font-weight: bold;">localident</span></p>         </td>
         <td><p>A long integer</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">xfer_ident</span> or <span style="font-weight: bold;">xferident</span></p>         </td>
         <td><p>Transfer Identifier</p>         </td>
      </tr>
   </tbody>
</table>

#### Examples

RETR name=dir1/file1&org=site1&start\_after=20011205

LIST name=../\*.txt state=IC org=nova

Note that:

-   For multiple responses, for every command, except <span class="code">LIST</span> where only one entry is required, the most recent command will be kept.
-   Only one list of states can be given: <span style="font-weight: bold;">state</span>, <span style="font-weight: bold;">mvs\_state</span>, or <span style="font-weight: bold;">ftpcs\_state</span>.
-   For real entries and directories, the fields <span style="font-weight: bold;">origin</span>, <span style="font-weight: bold;">destination</span>, <span style="font-weight: bold;">direction</span>, <span style="font-weight: bold;">state</span> and <span style="font-weight: bold;">mvs\_state</span>, are ignored. In addition, <span style="font-weight: bold;">date</span>, <span style="font-weight: bold;">end\_before</span>, and <span style="font-weight: bold;">start\_after</span>, are compared to the last modification date.
-   If some fields are inconsistent but syntactically correct, no syntax error is returned. However, the command cannot be executed because it does not match any entry. Therefore, it can provoke negative responses such as <span style="font-weight: bold;font-style: italic;">File not found</span>.

#### Example

RETR name=file&state=C

In this example, the user tries to download the most recent entry called "file" and in the state "canceled". This is syntactically correct, but Gateway does not allow a canceled file to be downloaded and returns the following response:

550 File not found

#### Gateway list query reply format

Axway MFT products use several list formats in response to the <span class="code" style="font-weight: bold;">LIST</span> command:

-   UNIX format
-   NLST format (filenames only)
-   Axway EndPoint FTPCS format
-   Gateway user format

#### UNIX list format

To obtain the UNIX format, send a <span class="code">LIST</span> command with a standard filter field.

The UNIX format is mapped as follows:

drwx------ X  &lt;origin\_alias> &lt;destination\_alias>  &lt;size>  &lt;date> &lt;time>  &lt;filename>

where:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Denotes</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>drwx</p>         </td>
         <td><p>Type and rights of the given entry</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>Mailbox status in accordance with the Gateway MVS format (or"-" for real entries and directories)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;origin_alias&gt;</p>         </td>
         <td><p>Originator Site alias (or --NA-- for real entries and directories)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;destination_alias&gt;</p>         </td>
         <td><p>Destination Site alias (or --NA-- for real entries and directories)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;size&gt;</p>         </td>
         <td><p>Size in bytes of the file to transfer</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;date&gt;</p>         </td>
         <td><p>Transfer date in YYYY month day format (for example, 2006 Jan 20)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;time&gt;</p>         </td>
         <td><p>Transfer time in HH:MM format (for example, 18:30)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;filename&gt;</p>         </td>
         <td><ul>
<li><span style="font-style: italic;">s&lt;xfer_ident&gt;.&lt;filename&gt;</span> or <span style="font-style: italic;">&lt;filename&gt;</span> (dependent on <a href="../../../transfers_start_here/virtual_file_directory_start_here#VFD_file_name_display_option">VFD file name display option</a>) for virtual files</li>
<li><span style="font-style: italic;">&lt;filename&gt;</span> for real files and directories</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Example

-r-------- 9        FTPL      RFTP  2006 jan 20  18:30   file1

A remote client can use the "?" and "\*" wildcard characters for file selection.

Standard <span class="code">LIST</span> or <span class="code">NLST</span> commands only display transfers to start or to restart.

#### Gateway list format

The format for the Gateway file filter command is the following:

&lt;local\_ident> &lt;direct> XYZ &lt;origin\_alias> &lt;dest\_alias>  &lt;size> &lt;date> &lt;time>

where:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Denotes</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>&lt;filename&gt;&lt;local_ident&gt;</p>         </td>
         <td><p>Transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;direct&gt;</p>         </td>
         <td><p>Direction SEND or RECV</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>Gateway transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>Y</p>         </td>
         <td><p>State translated to Gateway MVS format</p>         </td>
      </tr>
      <tr>
         <td><p>Z</p>         </td>
         <td><p>Route state: E(empty route), T(to route), R(routed), A(acknowledged)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;origin_alias&gt;</p>         </td>
         <td><p>Site alias of the transfer origin (or --NA-- for real entries and directories)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;dest_alias&gt;</p>         </td>
         <td><p>Site alias of the transfer destination (or --NA-- for real entries and directories)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;size&gt;</p>         </td>
         <td><p>Size in bytes of the file to transfer</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;date&gt;</p>         </td>
         <td><p>Transfer date expressed as YYYY month day (ex: 2006 Jan 20)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;time&gt;</p>         </td>
         <td><p>Transfer time expressed as HH:MM (ex  18:30)</p>         </td>
      </tr>
      <tr>
         <td><p>&lt;filename&gt;</p>         </td>
         <td><p>Protocol filename provided in the Transfer Request</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

   <span style="font-weight: bold;">49 SEND E5   R65      TFTP              4 Dec 24 15:08 s49.UNIX</span>

#### Axway EndPoint FTPCS format

Gateway provides the field <span class="code">ftpcs\_list\_fields</span> to define, in server mode, the columns that can be sent in the <span class="code">LIST</span> command to clients connecting to Gateway with Axway EndPoint FTPCS.

The command line syntax is:

peladm update\_site &lt;field name>,&lt;field name>,&lt;field name>

where the available field names are taken from the following table:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field name</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>LOCID <sup>(2)</sup></p>         </td>
         <td><p>Transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>GTYPE <sup>(1) (2)</sup></p>         </td>
         <td><p>VFD type (virtual directory, real directory, virtual file, real file)</p>         </td>
      </tr>
      <tr>
         <td><p>RIGHTS <sup>(1)</sup></p>         </td>
         <td><p>VFD rights</p>         </td>
      </tr>
      <tr>
         <td><p>FILENAME <sup>(1)</sup></p>         </td>
         <td><p>Long name</p>
<ul>
<li><span style="font-style: italic;">s&lt;xfer_ident&gt;.&lt;filename&gt;</span> or <span style="font-style: italic;">&lt;filename&gt;</span> (dependent on <a href="../../../transfers_start_here/virtual_file_directory_start_here#VFD_file_name_display_option">VFD file name display option</a>) for virtual files</li>
<li><span style="font-style: italic;">&lt;filename&gt;</span> for real files and directories</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SFILENAME <sup>(1)</sup></p>         </td>
         <td><p>Short name, &lt;filename&gt; only</p>         </td>
      </tr>
      <tr>
         <td><p>APPLI</p>         </td>
         <td><p>Application name</p>         </td>
      </tr>
      <tr>
         <td><p>SIZE <sup>(1)</sup></p>         </td>
         <td><p>Size</p>         </td>
      </tr>
      <tr>
         <td><p>DATE<sup>(1)</sup></p>         </td>
         <td><p>Transfer creation date or Latest Modification date</p>         </td>
      </tr>
      <tr>
         <td><p>TYPE</p>         </td>
         <td><p>MVS transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>RSTATE</p>         </td>
         <td><p>Route state: E(empty route), T(to route), R(routed), A(acknowledged)</p>         </td>
      </tr>
      <tr>
         <td><p>UMSG</p>         </td>
         <td><p>User message</p>         </td>
      </tr>
      <tr>
         <td><p>ORG</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>DEST</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
      <tr>
         <td><p>P1</p>         </td>
         <td><p>Undefined parameter 1</p>         </td>
      </tr>
      <tr>
         <td><p>P2</p>         </td>
         <td><p>Undefined parameter 2</p>         </td>
      </tr>
      <tr>
         <td><p>PERM</p>         </td>
         <td><p>Permanent transfer indicator</p>         </td>
      </tr>
      <tr>
         <td><p>DATA_CODE</p>         </td>
         <td><p>B (Binary), T (Text)</p>         </td>
      </tr>
   </tbody>
</table>

When the item described in the listing is not a virtual file, transfer Mailbox, only these fields apply and are completed by the Gateway FTP server. Also, if not positioned, they are still sent to the client (in the last columns).

By default, <span class="code">ftpcs\_list\_fields</span> contains all fields.

The list is unordered which means that, irrespective of the order in which you type the fields to be displayed, they are sent to the FTP CS client in a predefined order (as laid out in the table above).

### Restarting a transfer (REST command)

Gateway can automatically restart transfers interrupted by incidents or by the user. In addition, before sending or receiving a file, an FTP client can indicate a restart by issuing the restart (<span class="code">REST</span>) command followed by a <span class="code">RETR</span>, <span class="code">STOR</span>, or <span class="code">STOU</span> command.

You must set the transfer restart option (<span style="font-style: italic;">Restart allowed</span> attribute) in the Remote Site that represents the client partner. This parameter is only relevant to the Gateway server. Its behavior mainly depends on the transmission mode:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Transmission mode</p>         </th>
<th class="HeadE-Column1-Header1"><p>Restart point</p>         </th>
<th class="HeadD-Column1-Header1"><p>Restart process</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>BLOCK</p>
<p>or COMPRESSED</p>         </td>
         <td><p>Named synchronization points are sent with data.</p>
<p>Gateway keeps these synchronization points in the transfer Mailbox record. (This means that you cannot restart transfers in real directories in BLOCK or COMPRESSED mode.)</p>         </td>
         <td><p>On transfer restart, the partners negotiate the synchronization point from which to restart the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>STREAM</p>         </td>
         <td><p>No meta-data can be added to the data flow. Therefore the client determines the restart point.</p>         </td>
         <td><p>If the client is:</p>
<ul>
<li>Downloading the file: the size already received is known</li>
<li>Uploading the file, the client uses the <span class="code">SIZE</span> command to retrieve the size already received by the server</li>
</ul>
<p>The client sends this restart offset to the server. Both partners initialize their file access in relation to the restart offset and the transfer can begin.</p>         </td>
      </tr>
   </tbody>
</table>

FTP defines behavior for the <span class="code">SIZE</span> and <span class="code">REST</span> commands. The <span class="code">SIZE</span> command parameter is a file name, and the <span class="code">REST</span> command accepts the restart offset. Offsets and file sizes must be expressed as a number of 8-bit bytes transferred.

The file size varies depending on the data representation type, for example, when data is encoded as ASCII (where line endings are CRLF) or IMAGE (where they are system-dependent: CR, CRLF, NL, or other values).

Most of the time, the only way to determine an FTP file size, or a physical restart offset from the <span class="code">REST</span> argument, is to parse the file in order to evaluate the pair (<span class="code">REST</span> offset, physical offset).

<span style="font-weight: bold;">Note:</span> In Responder mode, the <span class="code">REST</span> and <span class="code">SIZE</span> commands are not supported in RECORD structure. Since <span class="code">SIZE</span> is usually used before STREAM mode restarts, it is not supported in BLOCK or COMPRESSED mode.

### Receiving a file with a unique file name (STOU command)

The store unique (<span class="code">STOU</span>) command is supported in Responder mode in both virtual and real directories. The Gateway FTP server handles this in the same way as the <span class="code">STOR</span> command in virtual directories (Mailbox entries are unique by definition).

In real directories, <span class="code">STOU</span> makes the server search for a unique file name in the given directory. If a file with the same name already exists, a <span style="font-weight: bold;">.1</span> suffix is added. If that file name exists already, the suffix is incremented by 1 (<span style="font-weight: bold;">.2</span>, <span style="font-weight: bold;">.3</span>, and so on) until a free entry is found.

### Securing a server

#### Defending against hammer attacks

A hammer attack can occur when a user floods the server with requests until it can no longer respond to any other users. Gateway provides the following prevention methods against this type of attack:

-   Transfer quotas
-   Command sensitivity
-   Maximum file upload size limits

You can set each of these restrictions either using the exit routine <span style="font-weight: bold;">ExitProtocolConnection</span> or the Gateway Site, CGate, and CGateGroup objects.

#### Transfer quotas

Gateway provides four quota parameters for you to set transfer upload or download limits within a designated time period.

The following table describes transfer quota fields. By default, the fields are set to 0, which is equivalent to deactivating the quota restriction.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Transfer quota</p>         </th>
<th class="HeadE-Column1-Header1"><p>Definition</p>         </th>
<th class="HeadD-Column1-Header1"><p>Defense if exceeded</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>max_upload_rate</p>         </td>
         <td><p>Upload quota in KB per minute.</p>         </td>
         <td><p>Drops all transfers, irrespective of the direction (upload or download) in which the quota was exceeded.</p>
<p>Suspends transfer rights for the relevant direction.</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_rate</p>         </td>
         <td><p>Download quota in KB per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>max_upload_requests_rate</p>         </td>
         <td><p>Maximum number of upload-type transfers that can be requested per minute.</p>         </td>
         <td><p>Refuses client the right to transfer in the appropriate direction (upload or download) until it returns within the quota limit.</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_requests_rate</p>         </td>
         <td><p>Maximum number of download-type transfers that can be requested per minute.</p>         </td>
      </tr>
   </tbody>
</table>

#### Command sensitivity

The principle behind this mechanism of attributing a time-limited request credit to each client user is based on an implicit cost imputed to each command emitted (transfer, directory listing and so on), and disconnection when the available credit is exceeded.

The credit is represented by the level of sensitivity of your server to client requests. The more tolerant your machine is to client requests, the more credit is available. Set the sensitivity level using the <span style="font-weight: bold;">Command sensitivity</span> slide in the GUI or by setting the<span class="code"> command\_sensitivity</span> parameter to an integer value between 0 and 5 (where 0 is no sensitivity and 5 is maximum sensitivity).

The Gateway FTP server manages client consumption of these credits for all quotas (transfer and command sensitivity) in one sliding window. The window size is set in the configuration menu <span style="font-weight: bold;">Quota window size</span> field (specified in minutes). The default is 0, that is, all defenses are disabled irrespective of the quota limits already set.

#### Example

If, for example, the following elements are set:

-   <span style="font-weight: bold;">Quota window size</span> = 10 minutes
-   <span class="code" style="font-weight: bold;">max\_upload\_requests\_rate</span> = 8 uploads per minute

Then the Gateway FTP server verifies that the client does not exceed 80 uploads in <span style="font-weight: bold;">any 10-minute interval</span>. If the client sends a request that exceeds this limit, the server automatically activates the defenses, cutting all connections and refusing all further client access. These defenses remain active for the number of minutes necessary for the volume of uploads over the preceding 10-minute period to return to within the quota limit.

#### Maximum file upload size limit

Gateway refuses a transfer from a client if the file size in question exceeds the number of megabytes that you define using the <span class="code">maximum\_upload\_file\_size</span> parameter.

#### Monitoring User quotas

In the Gateway GUI, you can track user and quota consumption via the Connected User record. The interface displays:

-   Number of uploads and downloads
-   Volume of data transferred
-   Percentage of <span class="code">max\_upload\_rate</span> and <span class="code">max\_download\_rate</span> quotas used
-   Percentage of <span class="code">max\_upload\_requests\_rate</span> and <span class="code">max\_download\_requests\_rate</span> quotas used

Gateway also provides the online command <span class="code" style="font-weight: bold;">pelctl reset\_connected\_user</span> to:

-   Reset recorded consumption to zero
-   Delete the connection if it is no longer active

This command therefore serves as a mechanism to authorize a client to reconnect after being suspended.

<span id="Defending_against_bounce_attacks"></span>

#### Defending against bounce attacks

A bounce attack can occur when a client opens a data session between an FTP server (A) and a listening port on another machine (server B). The client then uses this session to send a file with commands that server B will understand. The result of this indirect communication is that it is generally extremely difficult to identify or trace the user responsible for the commands.

The IP address provided by the remote partner is compared with the remote address in the control session. If they are not the same, an error is returned, and logged.

You can set this option in the Remote Site and in the Proxy object (in the <span class="code">change\_data\_addr</span> field). To reject data sessions with addresses different to those in the control sessions, set the <span class="code">change\_data\_addr</span> parameter to <span style="font-style: italic;">No</span>.

Related topics

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

[Configuring protocols: FTP options](../../../configuration_start_here/config_protocols_about/config_ftp_options)

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

[Monitoring Connections](../../../transfers_start_here/monitoring_transfers_start_here/monitoring_connections_gui)

[Monitoring Connections (command line)](../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connections_cli)

[Monitoring Connected Users](../../../transfers_start_here/monitoring_transfers_start_here/monitoring_connected_users_(gui))

[Monitoring Connected Users (command line)](../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connected_users_cli)

[Working with Proxies](../../../managing_partners_start_here/proxies_about/managing_proxies)

[Working with Proxies (command line)](../../../managing_partners_start_here/proxies_about/managing_proxies_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
