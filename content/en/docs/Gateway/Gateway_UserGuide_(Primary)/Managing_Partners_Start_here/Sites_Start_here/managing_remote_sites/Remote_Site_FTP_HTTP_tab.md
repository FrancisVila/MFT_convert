{
    "title": "New Remote Site: FTP, HTTP, FTP/HTTP tabs",
    "linkTitle": "FTP/HTTP tab",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

This topic describes the fields on the following tabs of the <span style="font-style: italic;">New Remote Site</span> window:

-   FTP/HTTP
-   FTP
-   HTTP

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>HTTP/FTP: Protocol security:</p>         </td>
      </tr>
      <tr>
         <td><strong>ID to Send</strong> (field)<br />
<span style="font-weight: normal;">+ <strong>Set password to send to partner</strong> (button)</span>         </td>
         <td><p>Optional</p>
<p>Enter the identifier and password to send during the connection phase.<br />
Maximum: 63 alphanumeric characters in the ID field and 127 alphanumeric characters in the password field.</p>
<p>In client mode, Gateway uses the values that you set in these fields for the login phase on a remote server.</p>         </td>
      </tr>
      <tr>
         <td><strong>ID to Check</strong> (field)<strong><br />
</strong>+ <strong>Set password to receive from partner</strong> (button)<strong></strong>         </td>
         <td><p>Enter the identifier and password used to check partner identity. The identifier corresponds to the protocol identifier.</p>
<p>In server mode this field is mandatory. Gateway uses these values to check user/password values provided by the client.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>HTTP CGI Parameters /</p>
<p>FTP Specific command</p>         </td>
         <td><p>Enter specific FTP <span class="code">SITE</span> or <span class="code">QUOTE</span> commands or HTTP CGI parameters to send before or after the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Application method</p>         </td>
         <td><p>Responder mode only</p>
<p>Select the method to use to retrieve the Application object:</p>
<ul>
<li><span style="font-weight: bold;">User exit</span>: select this option if the Application name is not in the Remote Site definition, or when you need additional information to identify the Application name</li>
<li><span style="font-weight: bold;">User message field</span>: the Application is located in the AIM field and is transmitted with the FTP <span class="code">SITE</span> command</li>
<li><span style="font-weight: bold;">File name</span>: the Application is named in the file name parameter</li>
</ul>
<p>Note that if the Application is not defined in the method that you select in this field, the Transfer Request is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Acknowledgement option</p>         </td>
         <td><p>Select one of the following acknowledgement options:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span>: acknowledgement behavior not known (default)</li>
<li><span style="font-weight: bold;">Not to ack</span>: no reply expected</li>
<li><span style="font-weight: bold;">By monitor</span>: Gateway automatically sends an acknowledgement request</li>
<li><span style="font-weight: bold;">By user</span>: waits for a user acknowledgement request</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FTP:</p>         </td>
      </tr>
      <tr>
         <td><p>Disable Gateway specific behavior</p>         </td>
         <td><p>Select this option to disable the use of FTP commands specific to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Allow different IP addresses for control and data sessions</p>         </td>
         <td><p>The remote IP address of a proxy control session may be different from the remote address of its data session.</p>
<p>Select this option to disable the protection against FTP bounce attacks and allow different IP addresses for control and data sessions.</p>         </td>
      </tr>
      <tr>
         <td><p>Restart allowed</p>         </td>
         <td><p>Select this option to enable the restart function. This allows Gateway to restart Transfers interrupted by incidents.</p>
<p>In BLOCK or COMPRESSED mode, synchronization points are sent with the data. When you restart a Transfer, a synchronization point is negotiated, and both partners can start managing the file at the position they kept.</p>
<p>Gateway records these synchronization points in the Mailbox. This means that you cannot restart Transfers stored in real directories in BLOCK or COMPRESSED mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Restart type</p>         </td>
         <td><p>Select one of the following restart modes:</p>
<ul>
<li><span style="font-weight: bold;">Stream</span>: The client sends the restart offset to the server and both partners initialize their file access depending on the restart offset. The Transfer can then begin again. The client determines the restart point depending on the size of the data already received:
<ul>
<li>If downloading the file, the client knows the size already received</li>
<li>If uploading the file, the client must use the FTP <span class="code">SIZE</span> command to determine the size already received by the server</li>
</ul></li>
<li><span style="font-weight: bold;">Block and Compressed</span>: during data exchange, some restart information is sent in the data flow. The restart point can be a string of alphanumeric characters without a SPACE (<span class="code">" "</span>).</li>
<li><span style="font-weight: bold;">All</span>: enable Stream, Block and Compressed restart modes</li>
<li>None</li>
</ul>
<p>Note that you cannot set the Restart type to <span style="font-weight: bold;">Block and Compressed</span> if the <span style="font-weight: bold;">Transfer mode</span> is set to <span style="font-weight: bold;">None</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer mode</p>         </td>
         <td><p>You can transfer data in stream, block, or compressed mode.</p>
<ul>
<li><span style="font-weight: bold;">Stream mode:</span> In stream mode, a new data connection is established for each Transfer. In this mode, the Site can send and receive different files simultaneously. Stream mode is <span style="font-weight: bold;">always</span> available, regardless of the value you select in this field.</li>
<li><span style="font-weight: bold;">Block and compressed modes:</span> In these modes, the data connection may be kept open, depending on the FTP response code sent by the Responder after the end of each Transfer.</li>
</ul>
<p>Select one of the following Transfer modes:</p>
<ul>
<li>(Empty)</li>
<li><span style="font-weight: bold;">None</span> (Stream mode only) (default)</li>
<li><span style="font-weight: bold;">Compressed</span></li>
<li><span style="font-weight: bold;">Block</span></li>
<li><span style="font-weight: bold;">Block and compressed</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Data structure</p>         </td>
         <td><p>Select one of the following data structures:</p>
<ul>
<li><span style="font-weight: bold;">File</span>: no internal structure is defined and the file is considered to be a continuous sequence of data bytes</li>
<li><span style="font-weight: bold;">Record</span>: the file is made up of sequential records</li>
<li><span style="font-weight: bold;">File and Record</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Passive mode</p>         </td>
         <td><p>In passive mode, the client always initiates the data session.</p>
<p>Select one of the following passive mode options:</p>
<ul>
<li><span style="font-weight: bold;">Responder and Initiator</span></li>
<li><span style="font-weight: bold;">Responder</span>: if the Site is the responder, it must accept <span class="code" style="font-weight: bold;">PASV</span> commands</li>
<li><span style="font-weight: bold;">Initiator</span>: if the Site is the client, it can use <span class="code" style="font-weight: bold;">PASV</span> commands</li>
<li><span style="font-weight: bold;">None</span> (default): the Site does not accept <span class="code" style="font-weight: bold;">PASV</span> commands</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Quotas:</p>
<p>Use the quotas section to defend against hammer attacks. A hammer attack can occur when a user floods the server with requests until it can no longer respond to any other users.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum uploads<br />
B/min</p>         </td>
         <td><p>Set the maximum number of Kbytes that you can upload to this Remote Site per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum uploads<br />
Requests/min</p>         </td>
         <td><p>Set the maximum number of Transfer Requests that you can upload per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum uploads<br />
MB</p>         </td>
         <td><p>Set the maximum file size in MB.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum downloads<br />
KB/min</p>         </td>
         <td><p>Set the maximum number of Kbytes of data that you can download from this Remote Site per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum downloads<br />
Requests/min</p>         </td>
         <td><p>Set the maximum number of Transfer Requests that you can download per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Command sensitivity</p>         </td>
         <td><p>Move the sensitivity cursor to the level of sensitivity required.</p>
<p>This parameter allows you to define the number of commands that you can pass during a session. Each command corresponds to a certain credit, depending on how costly the command is in terms of memory and system resources. The higher the sensitivity, the fewer commands you can pass.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>FTP CS List fields</p>         </td>
         <td><p>Select this option in Responder mode to define which columns to send to FTPCS clients in the LIST command.</p>
<p>Click the <span style="font-weight: bold;">FTP CS List fields</span> button to display the list of fields that you can send to the FTPCS client. By default, all columns are listed.</p>
<p>Regardless of the field order that you specify, fields are always sent in the same predefined order (as listed below).</p>
<p>Check one or more of the following:</p>
<ul>
<li><span style="font-weight: bold;">LOCID</span>: local_ident</li>
<li><span style="font-weight: bold;">GTYPE</span>: VFD type (real or virtual directory, mount point, real or virtual file)</li>
<li><span style="font-weight: bold;">RIGHTS</span>: VFD rights</li>
<li><span style="font-weight: bold;">FILENAME</span>: long name - <span style="font-style: italic;">s&lt;xfer_ident&gt;.&lt;filename&gt;</span> for a virtual file, otherwise <span style="font-style: italic;">&lt;filename&gt;</span></li>
<li><span style="font-weight: bold;">SFILENAME</span>: short name - <span style="font-style: italic;">&lt;filename&gt;</span> only</li>
<li><span style="font-weight: bold;">APPLI</span>: Application name</li>
<li><span style="font-weight: bold;">SIZE</span>: file size</li>
<li><span style="font-weight: bold;">DATE</span>: date of last modification/ creation of transfer</li>
<li><span style="font-weight: bold;">TYPE</span>: MVS transfer state</li>
<li><span style="font-weight: bold;">RSTATE</span>: routing state (T: to route, R: routed, A: acked)</li>
<li><span style="font-weight: bold;">UMSG</span>: user message</li>
<li><span style="font-weight: bold;">ORG</span>: origin</li>
<li><span style="font-weight: bold;">DEST</span>: destination</li>
<li><span style="font-weight: bold;">P1</span>: parameter 1</li>
<li><span style="font-weight: bold;">P2</span>: parameter 2</li>
<li><span style="font-weight: bold;">PERM</span>: permanent transfer</li>
<li><span style="font-weight: bold;">DATA_CODE</span>: B for binary, T for test</li>
</ul>
<p>If the item described in the list is not a virtual file, the only significant fields are GTYPE, RIGHTS, FILENAME, SFILENAME, DATE and SIZE. The Gateway FTP server completes these fields.</p>
<p>LOCID and GTYPE are required fields and are always sent to the client.</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP client:</p>         </td>
      </tr>
      <tr>
         <td><p>Identification method</p>         </td>
         <td><p>Select the identification method to use when transferring files:</p>
<ul>
<li><span style="font-weight: bold;">Anonymous</span>: sends neither user nor password</li>
<li><span style="font-weight: bold;">CGI</span>: adds user and password to the CGI parameters</li>
<li><span style="font-weight: bold;">Web</span>: standard HTTP identification method (adds user and password to HTTP headers)</li>
<li><span style="font-weight: bold;">Cookies</span>: adds user and password to CGI parameters of the login request. Each subsequent Transfer Request does not send these parameters, but rather the cookies received with the login response. If you select this option, complete the <span style="font-weight: bold;">Login request</span> fields.</li>
<li><p><strong>NTLM</strong>: use NTLM authentication (based on configured user and password)</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Send transfer attributes</p>         </td>
         <td><p>Check this box to send the following Transfer attributes with the file:</p>
<ul>
<li><span class="code">appli</span></li>
<li><span class="code">dest</span></li>
<li><span class="code">org</span></li>
<li><span class="code">xfer_ident</span></li>
<li><span class="code">msg</span></li>
</ul>
<p>These attributes are sent as CGI parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>User agent</p>         </td>
         <td><p>Enter the ID of the client application used to contact the remote partner. This information is useful for certain logging and statistics processes.<br />
Maximum: 128 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Login request</span> (only available if you set <span style="font-weight: bold;">Identification method</span> to <span style="font-weight: bold;">Cookies</span>):</p>         </td>
      </tr>
      <tr>
         <td><p>Login path</p>         </td>
         <td><p>Specify the URL path to the server CGI script that will identify Gateway and return the cookie. Specify the path to use with the login request. For example: <span class="code">/cgi-bin/login.cgi</span>. This is not an absolute URL.<br />
Maximum: 256 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP method</p>         </td>
         <td><p>Select the HTTP method to use with the login request:</p>
<ul>
<li>GET</li>
<li>POST</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Login CGI parameters</p>         </td>
         <td><p>Optional</p>
<p>Enter additional CGI parameters to add to the login requests.</p>
<p>Maximum 80 alphanumeric characters in the format:</p>
<p>login_param1=value1&amp;login_param2=value2</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About FTP](../../../../protocols_about/ftp_about)

[About HTTP](../../../../protocols_about/http_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
