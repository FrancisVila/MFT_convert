{
    "title": "Model objects: Parameters List",
    "linkTitle": "Model objects: Parameters List",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

This topic lists the parameters that are available for managing Model objects.

Although a set of suggested values is provided, keep in mind that you can use symbolic variables to specify all values. However, if you use symbolic variables in a Model, Gateway does not substitute these variables when you submit a Transfer Request via the <span class="code" style="font-weight: bold;">peltrans</span> command.

[Using symbolic variables](#Using_symbolic_variables)

[Using User functions](#Using_User_functions)

[Model object parameters](#Model_parameters)

[Additional Model parameters for SWIFTNet](#swiftnet_model_params)

<span id="Using_symbolic_variables"></span>

## Using symbolic variables

To retrieve values specified in the incoming Transfer, use symbolic variables in the <span style="font-weight: bold;">Value</span> field for a given parameter. For example:

destination alias = &(dest\_alias)

Gateway retrieves the <span style="font-weight: bold;">destination alias</span> value from the incoming Transfer and applies it to the outgoing Transfer.

You can also use symbolic variables to retrieve local system time values:

-   &(date)
-   &(time)
-   &(yday)

<span id="Using_User_functions"></span>

## Using User functions

In addition, you can use the [user functions](../../../../managing_events_start_here/defining_decision_rule_conditions#Using_user_functions)<span class="code" style="font-weight: bold;"> substring()</span>, <span class="code" style="font-weight: bold;">substr()</span>, <span class="code" style="font-weight: bold;">sepstring()</span>, <span class="code" style="font-weight: bold;">strrep, lowercase()</span> and <span class="code" style="font-weight: bold;">uppercase()</span>.

<span id="Model_parameters"></span>

## Model object parameters

The following table lists Model object parameters (in alphabetical order) that you can you can use with the <span class="code" style="font-weight: bold;">peladm</span> and <span class="code" style="font-weight: bold;">peldsp</span> commands. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Meaning         </th>
<th class="HeadD-Column1-Header1">Values         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>acknowledgment_option (-ao)</p>
<p>acknowledgement option</p>         </td>
         <td><p>Specifies acknowledgement behavior for this transfer</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">TO_ACK</span> = Awaiting acknowledgement</li>
<li><span style="font-weight: bold;">NOT_TO_ACK</span> = Do not wait for acknowledgement</li>
<li><span style="font-weight: bold;">ACK_UNKNOWN</span> = Unspecified acknowledgement behavior</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>add_map (-am)</p>         </td>
         <td><p><span style="font-style: italic;">For XMS-type Models only</span>, when you set the value of <span class="code" style="font-weight: bold;">-protocol (-pr)</span> to <span style="font-weight: bold;">FROM_GTW</span><span style="font-style: italic;">.</span></p>
<p>Use this parameter to map values to one or more attributes of a properties list. The associated properties list is the list you specify in the <span class="code" style="font-weight: bold;">prop_list_name</span> parameter.</p>
<p>To map each value, use the syntax:</p>
<p>name=value</p>
<p>where:</p>
<ul>
<li><span style="font-style: italic;">name</span>: is the name of one of the attributes of the associated parameters list</li>
<li><span style="font-style: italic;">value</span>: is either a value you specify or a value called from the current transfer attributes via a symbolic variable using the syntax <span style="font-style: italic;">&amp;(attribute_name)</span></li>
</ul>
<p><span style="font-weight: bold;">Example:</span> To apply the value of the <span class="code">-appli</span> attribute of the current transfer to the <span class="code">application</span> attribute of the parameter list, enter:</p>
<p>-add_map "application=&amp;(appli)"</p>         </td>
         <td><p>Associate a name of one or more parameter list attributes with a value. The value can be called from the current transfer values by means of a symbolic variable.</p>
<p>Use the syntax</p>
<ul>
<li>name1=value1</li>
<li>name2=value2</li>
<li>...</li>
<li>nameN=valueN</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>append (-app)</p>
<p><span style="font-style: italic;font-weight: bold;">append</span></p>         </td>
         <td><p>FTP client only</p>
<p>Authorize the addition of data to the end of the file when received on the server.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = append allowed</li>
<li><span style="font-weight: bold;">N</span> = append forbidden</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>appli (-ap)</p>
<p><span style="font-style: italic;font-weight: bold;">application</span></p>         </td>
         <td><p>Application name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>attach_extract_file (-aef)</p>
<p><span style="font-style: italic;font-weight: bold;">attach extract file</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>Use this option to specify whether to attach or extract a file or not.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> if the file is not formatted as an email</li>
<li><span style="font-weight: bold;">N</span> if the file is formatted as an email</li>
<li><span style="font-weight: bold;">U</span> must open the file to determine how to proceed</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>block_size (-bs)</p>
<p><span style="font-style: italic;font-weight: bold;">block size</span></p>         </td>
         <td><p>BULL machines: Block size in bytes</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>User comment</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>compression (-comp)</p>
<p><span style="font-style: italic;font-weight: bold;">compression</span></p>         </td>
         <td><p>Compression type</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> = Undefined</li>
<li><span style="font-weight: bold;">H</span> = Horizontal</li>
<li><span style="font-weight: bold;">V</span> = Vertical</li>
<li><span style="font-weight: bold;">B</span> = Both</li>
<li><span style="font-weight: bold;">Z</span> = Zlib</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>content_type (-dct)</p>
<p>content type</p>         </td>
         <td><p>Optional transfer content information field</p>         </td>
         <td><p>A free text description of the transfer content type</p>         </td>
      </tr>
      <tr>
         <td><p>data_code (-dc)</p>
<p><span style="font-style: italic;font-weight: bold;">data code</span></p>         </td>
         <td><p>Data code</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">B</span> = Binary</li>
<li><span style="font-weight: bold;">A</span> = ASCII</li>
<li><span style="font-weight: bold;">A1</span> = ASCII1</li>
<li><span style="font-weight: bold;">A2</span> = ASCII2</li>
<li><span style="font-weight: bold;">A3</span> = ASCII3</li>
<li><span style="font-weight: bold;">A4</span> = ASCII4</li>
<li><span style="font-weight: bold;">A5</span> = ASCII5</li>
<li><span style="font-weight: bold;">E</span> = EBCDIC</li>
<li><span style="font-weight: bold;">E1</span> = EBCDIC1</li>
<li><span style="font-weight: bold;">E2</span> = EBCDIC2</li>
<li><span style="font-weight: bold;">E3</span> = EBCDIC3</li>
<li><span style="font-weight: bold;">E4</span> = EBCDIC4</li>
<li><span style="font-weight: bold;">E5</span> = EBCDIC5</li>
<li><span style="font-weight: bold;">ISO</span> = ISO</li>
<li><span style="font-weight: bold;">OEMPC</span> = OEMPC</li>
<li><span style="font-weight: bold;">U</span> = Undefined</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>date_to_begin (-dtb)</p>
<p><span style="font-style: italic;font-weight: bold;">date to begin</span></p>         </td>
         <td><p>Start date (requested)</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD</span></p>         </td>
      </tr>
      <tr>
         <td><p>date_to_end (-dte)</p>
<p><span style="font-style: italic;font-weight: bold;">date to end</span></p>         </td>
         <td><p>End date (requested)</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD</span></p>         </td>
      </tr>
      <tr>
         <td><p>delete_map</p>         </td>
         <td><p>Delete one or more mapping</p>         </td>
         <td><ul>
<li>name1</li>
<li>name2</li>
<li>...</li>
<li>nameN</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>dest_alias (-da)</p>
<p>destination alias</p>         </td>
         <td><p>General Model only</p>
<p>Destination Site alias name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>destination (-dest)</p>
<p><span style="font-style: italic;font-weight: bold;">destination</span></p>         </td>
         <td><p>Destination protocol identifier</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>direction (-dir)</p>
<p><span style="font-style: italic;font-weight: bold;">direction</span></p>         </td>
         <td><p>Transfer direction</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">0</span> = Output</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>dir_name (-dn)</p>
<p><span style="font-style: italic;font-weight: bold;">directory name</span></p>         </td>
         <td><p>FTP &amp; HTTP only</p>
<p>Absolute path of the directory that stores the file to be transferred. It can be used in one of the following modes:</p>
<ul>
<li>Initiator mode, in this case it is a directory loaded on the remote system</li>
<li>Responder mode, in this case it is a directory in the VFD device</li>
</ul>         </td>
         <td><p>Maximum: 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>dir_name_alias (-dna)</p>
<p><span style="font-style: italic;font-weight: bold;">dir name alias</span></p>         </td>
         <td><p>FTP and HTTP only</p>
<p>Alias of the VFD directory that stores the file to be transferred.</p>
<p>Only available in Responder mode.</p>         </td>
         <td><p>Maximum: 32 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>dir_type (-dt)</p>
<p><span style="font-style: italic;font-weight: bold;">dir type</span></p>         </td>
         <td><p>FTP only</p>
<p>DIR Transfer types in Initiator / Receiver mode only.</p>
<p>Specifies how to list the directory contents.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">LONG</span>: the LIST command returns a detailed list of directory contents. For example, this option differentiates between files and directories. The LONG format depends on the server and is typically in a UNIX format.</li>
<li><span style="font-weight: bold;">NAMES</span> (default): the NLST command returns a basic list of directory contents. This option does not differentiate between files and directories, and provides no extra information such as the last modification date, the file size, and so on.</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>external_sentinel_ident (-esi)</p>         </td>
         <td><p>Sentinel identifier that the external application passes in batch mode only. This identifier is not stored in the Transfer record.</p>         </td>
         <td><p>Maximum: 250 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>external_sentinel_objectname (-eso)</p>         </td>
         <td><p>Sentinel object name to be passed by external applications. Batch mode only. Not stored in the Transfer record.</p>         </td>
         <td><p>Maximum: 32 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>file_component (-fc)</p>
<p><span style="font-style: italic;font-weight: bold;">file component</span></p>         </td>
         <td><p>Local physical file name</p>         </td>
         <td><p>Maximum: 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>file_label (-fl)</p>
<p><span style="font-style: italic;font-weight: bold;">file label</span></p>         </td>
         <td><p>PeSIT only</p>
<p>Protocol label of the file</p>         </td>
         <td><p>Maximum: 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>file_name (-fn)</p>
<p><span style="font-style: italic;font-weight: bold;">file name</span></p>         </td>
         <td><p>Protocol file name</p>         </td>
         <td><p>Maximum: 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>file_org (-f_org)</p>
<p><span style="font-style: italic;font-weight: bold;">file organization</span></p>         </td>
         <td><p>File organization</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Sequential file</li>
<li><span style="font-weight: bold;">I</span> = Indexed file</li>
<li><span style="font-weight: bold;">R</span> = Relative file</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>file_type (-ft)</p>
<p><span style="font-style: italic;font-weight: bold;">file type</span></p>         </td>
         <td><p>PeSIT only</p>
<p>File type (protocol)</p>         </td>
         <td><p>Maximum: 16 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>frozen_state (-fs)</p>
<p><span style="font-style: italic;font-weight: bold;">frozen state</span></p>         </td>
         <td><p>Create the Request in frozen state</p>         </td>
         <td><p>State <span style="font-weight: bold;">F</span> = Frozen</p>         </td>
      </tr>
      <tr>
         <td><p>ftp_command (-ftpc)</p>
<p><span style="font-style: italic;font-weight: bold;">ftp command</span></p>         </td>
         <td><p>FTP, SFTP &amp; HTTP only</p>
<p><span style="font-weight: bold;">FTP and SFTP</span>: Use to define <span class="code" style="font-weight: bold;">SITE</span> and <span class="code" style="font-weight: bold;">QUOTE</span> commands</p>
<p><span style="font-weight: bold;">HTTP</span>: Use to add CGI parameters to the Transfer Request (format: <span style="font-style: italic;">xfer_param1=value1&amp;xfer_param2 =value2</span>)</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>
<p>For FTP and SFTP, you can overcome the 80 character limitation by <a href="../../../../protocols_about/ftp_about/ftp_initiator_mode#SCRIPT">calling a script</a> that contains a set of FTP commands (<span class="code">SITE</span>, <span class="code">QUOTE</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>generate_xfb_subject (-gxs)</p>
<p><span style="font-style: italic;font-weight: bold;">generate xfb subject</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>Specify whether or not to include specific Gateway parameters in the <span style="font-style: italic;">Subject</span> field.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y<span style="font-weight: normal;"> (yes)</span></li>
<li>N<span style="font-weight: normal;"> (no)</span></li>
<li>U<span style="font-weight: normal;"> (undefined)</span></li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>hist_create_date (-hd)</p>
<p><span style="font-style: italic;font-weight: bold;">hist create date</span></p>         </td>
         <td><p>PeSIT only</p>
<p>PeSIT creation date</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>interval (-int)</p>
<p><span style="font-style: italic;font-weight: bold;">interval</span></p>         </td>
         <td><p>PEL &amp; PeSIT only</p>
<ul>
<li><span style="font-weight: bold;">PEL</span>: interval between two Remote Site polls (LOTS and POLL commands)</li>
<li><span style="font-weight: bold;">PeSIT HS</span>: repetition interval in seconds, in case of selection failure</li>
</ul>         </td>
         <td><p>Value in seconds</p>         </td>
      </tr>
      <tr>
         <td><p>local_agent (-la)</p>
<p><span style="font-style: italic;font-weight: bold;">local agent</span></p>         </td>
         <td><p>Alias of the associated Local Site</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>local_site (-local)</p>
<p><span style="font-style: italic;font-weight: bold;">local Site</span></p>         </td>
         <td><p>PEL, PeSIT &amp; FTP only</p>
<p>Local Site name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>max_file (-m_file)</p>
<p><span style="font-style: italic;font-weight: bold;">max file</span></p>         </td>
         <td><p>PeSIT only</p>
<p>PeSIT HS cyclic selection request only: maximum number of files allowed.</p>         </td>
         <td><p>Decimal value: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32000</span>.<span style="font-weight: bold;"><br />
-1</span> = no imposed limits.</p>         </td>
      </tr>
      <tr>
         <td><p>max_request (-m_req)</p>
<p><span style="font-style: italic;font-weight: bold;">max request</span></p>         </td>
         <td><p>PeSIT only</p>
<p>PeSIT HS cyclic selection request only: maximum number of requests allowed.</p>         </td>
         <td><p>Decimal value: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32000</span>.<span style="font-weight: bold;"><br />
-1</span> = no imposed limits.</p>         </td>
      </tr>
      <tr>
         <td><p>mode (-m)</p>
<p><span style="font-style: italic;font-weight: bold;">mode</span></p>         </td>
         <td><p>Connection mode for the Transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>model (-ml)</p>
<p><span style="font-style: italic;font-weight: bold;">Name</span></p>         </td>
         <td><p>Model name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>nack_action (-nack)</p>
<p><span style="font-style: italic;font-weight: bold;">nack action</span></p>         </td>
         <td><p>PeSIT only</p>
<p>Indicates whether the Remote Site supports the negative EERP extension or not.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>newline_convention (-nlc)</p>
<p><span style="font-style: italic;font-weight: bold;">n</span><span style="font-style: italic;font-weight: bold;">ewline convention</span></p>         </td>
         <td><p>SFTP only</p>
<p>Line feed convention, depending on remote system type.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> / u (UNIX)</li>
<li><span style="font-weight: bold;">W</span> / w (Windows)</li>
<li>empty</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>org_alias (-oa)</p>
<p><span style="font-style: italic;font-weight: bold;">originator alias</span></p>         </td>
         <td><p>General Model only</p>
<p>Originator Site alias name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>originator (-org)</p>
<p><span style="font-style: italic;font-weight: bold;">originator</span></p>         </td>
         <td><p>Originator protocol identifier</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>padding (-pad)</p>
<p><span style="font-style: italic;font-weight: bold;">padding</span></p>         </td>
         <td><p>Padding character code</p>         </td>
         <td><p>Integer between <span style="font-weight: bold;">00</span> and <span style="font-weight: bold;">FF</span> or a symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>param1 (-p1)</p>
<p><span style="font-style: italic;font-weight: bold;">param1</span></p>         </td>
         <td><p>User parameter 1</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>param2 (-p2)</p>
<p><span style="font-style: italic;font-weight: bold;">param2</span></p>         </td>
         <td><p>User parameter 2</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>permanent (-perm)</p>
<p><span style="font-style: italic;font-weight: bold;">permanent</span></p>         </td>
         <td><p>Transfer Request permanent flag</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>priority (-prio)</p>
<p><span style="font-style: italic;font-weight: bold;">priority</span></p>         </td>
         <td><p>Transfer priority</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">0</span> = High priority</li>
<li><span style="font-weight: bold;">1</span> = Medium priority</li>
<li><span style="font-weight: bold;">2</span> = Low priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>prop_list_name (-pln)</p>         </td>
         <td><p>XMS-type Models only</p>
<p>Property List Name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>property (-prop)</p>
<p>jms property</p>         </td>
         <td><p>JMS only</p>
<p>JMS property</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>protocol (-pr)</p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>Protocol Name</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">GENERAL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>POP3</li>
<li>TO_GTW<span style="font-weight: normal;"> (</span><span style="font-style: italic;font-weight: normal;">For XMS-type Models only)</span></li>
<li>FROM_GTW<span style="font-weight: normal;"> (</span><span style="font-style: italic;font-weight: normal;">For XMS-type Models only)</span></li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>SWIFTNET</li>
<li>JMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>purge_option (-po)</p>
<p><span style="font-style: italic;font-weight: bold;">purge option</span></p>         </td>
         <td><p>Enable purge of Transfer Requests from Mailbox using the <span class="code" style="font-weight: bold;">pelpur</span> command.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>rcv_appli (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">rcv appli</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Receiver Application name.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_text (-rt)</p>
<p><span style="font-style: italic;font-weight: bold;">rcv text</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Receiver free text.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_user (-ru)</p>
<p><span style="font-style: italic;font-weight: bold;">rcv user</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Receiver user name.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rec_fmt (-rf)</p>
<p><span style="font-style: italic;font-weight: bold;">rec format</span></p>         </td>
         <td><p>Record format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed</li>
<li><span style="font-weight: bold;">FT</span> = Fixed Text</li>
<li><span style="font-weight: bold;">V</span> = Variable</li>
<li><span style="font-weight: bold;">VT</span> = Variable Text</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>rec_len (-rl)</p>
<p><span style="font-style: italic;font-weight: bold;">rec length</span></p>         </td>
         <td><p>Record length</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32768</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">receipt_nack_msg (-rnm)</span></p>
<p>receipt nack msg</p>         </td>
         <td><p><span style="font-style: italic;">EDIINT only</span></p>
<p>Gateway operating in Responder mode on receipt of a transfer.</p>
<p>Optionally, enter a text explaining a warning or error receipt.</p>         </td>
         <td><p>Maximum: 512 characters</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_reply_to_xfer (-rrtx)</p>
<p>receipt reply to xfer</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Gateway operating in Responder mode on receipt of a transfer.</p>
<p>Use this parameter to activate the generation of a receipt on reception of a transfer.</p>         </td>
         <td><p>The number of the transfer for which you want to generate and send a return receipt.</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_request (-rr)</p>
<p>receipt request</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Specify whether or not you want to receive a receipt for the reception of a file you send.</p>
<p>If you choose to receive a receipt, specify whether the receipt is signed or unsigned.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">none</span> = no receipt requested (default)</li>
<li><span style="font-weight: bold;">signed</span> = request signed receipt</li>
<li><span style="font-weight: bold;">unsigned</span> = request unsigned receipt (<span style="font-style: italic;">EDIINT only</span>)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>receipt_request_to (-rrto)</p>
<p>receipt request to</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>EDIINT: URL or email address to which the acknowledgement is sent.</p>
<p>SWIFTNet: Name of the receipt reception address. This is the address to which the receiving partner sends the receipt.</p>         </td>
         <td><p>The URL, email address or DN to which you want the transfer receipt to be sent.</p>
<p>Maximum: 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_request_sync (-rrs)</p>
<p>receipt request sync</p>         </td>
         <td><p>EDIINT only</p>
<p>Synchronize sending of receipts.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">receipt_type (-rt)</span></p>
<p>receipt type</p>         </td>
         <td><p><span style="font-style: italic;">EDIINT only</span></p>
<p>Gateway operating in Responder mode on receipt of a transfer.</p>
<p>Specify the type of receipt to return to the initiator of the received transfer.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>SUCCESS</li>
<li>ERROR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>remote_agent (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">remote agent</span></p>         </td>
         <td><p>General Model only</p>
<p>Alias of the associated Remote Site.</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>reply_to_xfer (-rtx)</p>
<p><span style="font-style: italic;font-weight: bold;">reply to xfer</span></p>         </td>
         <td><p>Local identifier of the Transfer Request to which the response must be sent.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>request_method (-rm)</p>
<p><span style="font-style: italic;font-weight: bold;">request method</span></p>         </td>
         <td><p>HTTP only</p>
<p>HTTP method to use during transfer.</p>         </td>
         <td><ul>
<li>GET or POST for incoming transfers</li>
<li>POST or PUT for outgoing transfers</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>retry_count_max (-rc_max)</p>
<p><span style="font-style: italic;font-weight: bold;">retry count max</span></p>         </td>
         <td><p>Maximum number of connection retries.</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">999</span></p>         </td>
      </tr>
      <tr>
         <td><p>smtp_bcc (-bcc)</p>
<p><span style="font-style: italic;font-weight: bold;">smtp bcc</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>Blind carbon copy addresses.</p>         </td>
         <td><p>No max limit</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_cc (-cc)</p>
<p><span style="font-style: italic;font-weight: bold;">smtp cc</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>Carbon copy addresses.</p>         </td>
         <td><p>No max limit</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_from (-from)</p>
<p><span style="font-style: italic;font-weight: bold;">smtp from</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>From address.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_subject (-subject)</p>
<p><span style="font-style: italic;font-weight: bold;">smtp subject</span></p>         </td>
         <td><p>SMTP &amp; POP3, AS2 &amp; AS3 only</p>
<p>Email subject.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to (-to)</p>
<p><span style="font-style: italic;font-weight: bold;">smtp to</span></p>         </td>
         <td><p>SMTP &amp; POP3 only</p>
<p>Destination addresses.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>snd_appli (-sa)</p>
<p><span style="font-style: italic;font-weight: bold;">snd appli</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Sender Application name.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>snd_msg (-sm)</p>
<p><span style="font-style: italic;font-weight: bold;">snd msg</span></p>         </td>
         <td><p>User message to send</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">OFTP</span>: User message to be transmitted at OFTP connection phase (maximum: 8 alphanumeric characters)</li>
<li><span style="font-weight: bold;">FTP</span>: List of special commands to send to remote server using <span class="code" style="font-weight: bold;">SITE</span> or <span class="code" style="font-weight: bold;">QUOTE</span> FTP command</li>
<li><span style="font-weight: bold;">PeSIT</span>: User message to be transmitted at the connection phase (maximum: 254 alphanumeric characters)</li>
<li><span style="font-weight: bold;">HTTP</span>: User message is used to add CGI parameters to Transfer Requests, formatted as follows: <span style="font-style: italic;">xfer_param1=value1 &amp; xfer_param2=value2</span></li>
<li><span style="font-weight: bold;">SWIFTNet</span>: Refer to <a href="#swiftnet_model_params">Additional Model parameters for SWIFTNet</a>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>snd_text (-st)</p>
<p><span style="font-style: italic;font-weight: bold;">snd text</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Sender free text.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>snd_user (-su)</p>
<p><span style="font-style: italic;font-weight: bold;">snd user</span></p>         </td>
         <td><p>PeSIT HS E, Store-and-Forward only</p>
<p>Sender user name.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>sys_dep (-sd)</p>
<p><span style="font-style: italic;font-weight: bold;">sys dep</span></p>         </td>
         <td><p>For BULL, AS400, GCOS and TANDEM machines: File type is system-dependent.</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>text_file</p>
<p><span style="font-style: italic;font-weight: bold;">text file</span></p>         </td>
         <td><p>Text file flag</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>tpm_dea_id (-tpmdea)</p>
<p>tpm dea id</p>         </td>
         <td><p>EDIINT only</p>
<p>PassPort (TPM) Document Exchange Address identifier.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>trade_ack_req (-tradear)</p>         </td>
         <td><p>EDIINT only</p>
<p>Acknowledgement required when sending a file to a partner.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">undef</span> (default)</li>
<li>none</li>
<li>signed</li>
<li>unsigned</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_ack_sync (-tradeas)</p>         </td>
         <td><p>EDIINT only</p>
<p>Synchronize acknowledgement.</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>trade_compress (-tradecomp)</p>
<p>trade compress</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Compression algorithm for use when sending a file to a partner.</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>trade_dest (-traded)</p>
<p>trade destination</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>The name of the destination partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>trade_dest_alias (-tradeda)</p>
<p>trade destination alias</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Alias of the destination partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>trade_encrypt (-tradee)</p>
<p>trade encrypt</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Encryption algorithm for use when sending a file to a partner.</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>trade_file_already_encoded (-tradefae)</p>
<p>trade file encoded</p>         </td>
         <td><p>EDIINT only</p>
<p>The use of this parameter is not recommended for transfer deposits.</p>
<p>Use this parameter when creating a Model to be applied on Decision Rule routing via EDIINT.</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>trade_format (-tradef)</p>
<p>trade format</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Indicate protocol version.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>SWIFTNet</li>
<li>RN</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_org (-tradeo)</p>
<p>trade originator</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>The name of the originating partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>trade_org_alias(-tradeoa)</p>
<p>trade originator alias</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Alias of the originating partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>trade_sign (-trades)</p>
<p>trade sign</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Certificate signing algorithm used when sending a file to a partner.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>truncating_allowed (-ta)</p>
<p><span style="font-style: italic;font-weight: bold;">truncating allowed</span></p>         </td>
         <td><p>If the transfer uses the truncating feature, this option allows you to truncate a record without taking into account the padding character.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>type (-ty)</p>
<p><span style="font-style: italic;font-weight: bold;">type</span></p>         </td>
         <td><p>Transfer type</p>         </td>
         <td><p>One of:</p>
<ul>
<li>DIR</li>
<li>TRANS</li>
<li>LOTS</li>
<li>POLL</li>
<li>LIST</li>
<li>EERP</li>
<li>SELECT</li>
<li>RECEIPT</li>
<li>MSG</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>unique_filename (-uf)</p>
<p><span style="font-style: italic;font-weight: bold;">unique filename</span></p>         </td>
         <td><p>FTP only</p>
<p>FTP store unique option</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>update_map (-um)</p>         </td>
         <td><p>Update one or more mappings</p>         </td>
         <td><ul>
<li>name1=value1</li>
<li>name2=value2</li>
<li>nameN=valueN</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_data_code (-xdc)</p>
<p><span style="font-style: italic;font-weight: bold;">xfer data code</span></p>         </td>
         <td><p>Transferred data code</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">B</span> = Binary</li>
<li><span style="font-weight: bold;">A</span> = ASCII</li>
<li><span style="font-weight: bold;">A1</span> = ASCII1</li>
<li><span style="font-weight: bold;">A2</span> = ASCII2</li>
<li><span style="font-weight: bold;">A3</span> = ASCII3</li>
<li><span style="font-weight: bold;">A4</span> = ASCII4</li>
<li><span style="font-weight: bold;">A5</span> = ASCII5</li>
<li><span style="font-weight: bold;">E</span> = EBCDIC</li>
<li><span style="font-weight: bold;">E1</span> = EBCDIC1</li>
<li><span style="font-weight: bold;">E2</span> = EBCDIC2</li>
<li><span style="font-weight: bold;">E3</span> = EBCDIC3</li>
<li><span style="font-weight: bold;">E4</span> = EBCDIC4</li>
<li><span style="font-weight: bold;">E5</span> = EBCDIC5</li>
<li><span style="font-weight: bold;">ISO</span> = ISO</li>
<li><span style="font-weight: bold;">OEMPC</span> = OEMPC</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_rec_fmt (-xrf)</p>
<p><span style="font-style: italic;font-weight: bold;">xfer rec format</span></p>         </td>
         <td><p>Transfer format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed</li>
<li><span style="font-weight: bold;">V</span> = Variable</li>
<li><span style="font-weight: bold;">T</span> = Text (<span style="font-style: italic;">OFTP only</span>)</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_rec_len (-xrl)</p>
<p><span style="font-style: italic;font-weight: bold;">xfer rec length</span></p>         </td>
         <td><p>Transfer record length</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32768</span></p>         </td>
      </tr>
      <tr>
         <td><p>mail_xpriority<br />
(-mailxprio)</p>         </td>
         <td><p>SMTP protocol only (with or without S/MIME) - the value for X-Priority mail header (SEPAmail standard)</p>         </td>
         <td><p>Integer, between <span style="font-weight: bold;">1</span> and <span style="font-weight: bold;">5</span></p>         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">sigalgo(-sga) </span>         </td>
         <td>Signature and hash algorithm used in payload
signature computation. Considered only when <span class="code">payload_integrity_option </span>is set to <span class="code">yes</span>. See <a href="../../../../../gateway_securityguide/managing_security_start_here/payloadsecurity/opensslexample" class="MCXref xref">Working with Payload integrity</a>         </td>
         <td>SHA256withRSA         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">sigfile(-sgf) </span>         </td>
         <td>File containing payload signature, in binary format. Considered only when <span class="code"><span class="code">payload_integrity_option </span></span>is set to <span class="code"><span class="code">yes</span></span>.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

<span id="swiftnet_model_params"></span>

## Additional Model parameters for SWIFTNet

The following table lists <span class="code" style="font-weight: bold;">peladm</span> and <span class="code" style="font-weight: bold;">peldsp</span> command parameters that are specific to SWIFTNet transfers. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Meaning         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-payload_type (-pto)</p>
<p>sw payload type</p>         </td>
         <td><p>InterAct only</p>
<p>SWIFTNet Interact payload format.</p>
<p>On the <span style="font-style: italic;">Initiator</span> side, you can use this parameter to overwrite the <span style="font-weight: bold;">Payload type</span> parameter defined in the Trading Partner.</p>
<p>On the <span style="font-style: italic;">Responder</span> side, when using the <span style="font-weight: bold;">Receipt request synchronized</span> option you can respond with a custom payload type. Even if you saved the request payload as embedded in the Trading Partner, you can answer back with text mode.</p>         </td>
         <td><ul>
<li>(empty) = undefined</li>
<li>text</li>
<li>embedded</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-rcv_msg</p>
<p>rcv msg</p>         </td>
         <td><p><span style="font-style: italic;">FileAct only</span></p>
<p><span style="font-weight: bold;">[0 - 255]</span>: File description, supplied by the sender. Free-text description of the file.</p>
<p><span style="font-weight: bold;">[256 - 511]</span>: File information, supplied by the sender. Structured information concerning the transfer. For more details, refer to the SWIFT documentation.</p>         </td>
         <td><p>Maximum: 256 + 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>
<p>snd msg</p>         </td>
         <td><p><span style="font-weight: bold;">FileAct</span> [0 - 255]: Transfer description, supplied by the initiator. Free-text description of the transfer.</p>
<p><span style="font-weight: bold;">FileAct</span> [256 - 511]: Transfer information, supplied by the initiator. Structured information concerning the transfer. For more details, refer to the SWIFT documentation.</p>
<p><span style="font-weight: bold;">InterAct</span> [0 - 511]: User message.</p>         </td>
         <td><p><span style="font-weight: bold;">FileAct:</span> Maximum 256 + 256 alphanumeric characters</p>
<p><span style="font-weight: bold;">InterAct:</span> Maximum 511 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-sw_add_params (-swaddpar)</p>
<p>sw add params</p>         </td>
         <td><p>Reference to file on disk containing additional SWIFTNet structures (for example, Header Info and/or Signature List). This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info#XML_File_structure">specific structure</a>.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-sw_auth_indicator (-ai)</p>
<p>sw auth indicator</p>         </td>
         <td><p>SWIFTNet Authorization notification indicator.</p>
<p>Select this option to receive Authorization system messages for files or messages sent over <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">Y-copy services</a>.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sw_copy_indicator (-ci)</p>
<p>sw copy indicator</p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">copy of the file or message</a> to be sent to a third party defined at the service level.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sw_message_id (-swmsgid)</p>
<p>swift message id</p>         </td>
         <td><p>The value of this parameter overwrites the message id created by Gateway in the Transfer Request.</p>
<p>Enter the SWIFTNet message id of the new transfer. This should be a Universal Unique IDentifier (UUID).</p>
<p>If the transfer is a Possible Duplicate, enter the message id of the initial transfer.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-sw_overdue_time (-swot)</p>
<p>sw overdue time</p>         </td>
         <td><p>SWIFTNet <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_overdue">OverdueTime</a></p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_pd_indication (-swpdind)</span></p>
<p>possible duplicate</p>         </td>
         <td><p>Possible Duplicate indicator.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes. Select this value to indicate to the responder that the transfer is a Possible Duplicate.</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_delivery_mode (-tradedmo)</p>
<p>trade delivery mode</p>         </td>
         <td><p>The delivery mode of the file or message.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">RT</span> = Real time (immediate)</li>
<li><span class="code" style="font-weight: bold;">SNF</span> = Store-and-Forward (send and then store in the queue in the SWIFTNet domain)</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_encrypt_dn (-tradeendn)</p>
<p>trade encrypt dn</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for encryption in Initiator mode.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_non_repudiation (-tradenr)</p>
<p>trade non repudiation</p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>Y</li>
<li>N</li>
<li>Symbolic variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_notif_queue (-tradenq)</p>
<p>trade notif queue</p>         </td>
         <td><p>Store-and-Forward mode only</p>
<p>Reception queue for Store-and-Forward delivery notifications.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_receipt_request_type (-traderrt)</p>
<p>trade receipt request type</p>         </td>
         <td><p>Type of acknowledgement request.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_request_type (-traderqt)</p>
<p>trade request type</p>         </td>
         <td><p>Type of request (as specified in the XML header).</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_service (-tradesc)</p>
<p>trade service</p>         </td>
         <td><p>SWIFT business service name (as specified in the XML header).</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign_dn (-tradesidn)</p>
<p>trade sign dn</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for signing in Initiator mode. Otherwise the securityDN (supplied by SNL) is used</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Models (command line)](../working_with_models_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
