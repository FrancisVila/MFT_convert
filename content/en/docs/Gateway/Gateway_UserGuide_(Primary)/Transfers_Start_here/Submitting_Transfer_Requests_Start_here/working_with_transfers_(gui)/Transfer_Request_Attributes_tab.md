{
    "title": "New Transfer Request: Attributes tab",
    "linkTitle": "Attributes tab",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Managing Transfers

Use the **Attributes** tab to define the properties of the transferred file.

Many of the fields on this tab correspond to Application object parameters. If you select an Application to use for this Transfer, you do not need to complete the fields on this tab. If you select an Application <span style="font-weight: bold;">and</span> complete fields here, the Transfer parameters override the Application parameters.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local attributes</p>         </td>
      </tr>
      <tr>
         <td><p>File component</p>         </td>
         <td><p>For files to be sent, enter the local file name (without the file path) of the physical file to send.</p>
<p>For files to be received, enter the physical name of the incoming file.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Record format</p>         </td>
         <td><p>Select the record format for the local file:</p>
<ul>
<li>Variable text</li>
<li>Variable</li>
<li>Fixed text</li>
<li>Fixed</li>
<li>Stream</li>
<li>Undefined</li>
<li>(Empty)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record length</p>         </td>
         <td><p>Specify the record length.<br />
Integer: <span style="font-weight: bold;">0 - 32768</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Data code</p>         </td>
         <td><p>Select the data code for the local file.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer attributes</p>         </td>
      </tr>
      <tr>
         <td><p>Directory name</p>         </td>
         <td><p>FTP, SFTP and HTTP only</p>
<p>Enter the absolute path of the directory that contains the file to transfer. This location is the destination of the file in the case of outgoing Transfers, or the path for an incoming Transfer.</p>
<p>If you specified:</p>
<ul>
<li><span style="font-weight: bold;">Initiator</span> mode on the <span style="font-weight: bold;">General</span> tab, specify a directory on the remote system</li>
<li><span style="font-weight: bold;">Responder</span> mode on the <span style="font-weight: bold;">General</span> tab, click the <span style="font-weight: bold;">Browse</span> button to select a directory in the VFD</li>
<li><span style="font-weight: bold;">DIR</span> in the <span style="font-weight: bold;">Type</span> field on the <span style="font-weight: bold;">General</span> tab, specify the directory whose contents you want to list. For FTP Transfers, you <span style="font-weight: bold;">must</span> add the file separator / at the end of the directory name. (The separator character is added automatically for HTTP Transfers.)</li>
</ul>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory alias</p>         </td>
         <td><p>FTP, SFTP and HTTP only</p>
<p>This field is only available if you selected <span style="font-weight: bold;">Responder</span> in the <span style="font-weight: bold;">Mode</span> field on the <span style="font-weight: bold;">General</span> tab.</p>
<p>Enter the alias of the VFD directory that contains the file to transfer.<br />
Maximum: 24 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>File name</p>         </td>
         <td><p>The value that you enter in this field depends on the Transfer type. If you selected:</p>
<ul>
<li><strong>DIR</strong> in the <strong>Type</strong> field on the <strong>General</strong> tab, this field is valid only for Gateway-to-Gateway transfers and it is optional. Use this field to define a filter on the file names returned by the server. For example, if you set this value to <span class="code">*.txt</span>, the server returns all .txt files in the directory that you specify in the <strong>Directory name</strong> field. If you do not fill in this field, Gateway does not set a default value. For DIR transfers to servers different from Gateway, this field should be left blank.</li>
<li><strong>Anything else</strong>, enter a file name for the transferred file. This file name is transmitted to the Transfer recipient.<br />
Maximum: 127 alphanumeric characters.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File type</p>         </td>
         <td><p>PeSIT only</p>
<p>Enter the protocol file type.<br />
<span style="font-weight: bold;">1 - 65535</span>.</p>
<p>Reserved values:</p>
<ul>
<li>65535 = MSG</li>
<li>65534 = EERP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record format</p>         </td>
         <td><p>Select the record format for the transferred file:</p>
<ul>
<li><span style="font-weight: bold;">Fixed</span></li>
<li><span style="font-weight: bold;">Variable</span></li>
<li><span style="font-weight: bold;">Stream</span></li>
<li><span style="font-weight: bold;">Text</span> <span style="font-style: italic;">(OFTP only)</span></li>
<li><span style="font-weight: bold;">Undefined</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record length</p>         </td>
         <td><p>Specify the record length for the transferred file.<br />
Integer: <span style="font-weight: bold;">0 - 32768</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Data code</p>         </td>
         <td><p>Select the data code for the transferred file.</p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>This option allows you to specify the compression options for the transferred file.<br />
Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">No</span></li>
<li><span style="font-weight: bold;">Horizontal</span></li>
<li><span style="font-weight: bold;">Vertical</span></li>
<li><span style="font-weight: bold;">Both</span></li>
<li><span style="font-weight: bold;">Zlib</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Newline convention</p>         </td>
         <td><p>SFTP only</p>
<p>Set the end-of-line code, depending on the remote system type. This parameter is valid for text file transfers in both send and receive mode. Although this parameter is also available in the Remote Site definition, the Transfer Request parameter takes priority.</p>
<p>Enter one of the following values:</p>
<ul>
<li><strong>U</strong> for UNIX</li>
<li><strong>W</strong> for Windows</li>
<li>Blank for Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Format</p>         </td>
      </tr>
      <tr>
         <td><p>Padding character (Hexa)</p>         </td>
         <td><p>Specify the padding character code.<br />
You can enter two characters, from <span style="font-weight: bold;">00</span> to <span style="font-weight: bold;">FF</span>.<br />
Commonly-used value: <span style="font-weight: bold;">20</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Truncating allowed</p>         </td>
         <td><p>If the Transfer uses the truncating feature, this option allows you to truncate a record without taking into account the padding character.</p>         </td>
      </tr>
      <tr>
         <td><p>Multi transfer parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Filter</p>         </td>
         <td><p>FTP and SFTP multiple transfers only</p>
<p>Specify the filtering criteria to select files to send or receive. You can filter according to:</p>
<ul>
<li><p><span style="font-weight: bold;">Time</span>:</p>
<blockquote>
<p><span class="code">time = [ last | rounded ] N [ day[s] hour[s] | minute[s] ]</span></p>
<p><span class="code">[ yyyymmdd &lt;= ] time [ &lt;= yyyymmddss ]</span></p>
<p><span class="code">[ yyyymmddhhmmss &lt;= ] time [ &lt;= yyyymmddhhmmss ]</span></p>
<p>For example, if it is currently 2007/06/13 17:15:28, then:</p>
<p>last1day = 2007/06/12 17:15:28</p>
<p>rounded1day = 2007/06/13 00:00:00</p>
<p>last3days = 2007/06/10 17:15:28</p>
<p>rounded3days = 2007/06/11 00:00:00</p>
<p>last1hours = 2007/06/12 16:15:28</p>
<p>rounded1hours = 2007/06/12 17:00:00</p>
</blockquote></li>
<li><p><span style="font-weight: bold;">File size</span>:</p>
<blockquote>
<p><span class="code">[ min &lt; ] size [ &lt; max ]</span></p>
<p>Specify the file size in bytes.</p>
</blockquote></li>
<li><p><span style="font-weight: bold;">File name</span>:</p>
<blockquote>
<p><span class="code">name = regexp (use StringMatch)</span></p>
</blockquote></li>
</ul>
<p>Example:</p>
<p><span class="code">"20070528 &lt;= time &lt;= 20070609 ; 1 &lt; size &lt; 100000 ; name = *.dat"</span></p>         </td>
      </tr>
      <tr>
         <td><p>Hash type</p>         </td>
         <td><p>FTP and SFTP multiple transfers only</p>
<p>Select the type of hashing to use.</p>
<p>This parameter determines whether all files in a directory will be transferred a second time or only those files that have changed since the initial transfer. This is useful if a transfer has been interrupted or only updated files need to be sent.</p>
<p>Possible values:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: No hash. No check of duplicate file transfers is made. All files are transferred again.</li>
<li><span style="font-weight: bold;">1</span>: (default) Gateway checks the following criteria to determine if a file has changed since the initial transfer:
<ul>
<li>Alias of the partner</li>
<li>Direction</li>
<li>File size</li>
<li>File date</li>
<li>Directory name of the master</li>
<li>File name (short for MGET, long for MPUT)</li>
</ul>
<br />
If none of these criteria has changed, the file is considered as unchanged and is therefore not sent.</li>
<li><span style="font-weight: bold;">2</span>: <span style="font-style: italic;">For future use</span></li>
<li><span style="font-weight: bold;">3</span>: <span style="font-style: italic;">For future use</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Model to use for child transfers</p>         </td>
         <td><p>FTP and SFTP multiple transfers only</p>
<p>Select the name of the Model to use to deposit <span style="font-style: italic;">child</span> transfers.</p>
<p>If this parameter is not filled-in, the Transfer Request for a <span style="font-style: italic;">child</span> is created using the Application of the <span style="font-style: italic;">master</span>. In all cases, a Transfer Request for a <span style="font-style: italic;">child</span> is made with <span style="font-weight: bold;">Type</span> = TRANS and <span style="font-weight: bold;">Mode</span>, <span style="font-weight: bold;">Direction</span>, <span style="font-weight: bold;">Originator alias</span> and <span style="font-weight: bold;">Destination alias</span> derived from the <span style="font-style: italic;">master</span>.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[Transferring multiple files with FTP](../../../../protocols_about/ftp_about/ftp_multiple_file_transfer)

[Transferring multiple files with SFTP](../../../../protocols_about/sftp_about/sftp_multiple_file_transfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
