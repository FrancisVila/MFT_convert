{
    "title": "Transfers: Parameters List ",
    "linkTitle": "Transfers: Parameters List",
    "weight": "200"
}<a href="#General_transfer_parameters" class="selected">General parameters for creating and updating transfers</a>

<a href="#oftp_transfer_parameters" class="selected">Additional Transfer Request parameters for OFTP</a>

<a href="#SWIFTNet_transfer_parameters" class="selected">Additional Transfer Request parameters for SWIFTNet</a>

<a href="#x400_transfer_parameters" class="selected">Additional Transfer Request parameters for X.400</a>

<a href="#Diffusion_List_transfer_parameters" class="selected">Additional Transfer Request parameters for Diffusion Lists</a>

<a href="#pelpur_parameters" class="selected">Purging Transfers: <code>pelpur</code> command parameters</a>

<a href="#peldsp_parameters" class="selected">Displaying Transfers: <code>peldsp</code> command parameters</a>

<span id="General_transfer_parameters"></span>

## General parameters for creating and updating transfers

The following table contains parameters you can use with the `peltrans` and/or the `peladm update_trans` commands. The corresponding field name in the Gateway GUI is displayed in **italics**.

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
         <td><p>-acknowledgment_option (-ao)</p>
<p><span style="font-style: italic;font-weight: bold;">Ack option</span></p>         </td>
         <td><p>OFTP, PeSIT, SMTP and SWIFTNet only</p>
<p>Specify acknowledgement behavior for this Transfer.</p>
<p>For SMTP, refer to <a href="../../../../protocols_about/smtp_pop3_about/smtp_config#Requesting_an_acknowledgement">Configuring SMTP: Requesting an acknowledgement</a>.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">TO_ACK</span> = Wait for acknowledgement</li>
<li><span style="font-weight: bold;">NOT_TO_ACK</span> = Do not wait for acknowledgement</li>
<li><span style="font-weight: bold;">ACK_UNKNOWN</span> = Unspecified acknowledgement behavior</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-append (-app)</p>
<p><span style="font-style: italic;font-weight: bold;">Append option</span></p>         </td>
         <td><p>FTP client mode only</p>
