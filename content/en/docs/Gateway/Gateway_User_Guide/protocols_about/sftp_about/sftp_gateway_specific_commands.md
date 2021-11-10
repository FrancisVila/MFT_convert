{
    "title": "Gateway-specific SFTP commands",
    "linkTitle": "Gateway specific SFTP commands",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[Recognizing a Gateway partner](#Recognizing_a_Gateway_partner)

[Using an Application](#Using_an_application)

[Identifying a transfer](#Identifying_a_transfer)

[File filter and list query](#File_filter_and_list_query)

[Pre-transfer and post-transfer commands](#Pre_transfer_and_post_transfer_commands)

<span id="Recognizing_a_Gateway_partner"></span>

## Recognizing a Gateway partner

Gateway extensions to standard SFTP behavior can only be used between Gateway entities. To identify the two parties, a Gateway client sends the following extensions during the initialization phase in the format described in [SFTP extensions](../#SFTP_extensions).

-   "SSH\_FXP\_OPEN@axway.com"
-   "SSH\_FXP\_OPENDIR@axway.com"

A server that recognizes all or part of these primitives returns the parameters that it recognizes in its reply.

For each of these requests, the data field that accompanies them indicates the parameters that you can enter. For example, the field <span style="font-weight: bold;">name&appli&dest&org&snd\_msg</span>, provided as a complement to *SSH\_FXP\_OPEN@axway.com*, indicates the set of parameters that the client can supply to identify a transfer.

Similarly, the data fields accompanying the server responses contain the parameters recognized by the server for information purposes.

Parameters that are not recognized by the extended syntax are ignored.

<span id="Using_an_application"></span>

## Using an Application

There are two methods for a server to find the Application to use for a file transfer:

-   Set the Application name as an open file parameter, as described in [About Applications](../../../transfers_start_here/parameters_start_here/applications_start_here)
-   Use an FTP Application exit

If you do not select either of these two methods, Gateway uses the *FTP\_B* Application. This is the standard Application to use with SFTP because it does not apply any data code conversion or transformation. SFTP always transfers files in binary mode.

<span id="Identifying_a_transfer"></span>

## Identifying a transfer

Remote file access is performed with the command <span class="code" style="font-weight: bold;">FXP\_OPEN</span>. The extended file name syntax illustrated in the example below is similar to the syntax used in FTP/HTTP Transfer Requests.

The table below describes the elements that Gateway uses as parameters for <span class="code" style="font-weight: bold;">FXP\_OPEN</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Mode</p>         </th>
<th class="HeadE-Column1-Header1"><p>Client to server transfer</p>         </th>
<th class="HeadD-Column1-Header1"><p>Server to client transfer</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>RFD (monitored or not)</p>         </td>
         <td><p>Names as they are received on the system.</p>
<p>Gateway applies the options (read, write, append, creat, trunc, excl) and takes the VFD rights for the user into account.</p>         </td>
         <td><p>System file names are kept and are visible if this client has authorized access.</p>         </td>
      </tr>
      <tr>
         <td><p>VFD</p>         </td>
         <td><p>The server can modify file names when it receives files, taking into account the local identifier and file name.</p>         </td>
         <td><p>Files are made available to the client with virtual (logical) names. By default, the file name presented to the client is in the format:</p>
<p>"s"+<em>&lt;xfer_ident&gt;+</em>"."+<em>&lt;filename&gt; <span style="font-weight: bold;">or</span> file name only</em> (depending on <a href="../../../transfers_start_here/virtual_file_directory_start_here#VFD_file_name_display_option">VFD file name display option</a>)</p>
<p>However, it is possible to retain the protocol file name.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

name=dir1/file1&org=site1&dest=site0

This syntax allows you to set additional parameters required for transfers between two Gateway entities:

-   <span style="font-weight: bold;">name</span>: file name (the identifier of the connected user must not appear in the file names)
-   <span style="font-weight: bold;">appli</span>: application name
-   <span style="font-weight: bold;">dest</span>: destination
-   <span style="font-weight: bold;">org</span>: originator
-   <span style="font-weight: bold;">snd\_msg</span>: accompanying messages

The slash ("/") is used as a directory separator, the period "." identifies the current directory and two dots ".." the parent directory. The client can request file names that it can see in the directory list.

<span id="File_filter_and_list_query"></span>

## File filter and list query

You can request the transfer of a list of files in a directory. The result of the operation is stored in a file that can be used for subsequent requests.

Gateway allows you to filter a directory listing. If both parties are Gateway systems, the Initiator of the request can filter file names using the extension **SSH\_FXP\_OPENDIR**.

A file filter is a string that contains <span style="font-style: italic;font-weight: bold;">field</span>=<span style="font-style: italic;font-weight: bold;">value</span>pairs, separated by the "&" character. This filter replaces the directory name in transfer commands.

The table below shows the accepted field values.

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
         <td><p>Can be a regular expression that matches paths and protocol file names, or a transfer identifier format (&lt;xfer_ident&gt;.&lt;proto_filename&gt;)</p>         </td>
      </tr>
      <tr>
         <td><p>date</p>         </td>
         <td><p>The exact moment of the transfer, given in the following date format: YYYYMMDDhhmmss</p>
<ul>
<li>Date fields (year, month, day of month) can be separated by a "/" character.</li>
<li>Time fields (hours, minutes, and seconds) can be separated by ":" characters.</li>
<li>Time can be provided without a date. The current day is then considered as the default date.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>direction</p>         </td>
         <td><p>Accepted values are IN, OUT, or BOTH. It is not case-sensitive.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">endbefore</span> or <strong>end_before</strong></p>         </td>
         <td><p>All transfers requested or performed later than the given date are not selected. The value is of date format.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">startafter</span> or <strong>start_after</strong></p>         </td>
         <td><p>All transfers requested or performed earlier than the given date are not selected. The value is of date format.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">origin</span> or <span style="font-weight: bold;">org</span></p>         </td>
         <td><p>Originator Site alias</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">dest</span> or <strong>destination</strong></p>         </td>
         <td><p>Destination Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>List of states in Gateway format. Each selected transfer has one of the given states.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">localident</span> or <strong>local_ident</strong></p>         </td>
         <td><p>Long integer</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">xferident</span> or <strong>xfer_ident</strong></p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

The following command lists files on the server SITE1, in the <span class="code">sftp/dir1</span> directory, dated between 03/03/2006 12:13:14 and 03/03/2007 12:13:14.

peltrans  –oa SITE1

–dir\_name "name=/sftp/dir1/&start\_after=20060303121314&end\_before=20070303121314"

–type DIR  –dir I  –ap FTP\_B

### List query reply format

In a standard request for a directory listing, the information returned for each entry is the:

-   short file name
-   long file name
-   file attributes

The long file name is a field used for presentation purposes only.

#### Example

drwxrwxrwx 9 LSFTP RSFTP 12345 2006 Mar 25 14:29 file1

where:

-   *drwxrwxrwx* = rights
-   *9* = Mailbox status (translated into Axway Transfer InterPel MVS format or ‘-‘ in RFD)
-   *LSFTP* = originating site alias or ‘—NA—‘ in RFD
-   *RSFTP* = destination site alias or ‘—NA—‘ in RFD
-   *12345* = size in KB
-   *2006 Mar 25 14:29* = last modification date
-   *file1* = file name

<span id="Pre_transfer_and_post_transfer_commands"></span>

## Pre-transfer and post-transfer commands

With the SFTP protocol you can send commands or information before and after a transfer using the <span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands.

### SITE command

<span class="code" style="font-weight: bold;">SITE</span> commands are used to send the SFTP protocol extensions. They must be negotiated during the SFTP initialization phase.

#### Example

SITE command data

This <span class="code" style="font-weight: bold;">SITE</span> command generates the transmission of an **SSH\_FXP\_EXTENDED** type with the parameters <span class="code">command@axway.com /data</span>.

### QUOTE command

<span class="code" style="font-weight: bold;">QUOTE</span> commands allow you to send standard commands, such as renaming a file after a transfer. The actions that are available with the <span class="code" style="font-weight: bold;">QUOTE</span> command include:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Action</p>         </th>
<th class="HeadE-Column1-Header1"><p>Command syntax</p>         </th>
<th class="HeadD-Column1-Header1"><p>SFTP Message</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Delete a file</p>         </td>
         <td><p>REM <em>file_name</em></p>         </td>
         <td><p>SSH_FXP_REMOVE</p>         </td>
      </tr>
      <tr>
         <td><p>Rename/Move a file</p>         </td>
         <td><p>RENAME <em>file1 file2</em></p>         </td>
         <td><p>SSH_FXP_RENAME</p>         </td>
      </tr>
      <tr>
         <td><p>Create a directory</p>         </td>
         <td><p>MKDIR <em>dir_name</em></p>         </td>
         <td><p>SSH_FXP_MKDIR</p>         </td>
      </tr>
      <tr>
         <td><p>Delete a directory</p>         </td>
         <td><p>RMDIR <em>dir_name</em></p>         </td>
         <td><p>SSH_FXP_RMDIR</p>         </td>
      </tr>
      <tr>
         <td><p>Set remote pathname rights</p>         </td>
         <td><p>CHMOD [N]NNN <span style="font-style: italic;">pathname</span><br />
where 0&lt;=N&lt;=7</p>         </td>
         <td><p>SSH_FXP_SETSTAT</p>         </td>
      </tr>
   </tbody>
</table>

SFTP servers do not enable you to change the current directory. This can only be done on the client side.

<span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands are used for pre-transfer processing. To indicate that a command must be processed *after* the transfer, you must use:

-   AE\_QUOTE
-   AC\_QUOTE
-   AE\_SITE
-   AC\_SITE

Use the <span class="code" style="font-weight: bold;">AE\_</span> prefix when the transfer status must remain *ENDED* if the command fails, and the <span class="code" style="font-weight: bold;">AC\_</span> prefix if the status is set to *CANCELED* if an error occurs.

<span style="font-weight: bold;">Note:</span> The post-transfer command will not be processed if the transfer fails (status is not *ENDED*).

#### Example

AC\_QUOTE RENAME TOTO1.TMP TOTO1.OK

This command renames the file <span class="code">TOTO1.TMP</span> to <span class="code">TOTO1.OK</span> after the file transfer has ended (when the status is ENDED).

### Calling a script

You can place <span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands in a script and call it using the following syntax:

peladm update\_site  -snd\_msg "SCRIPT &lt;script\_site>"

peltrans  -ftp\_command "SCRIPT &lt;script\_xfer>"

In a script file, you must write each command on a separate line or use a semi-colon (;) to separate commands.

#### Example script

AC\_QUOTE RENAME old\_name new\_name

AC\_QUOTE REM filename

<span style="font-weight: bold;">Note:</span> Gateway does not permit calling a script within a script.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
