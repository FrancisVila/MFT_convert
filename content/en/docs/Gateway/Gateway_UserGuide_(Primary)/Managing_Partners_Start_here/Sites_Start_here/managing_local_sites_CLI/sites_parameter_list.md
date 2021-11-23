{
    "title": "Site objects: Parameters List",
    "linkTitle": "Site objects: Parameters List",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Managing Partners

[Standard Site parameters](#Standard_parameters)

[Communication path parameters](#Communication_path_parameters)

[Additional Site parameters for JMS](#JMS_site_parameters)

[Additional Site parameters for SWIFTNet](#SWIFTNet_site_parameters)

[Additional Site parameters for X.400](#x400_site_parameters)

<span id="Standard_parameters"></span>

## Standard Site parameters

The following table lists standard Site command parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in **italics**.

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
         <td><p>-acknowledgment_option (-ao)</p>
<p>Acknowledgement option</p>         </td>
         <td><p>PeSIT HS E, FTP, OFTP and POP3 only</p>
<p>Acknowledgement behavior</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">ack_by_monitor</span> = automatically send an acknowledgement request</li>
<li><span class="code" style="font-weight: bold;">ack_by_user</span> = wait for a user acknowledgement request</li>
<li><span class="code" style="font-weight: bold;">not_to_ack</span> = no acknowledgement</li>
<li><span class="code" style="font-weight: bold;">ack_unknown</span> = acknowledgement behavior undefined (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-alias (-a)</p>
<p><span style="font-style: italic;font-weight: bold;">Alias</span></p>         </td>
         <td><p>Site alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-attach_extract_file (-aef)</p>
<p><span style="font-style: italic;font-weight: bold;">Attach / Extract file</span></p>         </td>
         <td><p>SMTP/POP3 only</p>
<p>Define whether or not to attach or extract a file by default.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span> if the file is not formatted as an email</li>
<li><span style="font-weight: bold;">No</span> if the file is already formatted as an email</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-auth_obj_name</p>
<p>Authentication certificate: Name</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the name of the authentication certificate to use.</p>         </td>
         <td><p>Maximum: 639 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-auth_obj_type</p>
<p>Authentication certificate: Type</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the type of authentication certificate to use.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>SECS_ALIAS</li>
<li>XPP_ENTITY</li>
<li>XPP_CERTIFICATE</li>
</ul>         </td>
      </tr>
      <tr>
         <td><code style="font-weight: bold;">-bypass_xsr (-byxsr)</code>
<p><em>Bypass XSR for this site</em></p>         </td>
         <td>If active, all outgoing connections to this site will be made directly, even if XSR is enabled. This setting overrides the global setting for the address masks to skip XSR in outgoing calls.         </td>
         <td><ul>
<li>Yes: all outgoing calls are made directly (bypassing XSR)</li>
<li>No: outgoing calls are made through XSR, if XSR is enabled</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-change_data_addr (-cda)</p>
<p><span style="font-style: italic;font-weight: bold;">Allow different IP addresses for control and data sessions</span></p>         </td>
         <td><p>FTP only</p>
<p>Disables protection against FTP bounce attacks by allowing different IP addresses for control and data sessions</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-check_login_ident (-chkl_id)</p>
<p>Depending on protocol:</p>
<p>(Pre-Connection) ID to receive from partner</p>
<p>Username to check</p>         </td>
         <td><p>PeSIT, SFTP only</p>
<p>Pre-connection identifier to check from the partner</p>         </td>
         <td><ul>
<li>PeSIT: Up to 8 alphanumeric characters</li>
<li>SFTP: Up to 24 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-check_login_password (-chkl_password)</p>
<p>Depending on protocol:</p>
<p>(Pre-Connection) Password to receive from partner</p>
<p>Password to check</p>         </td>
         <td><p>PeSIT and SFTP</p>
<p>Also for X.400 - described later in this topic</p>
<p>Pre-connection password to check from the partner</p>         </td>
         <td><ul>
<li>PeSIT: Up to 8 alphanumeric characters</li>
<li>SFTP: Up to 14 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-check_password (-c_pswd)</p>
<p><span style="font-style: italic;font-weight: bold;">(Connection phase) Client password to check</span></p>         </td>
         <td><p>Client connection password to check by the server</p>         </td>
         <td><p>Maximum: 15 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-check_password2 (-c_pswd2)</p>
<p><span style="font-style: italic;font-weight: bold;">(Connection phase) Server password to check</span></p>         </td>
         <td><p>PeSIT HS</p>
<p>Corresponds to the password field in PI 5 of FPDU_ACKCONNECT</p>         </td>
         <td><ul>
<li>PeSIT HS D: a numeric value less than <span style="font-weight: bold;">65536</span></li>
<li>PeSIT HS E: up to 8 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-check_window (-cw)</span></p>
<p>Depending on protocol:</p>
<p>Synchronization acknowledgment window</p>
<p>Number of blocks between acknowledgments</p>
<p>Network credit</p>
<p>Pipeline level</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">PeSIT</span><span style="font-weight: bold;">:</span> Synchronization acknowledgement window: number of synchronization points between two acknowledgement messages</li>
<li><span style="font-weight: bold;">PEL:</span> Number of data blocks between acknowledgments</li>
<li><span style="font-weight: bold;">OFTP:</span> Number of Data Exchange Buffers the sender can send before the end of file or the credit value is reached. The sender must then wait for an acknowledgement (a CDT response) before sending more DATA commands.</li>
<li><span style="font-weight: bold;">SFTP:</span> Pipeline level: maximum number of outstanding buffers (non-acknowledged) that the client may send to the server before waiting for an acknowledgement</li>
</ul>         </td>
         <td><ul>
<li>PeSIT, PEL: Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">4</span><br />
(<span style="font-weight: bold;">0</span> means that no synchronization points are used.)<br />
Default: <span style="font-weight: bold;">4</span></li>
<li>OFTP: Integer: <span style="font-weight: bold;">0</span> – <span style="font-weight: bold;">99</span><br />
(<span style="font-weight: bold;">0</span> means that no synchronization points are used.)</li>
<li>SFTP: Integer: <span style="font-weight: bold;">0</span> – <span style="font-weight: bold;">255</span><br />
(the values <span style="font-weight: bold;">0</span> and <span style="font-weight: bold;">1</span> are equivalent.)<br />
Default: <span style="font-weight: bold;">0</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-command_sensitivity (-cmd_s)</p>
<p><span style="font-style: italic;font-weight: bold;">Command sensitivity</span></p>         </td>
         <td><p>FTP security</p>
<p>Level of command sensitivity.</p>
<p>This parameter allows you to define the number of commands that you can pass during a session. Each command corresponds to a certain credit, depending on how costly the command is in terms of memory and system resources. The higher the sensitivity, the fewer commands you can pass.</p>         </td>
         <td><p>Integer: 1 - 5.</p>
<p>1 is the lowest level of sensitivity.</p>         </td>
      </tr>
      <tr>
         <td><p>-comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>User comments</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-commpath_used (-cu)</p>
<p>(None)</p>         </td>
         <td><p><span style="font-style: italic;">Starting a Remote Site and displaying Site status:</span></p>
<p>Communication path used to connect the Site</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">MAIN</span> = Main communication address</li>
<li><span style="font-weight: bold;">ALT1</span> = First backup communication address</li>
<li><span style="font-weight: bold;">ALT2</span> = Second backup communication address</li>
<li><span style="font-weight: bold;">ALT3</span> = Third backup communication address</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-conn_hold_delay (-hold_delay)</p>
<p>Connection hold delay</p>         </td>
         <td><p>PeSIT HS only</p>
<p>The time (in seconds) that the connection remains active without any transmission events.</p>
<p>Use this parameter in conjunction with the parameters:</p>
<ul>
<li>permanent_conn</li>
<li>heartbeat_rate</li>
</ul>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-data_size_max (-ds)</p>
<p>Maximum data block size</p>         </td>
         <td><p>Maximum data block size in bytes</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">128</span> - <span style="font-weight: bold;">32768</span><br />
(default: <span style="font-weight: bold;">4000</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-data_window (-dw)</p>
<p>Depending on protocol:</p>
<p>Interval between synchronization points</p>
<p>Data windows</p>         </td>
         <td><p>Interval between synchronization points. Synchronization points are used to set the position in the file during the restart phase.</p>
<ul>
<li><span style="font-weight: bold;">PeSIT</span><span style="font-weight: bold;">:</span> maximum number of Kbytes sent before the sending Site sends a synchronization point to the receiving Site</li>
<li><span style="font-weight: bold;">OFTP:</span> maximum number of buffers sent or received before the Site puts a synchronization point into the Mailbox</li>
</ul>         </td>
         <td><ul>
<li>PeSIT: Integer: <span style="font-weight: bold;">–1 – 999</span><br />
(<span style="font-weight: bold;">–1</span> = synchronization points not used)<br />
Default: <span style="font-weight: bold;">100</span></li>
<li>OFTP: Integer: <span style="font-weight: bold;">1 – 999</span><br />
Default: <span style="font-weight: bold;">100</span><br />
(<span style="font-weight: bold;">0</span> means that no synchronization points are used.)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-dir_path (-dp)</p>
<p><span style="font-style: italic;font-weight: bold;">Directory for received files</span></p>         </td>
         <td><p>The directory of the local file management system where received files are stored.</p>         </td>
         <td><p>Maximum: 127 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-disable_sftpv6(-nov6)</span></p>
<p><em>Disable SFTPv6</em></p>
<p><em></em></p>         </td>
         <td><p><em>SFTP only</em></p>
<p>Disable SFTPv6</p>         </td>
         <td><p>One of:</p>
<ul>
<li><strong>Y</strong> - SFTPv6 will not be negotiated (server role - not advertised, client role - not selected) nor accepted (server role, when client is starting directly with SFTPv6, Gateway server will respond with SFTPv3).<br />
Only SFTPv3 will be used for this remote site.</li>
<li><strong>N</strong> (default) - SFTPv6 is preferred (whenever available).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-eerp_style (-es)</p>
<p><span style="font-style: italic;font-weight: bold;">EERP style</span></p>         </td>
         <td><p>OFTP only</p>
<p>Acknowledgement style</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">FR</span> = French</li>
<li><span style="font-weight: bold;">IN</span> = International</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-error_mail_disposal (-emd)</p>
<p><span style="font-style: italic;font-weight: bold;">Mail disposition on error</span></p>         </td>
         <td><p>POP3 only</p>
<p>Behavior in case of error during transfer</p>         </td>
         <td><p>One of:</p>
<ul>
<li>undefined</li>
<li>leave</li>
<li>delete</li>
<li>recover (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ftpcs_list_fields (-ftpcs_lf)</span></p>
<p><span style="font-style: italic;font-weight: bold;">FTP CS List fields</span></p>         </td>
         <td><p>In Responder mode, this parameter defines which columns will be sent in the <span class="code">LIST</span> command to FTPCS clients.</p>
<p>If the item described in the list is not a virtual file, the only significant fields are GTYPE, RIGHTS, FILENAME, SFILENAME, DATE and SIZE. The Gateway FTP server completes these fields.</p>
<p>By default, the parameter lists all fields.</p>
<p>Regardless of the field order that you specify, fields are always sent in the same predefined order.</p>
<p>LOCID and GTYPE are required fields and are always sent to the client.</p>         </td>
         <td><p>A list of one or more of the following, separated by a comma:</p>
<ul>
<li>LOCID: local_ident</li>
<li>GTYPE: VFD type (real or virtual directory, mount point, real or virtual file)</li>
<li>RIGHTS: VFD rights</li>
<li>FILENAME: long name - s&lt;xfer_ident&gt;.&lt;filename&gt; for a virtual file, otherwise &lt;filename&gt;</li>
<li>SFILENAME: short name - &lt;filename&gt; only</li>
<li>APPLI: Application name</li>
<li>SIZE: file size</li>
<li>DATE: date of last modification/ creation of transfer</li>
<li>TYPE: MVS transfer state</li>
<li>RSTATE: routing state (T: to route, R: routed, A: acked)</li>
<li>UMSG: user message</li>
<li>ORG: origin</li>
<li>DEST: destination</li>
<li>P1: parameter 1</li>
<li>P2: parameter 2</li>
<li>PERM: permanent transfer</li>
<li>DATA_CODE: B for binary, T for test</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ftp_data_struct (-ftp_ds)</p>
<p><span style="font-style: italic;font-weight: bold;">Data structure</span></p>         </td>
         <td><p>FTP only</p>
<p>Data structure type</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">FILE</span> = File structure type allowed (default)</li>
<li><span style="font-weight: bold;">NONE</span> = No data structure type allowed</li>
<li><span style="font-weight: bold;">RECORD</span> = Record structure type allowed</li>
<li><span style="font-weight: bold;">BOTH</span> = File and record structure type allowed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ftp_disable_xfb_commands (-ftp-dxc)</p>
<p>Disable Gateway specific behavior</p>         </td>
         <td><p><span style="font-style: italic;">FTP only</span></p>
<p>Disables the use of FTP commands specific to Gateway.</p>         </td>
         <td><ul>
<li>Y</li>
<li><span style="font-weight: bold;">N</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ftp_passive_mode (-ftp_pm)</p>
<p><span style="font-style: italic;font-weight: bold;">Passive mode</span></p>         </td>
         <td><p>FTP only</p>
<p>Passive mode capability</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">NONE</span> = No passive mode allowed</li>
<li><span style="font-weight: bold;">INIT</span> = Passive command sent in Initiator mode</li>
<li><span style="font-weight: bold;">RESP</span> = Passive command reception allowed</li>
<li><span style="font-weight: bold;">BOTH</span> = Both <em>init</em> and <em>resp</em> passive mode (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ftp_restart_type (-ftp_rs)</p>
<p><span style="font-style: italic;font-weight: bold;">Restart type</span></p>         </td>
         <td><p>FTP only</p>
<p>Restart mode</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">STREAM</span> = Stream restart mode allowed</li>
<li><span style="font-weight: bold;">INFO</span> = Block and compressed restart mode</li>
<li><span style="font-weight: bold;">BOTH</span> = Stream, block and compressed restart modes allowed (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-get_appli_method (-gam)</p>
<p><span style="font-style: italic;font-weight: bold;">Application method</span></p>         </td>
         <td><p>FTP, HTTP, OFTP, SFTP, POP3 only</p>
<p>Method used to retrieve Application object name</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">AIF</span> = <span style="font-weight: bold;">A</span>pplication <span style="font-weight: bold;">I</span>n <span style="font-weight: bold;">F</span>ilename field</li>
<li><span style="font-weight: bold;">AIM</span> = <span style="font-weight: bold;">A</span>pplication <span style="font-weight: bold;">I</span>n user <span style="font-weight: bold;">M</span>essage field</li>
<li><span style="font-weight: bold;">AIE</span> = <span style="font-weight: bold;">A</span>pplication <span style="font-weight: bold;">I</span>n user <span style="font-weight: bold;">E</span>xit sub-routine (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-group (-gr)</p>
<p><span style="font-style: italic;font-weight: bold;">Group name</span></p>         </td>
         <td><p>Group name</p>         </td>
         <td><p>Maximum: 15 alphanumeric characters<br />
(default: <span style="font-weight: bold;">GDEFAULT</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-heartbeat_rate (&amp;#45;heartbeat)</p>
<p>Heartbeat rate</p>         </td>
         <td><p>PeSIT HS only</p>
<p>The interval (in seconds) between Heartbeat messages emitted by the server to confirm the presence of a file-requestor client.</p>
<p>Use this parameter in conjunction with the parameters:</p>
<ul>
<li>permanent_conn</li>
<li>conn_hold_delay</li>
</ul>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">(2^31 - 1)</span></p>         </td>
      </tr>
      <tr>
         <td><p>-init_conn_count</p>
<p><span style="font-style: italic;font-weight: bold;">Number of connections from this Site</span></p>         </td>
         <td><p><span style="font-style: italic;">Displaying Remote Site status</span></p>
<p>Number of established connections in Initiator mode.</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span class="code" style="font-weight: bold;">init_conn_max</span></p>         </td>
      </tr>
      <tr>
         <td><p>-init_conn_max (-i_max)</p>
<p>Depending on protocol:</p>
<p>Maximum number of simultaneous connections to this Site</p>
<p>Maximum number of client processes</p>         </td>
         <td><p><span style="font-style: italic;">All protocols except SWIFTNet:</span><br />
Maximum number of connections initiated to this Site.</p>
<p><span style="font-style: italic;">POP3:</span><br />
This value is always set to 1.</p>
<p>SWIFTNet:<span style="font-style: normal;"><br />
Maximum number of simultaneous client processes allowed.</span></p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0 - 999</span><br />
(default: <span style="font-weight: bold;">1</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-init_mode (-im)</p>
<p><span style="font-style: italic;font-weight: bold;">Initiating Site</span></p>         </td>
         <td><p>Set the initialization attribute to Initiator Site.</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-init_receiver (-ir)</p>
<p><span style="font-style: italic;font-weight: bold;">Initiator/Receiver</span></p>         </td>
         <td><p>Receiver in Initiator mode</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-init_sender (-is)</p>
<p><span style="font-style: italic;font-weight: bold;">Initiator/Sender</span></p>         </td>
         <td><p>Sender in Initiator mode</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-is_monitor (-ism)</p>
<p><span style="font-style: italic;font-weight: bold;">Send transfer attributes</span></p>         </td>
         <td><p>HTTP only</p>
<p>When set to <span style="font-weight: bold;">Yes</span>, Transfer CGI parameters (<span class="code">P_ORG</span>, <span class="code">P_DEST</span>, <span class="code">P_APPLI</span>, <span class="code">P_MSG</span>) are sent with the file.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-local_certificate_alias (-lcerta)</p>
<p><span style="font-style: italic;font-weight: bold;">Certificate alias</span></p>         </td>
         <td><p>SFTP only</p>
<p>Certificate alias to use to authenticate your Site to the partner</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-local_private_key_alias (-lprvka)</p>
<p><span style="font-style: italic;font-weight: bold;">Private key alias</span></p>         </td>
         <td><p>SFTP only</p>
<p>Private key alias to use to authenticate your Site to the partner</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-login_ident (-l_id)</p>
<p>Depending on protocol:</p>
<p>(Pre-Connection phase) ID to send to partner</p>
<p>User name</p>
<p>Login</p>
<p>ID/Password to send <span style="font-weight: normal;">(ID part)</span></p>         </td>
         <td><p>PeSIT: Pre-connection identifier to send</p>
<p>SFTP: User name to send to the Remote Site</p>
<p>HTTP: Identifier to send during the connection phase</p>
<p>JMS: The user name (for the MOM user) for connection to the JMS provider</p>
<p>SWIFTNet: Client user name to send to the Remote Site during the connection phase.</p>         </td>
         <td><ul>
<li>PeSIT: Maximum: 8 alphanumeric characters</li>
<li>SFTP: Maximum: 63 alphanumeric characters</li>
<li>HTTP: Maximum: 63 alphanumeric characters</li>
<li>JMS: Maximum: 63 alphanumeric characters</li>
<li>SWIFTNet: Maximum: 63 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-login_method (-lm)</p>
<p><span style="font-style: italic;font-weight: bold;">HTTP method</span></p>         </td>
         <td><p>HTTP method to use with the login request</p>         </td>
         <td><p>One of:</p>
<ul>
<li>GET</li>
<li>POST</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-login_password (-l_pswd)</p>
<p>Depending on protocol:</p>
<p>(Pre-Connection phase) Password to send to partner</p>
<p>Password</p>
<p>ID/Password to send <span style="font-weight: normal;">(Password part)</span></p>         </td>
         <td><p>PeSIT: Pre-connection password to send</p>
<p>SFTP: User password to send to the Remote Site</p>
<p>HTTP: User password to send during the connection phase</p>
<p>JMS: The password (for the MOM user) for connection to the JMS provider</p>
<p>SWIFTNet: Password to send to the Remote Site during the connection phase</p>
<p>X.400: <span style="font-style: italic;">described later in this topic</span></p>         </td>
         <td><ul>
<li>PeSIT: Maximum: 8 alphanumeric characters</li>
<li>SFTP: Maximum: 127 alphanumeric characters</li>
<li>HTTP: Maximum: 127 alphanumeric characters</li>
<li>JMS: Maximum: 127 alphanumeric characters</li>
<li>SWIFTNet: Maximum: 20 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-login_type (-lt)</p>
<p><span style="font-style: italic;font-weight: bold;">Identification method</span></p>         </td>
         <td><p>HTTP only</p>
<p>Identification method to use when transferring files</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Anonymous</span> = Sends neither <em>user</em> nor <em>password</em></li>
<li><span style="font-weight: bold;">Web</span> = standard HTTP identification method (adds <em>user</em> and <em>password</em> to HTTP headers)</li>
<li><span style="font-weight: bold;">CGI</span> = adds <em>user</em> and <em>password</em> to the CGI parameters</li>
<li><span style="font-weight: bold;">Cookies</span> = adds <em>user</em> and <em>password</em> to the CGI parameters of the login request. Each Transfer Request following the login request will not send those parameters but cookies received with login response.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-login_url (-lu)</p>
<p><span style="font-style: italic;font-weight: bold;">Login path</span></p>         </td>
         <td><p>HTTP only</p>
<p>Path to use with login request (for example, <span class="code">/cgi-bin/login.cgi</span>). This is not an absolute URL like <span class="code">http://server:port...</span></p>         </td>
         <td><p>Maximum: 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-login_user_param (-lup)</p>
<p>Login CGI parameters</p>         </td>
         <td><p>HTTP only</p>
<p>CGI parameters to add login requests.</p>
<p>Use this parameter if you set<span class="code"> login_type</span> to <span style="font-style: italic;">Cookies</span>.</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>
<p>Format:<span class="code"><br />
login_param1=value1&amp; login_param2=value2</span></p>         </td>
      </tr>
      <tr>
         <td><p>-mail_address (-email)</p>
<p><span style="font-style: italic;font-weight: bold;">Default email address</span></p>         </td>
         <td><p>SMTP only</p>
<p>Default email address to use if no address is specified in the Transfer Request.</p>
<p>This parameter applies to both Remote and Local Sites:</p>
<ul>
<li>Remote: default <span style="font-weight: bold;">To</span> address</li>
<li>Local: default <span style="font-weight: bold;">From</span> address</li>
</ul>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><code style="font-weight: bold;">-mail_xprio_alpha(-mxa) </code><em>Alphanumeric XPriority header</em>         </td>
         <td><p><em>SMTP only</em></p>
<p>Controls the way the X-Priority header is built:</p>
<ul>
<li>numeric (default) or</li>
<li>alphanumeric</li>
</ul>         </td>
         <td><p>Values:</p>
<ul>
<li><strong>N</strong> (default value)<br />
X-Priority takes numeric values (1 to 5)</li>
<li><strong>Y</strong><br />
X-Priority takes alphanumeric values (<em>HIGHEST</em>, <em>HIGH</em>, <em>NORMAL</em>, <em>LOW</em>, <em>LOWEST</em>)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-max_download_rate (-max_downr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum downloads KB/min</span></p>         </td>
         <td><p>FTP security:</p>
<p>To reduce the risk of hammer attacks, limit the size of downloaded data per minute.</p>         </td>
         <td><p>Integer (KB/min)</p>         </td>
      </tr>
      <tr>
         <td><p>-max_download_requests_rate (-maxdownreqr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum downloads Requests/min</span></p>         </td>
         <td><p>FTP security:</p>
<p>To reduce the risk of hammer attacks, limit the number of download requests per minute.</p>         </td>
         <td><p>Integer (number of requests /min)</p>         </td>
      </tr>
      <tr>
         <td><p>-max_upload_file_size (-maxupsize)</p>
<p><span style="font-style: italic;font-weight: bold;">Max upload file size</span></p>         </td>
         <td><p>FTP security:</p>
<p>To reduce the risk of hammer attacks, limit the upload file size.</p>         </td>
         <td><p>Integer (MB)</p>         </td>
      </tr>
      <tr>
         <td><p>-max_upload_rate (-max_upr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum uploads KB/min</span></p>         </td>
         <td><p>FTP security:</p>
<p>To reduce the risk of hammer attacks, limit the size of uploaded data per minute.</p>         </td>
         <td><p>Integer (KB/min)</p>         </td>
      </tr>
      <tr>
         <td><p>-max_upload_requests_rate (-maxupreqr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum uploads Requests/min</span></p>         </td>
         <td><p>FTP security:</p>
<p>To reduce the risk of hammer attacks, limit the number of upload requests per minute.</p>         </td>
         <td><p>Integer (number of requests /min)</p>         </td>
      </tr>
      <tr>
         <td><p>-nack_option (-nao)</p>
<p><span style="font-style: italic;font-weight: bold;">Negative acknowledgement option</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>The Nack (Negative acknowledgement) option indicates whether the Remote Site supports the negative EERP extension or not. If this option is not set, all negative acknowledgement requests are denied.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-newline_convention (-nlc)</p>
<p><span style="font-style: italic;font-weight: bold;">Newline convention</span></p>         </td>
         <td><p>SFTP only</p>
<p>Line feed convention, depending on remote system type</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">U</span> / u (UNIX)</li>
<li><span style="font-weight: bold;">W</span> / w (Windows)</li>
<li>empty</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-network_security_option (-nsopt)</p>
<p><span style="font-style: italic;font-weight: bold;">Network security</span></p>         </td>
         <td><p>Network Security Type to use with this Site.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">NONE</span> = No network security (default)</li>
<li><span style="font-weight: bold;">TLS</span> = TLS network security</li>
<li><span style="font-weight: bold;">SSH</span> = SSH network security</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code style="font-weight: bold;">-ntlm_version (-ntlmv)</code></p>
<p><em>NTLM version</em></p>         </td>
         <td><p><em>HTTP only</em></p>
<p>The NTLM version to be used for authentication to a HTTP server.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><strong>NTLM</strong></li>
<li><strong>NTLM2</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-oftp_auth_method</p>
<p>Authentication method</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the authentication method to use.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>None</li>
<li>EncryptedData</li>
<li>EnvelopedData</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-oftp_max_file_size (-oftp_mfs)</p>
<p>Max. size for received files</p>         </td>
         <td><p>OFTP only</p>
<p>Enter the maximum size allowed for received files. Specify the value in KB.</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0 - 999 999 999</span><br />
</p>
<p><strong>0</strong> = no limit.</p>         </td>
      </tr>
      <tr>
         <td><p>-old_password (-o_pswd)</p>
<p>(None)</p>         </td>
         <td><p>PeSIT</p>
<p>Old password to specify in Initiator mode</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-old_password2 (-o_pswd2)</p>
<p>(None)</p>         </td>
         <td><p>PeSIT HS E</p>
<p>Optional parameter corresponding to the old password field in PI 5 of <span class="code">FPDU_ACKCONNECT</span>.</p>         </td>
         <td><p>Maximum: 8 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-partner_loc_alias (-pla)</p>
<p><span style="font-style: italic;font-weight: bold;">Partner local alias</span></p>         </td>
         <td><p>Local Site alias to use during connection phase.</p>
<p>If you do not complete this parameter, Gateway uses the default Local Site specified in the configuration menu.</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-password (-pswd)</p>
<p><span style="font-style: italic;font-weight: bold;">(Connection phase) Client password to send</span></p>         </td>
         <td><p>PeSIT</p>
<p>Connection password to send</p>         </td>
         <td><p>Maximum: 15 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-password2 (-pswd2)</p>
<p><span style="font-style: italic;font-weight: bold;">(Connection phase) Server password to send</span></p>         </td>
         <td><p>PeSIT:</p>
<p>Corresponds to the password field in PI 5 of <span class="code">FPDU_ACKCONNECT</span></p>
<p>FTP:</p>
<p>Corresponds to the <span class="code" style="font-weight: bold;">ACCT</span> account command sent after a <span class="code" style="font-weight: bold;">PASS</span> command in client mode</p>         </td>
         <td><ul>
<li>PeSIT HS D: Numeric value less than 65536</li>
<li>PeSIT HS E: Up to 8 alphanumeric characters</li>
<li>FTP: Up to 15 alphanumeric characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-permanent_conn (-perm_conn)</p>
<p>Permanent connection</p>         </td>
         <td><p>PeSIT HS only</p>
<p>When the polling option is configured, this parameter enables you to establish permanent polled connections between server and client.</p>
<p>Use this parameter in conjunction with the parameters:</p>
<ul>
<li>heartbeat_rate</li>
<li>conn_hold_delay</li>
</ul>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-poll_conn_count</p>
<p>(None)</p>         </td>
         <td><p><span style="font-style: italic;">Displaying Site status</span></p>
<p>Maximum number of established Change Direction connections</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span class="code" style="font-weight: bold;">poll_conn_max</span></p>         </td>
      </tr>
      <tr>
         <td><p>-poll_conn_max (-pollmax)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum connections</span></p>         </td>
         <td><p>PeSIT HS E:</p>
<p>The maximum number of concurrent active connections allowed of Change Direction type.</p>
<p>POP3:</p>
<p>This value is always set to 1 and cannot be modified.</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span style="font-weight: bold;">999</span><br />
(default: <span style="font-weight: bold;">0</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-poll_interval (-pollint)</p>
<p><span style="font-style: italic;font-weight: bold;">Polling interval</span></p>         </td>
         <td><p>PeSIT HS E and POP3 only</p>
<p>The polling interval defines the time (in minutes) to wait before starting the next polling cycle.</p>         </td>
         <td><p>In the format <span style="font-style: italic;">MM</span> (default: <span style="font-weight: bold;">0</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-poll_mode (-pm)</p>
<p><span style="font-style: italic;font-weight: bold;">Activated</span></p>         </td>
         <td><p>PeSIT HS E and POP3 only</p>
<p>Activates polling on the Remote Site</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-poll_option (-poll)</p>
<p><span style="font-style: italic;font-weight: bold;">Change direction support</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>The Change Direction mode indicates whether this Remote Site is polled on Gateway startup. Use this parameter to activate or deactivate the Change Direction connection dynamically.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-pop3_auth_method</p>
<p><span style="font-style: italic;font-weight: bold;">POP3 authentication method</span></p>         </td>
         <td><p>POP3 only</p>
<p>Select the authentication method to use for POP3 connections</p>         </td>
         <td><p>One of:</p>
<ul>
<li>auto</li>
<li>basic (default)</li>
<li>apop</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-proto_ident (-pi)</p>
<p>Protocol identifier</p>         </td>
         <td><p>Not available for FTP and SFTP</p>
<p>Site protocol name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters (default: <span class="code">alias_name</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-protocol (-pr)</p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>Interchange protocol</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">FTP</span></li>
<li>HTTP</li>
<li><span style="font-weight: bold;">FTP_HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>JMS</li>
<li>SWIFTNET</li>
<li>X400</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-recv_xfer_active</p>
<p>(None)</p>         </td>
         <td><p><span style="font-style: italic;">Displaying Remote Site status</span></p>
<p>Current number of Transfers received from the Site</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span class="code" style="font-weight: bold;">recv_xfer_total</span></p>         </td>
      </tr>
      <tr>
         <td><p>-recv_xfer_total</p>
<p><span style="font-style: italic;font-weight: bold;">Number of receptions</span></p>         </td>
         <td><p><span style="font-style: italic;">Displaying Remote Site status</span></p>
<p>Total number of Transfers received from the Site</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_issuer_cert_alias (-risscerta)</p>
<p><span style="font-style: italic;font-weight: bold;">Issuer certificate alias</span></p>         </td>
         <td><p>SFTP only</p>
<p>Issuer (CA) certificate alias</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_issuer_name_pattern (-rissnp)</p>
<p><span style="font-style: italic;font-weight: bold;">Issuer name pattern</span></p>         </td>
         <td><p>SFTP only</p>
<p>Issuer (CA) name pattern</p>         </td>
         <td><p>Maximum: 512 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_public_key_alias (-rpubka)</p>
<p><span style="font-style: italic;font-weight: bold;">Public key alias</span></p>         </td>
         <td><p>SFTP only</p>
<p>Public key alias to use to authenticate the partner</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_public_key_group (-rpubkg)</p>
<p><span style="font-style: italic;font-weight: bold;">Public key group</span></p>         </td>
         <td><p>SFTP only</p>
<p>Public key group for keys imported automatically</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_subject_cert_alias (-rsubca)</p>
<p><span style="font-style: italic;font-weight: bold;">Subject certificate alias</span></p>         </td>
         <td><p>SFTP only</p>
<p>Certificate alias to use to authenticate the partner</p>         </td>
         <td><p>Maximum: 512 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_subject_name_pattern (-rsubnp)</p>
<p><span style="font-style: italic;font-weight: bold;">Subject name pattern</span></p>         </td>
         <td><p>SFTP only</p>
<p>Subject name pattern to use to filter accepted partner certificates</p>         </td>
         <td><p>Maximum: 512 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-resp_conn_count</p>
<p><span style="font-style: italic;font-weight: bold;">Number of connections accepted by this Site</span></p>         </td>
         <td><p><span style="font-style: italic;">Displaying Remote Site status</span></p>
<p>Number of established connections in Responder mode</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0</span> - <span class="code" style="font-weight: bold;">resp_conn_max</span></p>         </td>
      </tr>
      <tr>
         <td><p>-resp_conn_max (-r_max)</p>
<p>Depending on protocol:</p>
<p>Maximum number of simultaneous connections from this Site</p>
<p>Maximum number of server processes</p>         </td>
         <td><p>Maximum number of connections from this Site.</p>
<p>POP3:</p>
<p>This value is always set to 0.</p>
<p>SWIFTNet:</p>
<p>Maximum number of simultaneous server processes allowed.</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0 - 999</span><br />
(default: <span style="font-weight: bold;">1</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-resp_mode (-rm)</p>
<p><span style="font-style: italic;font-weight: bold;">Responding Site</span></p>         </td>
         <td><p>Set the initialization attribute to Responder Site.</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-resp_receiver (-rr)</p>
<p><span style="font-style: italic;font-weight: bold;">Responder/Receiver</span></p>         </td>
         <td><p>Receiver in Responder mode.</p>
<p>Mandatory for SMTP Sites.</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-resp_sender (-rs)</p>
<p><span style="font-style: italic;font-weight: bold;">Responder/Sender</span></p>         </td>
         <td><p>Sender in Responder mode.</p>
<p>Mandatory for POP3 Sites.</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restart_allowed (-restart)</p>
<p><span style="font-style: italic;font-weight: bold;">Restart allowed</span></p>         </td>
         <td><p>Restart function</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-resync_allowed (-resynch)</p>
<p><span style="font-style: italic;font-weight: bold;">Resynchronization allowed</span></p>         </td>
         <td><p>Resynchronization function</p>         </td>
         <td><ul>
<li>Y (default)</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-retry_count_max (-rc_max)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum number of connection retries before time limit</span></p>         </td>
         <td><p>Maximum number of connection retries before timeout</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0 - 999</span><br />
(default: <span style="font-weight: bold;">10</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_count</p>
<p><span style="font-style: italic;font-weight: bold;">Number of retries</span></p>         </td>
         <td><p>Number of current connection retries</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_delay</p>
<p>(None)</p>         </td>
         <td><p>Current connection retry delay</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_delay_max (-rd_max)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum interval between retries</span></p>         </td>
         <td><p>Maximum interval between connection retries (in seconds)</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">9999</span><br />
(default: <span style="font-weight: bold;">600</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_delay_min (-rd_min)</p>
<p><span style="font-style: italic;font-weight: bold;">Time before first retry</span></p>         </td>
         <td><p>Minimum interval between connection retries (in seconds)</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">9999</span><br />
(default: <span style="font-weight: bold;">10</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>-send_xfer_active</p>
<p>(None)</p>         </td>
         <td><p>Number of active Transfers sent to the Site</p>         </td>
         <td><p>Integer: <span style="font-weight: bold;">0 -</span><span class="code" style="font-weight: bold;">send_xfer_total</span></p>         </td>
      </tr>
      <tr>
         <td><p>-send_xfer_total</p>
<p><span style="font-style: italic;font-weight: bold;">Number of transmissions</span></p>         </td>
         <td><p>Number of Transfers to be sent to the Site or that are in progress.</p>         </td>
         <td><p>Integer</p>         </td>
      </tr>
      <tr>
         <td><p>-sentinel_transfer_filter (-stf)</p>
<p><span style="font-style: italic;font-weight: bold;">Sentinel Transfer filter</span></p>         </td>
         <td><p>Set the notification level for Transfer state changes to send to the Sentinel server.</p>         </td>
         <td><p>One of:</p>
<ul>
<li>ALL</li>
<li>SUMMARY: Summary transfer states are: canceled, ended, acked, created, to_begin.</li>
<li>NONE</li>
<li>UNDEFINED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-session_max</span></p>
<em>Max number of sessions</em>         </td>
         <td><p><em>OFTP only</em></p>
<p>Maximum number of sessions (IN + OUT) for each remote site.</p>
<p>Please note that Gateway supports per-partner granularity for selecting the template when using <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PM.</p>
<ul>
<li>If a remote site with alias = <span class="code">SSIDCODE.SIOICD+SSIDCODE.SIOORG </span>exists in Gateway, this site is selected as the template site.</li>
<li>If not, the default configured template site is used (<code>TODT</code>).</li>
</ul>         </td>
         <td><p>Integer: <strong>0 - 999</strong></p>
<p>(default : <strong>1</strong>)</p>         </td>
      </tr>
      <tr>
         <td><p>-smtp_auth_method</p>
<p><em>SMTP authentication method</em></p>         </td>
         <td><p>SMTP only</p>
<p>Select the authentication method to use for SMTP connections</p>         </td>
         <td><p>One of:</p>
<ul>
<li>NONE (default)</li>
<li>PLAIN</li>
<li>LOGIN</li>
<li>ANONYMOUS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>
<p>User message</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">OFTP:</span> user message to be transmitted at OFTP connection phase</li>
<li><span style="font-weight: bold;">FTP:</span> list of special commands to send to remote server using FTP <span class="code">SITE</span> or <span class="code">QUOTE</span> command</li>
<li><span style="font-weight: bold;">PeSIT:</span> user message to be transmitted at the connection phase</li>
<li><span style="font-weight: bold;">HTTP:</span> user message used to add CGI parameters to Transfer Requests</li>
</ul>         </td>
         <td><ul>
<li>OFTP: Up to 8 alphanumeric characters</li>
<li>PeSIT: Up to 512 alphanumeric characters</li>
<li>HTTP: formatted as follows: <span class="code">xfer_param1=value1&amp; xfer_param2=value2</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-special_logic</p>
<p><span style="font-style: italic;font-weight: bold;">Special Logic Coding</span></p>         </td>
         <td><p>OFTP only</p>
<p>Special logic coding capabilities</p>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ssh_profile (-sshprf)</p>
<p><span style="font-style: italic;font-weight: bold;">SSH Profile</span></p>         </td>
         <td><p>SFTP only</p>
<p>SSH Profile to use in client mode</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-tls_sprof_in (-tsi)</p>
<p><span style="font-style: italic;font-weight: bold;">Security profile for incoming connection</span></p>         </td>
         <td><p>Optional</p>
<p>Incoming TLS Security Profile name.</p>
<p>The network security option must be set to <span style="font-weight: bold;">TLS</span>.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-tls_sprof_out (-tso)</p>
<p><span style="font-style: italic;font-weight: bold;">Security profile for outgoing connection</span></p>         </td>
         <td><p>Optional</p>
<p>Outgoing TLS Security Profile name.</p>
<p>The network security option must be set to <span style="font-weight: bold;">TLS</span>.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-trace_mode (-tm)</p>
<p><span style="font-style: italic;font-weight: bold;">Trace</span></p>         </td>
         <td><p>Initialization attribute: enable or disable trace mode</p>         </td>
         <td><ul>
<li>Y</li>
<li>N (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-trans_mode (-trm)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer Mode</span></p>         </td>
         <td><p>FTP and OFTP only</p>
<p>Transfer mode capabilities</p>
<ul>
<li><span style="font-weight: bold;">FTP:</span> STREAM transfer mode is <span style="font-weight: bold;">always</span> available (non-modifiable)</li>
<li><span style="font-weight: bold;">OFTP:</span> only COMPRESSED is available.</li>
</ul>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">NONE</span> = unused (default)</li>
<li><span style="font-weight: bold;">COMPRESSED</span> = compressed mode allowed</li>
<li><span style="font-weight: bold;">BLOCK</span> = block mode allowed</li>
<li><span style="font-weight: bold;">BOTH</span> = compressed and block mode allowed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-user_agent (-ua)</p>
<p>User agent</p>         </td>
         <td><p>HTTP only</p>
<p>Enter the ID of the client application used to contact the remote partner. This information is useful for certain logging and statistics processes.</p>         </td>
         <td><p>Maximum: 128 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-username (-un)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer owner</span></p>         </td>
         <td><p>If specified, defines the <span style="font-weight: bold;">Transfer owner name</span> to associate with Transfers created by Gateway. If you do not specify a value, the user name defined in the configuration menu is used.</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-use_trade_unpacking (-tradeu)</p>         </td>
         <td><p>EDIINT only</p>
<p>Enables S/MIME, or alternatively ASx, to search in the transported file contents for security related information.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">undefined</span> = unused (default)</li>
<li><span style="font-weight: bold;">SMIME</span> = enables S/MIME to unpack file</li>
<li><span style="font-weight: bold;">EDIINT</span> = enables an EDIINT protocol to unpack file</li>
<li><span style="font-weight: bold;">RN</span> = enables RosettaNet protocol to unpack</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-version (-ver)</p>
<p><span style="font-style: italic;font-weight: bold;">Version</span></p>         </td>
         <td><p>PEL and OFTP only</p>
<p>Protocol version.</p>         </td>
         <td><p><span style="font-style: italic;">For PEL</span>, one of:</p>
<ul>
<li>no value</li>
<li><span style="font-weight: bold;">HV</span> = High Value</li>
<li><span style="font-weight: bold;">TR</span> = Trailer</li>
<li><span style="font-weight: bold;">CRC</span> = Cyclic Redundancy Code</li>
<li><span style="font-weight: bold;">HV/TR</span> = High Value and Trailer</li>
<li><span style="font-weight: bold;">HV/CRC</span> = High Value and Cyclic Redundancy Code</li>
<li><span style="font-weight: bold;">CRC/TR</span> = Cyclic Redundancy Code and Trailer</li>
<li><span style="font-weight: bold;">HV/CRC/TR</span> = High Value and Cyclic Redundancy Code and Trailer</li>
</ul>
<p><span style="font-style: italic;">For OFTP</span>, one of:</p>
<ul>
<li><span style="font-weight: bold;">R1.2</span></li>
<li><span style="font-weight: bold;">R1.3</span> (default)</li>
<li><span style="font-weight: bold;">R1.4</span></li>
<li><span style="font-weight: bold;">R2.0</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="_xsr_arl"></span><span class="code" style="font-weight: bold;">-xsr_allowed_ra_list (-xsr_arl)</span></p>
<p><span style="font-weight: bold;font-style: italic;">Allowed Router Agents</span></p>         </td>
         <td><p>Specify the Secure Relay Router Agents that are allowed to connect to this Site.</p>
<p>Use this parameter with the <span class="code">peladm update_site</span> command to add or remove Router Agents from the list. Separate Router Agent names with commas.</p>
<p><strong>To add RAs to the list, use the command:</strong></p>
<p><span class="code">peladm update_site –a SITE_NAME –xsr_arl ADD,RA_NAME1,RA_NAME2</span></p>
<p>You can omit ADD as adding RAs is the default function for this parameter.</p>
<p><strong>To remove RAs from the list, use the command:</strong></p>
<p><span class="code">peladm update_site –a SITE_NAME –xsr_arl REM,RA_NAME1,RA_NAME2</span></p>         </td>
         <td><p><span class="code">ADD</span> or <span class="code">REM</span> (remove) followed by a list of Router Agent names separated by a comma.</p>
<p><strong>Examples:</strong></p>
<p><span class="code">peladm update_site –a SAMPLE_SITE –xsr_arl RA1,RA2</span></p>
<p><span class="code">peladm update_site –a SAMPLE_SITE –xsr_arl REM,RA2</span></p>
<p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Communication_path_parameters"></span>

## Communication path parameters

The following parameters describe the main communication path and the three backup communication paths.

To differentiate the parameters, they are marked with extension <span class="code">\_1</span>, <span class="code">\_2</span> or <span class="code">\_3</span>. For example, <span class="code">comm\_type\_1</span> describes the communication type for the first backup communication type.

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
         <td><p>-comm_options (-opt)</p>
<p><span style="font-style: italic;font-weight: bold;">Facilities</span></p>         </td>
         <td><p>Network options</p>         </td>
         <td><p>Syntax for:</p>
<ul>
<li><span style="font-weight: bold;">TCP/IP</span>: Not used</li>
<li><span style="font-weight: bold;">SNA LU 6.2</span>: <span class="code">@lupartner@mode@tpn</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-comm_type (-ct)</p>
<p><span style="font-style: italic;font-weight: bold;">Network type</span></p>         </td>
         <td><p>Type of communication interface</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">PAD</span></li>
<li><span style="font-weight: bold;">TCPIP</span> (default)</li>
<li><span style="font-weight: bold;">LU62</span></li>
<li><span style="font-weight: bold;">DSA</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-dest_address (-da)</p>
<p><span style="font-style: italic;font-weight: bold;">Called address</span></p>         </td>
         <td><p>Address to call (destination network address for the Remote Site)</p>         </td>
         <td><p>Maximum: 63 alphanumeric characters.</p>
<p>Syntax:</p>
<ul>
<li><span style="font-weight: bold;">TCP/IP</span>: IP address/TCP port number</li>
<li><span style="font-weight: bold;">SNA LU 6.2</span>: <span class="code">@machine@locallu@opt</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-ft_proxy (-fpx)</p>
<p><span style="font-style: italic;font-weight: bold;">FTP / HTTP proxy</span></p>         </td>
         <td><p>FTP/HTTP only</p>
<p>FTP or HTTP Proxy name for the main communication address</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>-logon (-log)</p>
<p><span style="font-style: italic;font-weight: bold;">Logon message</span></p>         </td>
         <td><p>PeSIT and PEL protocols only</p>
<p>Message sent before protocol exchange to route the call to the right Application</p>         </td>
         <td><ul>
<li>PEL: up to 31 characters</li>
<li>PeSIT: up to 8 characters</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-logon_code (-log_co)</p>
<p><span style="font-style: italic;font-weight: bold;">Logon code</span></p>         </td>
         <td><p>Logon message code</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">A</span> = ASCII</li>
<li><span style="font-weight: bold;">E</span> = EBCDIC</li>
<li><span style="font-weight: bold;">B</span> = Binary</li>
<li><span style="font-weight: bold;">ISO</span> = ISO</li>
<li><span style="font-weight: bold;">OEMPC</span> = OEMPC</li>
<li><span style="font-weight: bold;">A1</span> = ASCII1</li>
<li><span style="font-weight: bold;">A2</span> = ASCII2</li>
<li><span style="font-weight: bold;">A3</span> = ASCII3</li>
<li><span style="font-weight: bold;">A4</span> = ASCII4</li>
<li><span style="font-weight: bold;">A5</span> = ASCII5</li>
<li><span style="font-weight: bold;">E1</span> = EBCDIC1</li>
<li><span style="font-weight: bold;">E2</span> = EBCDIC2</li>
<li><span style="font-weight: bold;">E3</span> = EBCDIC3</li>
<li><span style="font-weight: bold;">E4</span> = EBCDIC4</li>
<li><span style="font-weight: bold;">E5</span> = EBCDIC5</li>
<li><span style="font-weight: bold;">U</span> = Undefined (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-net_proxy (-npx)</p>
<p><span style="font-style: italic;font-weight: bold;">Network proxy</span></p>         </td>
         <td><p>SOCKS4 or HTTPS</p>
<p>Network Proxy name for the main communication address</p>         </td>
         <td><p>Maximum: 31 characters</p>         </td>
      </tr>
      <tr>
         <td><p>-org_address (-oa)</p>
<p><span style="font-style: italic;font-weight: bold;">Calling address</span></p>         </td>
         <td><p>Not applicable for TCP/IP</p>
<p>Calling address (originator network address for the Site)</p>         </td>
         <td><p>Maximum: 63 alphanumeric characters.</p>
<p>Syntax for SNA LU 6.2:<span class="code"><br />
@user@password@type</span></p>         </td>
      </tr>
      <tr>
         <td><p>-user_data (-ud)</p>
<p><span style="font-style: italic;font-weight: bold;">User data in the call request packet</span></p>         </td>
         <td><p>User data in the call request packet</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">TCP/IP</span>: Not used</li>
<li><span style="font-weight: bold;">SNA LU 6.2</span>: Corresponds to the PIP fields in the Remote Site <span style="font-weight: bold;">Network address</span> tab.<br />
Refer to <a href="../../managing_remote_sites/site_objects_address_config#SNA_LU62">Address configuration for Remote Sites</a>.<br />
Each of the 8 alphanumeric characters of the PIP must be hexadecimal.<span style="font-weight: bold;"><br />
Example:</span> to obtain the string: "hexa", enter "68657861"</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="JMS_site_parameters"></span>

## Additional Site parameters for JMS

The following table lists Site parameters that are specific to JMS. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-jms_ClassLoader</p>
<p>Class loader</p>         </td>
         <td><p>The Java class path used to locate <span class="code">jar</span> files of the JMS provider.</p>
<p>Enter the list of fully qualified <span class="code">jar</span> files path separated by the '<span style="font-weight: bold;">:</span>' character on UNIX systems and '<span style="font-weight: bold;">;</span>' on Windows systems.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_ConnectionFactory</p>
<p>Connection factory</p>         </td>
         <td><p>The JNDI lookup name of the connection factory to be used (configured by the JMS provider administrator).</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_init_property (-jip)</p>
<p><span style="font-weight: bold;font-style: italic;">Property</span> and <span style="font-weight: bold;font-style: italic;">Value</span></p>         </td>
         <td><p>Add an initialization property for JMS connection. The syntax is <span class="code">NewProperty=Value</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_InitialFactory</p>
<p>Initial factory</p>         </td>
         <td><p>The Java class name of the Initial Context Factory.</p>
<p>For example:</p>
<p>com.sun.jndi.fscontext.RefFSContextFactory</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_msgInSelector</p>
<p>Msg In selector</p>         </td>
         <td><p>The JMS selector used to filter messages coming from JMS and transferred to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_msgInDirectory</p>
<p>Msg In directory</p>         </td>
         <td><p>The output directory used to store the data of JMS messages transferred to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_name</p>
<p>JNDI name</p>         </td>
         <td><p>The JNDI lookup name of the queue/topic to be used (configured by the JMS provider administrator).</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_topicClientId</p>
<p>Topic client Id</p>         </td>
         <td><p>If topics are used, the client identifier used to subscribe to the topic.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_topicSubscription</p>
<p>Topic subscription</p>         </td>
         <td><p>If topics are used, the subscription name used to subscribe to the topic.</p>         </td>
      </tr>
      <tr>
         <td><p>-jms_type</p>
<p>Type</p>         </td>
         <td><p>The type of object used by the JMS provider to store/retrieve messages for this Site.</p>
<p>Possible values:</p>
<ul>
<li>QUEUE</li>
<li>TOPIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-jms_URL</p>
<p>URL</p>         </td>
         <td><p>The connection URL of the JMS provider. It usually consists of:</p>
<ul>
<li>a protocol</li>
<li>a hostname</li>
<li>a listening port</li>
</ul>
<p>For example:</p>
<p>tcp://localhost:4569</p>
<p>or</p>
<p>file:/var/mqm</p>         </td>
      </tr>
      <tr>
         <td><p>-remove_jms_init_property (-rjip)</p>         </td>
         <td><p>Remove an initialization property. Enter the name of the property to remove.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SWIFTNet_site_parameters"></span>

## Additional Site parameters for SWIFTNet

The following table lists Site parameters that are specific to SWIFTNet. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-add_channel</p>
<p><strong>New</strong> button on <strong>SnF</strong> sub-tab</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-backup_site (-bks)</p>
<p>Backup sites aliases</p>         </td>
         <td><p>Specify the aliases of the backup Sites to use for the current Remote Site. (Gateway checks that the specified backup Site aliases exist.)</p>
<p>Up to 4 backup Sites can be defined, separated by space.</p>
<p>For example, to create a nominal Site ABCD with backup Sites BKPSITE1 and BKPSITE2, enter:</p>
<p>•<code>  peladm create _site -a ABCD -bks “BKSITE1 BKSITE2”</code></p>         </td>
      </tr>
      <tr>
         <td><p>-channel_name (-chnname)</p>
<p>Channel name</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-channel_subset (-chnsbs)</p>
<p>Select subset...</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_decrypt_ident_list"></span>-decrypt_ident_list (-dil) login1:password1 login2:password2 ...</p>
<p>Decrypt ident list</p>         </td>
         <td><p>List of decrypting SWIFTNet users.</p>
<p>This is a list of user login ids with their corresponding passwords. For each user, use the <span style="font-weight: bold;">:</span> (colon) character to separate the login id and password. Use the space character to separate each login id/password pair.</p>         </td>
      </tr>
      <tr>
         <td><p>-event_end_point (-eep)</p>
<p>Event end point</p>         </td>
         <td><p>Mandatory</p>
<p>Arbitrary name allowing SAG to route received events.</p>         </td>
      </tr>
      <tr>
         <td><p>-message_partner (-msp)</p>
<p>Message partner</p>         </td>
         <td><p>Mandatory</p>
<p>Application name declared in SAG.</p>         </td>
      </tr>
      <tr>
         <td><p>-new_channel_name (-newcn)</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-new_queue_name (-newqn)</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-queue_name (-qname)</p>
<p>Queue name</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-ra_config_file (-rac)</p>
<p>Alternate configuration file</p>         </td>
         <td><p>Alternative configuration file for the instance of SWIFTNet RA.</p>         </td>
      </tr>
      <tr>
         <td><p>-ra_instance (-rai)</p>
<p>RA instance</p>         </td>
         <td><p>Mandatory</p>
<p>Name of the SWIFTNet RA (Remote API host adapter) local access point.</p>         </td>
      </tr>
      <tr>
         <td><p>-ra_pathname (-rap)</p>
<p>Alternate RA installation pathname</p>         </td>
         <td><p>Only if SWIFTNet RA has been installed in more than one place</p>
<p>Alternative path for SWIFTNet RA.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_sign_ident_list"></span>-sign_ident_list (-sil) login1:password1 login2:password2 ...</p>
<p>Sign ident list</p>         </td>
         <td><p>List of signatory SWIFTNet users.</p>
<p>This is a list of user login ids with their corresponding passwords. For each user, use the <span style="font-weight: bold;">:</span> (colon) character to separate the login id and password. Use the space character to separate each login id/password pair.</p>         </td>
      </tr>
      <tr>
         <td><p>-snf_queues (-swq)</p>
<p>Queues</p>         </td>
         <td><p>List of all SnF queues to be managed.</p>         </td>
      </tr>
      <tr>
         <td><p>-snl_end_point (-sep)</p>
<p>SNL end point</p>         </td>
         <td><p>Name allowing the reception of SnF events.</p>         </td>
      </tr>
      <tr>
         <td><p>-window_size (-wndsz)</p>
<p>Window size</p>         </td>
         <td><p>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-receive_retrieved_messages
(-rcvretrmsg)</span></p>
<p><span class="bold_in_para">Receive retrieved messages</span></p>         </td>
         <td>Refer to <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras">SWIFTNet queues and output channels</a>.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sw_init_xfer_max(-swixm)</span></p>
<p><strong>Maximum number of initiator transfers</strong></p>         </td>
         <td>The value of the maximum number of transfers in Initiator mode, FileAct only. By default, this parameter is set to 0, meaning unlimited. The maximum value allowed is 999. Transfers switched from a nominal site to a backup site will be subject to the nominal's site limit. The site parameter is not available to the connection related user exits.         </td>
      </tr>
   </tbody>
</table>

##  

<span id="x400_site_parameters"></span>

## Additional Site parameters for X.400

The following table lists Site parameters that are specific to X.400. You can use these parameters with the <span class="code" style="font-weight: bold;">[peladm create\_site](../managing_remote_sites_cli#peladm_create_site)</span> and <span class="code" style="font-weight: bold;">[peladm update\_site](../managing_remote_sites_cli#peladm_update_site)</span> commands when managing Remote Sites. The corresponding field name in the Gateway GUI is displayed in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-proto_ident (-pi)</p>
<p><span style="font-style: italic;font-weight: bold;">Version</span></p>         </td>
         <td><p>Specify either <span class="code" style="font-weight: bold;">MTA</span> or <span class="code" style="font-weight: bold;">MSP7</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-login_password (-l_pswd)</p>
<p>Password - Own</p>         </td>
         <td><p>For MTA:</p>
<p>Password that the local MTA uses to access the remote MTA.</p>
<p>For MSP7:</p>
<p>Password that the MS uses to authenticate itself. The MS in the connection-accept response sends the password and the P7-client validates the password before initiating any operations. Default: No authentication.</p>         </td>
      </tr>
      <tr>
         <td><p>-check_login_password (-chkl_password)</p>
<p>Password - Partner</p>         </td>
         <td><p>For MTA:</p>
<p>Password that the remote MTA uses to access the local MTA.</p>
<p>For MSP7:</p>
<p>Password used by the P7-client to authenticate itself. The client at connection establishment sends the password and the MS validates the password before it accepts the connection.</p>         </td>
      </tr>
      <tr>
         <td><p>-EXTERNAL_MTA_NAME</p>
<p>External name</p>         </td>
         <td><p>To have more than one remote MTA with the same MTA name, it is important to specify an external name that is to be used when contacting the MTA (MTA-MTA protocol). The MTA name specified in the X.400 MTA dialog is used locally and must be unique, whereas several MTAs can have the same external name. If no external name is specified, the MTA name specified in the X.400 MTA dialog is used.</p>         </td>
      </tr>
      <tr>
         <td><p>-ADMD</p>
<p>ADMD</p>         </td>
         <td><p>If you use this parameter, the specified ADMD name is put in the originator's address if ADMD is set to an asterisk (*) when sending messages to this MTA. The reason for allowing this is that some ADMDs require the ADMD field to be set to their ADMD name when sending messages to that particular ADMD. The specified ADMD name will only be substituted if the ADMD attribute in the O/R address of the originator is set to (*).</p>
<p><span style="font-weight: bold;">Note:</span> ADMD substitutions should only be used when you communicate with multiple ADMDs, and only if the ADMD requires that its ADMD name be used when contacting it.</p>         </td>
      </tr>
      <tr>
         <td><p>Communication parameters</p>
<p>The parameters <span class="code">PSAP_SELECTOR</span>, <span class="code">SSAP_SELECTOR</span> and <span class="code">TSAP_SELECTOR</span> identify the service access points for the different communication layers. You must specify at least one of these parameters. Typically the TSAP is used.</p>         </td>
      </tr>
      <tr>
         <td><p>-PSAP_SELECTOR</p>
<p>PSAP</p>         </td>
         <td><p>Presentation Service Access Point.</p>
<p>This parameter defines the OSI address for the net, transport, session, and presentation layer.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-SSAP_SELECTOR</p>
<p>SSAP</p>         </td>
         <td><p>Session Service Access Point.</p>
<p>This parameter defines the SSAP. Maximum 16 characters.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-TSAP_SELECTOR</p>
<p>TSAP</p>         </td>
         <td><p>Transport Service Access Point.</p>
<p>This parameter defines the TSAP. Maximum 20 characters.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-RTS_X410_MODE</p>
<p>RTS X.410 mode</p>         </td>
         <td><p>Typically, a version 84 system uses RTS X.410 mode whereas non-84 systems do not use RTS X.410 mode.</p>
<p>Specify this option as appropriate.</p>
<p>Possible values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">1</span> - use RTS X.410 mode</li>
<li><span class="code" style="font-weight: bold;">0</span> - do not use RTS X.410 mode (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-MTA_VERSION</p>
<p>Version 84</p>         </td>
         <td><p>MTA version. Typically the MTA version is greater than 84. If the version is 84, specify <span class="code" style="font-weight: bold;">84</span>.</p>
<p>Possible values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">84</span></li>
<li><span class="code" style="font-weight: bold;">0</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">MTA_ADDR_...</span> parameters</p>
<p>When there is no explicit information on where to route a message, the destination O/R address is matched against any defined remote MTA routing address and the one which gives the best match is used.</p>         </td>
      </tr>
      <tr>
         <td><p>-MTA_ADDR.CN</p>
<p><span style="font-weight: bold;">Routing O/R address</span> [part]</p>         </td>
         <td><p>CN part of O/R address.</p>
<p><span style="font-weight: bold;">Note:</span> In this case, CN refers to Country (not Common Name).</p>         </td>
      </tr>
      <tr>
         <td><p>-MTA_ADDR.ADMD</p>
<p><span style="font-weight: bold;">Routing O/R address</span> [part]</p>         </td>
         <td><p>ADMD part of O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>-MTA_ADDR.PRMD</p>
<p><span style="font-weight: bold;">Routing O/R address</span> [part]</p>         </td>
         <td><p>PRMD part of O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>-MTA_ADDR.ORG_NAME</p>
<p><span style="font-weight: bold;">Routing O/R address</span> [part]</p>         </td>
         <td><p>ORG_NAME part of O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>-MTA_ADDR.ORG_UNIT_NAME_1</p>
<p><span style="font-weight: bold;">Routing O/R address</span> [part]</p>         </td>
         <td><p>ORG_UNIT_NAME_1 part of O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-TIME_BETWEEN_SUBMISSION</p>
<p>Time between submission</p>         </td>
         <td><p>MSP7 only</p>
<p>Specifies the number of seconds between message submission. When the submission time event occurs, a check is made to see if the UA has any messages to be sent. If there are pending messages, a connection is established and all messages are sent. If this parameter is set to 0, the message submission will be done immediately after the UA has made a submission request.</p>
<p>Default value: 0.</p>         </td>
      </tr>
      <tr>
         <td><p>-MAX_INACTIVITY_TIME</p>
<p>Max inactivity time</p>         </td>
         <td><p>MSP7 only</p>
<p>Specifies the number of seconds that the P7-client will keep an established MS connection up without any activity. If the parameter is set to 0, a connection is released as soon as all MS operations are made.</p>
<p>Default value: 0.</p>         </td>
      </tr>
      <tr>
         <td><p>-MAX_NR_OF_CON_ATTEMPTS</p>
<p>Max connection attempts</p>         </td>
         <td><p>MSP7 only</p>
<p>Used by the P7-client when it fails to connect to the MS. The parameter states how many times a new connection attempt should be made before all messages waiting for submission will be returned to the UA as non-deliverable.</p>
<p>Default value: 8.</p>         </td>
      </tr>
      <tr>
         <td><p>-TIME_BETWEEN_CON_ATTEMPTS</p>
<p>Time between connection attempts</p>         </td>
         <td><p>MSP7 only</p>
<p>Used by the P7-client when it fails to connect to the MS. The parameter specifies the time, in seconds, that the P7-client should wait before it makes a new connection attempt.</p>
<p>Default value: 60 seconds.</p>         </td>
      </tr>
      <tr>
         <td><p>-CALLING_PSAP.TSAP_SELECTOR</p>
<p>Local TSAP</p>         </td>
         <td><p>MSP7 only</p>
<p>Specifies the local TSAP. Maximum 20 characters.</p>
<p>Default value: P7.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>-POLL_AT_SUBMISSION</p>
<p>Poll at submission</p>         </td>
         <td><p>MSP7 only</p>
<p>Determines whether or not the P7-client is allowed to retrieve messages after message submission.</p>
<p>If selected, the P7-client is allowed to poll the Mailbox before the connection is released even if it is not yet time for the next Mailbox poll.</p>
<p>Possible values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">1</span> - selected (default)</li>
<li><span class="code" style="font-weight: bold;">0</span> - not selected</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-SUBMIT_AT_POLL</p>
<p>Submit at poll</p>         </td>
         <td><p>MSP7 only</p>
<p>Determines whether or not the P7-client is allowed to submit messages after a Mailbox poll.</p>
<p>If selected, the P7-client is allowed to submit messages before the connection is released even if it is not yet time for the next message submission.</p>
<p>Possible values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">1</span> - selected (default)</li>
<li><span class="code" style="font-weight: bold;">0</span> - not selected</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-AUTO_ALERT</span></p>
<p>Auto alert</p>         </td>
         <td><p>MSP7 only</p>
<p>Determines whether or not the P7-client should request the auto alert functionality in the MS. The auto alert functionality enables the MS to immediately inform the P7-client that a new message or report has been entered into the users mailbox. When the P7-client receives an alert indication, it will immediately fetch the new message or report.</p>
<p><span style="font-weight: bold;">Note:</span> The alert indication is only sent on an existing connection initiated by the P7-client. The auto alert function is used only if the configuration parameter Max inactivity time is greater than 0.</p>
<p>If selected, the auto alert function is requested. If not selected, no auto alert function is requested.</p>
<p>Possible values:</p>
<ul>
<li><span class="code" style="font-weight: bold;">1</span> - selected</li>
<li><span class="code" style="font-weight: bold;">0</span> - not selected (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Scheduling parameters</p>         </td>
      </tr>
      <tr>
         <td><p>-add_ms_weekly_poll_entry (-add_mswpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Add weekly poll entry at the latest position.</p>
<p>Start_weekday:Stop_weekday:Start_hour:Start_min:Start_sec:Stop_hour:Stop_min:Stop_sec:Frequency_hour:Frequency_min:Frequency_sec</p>         </td>
      </tr>
      <tr>
         <td><p>-del_ms_weekly_poll_entry (-del_mswpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Delete latest weekly poll entry.</p>         </td>
      </tr>
      <tr>
         <td><p>-update_ms_weekly_poll_entry (-upd_mswpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Update weekly poll entry occurrence. Can contain empty parameters.</p>
<p>Occurrence:Start_weekday:Stop_weekday:Start_hour:Start_min:Start_sec:Stop_hour:Stop_min:Stop_sec:Frequency_hour:Frequency_min:Frequency_sec</p>         </td>
      </tr>
      <tr>
         <td><p>-add_ms_monthly_poll_entry (-add_msmpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Add monthly poll entry at the latest position.</p>
<p>Month:Start_monthday:Stop_monthday:Start_hour:Start_min:Start_sec:Stop_hour:Stop_min:Stop_sec:Frequency_hour:Frequency_min:Frequency_sec</p>         </td>
      </tr>
      <tr>
         <td><p>-del_ms_monthly_poll_entry (-del_msmpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Delete latest monthly poll entry.</p>         </td>
      </tr>
      <tr>
         <td><p>-update_ms_monthly_poll_entry (-upd_msmpe)</p>         </td>
         <td><p>MSP7 only</p>
<p>Update monthly poll entry occurrence. Can contain empty parameters.</p>
<p>Occurrence:Month:Start_monthday:Stop_monthday:Start_hour:Start_min:Start_sec:Stop_hour:Stop_min:Stop_sec:Frequency_hour:Frequency_min:Frequency_sec</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Local Sites (command line)](../)

[Working with Remote Sites (command line)](../managing_remote_sites_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