<p>Option that allows you to add data to the end of an existing file</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = append allowed</li>
<li><span style="font-weight: bold;">N</span> = append forbidden (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-appli (-ap)</p>
<p><span style="font-style: italic;font-weight: bold;">Application</span></p>         </td>
         <td><p>Application name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-attach_extract_file (-aef)</p>
<p><span style="font-style: italic;font-weight: bold;">Attach file</span></p>         </td>
         <td><p>SMTP only</p>
<p>Define whether to create and attach a file or not.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span></li>
<li><span style="font-weight: bold;">N</span></li>
<li><span style="font-weight: bold;">U</span>ndefined (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-block_size (-bs)</p>
<p>(None)</p>         </td>
         <td><p>For BULL machines and AS400: Block size in bytes</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-compression (-comp)</p>
<p><span style="font-style: italic;font-weight: bold;">Compression</span></p>         </td>
         <td><p>Compression type</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> = Undefined (default)</li>
<li><span style="font-weight: bold;">H</span> = Horizontal</li>
<li><span style="font-weight: bold;">V</span> = Vertical</li>
<li><span style="font-weight: bold;">B</span> = Both</li>
<li><span style="font-weight: bold;">Z</span> = Zlib (<span style="font-style: italic;">PeSIT only</span>)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-content_type (-dct)</p>         </td>
         <td><p>Optional transfer content information</p>         </td>
         <td><p>Free text description of the transfer content type.</p>
<p>For example, you may choose to enter one of the following content types:</p>
<ul>
<li>application/EDI-X12</li>
<li>application/EDIFACT</li>
<li>application/XML</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-data_code (-dc)</p>
<p><span style="font-style: italic;font-weight: bold;">Data code</span></p>         </td>
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
</ul>         </td>
      </tr>
      <tr>
         <td><p>-date_to_begin (-dtb)</p>
<p><span style="font-style: italic;font-weight: bold;">Earliest start date</span></p>         </td>
         <td><p>Date to begin Transfer (requested)</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-date_to_end (-dte)</p>
<p><span style="font-style: italic;font-weight: bold;">Latest start date</span></p>         </td>
         <td><p>Date to end Transfer (requested)</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-destination_address (-addr)</p>         </td>
         <td><p>Remote Site destination address to use together with the <span class="code">username</span> and <span class="code">password</span> parameters to create a temporary destination site for a transfer. Use these parameters in place of the association of a destination Site object.</p>         </td>
         <td><p>The remote destination address for a transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>
<p><span style="font-style: italic;font-weight: bold;">Destination alias</span></p>         </td>
         <td><p>Destination Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-destination (-dest)</p>
<p><span style="font-style: italic;font-weight: bold;">Destination</span></p>         </td>
         <td><p>Destination protocol identifier</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_name (-dn)</p>
<p><span style="font-style: italic;font-weight: bold;">Directory name</span></p>         </td>
         <td><p>HTTP, FTP &amp; SFTP only</p>
<p>Absolute path of the directory that contains the file to transfer. The directory depends on the mode:</p>
<ul>
<li>Initiator mode: a directory on the remote system</li>
<li>Responder mode: a directory in the VFD</li>
</ul>
<p>If the Transfer mode is DIR, specify the name of the directory whose contents you want to list.</p>         </td>
         <td><p>Maximum: 127 alphanumeric characters</p>
<p>FTP <span style="font-weight: bold;">DIR</span> Transfer type: make sure you add the separator character<span class="code" style="font-weight: bold;"> /</span> at the end of the directory name.</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_name_alias (-dna)</p>
<p><span style="font-style: italic;font-weight: bold;">Directory alias</span></p>         </td>
         <td><p>HTTP, FTP &amp; SFTP only</p>
<p>Only available when submitting a Transfer Request in Responder mode: Alias of the VFD directory that contains the file to transfer</p>         </td>
         <td><p>Maximum: 32 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_type (-dt)</p>
<p><span style="font-style: italic;font-weight: bold;">Directory listing type</span></p>         </td>
         <td><p>FTP only</p>
<p>This parameter is only significant for DIR type Transfers in Initiator/ Receiver mode. This parameter defines the level of detail in the directory listing.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">NAMES</span>: (default) sends an NLST command that returns a list of file and directory names.</li>
<li><span style="font-weight: bold;">LONG</span>: sends a LIST command that returns more detailed information on each element.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>
<p><span style="font-style: italic;font-weight: bold;">Direction</span></p>         </td>
         <td><p>Transfer direction</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = In</li>
<li><span style="font-weight: bold;">O</span> = Out</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-external_sentinel_ident (-esi)</p>
<p>(None)</p>         </td>
         <td><p>Sentinel identifier that the external application passes in batch mode only. This identifier is not stored in the Transfer record.</p>         </td>
         <td><p>Maximum: 250 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-external_sentinel_objectname (-eso)</p>
<p>(None)</p>         </td>
         <td><p>Sentinel object name to be passed by external applications. Batch mode only. Not stored in the Transfer record.</p>         </td>
         <td><p>Maximum: 32 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_component (-fc)</p>
<p><span style="font-style: italic;font-weight: bold;">File component</span></p>         </td>
         <td><p>Local file name</p>         </td>
         <td><p>Maximum: 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_label (-fl)</p>
<p><span style="font-style: italic;font-weight: bold;">File label</span></p>         </td>
         <td><p>PeSIT HS only</p>
<p>Protocol label of the file</p>         </td>
         <td><p>PeSIT PI 37</p>
<p>Maximum: 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>
<p><span style="font-style: italic;font-weight: bold;">File Name</span></p>         </td>
         <td><p>Protocol file name</p>
<p>For FTP and HTTP DIR type Transfers, this parameter defines a filter on the file names that the server returns.</p>
<p>For example: <span class="code" style="font-weight: bold;">*.txt</span> returns all <span class="code">.txt</span> files in the directory that you specify.</p>         </td>
         <td><p>Maximum: 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_org (-f_org)</p>
<p><span style="font-style: italic;font-weight: bold;">Organization</span></p>         </td>
         <td><p>File organization</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Sequential file (default)</li>
<li><span style="font-weight: bold;">I</span> = Indexed file</li>
<li><span style="font-weight: bold;">R</span> = Relative file</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-file_type (-ft)</p>
<p><span style="font-style: italic;font-weight: bold;">File type</span></p>         </td>
         <td><p>PeSIT HS only</p>
<p>File type</p>         </td>
         <td><p>Maximum: 16 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-frozen_state (-fs)</p>
<p><span style="font-style: italic;font-weight: bold;">Frozen state</span></p>         </td>
         <td><p>Create the Transfer in frozen state</p>         </td>
         <td><p>Parameter without a value</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_ftp_command"></span>-ftp_command (-ftpc)</p>
<p>HTTP CGI parameters/<br />
FTP user command</p>         </td>
         <td><p>FTP, SFTP, HTTP and SWIFTNet InterAct only</p>
<ul>
<li>FTP: Send a special remote command or an unsupported command to the FTP server before or after the Transfer. <span class="code">SITE</span> and <span class="code">QUOTE</span> commands are supported.</li>
<li>SFTP: Send commands to remote server using <span class="code">QUOTE</span> or <span class="code">SITE</span> command</li>
<li>HTTP: Add CGI parameters to the Transfer Request</li>
<li>SWIFTNet InterAct: Specify payload attributes or compression information</li>
</ul>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>
<p><strong>FTP and SFTP:</strong></p>
<p>Enter the command in the following format:</p>
<p>"SITE &lt;fct1&gt; &lt;param1&gt;; SITE &lt;fct2&gt; &lt;param2&gt;"</p>
<p>You can overcome the 80 character limitation by <a href="../../../../protocols_about/ftp_about/ftp_initiator_mode#SCRIPT">calling a script</a> that contains a set of FTP commands (<span class="code">SITE</span>, <span class="code">QUOTE</span>).</p>
<p><strong>HTTP:</strong></p>
<p>Enter CGI parameters in the following format:</p>
<p>xfer_param1=value1&amp;xfer_param2=value2</p>
<p><strong>SWIFTNet InterAct:</strong></p>
<p>Enter either:</p>
<ul>
<li>payload attributes in the following format:<br />
<span class="code">attrib1=\"value1\"</span></li>
<li>compression information in the following format:<br />
<span class="code">dt=\"GZIP-Base64\"</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-generate_xfb_subject (-gxs)</p>
<p><span style="font-style: italic;font-weight: bold;">Add Gateway parameters to subject</span></p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Set this option to <span style="font-weight: bold;">Yes</span> to add the following Gateway-specific parameters to the email subject:</p>
<ul>
<li>destination (<span class="code">-dest</span>)</li>
<li>origin (<span class="code">-org</span>)</li>
<li>protocol file name (<span class="code">-file_name</span>)</li>
<li>application (<span class="code">-appli</span>)</li>
</ul>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">N</span></li>
<li><span style="font-weight: bold;">Y</span></li>
<li><span style="font-weight: bold;">U</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-hist_create_date (-hd)</p>
<p>(None)</p>         </td>
         <td><p>PeSIT creation date</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-interactive (-i)</p>
<p>(None)</p>         </td>
         <td><p>Wait for the end of the Transfer Request before starting a new one</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-interval (-int)</p>
<p><span style="font-style: italic;font-weight: bold;">Interval</span></p>         </td>
         <td><p>Retry interval</p>
<ul>
<li>PEL: interval between two Remote Site polls (LOTS and POLL commands)</li>
<li>PeSIT HS: cyclic selection request only: repetition time interval in seconds, in case of selection failure</li>
</ul>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-keep_offset (-ko)</p>         </td>
         <td><p>Indicative value for indexing on the remote machine</p>         </td>
         <td><p>PeSIT PI 39</p>         </td>
      </tr>
      <tr>
         <td><p>-key_len (-kl)</p>         </td>
         <td><p>Indicative value for indexing on the remote machine</p>         </td>
         <td><p>PeSIT PI 38</p>         </td>
      </tr>
      <tr>
         <td><p>-local_agent (-la)</p>
<p><span style="font-style: italic;font-weight: bold;">Local agent alias</span></p>         </td>
         <td><p>Alias of the associated Local Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-max_file (-m_file)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum number of files</span></p>         </td>
         <td><p>PeSIT HS cyclic selection request only</p>
<p>Maximum number of files allowed</p>         </td>
         <td><p>Decimal value: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32000</span>.<br />
<span style="font-weight: bold;">1</span> = no imposed limits.</p>         </td>
      </tr>
      <tr>
         <td><p>-max_request (-m_req)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum number of requests</span></p>         </td>
         <td><p><span style="font-style: italic;">PeSIT HS cyclic selection</span> request only</p>
<p>Maximum number of requests allowed</p>         </td>
         <td><p>Decimal value: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32000</span>.<br />
<span style="font-weight: bold;">1</span> = no imposed limits.</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>
<p><span style="font-style: italic;font-weight: bold;">Mode</span></p>         </td>
         <td><p>Connection mode for the Transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-model (-ml)</p>
<p><span style="font-style: italic;font-weight: bold;">Model name</span></p>         </td>
         <td><p>Model used to submit the Transfer Request</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-multi_filter (-muf)</p>
<p>Filter</p>         </td>
         <td><p>FTP and SFTP multiple transfers only</p>
<p>Specify the filtering criteria to select files to send or receive.</p>
<p>You can filter according to:</p>
<ul>
<li>Time</li>
<li>File size</li>
<li>File name</li>
</ul>         </td>
         <td><p><span style="font-weight: bold;">Time</span></p>
<p>time = [ last | rounded ] N [ day[s] hour[s] | minute[s] ]</p>
<p>[ yyyymmdd &lt;= ] time [ &lt;= yyyymmddss ]</p>
<p>[ yyyymmddhhmmss &lt;= ] time [ &lt;= yyyymmddhhmmss ]</p>
<p>For example, if it is currently 2010/06/13 17:15:28, then:</p>
<ul>
<li>last1day = 2010/06/12 17:15:28</li>
<li>rounded1day = 2010/06/13 00:00:00</li>
<li>last3days = 2010/06/10 17:15:28</li>
<li>rounded3days = 2010/06/11 00:00:00</li>
<li>last1hours = 2010/06/12 16:15:28</li>
<li>rounded1hours = 2010/06/12 17:00:00</li>
</ul>
<p><span style="font-weight: bold;">File size</span></p>
<p>[ min &lt; ] size [ &lt; max ]</p>
<p><strong>File name</strong></p>
<p><span class="code">name = regexp (use StringMatch)</span></p>
<p><strong>Note:</strong> all the spaces that comes after "<span class="code">name =</span>" are treated as part of the file name. To search for a file that starts with <span class="code">file </span>, you should use :<br />
<span class="code">name =file*</span></p>
<p><strong>Example:</strong></p>
<p><code>-muf "20100528 &lt;= time &lt;= 20100609 ; 1 &lt; size &lt; 100000 ; name =*.dat"</code></p>         </td>
      </tr>
      <tr>
         <td><p>-multi_hash_type (-muh)</p>
<p>Hash type</p>         </td>
         <td><p><span style="font-style: italic;">FTP and SFTP multiple transfers only</span></p>
<p>Specify the type of hashing to use.</p>
<p>This parameter determines whether all files in a directory will be transferred a second time or only those files that have changed since the initial transfer. This is useful if a transfer has been interrupted or only updated files need to be sent.</p>         </td>
         <td><p>One of:</p>
<p><span style="font-weight: bold;">0</span>: No hash. No check of duplicate file transfers is made. All files are transferred again.</p>
<p><span style="font-weight: bold;">1</span>: (default) Gateway checks the following criteria to determine if a file has changed since the initial transfer:</p>
<ul>
<li>alias of the partner</li>
<li>direction</li>
<li>file size</li>
<li>file date</li>
<li>directory name of the master</li>
<li>file name (short for MGET, long for MPUT)</li>
</ul>
<p>If none of these criteria has changed, the file is considered as unchanged and is therefore not sent.</p>
<p><span style="font-weight: bold;">2</span>: <span style="font-style: italic;">For future use</span></p>
<p><span style="font-weight: bold;">3</span>: <span style="font-style: italic;">For future use</span></p>         </td>
      </tr>
      <tr>
         <td><p>-multi_model (-mum) &lt;Model name&gt;</p>
<p>Model to use for child transfers</p>         </td>
         <td><p>FTP and SFTP multiple transfers only</p>
<p>Specify the name of the Model to use to submit <span style="font-style: italic;">child</span> transfers.</p>
<p>If this parameter is not specified, the Transfer Request for a <span style="font-style: italic;">child</span> is created using the Application of the <span style="font-style: italic;">master</span>.</p>
<p>In all cases, a Transfer Request for a <span style="font-style: italic;">child</span> is made with <span class="code">type</span> = TRANS and <span class="code">mode</span>, <span class="code">direction</span>, <span class="code">org_alias</span> and <span class="code">dest_alias</span> derived from the <span style="font-style: italic;">master</span>.</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-nack_by_user (-nack)</p>
<p><span style="font-style: italic;font-weight: bold;">Negative ack option</span></p>         </td>
         <td><p>PeSIT HS only</p>
<p>The Nack (Negative acknowledgement) option indicates whether the Remote Site supports the negative EERP extension or not. If this option is not set, all negative acknowledgement requests are refused.</p>         </td>
         <td><ul>
<li><strong>Y</strong></li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-newline_convention</p>
<p><span style="font-style: italic;font-weight: bold;">Newline convention</span></p>         </td>
         <td><p>SFTP only</p>
<p>Set the end-of-line code, depending on the remote system type. This parameter is valid for text file transfers in both send and receive mode.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> or <span style="font-weight: bold;">u</span> (UNIX)</li>
<li><span style="font-weight: bold;">W</span> or <span style="font-weight: bold;">w</span> (Windows)</li>
<li><span style="font-weight: bold;">' '</span> (undefined)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-org_alias (-oa)</p>
<p>Originator alias</p>         </td>
         <td><p>Originator Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-originator (-org)</p>
<p><span style="font-style: italic;font-weight: bold;">Originator</span></p>         </td>
         <td><p>Originator protocol identifier</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-padding (-pad)</p>
<p><span style="font-style: italic;font-weight: bold;">Padding character</span></p>         </td>
         <td><p>Padding character code</p>         </td>
         <td><p>Hexadecimal value: 00 - FF</p>         </td>
      </tr>
      <tr>
         <td><p>-param1 (-p1)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 1</span></p>         </td>
         <td><p>User parameter 1.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-param2 (-p2)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 2</span></p>         </td>
         <td><p>User parameter 2.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-password (-passwd)</p>         </td>
         <td><p>Password to use together with the <span class="code">username</span> and <span class="code">dest_address</span> parameters to create a temporary destination site for a transfer. Use these parameters in place of the association of a destination Site object.</p>         </td>
         <td><p>The password associated with the value entered in the <span class="code">username</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>-permanent (-perm)</p>
<p><span style="font-style: italic;font-weight: bold;">Permanent</span></p>         </td>
         <td><p>This parameter controls the availability of files for download by remote clients when Gateway is acting in <span style="font-style: italic;">server mode</span>.</p>
<p>Usually ( when <span class="code">permanent = N</span>), Gateway makes a specified file available only to the first client that submits a Transfer Request for the file.</p>
<p>If you activate this option (<span class="code">permanent = Y</span>), Gateway responds to each client's Transfer Requests by sending a copy of the requested file, keeping the original in the database available for subsequent client Transfer Requests.</p>         </td>
         <td><p>Select one of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (to set Transfer availability to permanent)</li>
<li><span style="font-weight: bold;">N</span> (default)</li>
</ul>
<p>The value that you set here overrides the setting in the Model definition.</p>         </td>
      </tr>
      <tr>
         <td><p>-priority (-prio)</p>
<p><span style="font-style: italic;font-weight: bold;">Priority</span></p>         </td>
         <td><p>Also for X.400 - described later in this topic</p>
<p>Transfer priority</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">0</span> = High priority</li>
<li><span style="font-weight: bold;">1</span> = Medium priority</li>
<li><span style="font-weight: bold;">2</span> = Low priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-purge_option (-po)</p>
<p><span style="font-style: italic;font-weight: bold;">Purge option</span></p>         </td>
         <td><p>Enable purge of files associated with the Transfer Request, using the <span class="code" style="font-weight: bold;">pelpur</span> command.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-rcv_appli (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">Application</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Receiver Application name</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-rcv_text (-rt)</p>
<p><span style="font-style: italic;font-weight: bold;">Text</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Receiver free text</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-rcv_user (-ru)</p>
<p><span style="font-style: italic;font-weight: bold;">User</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Receiver user name</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_fmt (-rf)</p>
<p><span style="font-style: italic;font-weight: bold;">Record format</span></p>         </td>
         <td><p>Record format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed</li>
<li><span style="font-weight: bold;">V</span> = Variable</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
<li><span style="font-weight: bold;">FT</span> = Fixed Text</li>
<li><span style="font-weight: bold;">VT</span> = Variable Text</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-rec_len (-rl)</p>
<p><span style="font-style: italic;font-weight: bold;">Record length</span></p>         </td>
         <td><p>Record length</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32768</span></p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_nack_msg (-rnm)</p>         </td>
         <td><p>EDIINT. Gateway operating in Responder mode on receipt of a transfer</p>
<p>Optionally, enter a text explaining a warning or error receipt.</p>         </td>
         <td><p>Explanatory text.<br />
Maximum: 512 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_reply_to_xfer (-rrtx)</p>
<p>New Acknowledgement Message: Transfer ID to ack</p>         </td>
         <td><p>EDIINT or SWIFTNet. Gateway operating in Responder mode on receipt of a transfer.</p>
<p>Use this parameter to activate the generation of a receipt on reception of a transfer.</p>         </td>
         <td><p>The number of the transfer for which you want to generate and send a return receipt.</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request (-rr)</p>
<p>Receipt request</p>         </td>
         <td><p>EDIINT, SWIFTNet FileAct Realtime/SnF and SWIFTNet InterAct SnF only</p>
<p>Specify whether a return receipt is required when sending a file to a partner.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">undefined</span> (default)</li>
<li><span style="font-weight: bold;">none</span> = no receipt requested</li>
<li><span style="font-weight: bold;">signed</span> = request signed receipt</li>
<li><span style="font-weight: bold;">unsigned</span> = request unsigned receipt (<span style="font-style: italic;">EDIINT only</span>)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request_sync (-rrs)</p>         </td>
         <td><p>EDIINT only</p>
<p>Synchronize sending of receipts.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request_to (-rrto)</p>
<p>Depending on protocol:</p>
<p>Receipt url/email</p>
<p>Receipt DN</p>         </td>
         <td><p><span style="font-style: italic;">EDIINT:</span> The URL or email address to which the acknowledgement is sent.</p>
<p><span style="font-style: italic;">SWIFTNet FileAct Realtime:</span> The DN to which the acknowledgement is sent.</p>         </td>
         <td><p>The URL, email address or DN to which you want the transfer receipt to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_type (-rt)</p>         </td>
         <td><p>EDIINT. Gateway operating in Responder mode on receipt of a transfer</p>
<p>Specify the type of receipt to return to the initiator of the received transfer.</p>         </td>
         <td><p>The receipt type. One of:</p>
<ul>
<li>SUCCESS</li>
<li>ERROR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-remote agent (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">Remote agent alias</span></p>         </td>
         <td><p>Alias of the associated Remote Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-reply_to_xfer (-rtx)</p>
<p><span style="font-style: italic;font-weight: bold;">Reply to</span></p>         </td>
         <td><p>Local identifier of the Transfer Request to which the response must be sent</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-request_method (-rm)</p>
<p><span style="font-style: italic;font-weight: bold;">Request method</span></p>         </td>
         <td><p>HTTP only</p>
<p>Method to use during Transfer in HTTP protocol</p>         </td>
         <td><p>Incoming Transfers:</p>
<ul>
<li>GET</li>
<li>POST</li>
</ul>
<p>Outgoing Transfers:</p>
<ul>
<li>POST</li>
<li>PUT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-response_request_sync (-resprs)</p>
<p>Request a response</p>         </td>
         <td><p>RosettaNet only</p>
<p>Send a message requesting a synchronous response</p>         </td>
         <td><ul>
<li>Y</li>
<li><span class="code">N</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-response_to (-resptx)</p>
<p>Send a response</p>         </td>
         <td><p>RosettaNet only</p>
<p>Send a response</p>         </td>
         <td><p>Enter the local transfer identifier of the answered RosettaNet message</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_count_max (-rc_max)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum number of retries</span></p>         </td>
         <td><p>Maximum number of retries allowed</p>         </td>
         <td><p>Integer: 0 - 999.<br />
Default = 10.</p>         </td>
      </tr>
      <tr>
         <td><p>-route_from_xfer (-rfx)</p>
<p><span style="font-style: italic;font-weight: bold;">Route from</span></p>         </td>
         <td><p>Local identifier of the Request from which the Transfer is routed</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-route_state (-rs)</p>
<p><span style="font-style: italic;font-weight: bold;">Route state</span></p>         </td>
         <td><p><span style="font-style: italic;">Updating Transfer:</span></p>
<p>Routing state</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">TO_ROUTE</span></li>
<li><span class="code" style="font-weight: bold;">ROUTED</span></li>
<li><span class="code" style="font-weight: bold;">FAILED</span></li>
<li><span class="code" style="font-weight: bold;">ACKNOWLEDGED</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sentinel_transfer_filter (-stf)</p>
<p><span style="font-style: italic;font-weight: bold;">Sentinel Transfer Filter</span></p>         </td>
         <td><p>Indicate notification level for Transfer state changes to send to Sentinel server.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">ALL</span></li>
<li><span class="code" style="font-weight: bold;">SUMMARY</span></li>
<li><span class="code" style="font-weight: bold;">NONE</span></li>
<li><span class="code" style="font-weight: bold;">UNDEFINED</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-server</p>
<p>(None)</p>         </td>
         <td><p>Site name for the PEL <span style="font-weight: bold;">LOT</span> command</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_bcc (-bcc)</p>
<p><span style="font-style: italic;font-weight: bold;">Bcc</span></p>         </td>
         <td><p>SMTP only</p>
<p>Blind copy recipients</p>         </td>
         <td><p>No max length</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_cc (-cc)</p>
<p><span style="font-style: italic;font-weight: bold;">Cc</span></p>         </td>
         <td><p>SMTP only</p>
<p>Copied recipients</p>         </td>
         <td><p>No max length</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_from (-from)</p>
<p><span style="font-style: italic;font-weight: bold;">From</span></p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Email <span style="font-style: italic;">from</span> field. This parameter is not required if you set the <span class="code">attach_extract_file</span> parameter to <span class="code">No</span>. The file is already formatted as an email and already contains the From address.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_subject (-subject)</p>
<p><span style="font-style: italic;font-weight: bold;">email subject</span></p>         </td>
         <td><p>SMTP/POP3, AS2, AS3</p>
<p>Also for X.400 - described later in this topic</p>
<p>Email subject. This parameter is mandatory if Gateway must create the email (<span class="code">attach_extract_file</span> parameter set to <span class="code">Yes</span>). If you are sending a formatted email via a Gateway Transfer Request, do not complete this parameter.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_to (-to)</p>
<p><span style="font-style: italic;font-weight: bold;">To</span></p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Email <span style="font-style: italic;">to</span> field. This parameter is not required if you set the <span class="code">attach_extract_file</span> parameter to <span class="code">No</span>. The file is already formatted as an email and already contains the To address.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_appli (-sa)</p>
<p><span style="font-style: italic;font-weight: bold;">Application</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Sender Application name</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>
<p>Depending on protocol:</p>
<p>Message to send</p>
<p>Send text message</p>         </td>
         <td>OFTP: User message to transmit at the OFTP connection phase
FTP: List of special commands to send to the remote server using <span class="code">SITE</span> or <span class="code">QUOTE</span> FTP command
PeSIT: User message to transmit at the connection phase
HTTP: User message to add CGI parameters or <a href="../../../../protocols_about/http_about/http_client_non_std_headers">non-standard HTTP headers</a> to the Transfer Request
EDIINT: User message providing details about a WARNING or ERROR return receipt
SWIFTNet FileAct:
<ul>
<li>[0 - 255]: Transfer description, supplied by the initiator.<br />
Free-text description of the transfer.</li>
<li>[256 - 511]: Transfer information, supplied by the initiator.<br />
Structured information concerning the transfer.<br />
For more details, refer to the SWIFT documentation.</li>
</ul>
SWIFTNet InterAct:
<ul>
<li>[0 - 511]: User message.</li>
</ul>         </td>
         <td><ul>
<li>OFTP: Up to 8 alphanumeric characters</li>
<li>FTP: Up to 512 alphanumeric characters</li>
<li>PeSIT: Up to 512 alphanumeric characters</li>
<li>HTTP: Up to 512 alphanumeric characters.<br />
For CGI parameters, use the format: <span class="code">xfer_param1=value1&amp;xfer_param2=value2</span><br />
For non-standard HTTP headers, use the format: <span class="code">[xs4hh]X-Id1=v1&amp;X-Id2=v2[/xs4hh]</span>.</li>
<li>EDIINT: Up to 512 alphanumeric characters</li>
<li>SWIFTNet FileAct: Max 256 alphanumeric characters for each part</li>
<li>SWIFTNet InterAct: Max 512 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg_file (-smf)</p>
<p><span style="font-style: italic;font-weight: bold;">Send text message in file</span></p>         </td>
         <td><p><span style="font-style: italic;">Submitting an Application or Acknowledgement message:</span></p>
<p>The message content to send. Use this option if the message is stored in an external file (PI 91).</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_text (-st)</p>
<p><span style="font-style: italic;font-weight: bold;">Text</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Sender free text</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_user (-su)</p>
<p><span style="font-style: italic;font-weight: bold;">User</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward only</p>
<p>Sender user name</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-sys_dep (-sd)</p>
<p>(None)</p>         </td>
         <td><p>For BULL, AS400, GCOS and TANDEM machines: File type is system-dependent.</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-text_file</p>
<p><span style="font-style: italic;font-weight: bold;">Text file</span></p>         </td>
         <td><p>Text file flag</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-tpm_dea_id (-tpmdea)</p>         </td>
         <td><p>PassPort (TPM) Document Exchange Address identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-tpm_dea_id_2 (-tpmdea_2)</p>         </td>
         <td><p>PassPort (TPM) Document Exchange Address identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_trade_compress"></span>-trade_compress (-tradecomp)</p>
<p>EDIINT:</p>
<p>Is compressing</p>
<p>SWIFTNet:</p>
<p>Compress</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Compression algorithm for use when sending a file or message to a partner.</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">Y</span> = Use the compression algorithm</li>
<li><span style="font-weight: bold;">N</span> = No compression</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_dest (-traded)</p>
<p>EDIINT:</p>
<p>(None)</p>
<p>SWIFTNet:</p>
<p>Destination DN</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>The name of the destination partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_dest_alias (-tradeda)</p>
<p>Destination partner</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Alias of the destination partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_encrypt (-tradee)</p>
<p><span style="font-style: italic;">EDIINT:</span></p>
<p>Is encrypting</p>
<p>SWIFTNet:</p>
<p>Encrypt</p>         </td>
         <td><p>EDIINT and SWIFTNet InterAct only</p>
<p>Ciphering algorithm for use when sending a file to a partner.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_file_already_encoded (-tradefae)</p>         </td>
         <td><p>EDIINT only</p>
<p>The use of this parameter is not recommended when submitting Transfer Requests.</p>
<p>Use this parameter in Models to be applied on Decision Rule routing via EDIINT.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_format (-tradef)</p>
<p>(None)</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Protocol version.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>SWIFTNET</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_org (-tradeo)</p>
<p>EDIINT:</p>
<p>(None)</p>
<p>SWIFTNet:</p>
<p>Originator DN</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>The name of the originating partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_org_alias (-tradeoa)</p>
<p>Originator partner</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Alias of the originating partner of the trading partner exchange.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign (-trades)</p>
<p><span style="font-style: italic;">EDIINT:</span></p>
<p>Is signing</p>
<p>SWIFTNet:</p>
<p>Sign</p>         </td>
         <td><p>EDIINT and SWIFTNet only</p>
<p>Certificate signing algorithm used when sending a file to a partner.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_state (-ts)</p>         </td>
         <td><p>EDIINT only</p>
<p>Select transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li>TO_PROCESS</li>
<li>PROCESSING</li>
<li>PROCESSED</li>
<li>ACKED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-truncating_allowed (-ta)</p>
<p><span style="font-style: italic;font-weight: bold;">Truncating allowed</span></p>         </td>
         <td><p>If the Transfer uses the truncating feature, this option allows you to truncate a record without taking into account the padding character.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-type (-ty)</p>
<p><span style="font-style: italic;font-weight: bold;">Type</span></p>         </td>
         <td><p>Transfer type</p>         </td>
         <td><p>One of:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li><strong>MSG</strong> (equivalent to INTERACT Transfer type when using the GUI)</li>
<li>DIR</li>
<li>RECEIPT</li>
<li><strong>MULTI</strong>: MGET or MPUT for FTP or SFTP multiple transfer (the distinction between MGET and MPUT is indicated by the <span class="code">direction</span> parameter)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-unique_filename (-uf)</p>
<p><span style="font-style: italic;font-weight: bold;">Unique filename option</span></p>         </td>
         <td><p>FTP only</p>
<p>Store unique option</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-user_processed (-usr_proc)</p>
<p><span style="font-style: italic;font-weight: bold;">User processed</span></p>         </td>
         <td><p><span style="font-style: italic;">Modifying a Transfer:</span></p>
<p>Transfer processed by user</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-user_state (-usr_st)</p>
<p><span style="font-style: italic;font-weight: bold;">User state</span></p>         </td>
         <td><p><span style="font-style: italic;">Modifying, a Transfer:</span></p>
<p>User state field managed by the user application. Gateway does not interpret this field.</p>         </td>
         <td><p>One character</p>         </td>
      </tr>
      <tr>
         <td><p>-username (-un)</p>         </td>
         <td><p>User login name to use together with the <span class="code">password</span> and <span class="code">dest_address</span> parameters to create a temporary destination site for a transfer. Use these parameters in place of the association of a destination Site object.</p>         </td>
         <td><p>Enter the user login name, required for access to the destination Site identified in the <span class="code">dest_address</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>-x_data_code (-xdc)</p>
<p><span style="font-style: italic;font-weight: bold;">Data code</span></p>         </td>
         <td><p>Transferred file data code</p>         </td>
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
</ul>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_fmt (-xrf)</p>
<p><span style="font-style: italic;font-weight: bold;">Record format</span></p>         </td>
         <td><p>Transferred file record format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed</li>
<li><span style="font-weight: bold;">V</span> = Variable</li>
<li><span style="font-weight: bold;">T</span> = Text (OFTP only)</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
<li><span style="font-weight: bold;">U</span> = Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_len (-xrl)</p>
<p><span style="font-style: italic;font-weight: bold;">Record length</span></p>         </td>
         <td><p>Transferred file record length</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">32768</span></p>         </td>
      </tr>
      <tr>
         <td><p>-mail_xpriority<br />
(-mailxprio)</p>         </td>
         <td><p>SMTP protocol only (with or without S/MIME) - the value for X-Priority mail header (SEPAmail standard)</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">5</span></p>         </td>
      </tr>
      <tr>
         <td><span class="code"><strong>-sigalgo(-sga)</strong> </span>         </td>
         <td>Signature and hash algorithm used in payload
signature computation. Considered only when <span class="code">payload_integrity_option </span>is set to <span class="code">yes</span>. See <a href="../../../../../gateway_security_guide/managing_security_start_here/payloadsecurity/opensslexample" class="MCXref xref">Working with Payload integrity</a>         </td>
         <td>SHA256withRSA         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">-sigfile(-sgf)</span>         </td>
         <td>File containing payload signature, in binary format. Considered only when <span class="code"><span class="code">payload_integrity_option </span></span>is set to <span class="code"><span class="code">yes</span></span>.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

<span id="oftp_transfer_parameters"></span>

## Additional Transfer Request parameters for OFTP

The following table contains <span class="code" style="font-weight: bold;">peltrans</span> command parameters that are specific to OFTP file security (OFTP R2.0 only). The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

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
         <td><p>-sfidsign</p>
<p>Signed EERP</p>         </td>
         <td><p>Is signed EERP required?</p>         </td>
         <td><ul>
<li>Y</li>
<li><span class="code" style="font-weight: bold;">N</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sfiddesc</p>
<p>Virtual file description</p>         </td>
         <td><p>Virtual file description</p>         </td>
         <td><p>Free text</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_format (-tradef)</p>
<p>Format</p>         </td>
         <td><p>Trade format</p>         </td>
         <td><p><span class="code" style="font-weight: bold;">CMS</span> (Cryptographic Message Syntax)</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_org (-tradeo)</p>
<p>Originator partner</p>         </td>
         <td><p>Original Trading Partner (sender)</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_dest (-traded)</p>
<p>Destination partner</p>         </td>
         <td><p>Destination Trading Partner (receiver)</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign (-trades)</p>
<p>Is signing</p>         </td>
         <td><p>Is file signature required?</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign_algo (-tradesa)</p>         </td>
         <td><p>Signing algorithm</p>         </td>
         <td><p>SHA1withRSA</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_encrypt (-tradee)</p>
<p>Is encrypting</p>         </td>
         <td><p>Is file encryption required?</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_encryption_algo (-tradeea)</p>         </td>
         <td><p>Encryption algorithm</p>         </td>
         <td><ul>
<li>AES256</li>
<li>3DES</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_compress (-tradecomp)</p>
<p>Is compressing</p>         </td>
         <td><p>Is file compression required?</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="SWIFTNet_transfer_parameters"></span>

## Additional Transfer Request parameters for SWIFTNet

The following table contains <span class="code" style="font-weight: bold;">peltrans</span> command parameters that are specific to SWIFTNet transfers. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

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
         <td><p>-header_info (-hinf)</p>
<p>Header info</p>         </td>
         <td><p>Reference to file on disk containing Header Info. This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info#XML_File_structure">specific structure</a>.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-non_repudiation (-nr)</p>
<p>Non repudiation</p>         </td>
         <td><p>This option indicates whether SWIFT must keep proof of sending or not.<br />
(Availability depends on the service used.)</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-payload_type (-pto)</p>
<p>Payload type</p>         </td>
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
         <td><p><span id="_rcv_msg"></span>-rcv_msg</p>
<p>(None)</p>         </td>
         <td><p>FileAct only</p>
<p>[0 - 255]: File description, supplied by the sender. Free-text description of the file.</p>
<p>[256 - 511]: File information, supplied by the sender. Structured information concerning the transfer. For more details, refer to the SWIFT documentation.</p>         </td>
         <td><p>Maximum: 256 + 256 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_req_to (-rrto)</p>
<p>Receipt DN</p>         </td>
         <td><p>FileAct, Real time only</p>
<p>If specified, name of the receipt reception address. This is the address to which the receiving partner sends the receipt.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request_type (rrt)</p>
<p>Receipt request type</p>         </td>
         <td><p>FileAct, Real time only</p>
<p>Type of acknowledgement request</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-request_type (-rqt)</p>
<p>Request type</p>         </td>
         <td><p>Type of request (as specified in the XML header).</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-service (-sc)</p>
<p>Service name</p>         </td>
         <td><p>SWIFT business service name (as specified in the XML header).</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-sign_list (-signl)</p>
<p>Signature list</p>         </td>
         <td><p>Reference to file on disk containing a Signature List. This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_sig_list#XML_File_structure">specific structure</a>.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-sw_add_params (-swaddpar)</p>
<p>Additional params</p>         </td>
         <td><p>Reference to file on disk containing additional SWIFTNet structures (for example, Header Info and/or Signature List). This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info#XML_File_structure">specific structure</a>.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-sw_auth_indicator (-ai)</p>
<p>Request authorisation notification</p>         </td>
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
<p>Request copy</p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">copy of the file or message</a> to be sent to a third party defined at the service level.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sw_creation_time (-swcreatm)</p>
<p>(None)</p>         </td>
         <td><p>Store-and-Forward mode only</p>
<p>Use this parameter to set the same creation time as the original transfer when manually resending each lost transfer detected during the <a href="../../../../connectors_about/swiftnet_about/swiftnet_sig_list/swiftnet_system_recovery">SWIFTNet system recovery</a> procedure.</p>         </td>
         <td>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span>         </td>
      </tr>
      <tr>
         <td><p>-sw_empty_message_id (-swemptymsgid)</p>
<p>(None)</p>         </td>
         <td><p>Empty message id parameter.</p>
<p>For use with <a href="../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate#_sw_empty_message_id">SWIFTNet Possible Duplicate</a>.</p>
<p>Use this parameter to prevent Gateway from automatically generating a message id.</p>
<p>This is useful if you want to mark a transfer as a Possible Duplicate but <em>not</em> generate a message id for it, because it is unknown.</p>
<p><strong>Note:</strong> Do not use this parameter in combination with the <span class="code">sw_message_id</span> parameter! If you specify both parameters, then the <span class="code">sw_empty_message_id</span> parameter is not taken into account.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> – Prevent Gateway from automatically generating a message id</li>
<li><span class="code" style="font-weight: bold;">N</span> – Gateway automatically generates a message id (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sw_message_id (-swmsgid)</p>
<p>Message id</p>         </td>
         <td><p>SWIFTNet message id.</p>
<p>For use with <a href="../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate#_swmsgid">SWIFTNet Possible Duplicate</a>.</p>
<p>The value of this parameter overwrites the message id created by Gateway in the Transfer Request.</p>
<p>Enter the SWIFTNet message id of the new transfer. This should be a Universal Unique IDentifier (UUID).</p>
<p>If the transfer is a Possible Duplicate, enter the message id of the initial transfer.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_swot"></span>-sw_overdue_time (-swot)</p>
<p>Overdue time:<br />
Date and Time</p>         </td>
         <td><p>SWIFTNet <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_overdue">OverdueTime</a></p>         </td>
         <td>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span>         </td>
      </tr>
      <tr>
         <td><p>-sw_pd_indication (-swpdind)</p>
<p>Possible duplicate</p>         </td>
         <td><p>Possible Duplicate indicator</p>
<p>For use with <a href="../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate#_swpdind">SWIFTNet Possible Duplicate</a>.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">Y</span> - Select this value to indicate to the responder that the transfer is a Possible Duplicate.</li>
<li><span class="code" style="font-weight: bold;">N</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-sw_public_recipient_list_ind</p>
<p>(None)</p>         </td>
         <td><p>For use with a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_distribution_list">SWIFTNet Distribution List</a> (distribution to multiple recipients).</p>
<p>Use this parameter to specify whether or not the responder can receive the list of recipients.</p>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>-trade_delivery_mode (-tradedmo)</p>
<p>Delivery mode</p>         </td>
         <td><p>Indicates the delivery mode of the file or message.</p>
<p>Real time = immediate</p>
<p>Store-and-Forward = send and then store in the queue in the SWIFTNet domain.</p>         </td>
         <td><ul>
<li>RT</li>
<li>SNF</li>
<li><span class="code" style="font-weight: bold;">undef</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trade_encrypt_dn (-tradeendn)</p>
<p>Encrypt DN</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for encryption in Initiator mode.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_notif_queue (-tradenq)</p>
<p>Notif queue</p>         </td>
         <td><p>Store-and-Forward mode only</p>
<p>Reception queue for Store-and-Forward delivery notifications.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign_dn (-tradesidn)</p>
<p>Sign DN</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for signing in Initiator mode. Otherwise the securityDN (supplied by SNL) is used</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
   </tbody>
</table>

<span id="x400_transfer_parameters"></span>

## Additional Transfer Request parameters for X.400

The following table contains <span class="code" style="font-weight: bold;">peltrans</span> command parameters that are specific to X.400 (X.420) transfers. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

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
         <td><p>-content_id (-ctid)</p>
<p>Content Id</p>         </td>
         <td><p>Uniquely defines the message to be sent.</p>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>-dn_request (-dnreq)</p>
<p>Delivery notification request</p>         </td>
         <td><p>Delivery notification request.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">NDN</span> = Non Delivery Notification (default)</li>
<li><span class="code" style="font-weight: bold;">DN_NDN</span> = Delivery Notification and Non Delivery Notification</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ipmid_user_id (-ipmiduid)</p>
<p>Interpersonal messaging Id</p>         </td>
         <td><p>Define the IPM (Interpersonal Messaging) Identifier that uniquely identifies this IPM.</p>
<p>Mandatory user relative identifier, which uniquely identifies the IPM.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p1.originator</p>
<p>Originator</p>         </td>
         <td><p>Override the originator X.400 address.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p1.recipient</p>
<p>Recipient</p>         </td>
         <td><p>Override the recipient X.400 address.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.bodyPartType</p>
<p>Body part type</p>         </td>
         <td><p>Define the body part type to be used.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">ia5</span> (default)</li>
<li>g3facsimile</li>
<li>teletex</li>
<li>videotex</li>
<li>encrypted</li>
<li>bilaterallyDefined</li>
<li>externallyDefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-p2.importance</p>
<p>Importance</p>         </td>
         <td><p>Indicate the importance of the IPM.</p>         </td>
         <td><ul>
<li>low</li>
<li><span class="code" style="font-weight: bold;">normal</span> (default)</li>
<li>high</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-p2.ipmId.user</p>         </td>
         <td><p>Define the IPM Identifier that uniquely identifies this IPM.</p>
<p>Optional part that is a serialized user O/R address.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.originator.formalName</p>         </td>
         <td><p>Override the formal name part of the O/R Descriptor of the message originator.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.originator.freeFormalName</p>         </td>
         <td><p>Override the free formal name part of the O/R Descriptor of the message originator.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.originator.telephoneNumber</p>         </td>
         <td><p>Override the telephone number part of the O/R Descriptor of the message originator.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.primaryRecipient.recipient.formalName</p>         </td>
         <td><p>Override the formal name part of the O/R Descriptor of the primary recipient.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.primaryRecipient.recipient.freeFormalName</p>         </td>
         <td><p>Override the free formal name part of the O/R Descriptor of the primary recipient.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.primaryRecipient.recipient.telephoneNumber</p>         </td>
         <td><p>Override the telephone number part of the O/R Descriptor of the primary recipient.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.repliedToIpmId.user</p>         </td>
         <td><p>Set the IPM identifier which identifies the message to which this message is the reply.</p>
<p>Optional part.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.repliedToIpmId.userRelativeId</p>
<p>Replied to IPM Id</p>         </td>
         <td><p>Set the IPM identifier which identifies the message to which this message is the reply.</p>
<p>Mandatory user relative identifier, which uniquely identifies the IPM.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.replyDateTime</p>         </td>
         <td><p>Request (but not demand) a time when any replies to the present IPM should have been originated. It comprises a date and time.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-p2.sensitivity</p>
<p>Sensitivity</p>         </td>
         <td><p>Indicate the sensitivity of the IPM.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">unspecified</span> (default)</li>
<li>personal</li>
<li>private</li>
<li>companyConfidential</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-priority (-prio)</p>
<p><span style="font-style: italic;font-weight: bold;">Message transfer system priority</span></p>         </td>
         <td><p>Defines the priority level for the message.</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">0</span> = High priority</li>
<li><span style="font-weight: bold;">1</span> = Medium priority</li>
<li><span style="font-weight: bold;">2</span> = Low priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-recipient_receipt_notif_request (-rcptrnr)</p>
<p>Notification request</p>         </td>
         <td><p>Receipt request.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">None</span> (default)</li>
<li><span class="code" style="font-weight: bold;">NRN</span> = Non Receipt Notification</li>
<li><span class="code" style="font-weight: bold;">RN_NRN</span> = Receipt Notification and Non Receipt Notification</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-recipient_reply_request (-rcptrr)</p>
<p>Reply request</p>         </td>
         <td><p>Reply request.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">N</span> (default)</li>
<li>Y</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-smtp_subject (-subject)</p>
<p><span style="font-style: italic;font-weight: bold;">Subject</span></p>         </td>
         <td><p>Subject of the message.</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Diffusion_List_transfer_parameters"></span>

## Additional Transfer Request parameters for Diffusion Lists

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-nb_total</p>         </td>
         <td><p>Total number of Transfer Requests</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_ended</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">ended</span> state</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_to_begin</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">to_begin</span> state</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_suspended</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">suspended</span> state</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_canceled</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">canceled</span> state</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_frozen</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">frozen</span> state</p>         </td>
      </tr>
      <tr>
         <td><p>-nb_progressing/servicing</p>         </td>
         <td><p>Number of Transfer Requests in <span style="font-weight: bold;">progressing</span> or <span style="font-weight: bold;">servicing</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelpur_parameters"></span>

## Purging Transfers: pelpur parameters

The following table contains parameters you can use with the <span class="code" style="font-weight: bold;">pelpur</span> command or <span class="code">pelpur xferPurge</span> subcommand. (Both forms are functional and have the same result).

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
         <td><p>-all (-a)</p>
<p>(None)</p>         </td>
         <td><p>Purges all ended Transfer Requests (state <span style="font-style: italic;">Ended</span>, <span style="font-style: italic;">Canceled</span> and <span style="font-style: italic;">Acked</span>)</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-appli_name (-ap)</p>
<p><span style="font-style: italic;font-weight: bold;">Application name</span></p>         </td>
         <td><p>Application name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>
<p><span style="font-style: italic;font-weight: bold;">Destination alias</span></p>         </td>
         <td><p>Destination Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>
<p><span style="font-style: italic;font-weight: bold;">Direction</span></p>         </td>
         <td><p>Transfer direction</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">O</span> = Output</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>
<p><span style="font-style: italic;font-weight: bold;">File Name</span></p>         </td>
         <td><p>Protocol file name</p>
<p>For FTP and HTTP DIR type Transfers, this parameter defines a filter on the file names that the server returns.</p>
<p>For example: <span class="code" style="font-weight: bold;">*.txt</span> returns all <span class="code">.txt</span> files in the directory that you specify.</p>         </td>
         <td><p>Maximum: 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_type (-ft)</p>
<p><span style="font-style: italic;font-weight: bold;">File type</span></p>         </td>
         <td><p>PeSIT HS only</p>
<p>File type</p>         </td>
         <td><p>Maximum: 16 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-from_date (-fd)</p>
<p>(None)</p>         </td>
         <td><p>Earliest date for the Transfer</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-ident_inf (-id_inf)</p>
<p>(None)</p>         </td>
         <td><p>Minimum value of the Transfer identifiers to select</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-ident_sup (-id_sup)</p>
<p>(None)</p>         </td>
         <td><p>Maximum value of the Transfer identifiers to select</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-keep_last_day (-kld)</p>
<p>(None)</p>         </td>
         <td><p>Do not purge Transfers from the <span style="font-style: italic;">ddd</span> previous days.</p>
<p>Both the transfer <code>create_date</code> and <code>end_date</code> (if exists) are used for matching. They must be older than the <code>kld</code> value. The
<code>Kld</code> option is not applied as a filter over the "in memory" transfer list but iterates through the mailbox to select the matching transfers. This may impact performance when there is a large mailbox.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-keep_mailbox_entries(-ke)</p>
<p>(None)</p>         </td>
         <td>Skip purging the transfers from mailbox.         </td>
         <td>No value         </td>
      </tr>
      <tr>
         <td><code>-force (-f) </code>         </td>
         <td>Force files removal, ignoring value of <code>purge_option </code>parameter from transfer.         </td>
         <td>No value         </td>
      </tr>
      <tr>
         <td><p>-list_route_state (-lrs)</p>
<p>(None)</p>         </td>
         <td><p>Select, purge or display all Transfers with the specified routing status</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">A</span> = <span style="font-weight: bold;">A</span>cked</li>
<li><span style="font-weight: bold;">R</span> = <span style="font-weight: bold;">R</span>outed</li>
<li><span style="font-weight: bold;">F</span> = <span style="font-weight: bold;">F</span>ailed</li>
<li><span style="font-weight: bold;">T</span> = <span style="font-weight: bold;">T</span>o Route</li>
<li><span style="font-weight: bold;">N</span> = <span style="font-weight: bold;">N</span>ot Routed</li>
<li><span style="font-weight: bold;">E</span> =<span style="font-weight: bold;">E</span>mpty</li>
<li><strong>P</strong>=<strong>P</strong>rocessing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-list_trans_state (-lts)</p>
<p>(None)</p>         </td>
         <td><p>Select, purge or display all Transfers with the specified status</p>         </td>
         <td><p>One of:</p>
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
<li><span style="font-weight: bold;">G =</span> To_Si<span style="font-weight: bold;">G</span>n</li>
<li><span style="font-weight: bold;">U =</span> Nacked_<span style="font-weight: bold;">U</span>ser</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-local_agent (-la)</p>
<p><span style="font-style: italic;font-weight: bold;">Local agent alias</span></p>         </td>
         <td><p>Alias of the associated Local Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-local_ident (-i)</p>
<p>Local Identifier</p>         </td>
         <td><p>Local Transfer identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-master (-ma)</p>
<p><span style="font-style: italic;font-weight: bold;">Diffusion List: Local identifier</span></p>         </td>
         <td><p>Diffusion List Request identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>
<p><span style="font-style: italic;font-weight: bold;">Mode</span></p>         </td>
         <td><p>Connection mode for the Transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-no_archive (-no_arc)</p>
<p>(None)</p>         </td>
         <td><p>Purge the Transfer from the Mailbox without creating a Transfer archive file</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-org_alias (-oa)</p>
<p>Originator alias</p>         </td>
         <td><p>Originator Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-protocol (-pr)</p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>Protocol</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li>FTP</li>
<li>HTTP</li>
<li>FTP_HTTP</li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li>SFTP</li>
<li>SMTP</li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-purge_file (-pf)</p>
<p>(None)</p>         </td>
         <td><p>Purges the transferred file</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-purge_tmp_file(-ptf)</p>
<p>(None)</p>         </td>
         <td>Purge only the temporary file related to the transfers.         </td>
         <td>No value         </td>
      </tr>
      <tr>
         <td><p>-purge_xpr (-px)</p>
<p>(None)</p>         </td>
         <td><p>Purges the resolved script file and its output files for the Transfer</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>-remote agent (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">Remote agent alias</span></p>         </td>
         <td><p>Alias of the associated Remote Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-req_name (-rn)</p>
<p>(None)</p>         </td>
         <td><p>Name of the purge request that will be used in the log file to print statistics</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters<br />
Default = <span class="code">PELPUR</span></p>         </td>
      </tr>
      <tr>
         <td><p>-sequence_inf (-seq_inf)</p>
<p>(None)</p>         </td>
         <td><p>Lowest number in range of Transfers to select, purge or display</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-sequence_sup (-seq_sup)</p>
<p>(None)</p>         </td>
         <td><p>Highest number in range of Transfers to select, purge or display</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-to_date (-td)</p>
<p>(None)</p>         </td>
         <td><p>Latest date in the range of Transfers to select, purge or display.</p>
<p>The only transfer parameter that is checked is <code>create_date</code>.</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-type (-ty)</p>
<p><span style="font-style: italic;font-weight: bold;">Type</span></p>         </td>
         <td><p>Transfer type</p>         </td>
         <td><p>One of:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
<li>RECEIPT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-user_state (-usr_st)</p>
<p><span style="font-style: italic;font-weight: bold;">User state</span></p>         </td>
         <td><p>User state field managed by the user application. Gateway does not interpret this field.</p>         </td>
         <td><p>One character</p>         </td>
      </tr>
      <tr>
         <td><p>-username (-un)</p>
<p><span style="font-style: italic;font-weight: bold;">User name</span></p>         </td>
         <td><p>User name</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-yday_inf (-yd_inf)</p>
<p>(None)</p>         </td>
         <td><p>Start of the date range</p>         </td>
         <td><p>Format: <span style="font-style: italic;">ddd</span><br />
1 - 366</p>         </td>
      </tr>
      <tr>
         <td><p>-yday_sup (yd_sup)</p>
<p>(None)</p>         </td>
         <td><p>End of the date range</p>         </td>
         <td><p>Format: <span style="font-style: italic;">ddd</span><br />
1 - 366</p>         </td>
      </tr>
   </tbody>
</table>

The following table contains parameters you can use with the <span class="code">pelpur clean\_swha\_db</span> subcommand. The parameters refer only to SWIFTNet transfer entries saved in the HA database in the context of SWIFTNet High Availability.

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
         <td><p>-gatewayID
(-gtwID)</p>         </td>
         <td><p>Enter a gateway id as selection criteria for the purge operation.</p>         </td>
         <td><p>Integer
0-15</p>         </td>
      </tr>
      <tr>
         <td><p>-fromGatewayID (-fgtwID)]</p>         </td>
         <td><p>Enter a gateway id from which to start the selection, to select all fields with the gateway id greater or equal to it</p>         </td>
         <td><p>Integer
0-15</p>         </td>
      </tr>
      <tr>
         <td><p>-toGatewayID (-tgtwID)</p>         </td>
         <td><p>Enter a gateway id from which to start the selection, to select all fields with the gateway id less or equal to it.</p>         </td>
         <td><p>Integer
0-15</p>         </td>
      </tr>
      <tr>
         <td><p>-transferID (-trID)</p>         </td>
         <td><p>Enter a transfer id as selection criteria for the purge operation.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-fromTransferID (-ftrID)</p>         </td>
         <td><p>Enter a transfer id from which to start the selection, to select all fields with the transfer id greater or equal to it.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-toTransferID (-ttrID)</p>         </td>
         <td><p>Enter a transfer id from which to start the selection, to select all fields with the transfer id less or equal to it.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-flowType (-flTp)</p>         </td>
         <td><p>Enter the flow type as selection criteria for the purge operation.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>INTERACT</li>
<li>FILEACT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-deliveryMode (-delMode)</p>         </td>
         <td><p>Enter the transfer delivery mode as selection criteria for the purge operation.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>RT</li>
<li>SNF</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-localPartner (-lP)</p>         </td>
         <td><p>Enter the local partner alias as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remotePartner (-rP)</p>         </td>
         <td><p>Enter the remote partner alias as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-messageID (-mID)</p>         </td>
         <td><p>Enter the message identification number as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-service (-sv)</p>         </td>
         <td><p>Enter the service name as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-requestType (-rqTp)</p>         </td>
         <td><p>Enter the request type as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-requestorDN (-rquDN)</p>         </td>
         <td><p>Enter the requester DN as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-responderDN (-rpDN)</p>         </td>
         <td><p>Enter the responder DN as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-logicalName (-lgName)</p>         </td>
         <td><p>Enter the logical name of the file as selection criteria for the purge operation.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-createDate (-cDate)</p>         </td>
         <td>Enter the create date of the transfer as selection criteria for the purge operation.         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
      <tr>
         <td><p>-fromCreateDate (-fcDate)</p>         </td>
         <td><p>Enter the start create date of the transfer. It will match the transfers with create date equal to this one or after this date.</p>         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
      <tr>
         <td><p>-toCreateDate (-tcDate)</p>         </td>
         <td><p>Enter the start create date of the transfer. It will match the transfers with create date equal with this one or before this date.</p>         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
      <tr>
         <td><p>-modifyDate (-mDate)</p>         </td>
         <td><p>Enter the date when transfer was last modified as selection criteria for the purge operation.</p>         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
      <tr>
         <td><p>-fromModifyDate (-fmDate)</p>         </td>
         <td><p>Enter the date when the transfer was last modified. It will match the transfers with modify date equal with this one or after this date.</p>         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
      <tr>
         <td><p>-toModifyDate (-tmDate)</p>         </td>
         <td><p>Enter the date when the transfer was last modified. It will match the transfers with modify date equal with this one or before this date.</p>         </td>
         <td>Format: YYYYMMDD         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> To purge a transfer, the SWIFTNet High Availability feature has to be activated and connectivity with HA database must be functional.

<span id="peldsp_parameters"></span>

## Displaying Transfers: peldsp command parameters

The following table contains parameters you can use with the <span class="code" style="font-weight: bold;">peldsp status\_trans</span> and <span class="code" style="font-weight: bold;">peldsp select\_trans</span> commands.

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
         <td><p>-appli (-ap)</p>
<p><span style="font-style: italic;font-weight: bold;">Application</span></p>         </td>
         <td><p>Application name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>
<p><span style="font-style: italic;font-weight: bold;">Destination alias</span></p>         </td>
         <td><p>Destination Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-destination (-dest)</p>
<p><span style="font-style: italic;font-weight: bold;">Destination</span></p>         </td>
         <td><p>Destination protocol identifier</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>
<p><span style="font-style: italic;font-weight: bold;">Direction</span></p>         </td>
         <td><p>Transfer direction</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">O</span> = Output</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>
<p><span style="font-style: italic;font-weight: bold;">File Name</span></p>         </td>
         <td><p>Protocol file name</p>
<p>For FTP and HTTP DIR type Transfers, this parameter defines a filter on the file names that the server returns.</p>
<p>For example: <span class="code" style="font-weight: bold;">*.txt</span> returns all <span class="code">.txt</span> files in the directory that you specify.</p>         </td>
         <td><p>Maximum: 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-file_type (-ft)</p>
<p><span style="font-style: italic;font-weight: bold;">File type</span></p>         </td>
         <td><p>PeSIT HS only</p>
<p>File type</p>         </td>
         <td><p>Maximum: 16 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-from_date (-fd)</p>
<p>(None)</p>         </td>
         <td><p>Earliest date for the Transfer</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-ident_inf (-id_inf)</p>
<p>(None)</p>         </td>
         <td><p>Minimum value of the Transfer identifiers to select</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-ident_sup (-id_sup)</p>
<p>(None)</p>         </td>
         <td><p>Maximum value of the Transfer identifiers to select</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-list_route_state (-lrs)</p>
<p>(None)</p>         </td>
         <td><p>Select, purge or display all Transfers with the specified routing status</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">A</span> = <span style="font-weight: bold;">A</span>cked</li>
<li><span style="font-weight: bold;">R</span> = <span style="font-weight: bold;">R</span>outed</li>
<li><span style="font-weight: bold;">F</span> = <span style="font-weight: bold;">F</span>ailed</li>
<li><span style="font-weight: bold;">T</span> = <span style="font-weight: bold;">T</span>o Route</li>
<li><span style="font-weight: bold;">N</span> = <span style="font-weight: bold;">N</span>ot Routed</li>
<li><span style="font-weight: bold;">E</span> =<span style="font-weight: bold;">E</span>mpty</li>
<li><strong>P</strong>=<strong>P</strong>rocessing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-list_trans_state (-lts)</p>
<p>(None)</p>         </td>
         <td><p>Select, purge or display all Transfers with the specified status</p>         </td>
         <td><p>One of:</p>
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
<li><span style="font-weight: bold;">G =</span> To_Si<span style="font-weight: bold;">G</span>n</li>
<li><span style="font-weight: bold;">U =</span> Nacked_<span style="font-weight: bold;">U</span>ser</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-local_agent (-la)</p>
<p><span style="font-style: italic;font-weight: bold;">Local agent alias</span></p>         </td>
         <td><p>Alias of the associated Local Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-local_ident (-i)</p>
<p>Local Identifier</p>         </td>
         <td><p>Local Transfer identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-master (-ma)</p>
<p><span style="font-style: italic;font-weight: bold;">Diffusion List: Local identifier</span></p>         </td>
         <td><p>Diffusion List Request identifier</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>
<p><span style="font-style: italic;font-weight: bold;">Mode</span></p>         </td>
         <td><p>Connection mode for the Transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-model (-ml)</p>
<p><span style="font-style: italic;font-weight: bold;">Model name</span></p>         </td>
         <td><p>Model used to submit the Transfer Request</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-org_alias (-oa)</p>
<p><span style="font-style: italic;font-weight: bold;">Originator alias</span></p>         </td>
         <td><p>Originator Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-originator (-org)</p>
<p><span style="font-style: italic;font-weight: bold;">Originator</span></p>         </td>
         <td><p>Originator protocol identifier</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-param1 (-p1)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 1</span></p>         </td>
         <td><p>User parameter 1</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-param2 (-p2)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 2</span></p>         </td>
         <td><p>User parameter 2</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-permanent (-perm)</p>
<p><span style="font-style: italic;font-weight: bold;">Permanent</span></p>         </td>
         <td><p>Set to <span style="font-weight: bold;">Yes</span> to make the Transfer Request permanently available</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>-proto_ident (-pid)</p>
<p>(None)</p>         </td>
         <td><p>Site protocol name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-protocol (-pr)</p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>Protocol</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li>FTP</li>
<li>HTTP</li>
<li>FTP_HTTP</li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li>SFTP</li>
<li>SMTP</li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-remote agent (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">Remote agent alias</span></p>         </td>
         <td><p>Alias of the associated Remote Site</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-sequence_inf (-seq_inf)</p>
<p>(None)</p>         </td>
         <td><p>Lowest number in range of Transfers to select, purge or display</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-sequence_sup (-seq_sup)</p>
<p>(None)</p>         </td>
         <td><p>Highest number in range of Transfers to select, purge or display</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-sw_marked_by_system_recovery (-swmksysrec)</p>         </td>
         <td><p>Selection filter for SWIFTNet transfers marked during system recovery.</p>         </td>
         <td><ul>
<li>U = Undefined (default)</li>
<li>Y = Transfers marked by system recovery</li>
<li>N = Transfers that were not marked</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-to_date (-td)</p>
<p>(None)</p>         </td>
         <td><p>Latest date in the range of Transfers to select, purge or display.</p>         </td>
         <td><p>In the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-trade_state (-ts)</p>         </td>
         <td><p>Processing state of an EDIINT transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li>TO_PROCESS</li>
<li>PROCESSING</li>
<li>PROCESSED</li>
<li>ACKED</li>
<li>NACKED</li>
<li>ERROR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-type (-ty)</p>
<p><span style="font-style: italic;font-weight: bold;">Type</span></p>         </td>
         <td><p>Transfer type</p>         </td>
         <td><p>One of:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
<li>RECEIPT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-user_state (-usr_st)</p>
<p><span style="font-style: italic;font-weight: bold;">User state</span></p>         </td>
         <td><p>User state field managed by the user application. Gateway does not interpret this field.</p>         </td>
         <td><p>One character</p>         </td>
      </tr>
      <tr>
         <td><p>-username (-un)</p>
<p><span style="font-style: italic;font-weight: bold;">User name</span></p>         </td>
         <td><p>User name</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-yday_inf (-yd_inf)</p>
<p>(None)</p>         </td>
         <td><p>Start of the date range</p>         </td>
         <td><p>Format: <span style="font-style: italic;">ddd</span></p>
<p>1 - 366</p>         </td>
      </tr>
      <tr>
         <td><p>-yday_sup (-yd_sup)</p>
<p>(None)</p>         </td>
         <td><p>End of the date range</p>         </td>
         <td><p>Format: <span style="font-style: italic;">ddd</span></p>
<p>1 - 366</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Transfers (command line)](../)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
