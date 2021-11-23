{
    "title": "Using FTP in Initiator mode ",
    "linkTitle": "Using FTP in Initiator mode",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Protocols

After [configuring the Remote Site and Application for FTP](../ftp_config) you can submit a Transfer Request.

## Using an Application with the FTP protocol

### Initiator/Sender

If a remote FTP client, the Initiator, needs to select an Application for a file transfer, you can transmit an Application name with an FTP `SITE` command using the following syntax:

SITE P\_APPLI appli\_name

If you are using Gateway as an FTP client, it uses the FTP `SYST` command to detect whether or not the remote FTP server is Transfer InterPel or Gateway. In this case, the `SITE P_APPLI <appli_name>` FTP command is always sent.

This command is specific to Axway MFT, and can only be used with other Axway MFT FTP servers. In addition, this command is only taken into account if the **Application method** (<span class="code">get\_appli\_method</span>) field of the Gateway FTP server Remote Site is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>).

### Using peltrans commands for an FTP file transfer

The following table is a partial list of Transfer Request parameters relevant to FTP in Initiator/ Sender and Initiator/ Receiver modes. The parameters described here are in addition to those discussed previously. For the complete list of parameters and their possible values refer to [Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list).

**Initiator/Sender mode: Transfer Request parameters**

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" class="HeadE-Column1-Header1">Keyword names (*)         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Default         </th>
<th style="text-align: left;" class="HeadD-Column1-Header1">Use the parameter to:         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-snd_msg (-sm)</p>
<p>-snd_msg_file (-smf)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Enter a user message. Translated as a <span class="code">SITE P_MSG</span> <em>user_message</em>.</p>         </td>
      </tr>
      <tr>
         <td><p>-unique_filename (-uf)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Assign a unique file name on the server (<span class="code">STOU</span> command is sent in FTP)</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_name (-dn)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Define the remote file location</p>         </td>
      </tr>
      <tr>
         <td><p>-ftp_command (-ftpc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Send FTP commands to remote servers using <span class="code" style="font-weight: bold;">QUOTE</span> or <span class="code" style="font-weight: bold;">SITE</span> command</p>         </td>
      </tr>
      <tr>
         <td><p>-append (-app)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Append data files to a received file on the same server. For use only on the client side in sender mode.</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviated keyword names in parentheses.

### Defining the remote location of a file

In Initiator mode, the <span class="code">dir\_name</span> parameter of a Transfer Request enables you to define the location of a remote file. This location is the destination of the file (for an outgoing transfer), or the remote path (for an incoming transfer).

In UNIX/Windows, this parameter generally indicates a path. However, since a remote FTP server does not necessarily manage files with a hierarchical file system, or file separators, the FTP server can only concatenate <span class="code">dir\_name</span> and <span class="code">file\_name</span> without further analysis of the two strings.

#### Example:

In this example, the following Transfer Request:

peltrans  -mode I  -direction O  -dest\_alias FTP\_SERVER

  -appli FTP\_B  -file\_component local\_file

<span style="font-weight: bold;">  -dir\_name /dir1/  -file\_name file</span>

results in the FTP transfer command:

STOR /dir1/file

<span style="font-weight: bold;">Note:</span> If the trailing <span class="code" style="font-weight: bold;">/</span> character is omitted in the <span class="code">dir\_name</span> parameter, the transfer directory selected becomes:

STOR /dir1file

## Using FTP commands for a transfer

You can define the FTP commands used to retrieve or send a file (<span class="code" style="font-weight: bold;">RETR</span>, <span class="code" style="font-weight: bold;">STOR</span>, <span class="code" style="font-weight: bold;">STOU</span>, <span class="code" style="font-weight: bold;">REST</span> and so on) via the Gateway GUI or Gateway online commands.

### FTP commands that define a transfer

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" class="HeadE-Column1-Header1">FTP command         </th>
<th style="text-align: left;" class="HeadE-Column1-Header1">Define in:         </th>
<th style="text-align: left;" class="HeadD-Column1-Header1">Use to:         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>SYST</strong></p>         </td>
         <td><p>None (automatic Axway MFT command)</p>         </td>
         <td><p>Identify an Axway MFT product.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>RETR (GET)</strong></p>         </td>
         <td><p>Transfer</p>         </td>
         <td><p>Receive a transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>STOR (PUT)</strong></p>         </td>
         <td><p>Transfer</p>         </td>
         <td><p>Send a transfer (a request to store the current record in an output file).</p>         </td>
      </tr>
      <tr>
         <td><p><strong>STOU</strong></p>         </td>
         <td><p>Transfer</p>         </td>
         <td><p>Give the file a unique name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>REST</strong></p>         </td>
         <td><p>Remote Site</p>         </td>
         <td><p>Enable restart of an interrupted transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>SIZE file name</strong></p>         </td>
         <td><p>None (automatic Axway MFT command)</p>         </td>
         <td><p>Return the number of kilobytes transferred with the current transfer structure, mode and type to determine the restart point.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>REMOVEFILE</strong></p>         </td>
         <td>Transfer         </td>
         <td>Remove the transferred file from the remote server. The command takes no arguments.         </td>
      </tr>
      <tr>
         <td><p><strong>RENAMEFILE</strong></p>         </td>
         <td>Transfer         </td>
         <td>Rename/move the transferred file on the remote server to the given argument. The command is used with a filename or file pathname argument.         </td>
      </tr>
      <tr>
         <td><p><strong>LIST</strong></p>         </td>
         <td><p>Transfer</p>         </td>
         <td><p>Retrieve directory listings in Long format. (*)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>NLST</strong></p>         </td>
         <td><p>Transfer</p>         </td>
         <td><p>Retrieve directory listings in Names format. (*)</p>         </td>
      </tr>
   </tbody>
</table>

(\*) For a more precise listing, use the advanced queries and filters provided by Gateway.

### Using the SITE or QUOTE command

#### Identifying commands in the transfer

Use the <span class="code">-ftp\_command</span> field in a Transfer Request to send a server-specific remote command or an unsupported command to the FTP server before or after transfer. <span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands are supported as parameters of the <span class="code">-ftp\_command</span> field.

#### SITE command

An FTP client can use the FTP command <span class="code" style="font-weight: bold;">SITE</span> to send any server-specific command to a remote server.

The syntax using the <span class="code" style="font-weight: bold;">peltrans</span> command is:

peltrans

-ftp\_command "SITE &lt;fct1> &lt;parameter1>; SITE &lt;fct2> &lt;parameter2>"

Before Gateway sends the file, it sends each specific function to the remote server.

<span style="font-weight: bold;">Note:</span> If you receive a return code other than 200 (command OK) or 202 (command not implemented) for a <span class="code" style="font-weight: bold;">SITE</span> command, Gateway stops the current transfer.

#### QUOTE command

Use the FTP command <span class="code">QUOTE</span> to send a standard FTP command for it to be recognized by Gateway.

For example, Gateway cannot use <span class="code">CWD</span> (Change Working Directory) as an FTP command by itself. If you need to change the current directory on the remote file system for a specified file transfer, you can use the following in the <span class="code">**ftp\_command**</span> field in the Transfer Request:

QUOTE CWD &lt;dir>

<span style="font-weight: bold;">Note:</span> Receiving a return code greater than or equal to 400 for a <span class="code">QUOTE</span> command automatically stops the current transfer.

#### Post-transfer SITE and QUOTE commands

<span class="code">SITE</span> and <span class="code">QUOTE</span> commands always indicate pre-transfer processing. To specify that a command must be processed <span style="font-style: italic;">after</span> the transfer, use:

-   <span class="code">AE\_QUOTE</span> or <span class="code">AC\_QUOTE</span> instead of <span class="code">QUOTE</span>
-   <span class="code">AE\_SITE</span> or <span class="code">AC\_SITE</span> instead of <span class="code">SITE</span>

The <span class="code">AE\_</span> prefix is used when the transfer must remain *ENDED* if the command fails. With the <span class="code">AC\_</span> prefix, its state is set to *CANCELED* if an error occurs.

<span style="font-weight: bold;">Note:</span> The post-transfer command is not processed if the transfer fails (its state is not *ENDED*).

#### Example 1: Commands sent pre- and post-transfer

peltrans  -da RFTP  -ap UNIX  -fn UNIX  -fc File1.txt

  -ftpc QUOTE command1;AE\_QUOTE command2

Gateway executes command1 before the transfer begins and command2 after the transfer ends. If command2 fails, the transfer state remains *ENDED*.

#### Example 2: Command sent post-transfer

peltrans  -da RFTP  -ap UNIX  -fn UNIX  -fc File1.txt

  -ftpc AC\_QUOTE command1

Gateway sends *command1* after the transfer ends. If *command1* fails, the transfer state is set to CANCELED.

#### Example 3: File renamed post-transfer

peltrans  -da RFTP  -ap UNIX  -fn FILE1.TMP  -fc File1.txt

  -ftpc AC\_QUOTE RNFR FILE1.TMP;AC\_QUOTE RNTO FILE1.OK

The file is renamed from <span class="code">FILE1.TMP</span> to <span class="code">FILE1.OK</span> after the transfer ends. If renaming fails, the transfer state is set to *CANCELED*.

<span id="SCRIPT"></span>

#### Calling a script

You can place <span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands in a script and call it using the following syntax:

peladm update\_site  -snd\_msg "SCRIPT &lt;script\_site>"

peltrans  -ftp\_command "SCRIPT &lt;script\_xfer>"

In a script file, you must write each command on a separate line or use a semi-colon (;) to separate commands.

#### Example script

QUOTE CWD /tmp

QUOTE CWD public

SITE &lt;fct1> &lt;param1>; SITE &lt;fct2> &lt;param2>

SITE &lt;fct3> &lt;param3>

AC\_QUOTE RNFR old\_name

AC\_QUOTE RNTO new\_name

<span style="font-weight: bold;">Note:</span> Gateway does not permit calling a script within a script.

#### Defining SITE and QUOTE commands in the Remote Site

To change directories or send additional commands each time you connect to a remote FTP server, use the Remote Site parameter <span class="code">-snd\_ msg</span>.

You can only use <span class="code">QUOTE</span> and <span class="code">SITE</span> commands in this field (not <span class="code">AE\_</span> and <span class="code">AC\_</span> commands).

#### Example

peladm update\_site .. -snd\_msg QUOTE CWD /tmp

This command allows you to move to the <span class="code">/tmp</span> remote directory before starting the data transfers.

### Sending a file with a unique file name command (STOU command)

Some servers (IIS FTP, for example) only support the standard RFC 959 format, which defines the <span class="code" style="font-weight: bold;">STOU</span> command without any parameters.

If you receive a 500 code in response to a <span class="code">**STOU &lt;filename>**</span> command, this means that the Gateway FTP client is attempting to send a <span class="code" style="font-weight: bold;">STOU</span> command with no arguments. Therefore the protocol file name of the transfer record is not changed.

### Allocating file size (ALLO command)

If necessary, you can activate or deactivate the automatic **allocate request** option for reserving file space before you send a file in FTP. Use this feature, for example, if the rejection of your automatic allocation request causes Gateway to cancel your transfer. This parameter is active by default.

Set the <span class="code">allocate\_request</span> parameter in the configuration menu.

#### Configuring the ALLO command

<span class="code" style="font-weight: bold;">allocate\_request = 0</span>: deactivates the <span class="code">ALLO</span> command

<span class="code" style="font-weight: bold;">allocate\_request = 1</span>: activates the <span class="code">ALLO</span> command

## Directory listing (-type and dir\_type parameters)

Current versions of FTP (and HTTP) support the listing of directories in Initiator mode. To retrieve the contents of a given directory, Gateway requests a **DIR** type transfer. It saves the result in a file, just as for a standard download transfer. This file can then be processed in a post-transfer exit script.

This feature is useful primarily for retrieving files from a given directory when you do not know the exact file names. You can define a user script to parse the resulting directory listing file, and create a Transfer Request for each file name listed.

### <span class="code">type</span> and <span class="code">dir\_type</span> parameters

In FTP, the **DIR** transfer type indicates that you must send a <span class="code" style="font-weight: bold;">LIST</span> or <span class="code" style="font-weight: bold;">NLST</span> command instead of <span class="code" style="font-weight: bold;">RETR</span>. The online parameter (only used in Initiator/ Receiver mode) is <span class="code">-type</span> and its value must be set to *dir*.

The online parameter <span class="code">-dir\_type</span> is used to define the level of list detail. You can set this parameter to one of the following values:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" class="HeadE-Column1-Header1"><span class="code">-dir_type</span> value         </th>
<th style="text-align: left;" class="HeadE-Column1-Header1">Listing command sent         </th>
<th style="text-align: left;" class="HeadD-Column1-Header1">Disadvantage         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">names</span></p>
<p>(default)</p>         </td>
         <td><p>NLST</p>
<p>Retrieves the most basic details. Each line in the file indicates the name of an item.</p>         </td>
         <td><ul>
<li>No distinction between files and directories</li>
<li>No extra information is given. For example, the last modification date</li>
<li>Some servers do not send the whole list, or the complete relative path of each item</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>long</p>         </td>
         <td><p>LIST</p>
<p>Retrieves more detailed information than the <span class="code">NLST</span> command. Its content depends on the server and is typically in a UNIX format.</p>         </td>
         <td><ul>
<li>More complicated to parse the resulting file to retrieve this information</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### <span class="code">dir\_name</span> and <span class="code">file\_name</span>

The <span class="code">-dir\_name</span> field specifies the directory to list.

The <span class="code">-file\_name</span> field is optional, and (for DIR transfers) no default value is set if it is left empty. If set, its purpose is to define a filter on file names returned by the server.

The Gateway FTP client appends<span class="code"> -file\_name</span> to <span class="code">-dir\_name</span>, and sends the result in the Transfer Request. (In addition, HTTP adds the file separator <span class="code" style="font-weight: bold;">/</span> if it is not present at the end of <span class="code">-dir\_name</span>.) However, the server response to such a request is unpredictable as illustrated in the following example.

### Example

peltrans  -m I  -dir I  -oa FTP\_SERVER  -ty DIR

  -dt LONG  -dn /users/shared/  -fn \*.txt

In this example, the command <span class="code">LIST /users/shared/\*.txt</span> is sent to the FTP server. The server response may be any of the following:

-   Send a list of <span class="code">/users/shared</span> files whose names match the pattern <span class="code">\*.txt</span>
-   Return an error
-   Try to find the file whose name is exactly <span class="code">\*.txt</span>

<span style="font-weight: bold;">Note:</span> The final <span class="code" style="font-weight: bold;">/</span> character in the <span class="code">-dir\_name</span> field is mandatory for FTP since file separators are not specified. As a result, Gateway can only concatenate <span class="code">dir\_name</span> and <span class="code">file\_name</span> without further analysis of the two strings.

### Application

An Application is not mandatory for a DIR Transfer Request. If you do not specify an Application, the protocol supplies default parameters equivalent to <span class="code">FTP\_A</span> for FTP.

If you specify an Application, the corresponding encoding parameters (file attributes and transfer attributes) must match the default parameters. Otherwise Gateway processing is unpredictable.

## Identifying an Axway MFT product (SYST command)

In Initiator mode, Gateway uses the <span class="code" style="font-weight: bold;">SYST</span> command to identify whether or not the partner Site is an Axway MFT product.

In response to an FTP <span class="code">SYST</span> command, an Axway MFT product sends the following string:

"215 &lt;OS XFB/&lt;Operating\_System\_type>"

### Example

UNIX XFB/UNIX

Related topics

[Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
