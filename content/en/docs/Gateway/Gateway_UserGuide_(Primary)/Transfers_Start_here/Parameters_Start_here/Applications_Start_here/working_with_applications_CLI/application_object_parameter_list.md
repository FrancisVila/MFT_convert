{
    "title": "Application objects: parameters list",
    "linkTitle": "Application objects: parameters list",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Managing Transfers

The following table lists all Application command parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in **italics**.

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
         <td><p>alloc_unit (-au)</p>
<p><strong>(<span style="font-style: italic;">none</span>)</strong></p>         </td>
         <td><p>Allocation unit</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">R</span> = expressed in Records</li>
<li><span style="font-weight: bold;">K</span> = expressed in Kilobytes</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>attach_extract_file (-aef)</p>
<p><span style="font-style: italic;font-weight: bold;">Attach/extract file</span></p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Specify whether or not to attach a file</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (if the file is not already formatted as an email)</li>
<li><span style="font-weight: bold;">N</span> (if the file is already formatted as an email)</li>
<li><span style="font-weight: bold;">U</span> (undefined)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>block_size (-bs)</p>
<p><span style="font-style: italic;font-weight: bold;">Physical block size</span></p>         </td>
         <td><p>Block size in bytes</p>         </td>
         <td><p>Integer (default: <span style="font-weight: bold;">0</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>check_records (-c_rec)</p>
<p>Check records</p>         </td>
         <td><p>This parameter determines whether or not records are checked in RFD (Real File Directory) mode.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Check records in RFD mode (default)</li>
<li><span style="font-weight: bold;">N</span> = Skip the record checking phase in RFD. This is useful if the check takes too long (for example, with large ASCII files) and there is the risk of a time-out on the client side.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>User comments</p>         </td>
         <td><p>Up to 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>compression (-comp)</p>
<p><span style="font-style: italic;font-weight: bold;">Compression</span></p>         </td>
         <td><p>Compression</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> = Undefined (default)</li>
<li><span style="font-weight: bold;">H</span> = Horizontal</li>
<li><span style="font-weight: bold;">V</span> = Vertical</li>
<li><span style="font-weight: bold;">B</span> = Both</li>
<li><span style="font-weight: bold;">Z</span> = Zlib</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>data_code (-dc)</p>
<p><span style="font-style: italic;font-weight: bold;">Data code</span></p>         </td>
         <td><p>Data code (local file attributes)</p>         </td>
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
<li><span style="font-weight: bold;">U</span> = Undefined (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>dir_path (-dp)</p>
<p><span style="font-style: italic;font-weight: bold;">Directory for received files</span></p>         </td>
         <td><p>Storage directory for received files. You can define the local storage directory using Transfer variables.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>direction_allowed (-dir_all)</p>
<p><span style="font-style: italic;font-weight: bold;">Direction</span></p>         </td>
         <td><p>Direction allowed</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">O</span> = Output</li>
<li><span style="font-weight: bold;">I</span> = Input</li>
<li><span style="font-weight: bold;">B</span> = Both (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>etb5_auth_type (-5at)</p>
<p>Authentication</p>         </td>
         <td><p>Authentication type</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">UNUSED</span> (default)</li>
<li><span style="font-weight: bold;">SIMPLE</span></li>
<li><span style="font-weight: bold;">RECIPR</span> = reciprocal</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>etb5_ciph_type (-5ct)</p>
<p>Encryption</p>         </td>
         <td><p>Encryption type to ensure data confidentiality</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">UNUSED</span> (default)</li>
<li><span style="font-weight: bold;">DES_CBC_ART</span> = DES simple article</li>
<li><span style="font-weight: bold;">DES_CBC_FIC</span> = DES simple file</li>
<li><span style="font-weight: bold;">DES_TRI_ART</span> = DES triple article</li>
<li><span style="font-weight: bold;">DES_TRI_FIC</span> = DES triple file</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>etb5_id_bank (-5ba)</p>
<p>Bank identifier</p>         </td>
         <td><p>The bank identifier (PI 62)</p>         </td>
         <td><p>Up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>etb5_id_bank_sec (-5bs)</p>
<p>Secondary bank ID</p>         </td>
         <td><p>Optional</p>
<p>Enter a secondary bank identifier (PI 4 in FPDU.CREATE or FPDU.ACK.SELECT)</p>         </td>
         <td><p>Up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>etb5_id_client (-5cl)</p>
<p>Client identifier</p>         </td>
         <td><p>The client identifier (PI 61)</p>         </td>
         <td><p>up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>etb5_id_client_sec (-5cls)</p>
<p>Secondary client ID</p>         </td>
         <td><p>Optional</p>
<p>Enter a secondary client identifier (PI 3 in FPDU.CREATE or FPDU.ACK.SELECT)</p>         </td>
         <td><p>Up to 24 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>etb5_seal_type (-5st)</p>
<p>Sealing</p>         </td>
         <td><p>To ensure data integrity, enter a sealing option</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">UNUSED</span> (default)</li>
<li><span style="font-weight: bold;">DES_PAR_ART</span> = DES partial article</li>
<li><span style="font-weight: bold;">DES_FIN_ART</span> = DES final article</li>
<li><span style="font-weight: bold;">DES_FIN_FIC</span> = DES final file</li>
<li><span style="font-weight: bold;">MDC_FIN_FIC</span> = MDC final file</li>
<li><span style="font-weight: bold;">SHA_FIN_FIC</span> = SHA final file</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="file_action"></span>file_action (-faction)</p>
<p>File action</p>         </td>
         <td><p>PeSIT protocol only</p>
<p>Gateway action on a pre-existing file before receiving the transfer of a file with the same name.</p>
<p>Gateway responds to the various possible situations according to the value of the <span class="code"><a href="#file_dispo">file_dispo</a></span> parameter. If this parameter value is:</p>
<ul>
<li>NEW and a valid file with the same file name already exists, then:<br />
<span class="code">ERASE=NOK / DELETE=NOK / VERIFY=NOK</span></li>
<li>NEW and a file with the same file name does not already exist, then:<br />
<span class="code">ERASE=OK / DELETE=OK / VERIFY=OK</span></li>
<li>OLD and a valid file with the same file name already exists, then:<br />
<span class="code">ERASE=OK / DELETE=OK / VERIFY=OK</span> if empty or <span class="code">NOK</span> if not empty</li>
<li>OLD and a file with the same file name does not already exist, then:<br />
<span class="code">ERASE=NOK / DELETE=NOK / VERIFY=NOK</span></li>
<li>BOTH and a valid file with the same file name already exists, then:<br />
<span class="code">ERASE=OK / DELETE=OK / VERIFY=OK</span> if empty or <span class="code">NOK</span> if not empty</li>
<li>BOTH and a file with the same file name does not already exist, then:<br />
<span class="code">ERASE=OK / DELETE=OK / VERIFY=OK</span></li>
</ul>
<p>where:</p>
<p><span class="code">OK</span> = transfer accepted</p>
<p><span class="code">NOK</span> = transfer refused</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">undefined</span> = not applicable (default)</li>
<li><span style="font-weight: bold;">erase</span> = erases (resets) the existing file</li>
<li><span style="font-weight: bold;">delete</span> = deletes the existing file</li>
<li><span style="font-weight: bold;">verify</span> = checks that the exiting file is empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>file_component (-fc)</p>
<p><strong>(<span style="font-style: italic;">none</span>)</strong></p>         </td>
         <td><p>Local file name</p>
<p>You can define the local file name using Transfer variables. For example: <span style="font-style: italic;">F&amp;(x.local_ident)</span>.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span id="file_dispo"></span><span class="code">file_dispo (-fdisp)</span></p>
<p>File availability</p>         </td>
         <td><p>PeSIT protocol only</p>
<p>Presence-check indicator of the receiver file used to determine the action of the monitor if the file being transferred already exists.</p>
<p>This parameter operates together with the <span class="code"><a href="#file_action">file_action</a></span> parameter.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">undefined</span> = not applicable (default)</li>
<li><span style="font-weight: bold;">new</span> = the file must be created by the monitor. The transfer is refused if the file already exists.</li>
<li><span style="font-weight: bold;">old</span> = the file must already exist</li>
<li><span style="font-weight: bold;">both</span> = if the file does not exist, it will be created</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>file_org (-f_org)</p>
<p><span style="font-style: italic;font-weight: bold;">Organization</span></p>         </td>
         <td><p>Type of file organization</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Sequential file (default)</li>
<li><span style="font-weight: bold;">I</span> = Indexed file</li>
<li><span style="font-weight: bold;">R</span> = Relative file</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>file_type (-ft)</p>
<p><span style="font-style: italic;font-weight: bold;">System file type</span></p>         </td>
         <td><p>Specify the file type depending on the system: BULL, AS400, GCOS and TANDEM machines.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>generate_xfb_subject (-gxs)</p>
<p>Add Gateway parameters to subject</p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Use this field to specify whether or not to add specific Gateway parameters to the email <span style="font-style: italic;">Subject</span> field</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span></li>
<li><span style="font-weight: bold;">N</span></li>
<li><span style="font-weight: bold;">U</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>group (-gr)</p>
<p><span style="font-style: italic;font-weight: bold;">Group</span></p>         </td>
         <td><p>Group name</p>         </td>
         <td><p>Up to 15 alphanumeric characters (default: <span style="font-weight: bold;">GDEFAULT</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>local_dir_name (-ldn)</p>
<p><span style="font-style: italic;font-weight: bold;">Local directory</span></p>         </td>
         <td><p>FTP, HTTP &amp; SFTP only</p>
<p>VFD absolute path of the local directory that stores the file to be sent.</p>
<p>Useful in Responder mode and direction OUT only.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>local_dir_name_alias (-ldna)</p>
<p><span style="font-style: italic;font-weight: bold;">Local directory alias</span></p>         </td>
         <td><p>FTP, HTTP &amp; SFTP only</p>
<p>VFD alias of the local directory that stores the file to be sent.</p>
<p>Useful in Responder mode and direction OUT only.</p>         </td>
         <td><p>Up to 32 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>local_file_name (-lfn)</p>
<p><span style="font-style: italic;font-weight: bold;">Local filename</span></p>         </td>
         <td><p>Protocol name of the file sent or received.</p>
<p>Useful in Responder mode only.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">model (-ml)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Model</span></p>         </td>
         <td><p><em>This parameter only exists for reasons of compatibility with earlier product versions.</em></p>
<p>Model name used to create a Transfer Request</p>
<p>One specific use case is to route a transfer using a <em>Model inside an Application</em>. This option is only available via online commands.<br />
For more information, refer to <a href="../../../../../managing_events_start_here/working_with_decision_rules_cli">Working with Decision Rules (command line)</a>.</p>         </td>
         <td><p>Up to 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>name (-n)</p>
<p><span style="font-style: italic;font-weight: bold;">Name</span></p>         </td>
         <td><p>Application name</p>         </td>
         <td><ul>
<li>PEL: Up to 8 alphanumeric characters</li>
<li>Other protocols: Up to 16 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>param1 (-p1)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 1</span></p>         </td>
         <td><p>User parameter 1</p>         </td>
         <td><p>Up to 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>param2 (-p2)</p>
<p><span style="font-style: italic;font-weight: bold;">Param 2</span></p>         </td>
         <td><p>User parameter 2</p>         </td>
         <td><p>Up to 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>received_file_ciphered (-rfc)</p>
<p><span style="font-style: italic;font-weight: bold;">Encrypt received files</span></p>         </td>
         <td><p>Received file encryption option</p>         </td>
         <td><p><span style="font-weight: bold;">Y/N</span></p>         </td>
      </tr>
      <tr>
         <td><p>rcv_appli (-ra)</p>
<p><span style="font-style: italic;font-weight: bold;">Application ID</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Receiver Application name</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_text (-rt)</p>
<p><span style="font-style: italic;font-weight: bold;">Message text</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Receiver free text</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_user (-ru)</p>
<p><span style="font-style: italic;font-weight: bold;">User ID</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Receiver user name</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>rec_fmt (-rf)</p>
<p><span style="font-style: italic;font-weight: bold;">Record format</span></p>         </td>
         <td><p>Record format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed records</li>
<li><span style="font-weight: bold;">FT</span> = Fixed Text records</li>
<li><span style="font-weight: bold;">V</span> = Variable records</li>
<li><span style="font-weight: bold;">VT</span> = Variable Text records</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>rec_len (-rl)</p>
<p><span style="font-style: italic;font-weight: bold;">Record length</span></p>         </td>
         <td><p>Record length</p>
<p>The record length value must be less than or equal to the <span class="code">data_size_max</span> attribute defined for the corresponding Remote Site.</p>         </td>
         <td><p>Integer between <span style="font-weight: bold;">0</span> and <span style="font-weight: bold;">32768</span> (default: <span style="font-weight: bold;">0</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>remote_dir_name (-rdn)</p>
<p><span style="font-style: italic;font-weight: bold;">Remote directory</span></p>         </td>
         <td><p>Absolute path of the remote directory that stores the file sent or received.</p>
<p>Useful in Initiator mode only.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>remote_file_name (-rfn)</p>
<p><span style="font-style: italic;font-weight: bold;">Remote file name</span></p>         </td>
         <td><p>Protocol name of the file sent or received.</p>
<p>Useful in Initiator mode only.</p>         </td>
         <td><p>Up to 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel_transfer_filter (-stf)</p>
<p><span style="font-style: italic;font-weight: bold;">Sentinel Transfer Filter</span></p>         </td>
         <td><p>Indicate notification level for Transfer state changes to send to Sentinel server.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>ALL</li>
<li>SUMMARY</li>
<li>NONE</li>
<li>UNDEFINED (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>snd_appli (-sa)</p>
<p><span style="font-style: italic;font-weight: bold;">Application ID</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Sender Application name</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>snd_text (-st)</p>
<p><span style="font-style: italic;font-weight: bold;">Message text</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Sender free text</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>snd_user (-su)</p>
<p><span style="font-style: italic;font-weight: bold;">User ID</span></p>         </td>
         <td><p>PeSIT HS E Store-and-Forward use only</p>
<p>Sender user name</p>         </td>
         <td><p>Up to 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>sys_dep (-sd)</p>
<p><strong>(<span style="font-style: italic;">none</span>)</strong></p>         </td>
         <td><p>For BULL, AS400, GCOS and TANDEM machines: File type is system-dependent.</p>         </td>
         <td><p>No value</p>         </td>
      </tr>
      <tr>
         <td><p>text_file</p>
<p><strong>(<span style="font-style: italic;">none</span>)</strong></p>         </td>
         <td><p>Text file flag</p>         </td>
         <td><p><span style="font-weight: bold;">Y/N</span> (default: N)</p>         </td>
      </tr>
      <tr>
         <td><p>truncating_allowed (-ta)</p>
<p><span style="font-style: italic;font-weight: bold;">Truncating allowed</span></p>         </td>
         <td><p>Truncating option</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = The data transferred will be truncated even if the removed data does not match the padding character</li>
<li><span style="font-weight: bold;">N</span> = Truncates a record only if the padding character matches the data to remove (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_data_code (-xdc)</p>
<p><span style="font-style: italic;font-weight: bold;">Data code</span></p>         </td>
         <td><p>Transfer data code</p>         </td>
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
<li><span style="font-weight: bold;">U</span> = Undefined (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_file_org (-xfg)</p>         </td>
         <td><p>Type of organization of the transferred file</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = sender (default)</li>
<li><span style="font-weight: bold;">I</span> = initiator</li>
<li><span style="font-weight: bold;">R</span> = receiver</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_padding (-xpad)</p>
<p><span style="font-style: italic;font-weight: bold;">Padding character</span></p>         </td>
         <td><p>Padding character</p>         </td>
         <td><p>Hexadecimal number between <span style="font-weight: bold;">0</span> and <span style="font-weight: bold;">FF</span> (default: <span style="font-weight: bold;">00</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>x_rec_fmt (-xrf)</p>
<p><span style="font-style: italic;font-weight: bold;">Record format</span></p>         </td>
         <td><p>Transfer format</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">F</span> = Fixed records</li>
<li><span style="font-weight: bold;">V</span> = Variable records</li>
<li><span style="font-weight: bold;">T</span> = Text (<span style="font-style: italic;">OFTP only</span>)</li>
<li><span style="font-weight: bold;">S</span> = Stream</li>
<li><span style="font-weight: bold;">U</span> = Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>x_rec_len (-xrl)</p>
<p><span style="font-style: italic;font-weight: bold;">Record length</span></p>         </td>
         <td><p>Transfer record length</p>         </td>
         <td><p>Integer between <span style="font-weight: bold;">0</span> and <span style="font-weight: bold;">32768</span> (default: <span style="font-weight: bold;">0</span>)</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Applications (command line)](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
