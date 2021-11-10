{
    "title": "New Transfer Request: HTTP/FTP tab",
    "linkTitle": "HTTP/FTP tab",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>HTTP CGI parameters/ FTP user command</p>         </td>
         <td><p>Depending on the protocol, complete this field as follows:</p>
<ul>
<li><span style="font-weight: bold;">FTP:</span> Send special remote commands or unsupported FTP commands to the remote server before or after the Transfer. <span class="code">SITE</span>, <span class="code">QUOTE</span> and <span class="code">SCRIPT</span> commands are supported.
<ul>
<li><span class="code">SITE</span> and <span class="code">QUOTE</span> commands indicate pre-Transfer processing. For post-Transfer processing, use <span class="code">AE_QUOTE</span> and <span class="code">AE_SITE</span> (ended state if errors occur) or <span class="code">AC_QUOTE</span> and <span class="code">AC_SITE</span> (canceled state if errors occur).<br />
Enter the command in the following format:<br />
<span class="code">SITE &lt;fct1&gt; &lt;param1&gt;; SITE &lt;fct2&gt; &lt;param2&gt;</span></li>
<li><span class="code">SCRIPT</span> commands reference a script that contains a set of FTP (<span class="code">SITE</span> and <span class="code">QUOTE</span>) commands:<br />
<span class="code">SCRIPT &lt;script_xfer&gt;</span><br />
Refer to <a href="../../../../protocols_about/ftp_about/ftp_initiator_mode#SCRIPT">Calling a script</a>.</li>
</ul></li>
<li><span style="font-weight: bold;">HTTP:</span> Add CGI parameters to the Transfer Request in the following format:<span class="code"><br />
xfer_param1=value1&amp;xfer_param2=value2</span></li>
<li><strong>SWIFTNet InterAct:</strong> Specify either:
<ul>
<li>Payload attributes in the following format:<br />
<span class="code">attrib1=\"value1\"</span></li>
<li>Compression information in the following format:<br />
<span class="code">dt=\"GZIP-Base64\"</span></li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FTP</p>         </td>
      </tr>
      <tr>
         <td><p>Unique file name option</p>         </td>
         <td><p>FTP store unique option (<span class="code">STOU</span> command).</p>
<p>Use this option to assign a unique file name on the server. If a previous file with the same name exists on the server, a ".1" suffix is added to the file name. If a file name with this suffix already exists, the suffix is replaced with ".2" and so on until a unique name is found.</p>
<p>The <span class="code">STOU</span> command is supported in both real and virtual directories.</p>         </td>
      </tr>
      <tr>
         <td><p>Append option</p>         </td>
         <td><p>Use this option on the client side in sender mode. This option allows you to add data to the end of a received file.</p>
<p>To enable the append option, select <span style="font-weight: bold;">Yes</span>. Otherwise, select <span style="font-weight: bold;">No</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory listing type</p>         </td>
         <td><p>DIR Transfer types in Initiator/Receiver mode only.</p>
<p>Use this field to specify how to list the directory contents.</p>
<p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Names</span> (default): the <span class="code">NLST</span> command returns a basic list of directory contents. This option does not differentiate between files and directories, and provides no extra information such as the last modification date, the file size, and so on.</li>
<li><span style="font-weight: bold;">Long</span>: the <span class="code">LIST</span> command returns a detailed list of directory contents. For example, this option differentiates between files and directories. The LONG format depends on the server and is typically in a UNIX format.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>HTTP</p>         </td>
      </tr>
      <tr>
         <td><p>Request method</p>         </td>
         <td><p>Specify the method to use for HTTP Transfers:</p>
<ul>
<li><span style="font-weight: bold;">Get</span> or <span style="font-weight: bold;">Post</span> for incoming data</li>
<li><span style="font-weight: bold;">Post</span> or <span style="font-weight: bold;">Put</span> for outgoing data</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[About FTP](../../../../protocols_about/ftp_about)

[About HTTP](../../../../protocols_about/http_about)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
