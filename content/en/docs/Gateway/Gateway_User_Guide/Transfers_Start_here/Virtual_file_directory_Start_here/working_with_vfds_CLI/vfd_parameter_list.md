{
    "title": "Virtual File Directories: Parameters List",
    "linkTitle": "VFD: Parameters List",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[VFD directory parameters](#VFD_directory_parameters)

[VFD file parameters](#VFD_File_parameters)

<span id="VFD_directory_parameters"></span>

## VFD directory parameters

The following table lists all VFD directory parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in <span style="font-style: italic;font-weight: bold;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Values</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>alias (-a)</p>
<p><span style="font-style: italic;font-weight: bold;">Alias</span></p>         </td>
         <td><p>VFD directory alias. Use this alias to designate a specific directory (whether moved or renamed) within the VFD administration and Transfer Request command lines.</p>         </td>
         <td><p>Up to 32 alphanumeric characters</p>
<p>Its value must be unique in the whole VFD</p>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>Comments about a VFD directory</p>         </td>
         <td><p>Up to 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>dir_path (-dp)</p>
<p><span style="font-style: italic;font-weight: bold;">PathName + Name</span></p>         </td>
         <td><p>Absolute path of the VFD directory. You can either reference the VFD via the path name or via the alias.</p>         </td>
         <td><p>The total length of this parameter is limited to 255 characters (or slightly lower in some cases). Individual directory nodes in the path are limited to 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>filename_display_option (-fdo)</p>
<p>File name display option</p>         </td>
         <td><p>Indicates how file names are displayed</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Standard</strong> = file name only</li>
<li><strong>XFB</strong> = <span class="code">s.XferIdent.filename</span>(default)</li>
</ul>
<p>Refer to <a href="../../#VFD_file_name_display_option">VFD file name display option</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>filename_duplicate_policy (-fdp)</p>
<p>File name duplication policy</p>         </td>
         <td><p>Indicates how duplicate file names are managed</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li>duplicate<span style="font-weight: normal;"> (default)</span></li>
<li>forbid</li>
<li>override</li>
</ul>
<p>Refer to <a href="../../#VFD_file_name_duplication_policy">VFD file name duplication policy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>filter (-f)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Listing directory contents:</p>
<p>String which can contain "?" and "*" wildcard characters. Only displays the inner components of the current VFD directory whose name matches the filter string.</p>         </td>
         <td><p>Up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>is_cgi_bin (-icb)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>VFD CGI directory</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>mbx_recording (-mr)</p>
<p><span style="font-style: italic;font-weight: bold;">Monitoring</span></p>         </td>
         <td><p>RFD mode only</p>
<p>Gateway Mailbox recording option. This option indicates whether to trace the transfer operations on the current directory (downloading and uploading) in the Gateway Mailbox.</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>mount_dir_path (-mdp)</p>
<p><span style="font-style: italic;font-weight: bold;">Mount name</span></p>         </td>
         <td><p>Absolute path of the physical directory (RFD) to be mounted</p>         </td>
         <td><p>The total length of this parameter is limited to 255 characters. Individual directory nodes in the path are limited to 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>mount_point (-mp)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Indicates whether or not to mount the current directory</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>new_alias (-na)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Updating a VFD directory alias: Indicates new alias value</p>         </td>
         <td><p>Up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>new_dir_path (-ndp)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Moving or renaming a directory: VFD absolute path of the new location of the VFD directory</p>         </td>
         <td><p>The total length of this parameter is limited to 255 characters. Individual directory nodes in the path are limited to 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>no_dir (-nd)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Listing directory contents: Indicates that sub-directories must not be displayed</p>         </td>
         <td><p>–</p>         </td>
      </tr>
      <tr>
         <td><p>no_file (-nf)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Listing directory contents: Indicates that files must not be displayed</p>         </td>
         <td><p>–</p>         </td>
      </tr>
      <tr>
         <td><p>tls_only (-tls)</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>TLS only flag</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>user_attribute (-ua)</p>
<p><span style="font-style: italic;font-weight: bold;">User data</span></p>         </td>
         <td><p>User parameter associated with the current directory</p>         </td>
         <td><p>Up to 80 alphanumeric characters</p>         </td>
      </tr>
   </tbody>
</table>

<span id="VFD_File_parameters"></span>

## VFD file parameters

All of the following parameters are extracted from the related Gateway Mailbox record. The following table lists all VFD file parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in <span style="font-style: italic;font-weight: bold;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Values</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>access_rights</p>
<p><span style="font-weight: bold;">(<span style="font-style: italic;">None</span>)</span></p>         </td>
         <td><p>Access rights associated with the current VFD Item</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>appli</p>
<p><span style="font-style: italic;font-weight: bold;">Application</span></p>         </td>
         <td><p>Application name of the current VFD Item</p>         </td>
         <td><p>Up to 27 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>data_code</p>
<p><span style="font-style: italic;font-weight: bold;">Data code</span></p>         </td>
         <td><p>Indicates the data code of transferred data</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">B</span>= Binary</li>
<li><span style="font-weight: bold;">A</span>= ASCII</li>
<li><span style="font-weight: bold;">A1</span>= ASCII1</li>
<li><span style="font-weight: bold;">A2</span>= ASCII2</li>
<li><span style="font-weight: bold;">A3</span>= ASCII3</li>
<li><span style="font-weight: bold;">A4</span>= ASCII4</li>
<li><span style="font-weight: bold;">A5</span>= ASCII5</li>
<li><span style="font-weight: bold;">E</span>= EBCDIC</li>
<li><span style="font-weight: bold;">E1</span>= EBCDIC1</li>
<li><span style="font-weight: bold;">E2</span>= EBCDIC2</li>
<li><span style="font-weight: bold;">E3</span>= EBCDIC3</li>
<li><span style="font-weight: bold;">E4</span>= EBCDIC4</li>
<li><span style="font-weight: bold;">E5</span>= EBCDIC5</li>
<li><span style="font-weight: bold;">ISO</span>= ISO</li>
<li><span style="font-weight: bold;">OEMPC</span>= OEMPC</li>
<li><span style="font-weight: bold;">U</span>= Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>date_create</p>
<p><span style="font-style: italic;font-weight: bold;">Created on</span></p>         </td>
         <td><p>VFD file creation date</p>         </td>
         <td><p>Format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>
<p><span style="font-style: italic;font-weight: bold;">Destination</span></p>         </td>
         <td><p>Destination protocol identifier of the current VFD file</p>         </td>
         <td><p>Up to 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>direction</p>
<p><span style="font-style: italic;font-weight: bold;">Direction</span></p>         </td>
         <td><p>Direction of the Transfer related to the current VFD file</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">O</span> = Output</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>dir_path</p>
<p><span style="font-style: italic;font-weight: bold;">Dir path</span></p>         </td>
         <td><p>VFD absolute path of the current VFD Item parent directory</p>         </td>
         <td><p>Up to 255 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>duplicate_from_xfer</p>
<p><span style="font-style: italic;font-weight: bold;">Duplicated from</span></p>         </td>
         <td><p>Identifier of permanent Transfer Request used to generate the Transfer that corresponds to the current VFD file</p>         </td>
         <td><p>Integer (automatically assigned by Gateway)</p>         </td>
      </tr>
      <tr>
         <td><p>file_name</p>
<p><span style="font-style: italic;font-weight: bold;">Filename</span></p>         </td>
         <td><p>Protocol file name of the current VFD file</p>         </td>
         <td><p>Up to 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>file_size</p>
<p><span style="font-style: italic;font-weight: bold;">File size</span></p>         </td>
         <td><p>Size in bytes of the current VFD file</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>local_ident</p>
<p><span style="font-style: italic;font-weight: bold;">Local ident</span></p>         </td>
         <td><p>Local transfer identifier of the current VFD file</p>         </td>
         <td><p>Integer (automatically assigned by Gateway)</p>         </td>
      </tr>
      <tr>
         <td><p>originator</p>
<p><span style="font-style: italic;font-weight: bold;">Originator</span></p>         </td>
         <td><p>Originator protocol identifier of the current VFD file</p>         </td>
         <td><p>Up to 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>param1</p>
<p><span style="font-style: italic;font-weight: bold;">Param 1</span></p>         </td>
         <td><p>User parameter 1</p>         </td>
         <td><p>Up to 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>param2</p>
<p><span style="font-style: italic;font-weight: bold;">Param 2</span></p>         </td>
         <td><p>User parameter 2</p>         </td>
         <td><p>Up to 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>permanent</p>
<p><span style="font-style: italic;font-weight: bold;">Permanent</span></p>         </td>
         <td><p>Transfer Request permanent flag indicating whether the current VFD file is permanent or not</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>protocol</p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>Protocol (restricted to FTP, SFTP and HTTP)</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">HTTP</span> = HyperText Transfer Protocol</li>
<li><span style="font-weight: bold;">FTP</span> = File Transfer Protocol</li>
<li><span style="font-weight: bold;">SFTP</span> = SSH File Transfer Protocol</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>remote_agent</p>
<p><span style="font-style: italic;font-weight: bold;">Remote agent alias</span></p>         </td>
         <td><p>Remote Site alias associated with the current VFD file</p>         </td>
         <td><p>Up to 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>route_from_xfer</p>
<p><span style="font-style: italic;font-weight: bold;">Route from</span></p>         </td>
         <td><p>Request Local identifier used to route the Transfer related to the current VFD file</p>         </td>
         <td><p>Automatically assigned by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>route_state</p>
<p>Route state</p>         </td>
         <td><p>Store-and-forward state of the current VFD file</p>         </td>
         <td><p>Automatically assigned by Gateway. One of the following values:</p>
<ul>
<li>undefined</li>
<li>TO_ROUTE</li>
<li>ROUTED</li>
<li>FAILED</li>
<li>ACKNOWLEDGED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>route_to_xfer</p>
<p><span style="font-style: italic;font-weight: bold;">Route to</span></p>         </td>
         <td><p>Routed Transfer request identifier related to the current VFD file</p>         </td>
         <td><p>Automatically assigned by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>
<p><span style="font-style: italic;font-weight: bold;">State</span></p>         </td>
         <td><p>State of the Transfer Request associated with the current VFD file</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = <span style="font-weight: bold;">F</span>rozen</li>
<li><span style="font-weight: bold;">D</span> = <span style="font-weight: bold;">D</span>elayed</li>
<li><span style="font-weight: bold;">B</span> = To_<span style="font-weight: bold;">B</span>egin</li>
<li><span style="font-weight: bold;">P</span> = <span style="font-weight: bold;">P</span>rocessing</li>
<li><span style="font-weight: bold;">R</span> = To_<span style="font-weight: bold;">R</span>estart</li>
<li><span style="font-weight: bold;">S</span> = <span style="font-weight: bold;">S</span>uspended</li>
<li><span style="font-weight: bold;">E</span> = <span style="font-weight: bold;">E</span>nded</li>
<li><span style="font-weight: bold;">C</span> = <span style="font-weight: bold;">C</span>anceled</li>
<li><span style="font-weight: bold;">I</span> = <span style="font-weight: bold;">I</span>nterrupted</li>
<li><span style="font-weight: bold;">V</span> = ser<span style="font-weight: bold;">V</span>icing</li>
<li><span style="font-weight: bold;">A</span> = <span style="font-weight: bold;">A</span>cked (OFTP, PeSIT, FTP)</li>
<li><span style="font-weight: bold;">T</span> = Crea<span style="font-weight: bold;">T</span>ed</li>
<li><span style="font-weight: bold;">Z</span> = Deleted</li>
<li><span style="font-weight: bold;">W</span> = Ended_to_ack</li>
<li><span style="font-weight: bold;">G</span> = To_Si<span style="font-weight: bold;">G</span>n</li>
<li><span style="font-weight: bold;">U</span> = Nacked_<span style="font-weight: bold;">U</span>ser</li>
<li><span style="font-weight: bold;">X</span> = Nacked_<span style="font-weight: bold;">X</span>fer</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>type</p>
<p><span style="font-style: italic;font-weight: bold;">Type</span></p>         </td>
         <td><p>Transfer type of the current VFD file</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>user_msg</p>
<p><span style="font-style: italic;font-weight: bold;">User message</span></p>         </td>
         <td><p>User message associated with the current VFD file</p>         </td>
         <td><p>Up to 254 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>user_state</p>
<p><span style="font-style: italic;font-weight: bold;">User state</span></p>         </td>
         <td><p>User state that the user application assigns to the current VFD file</p>         </td>
         <td><p>Single character - value set in user exits</p>         </td>
      </tr>
      <tr>
         <td><p>vfd_nb_directory_max &lt;new value&gt;</p>         </td>
         <td><p>The maximum number of virtual file directories.</p>
<p><strong>Note:</strong> You must restart Gateway for the new value to be taken into account.</p>         </td>
         <td><p>Integer 1024 - 100 000</p>
<p>(default 8192)</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Overview: Virtual File Directories](../../../../ov_gateway/ov_vfd)

[Working with Virtual File Directories (command line)](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
