{
    "title": "CGates and CGateGroups: Parameters List",
    "linkTitle": "CGates and CGateGroups: Parameters List",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Managing Partners

The following table lists all CGate and CGateGroup command parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in **italics**.

Most parameters are shared by the two object types. When they are not shared, the relevant object is indicated in parentheses: (CGATE) or (CGATEGROUP). In addition, when the parameter is shared, the way it is inherited within a given hierarchy is specified in brackets:

-   \[S\]: single definition in given hierarchy
-   \[O\]: overwritten by hierarchy
-   \[A\]: additive
-   \[H\]: hidden

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
         <td><p>add_calling_addr (-acinga)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>List of Calling Address Controls to add to the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each rights definition follows the syntax:</p>
<p>"calling_address_pattern": "authorization"</p>
<p>where:</p>
<ul>
<li><span style="font-style: italic;">calling_address_pattern</span>: Up to 31 alphanumeric characters, including wildcards</li>
<li><span style="font-style: italic;">authorization</span>: enumerated [ A (allowed) | D (denied) ]</li>
</ul>
<p>This parameter can contain multiple calling address control definitions, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>add_calling_addr_file (-acingaf)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>Text file that contains the Calling Address Controls to add to the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each line must contain a Calling Address Control definition following the syntax described above.</p>         </td>
      </tr>
      <tr>
         <td><p>add_vfd_right (-avr)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>List of VFD rights to add to the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each rights definition follows the syntax:</p>
<p><span class="code">&lt;VFD_dir_path&gt;: &lt;file_pattern&gt;: &lt;file_rights&gt;: &lt;directory_rights&gt;: &lt;subdir_inheritance&gt;</span></p>
<p>where:</p>
<ul>
<li><span class="code">VFD_dir_path</span>: Up to 127 alphanumeric characters</li>
<li><span class="code">file_pattern</span>: Up to 127 alphanumeric characters</li>
<li><span class="code">file_rights</span>: One to three alphanumeric characters, any combination of <span style="font-weight: bold;">R</span>, <span style="font-weight: bold;">W</span>, <span style="font-weight: bold;">D</span></li>
<li><span class="code">directory_rights</span>: One to three alphanumeric characters, any combination of <span style="font-weight: bold;">R</span>, <span style="font-weight: bold;">C</span>, <span style="font-weight: bold;">L</span></li>
<li><span class="code">subdir_inheritance</span>: enumerated [Y | N]</li>
</ul>
<p>This parameter can contain multiple rights definitions, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>add_vfd_right_file (-avrf)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>Text file that contains the VFD rights to add to the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each line must contain a rights definition that follows the syntax described above.</p>         </td>
      </tr>
      <tr>
         <td><p>called_addr (-ceda)</p>
<p><span style="font-weight: bold;">(CGATEGROUP) [S]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Called address</span></p>         </td>
         <td><p>Called address field for CGate selection.</p>         </td>
         <td><p>Maximum 64 alphanumeric characters, including wildcards</p>         </td>
      </tr>
      <tr>
         <td><p>calling_addr (-cinga)</p>
<p><span style="font-style: italic;font-weight: bold;">Calling address</span></p>         </td>
         <td><p>List of Calling Address Controls to associate with the CGate or CGateGroup being created</p>         </td>
         <td><p>Each rights definition follows the syntax:</p>
<p>"calling_address_pattern": "authorization"</p>
<ul>
<li><span style="font-style: italic;">calling_address_pattern</span>: Up to 31 alphanumeric characters, including wildcards</li>
<li><span style="font-style: italic;">authorization</span>: enumerated [ A (allowed) | D (denied) ]</li>
</ul>
<p>This parameter can contain multiple Calling Address Control definitions, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>calling_addr_file (-cingaf)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Text file that contains the Calling Address Controls to associate with the CGate or CGateGroup being created</p>         </td>
         <td><p>Each line must contain a Calling Address Control definition following the syntax described above</p>         </td>
      </tr>
      <tr>
         <td><p>change_password_option (-cpo)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Change password</span></p>         </td>
         <td><p>Defines password modification rights for a user connected to this CGate</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">N</span> = Never: a connected user can never change the password of this CGate</li>
<li><span style="font-weight: bold;">A</span> = Allowed: a connected user can change the password of this CGate</li>
<li><span style="font-weight: bold;">F</span> = Forced: a connected user must change the password of this CGate on first connection</li>
</ul>
<p>When the password is changed, the value of this parameter automatically switches to <span style="font-weight: bold;">A</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>client_ident (-ci)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Client ID</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>Client connection partner identifier</p>         </td>
         <td><p>Maximum 31 alphanumeric characters, including wildcards for generic pattern matching</p>         </td>
      </tr>
      <tr>
         <td><p>client_password (-cp)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Client password</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>Client connection partner password</p>         </td>
         <td><p>Maximum 31 alphanumeric characters, including wildcards for generic pattern matching</p>         </td>
      </tr>
      <tr>
         <td><p>command_sensitivity (-cmd_s)</p>
<p><span style="font-style: italic;font-weight: bold;">Command sensitivity</span></p>         </td>
         <td><p>FTP security</p>
<p>Level of command sensitivity.</p>
<p>This parameter allows you to define the number of commands that you can pass during a session. Each command corresponds to a certain credit, depending on how costly the command is in terms of memory and system resources. The higher the sensitivity, the fewer commands you can pass.</p>         </td>
         <td><p>Integer: 1 - 5.</p>
<p>1 is the lowest level of sensitivity.</p>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>Comments associated with the CGate or CGateGroup object</p>         </td>
         <td><p>Maximum 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>del_calling_addr (-dcinga)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>List of Calling Address Controls to remove from the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each Calling Address Controls definition is identified by an integer (internally set by Gateway) which you can obtain by displaying the contents of the CGateGroup object.</p>
<p>This parameter can contain multiple Calling Address Controls definition identifiers, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>del_vfd_right (-dvr)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying CGates/ CGateGroups</p>
<p>List of VFD rights to remove from the CGate or CGateGroup being updated</p>         </td>
         <td><p>Each rights definition is identified by an integer (internally set by Gateway) which you can obtain by displaying the contents of the CGate or CGateGroup object.</p>
<p>This parameter can contain multiple rights definitions identifiers, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>ftpcs_list_fields (-ftpcs_lf)</p>
<p><span style="font-style: italic;font-weight: bold;">FTP CS List fields</span></p>         </td>
         <td><p>In Responder mode, this field defines which columns will be sent in the LIST command to FTPCS clients.</p>
<p>If the item described in the list is not a virtual file, the only significant fields are GTYPE, RIGHTS, FILENAME, SFILENAME, DATE and SIZE. The Gateway FTP server completes these fields.</p>
<p>By default, the parameter lists all fields.</p>
<p>Regardless of the field order that you specify, fields are always sent in the same predefined order.</p>
<p>LOCID and GTYPE are required fields and are always sent to the client.</p>         </td>
         <td><p>A list of one or more of the following, separated by a comma:</p>
<ul>
<li>LOCID: local_ident</li>
<li>GTYPE: VFD type (real or virtual directory, mount point, real or virtual file)</li>
<li>RIGHTS: VFD rights</li>
<li>FILENAME: long name - s&lt;xfer_ident&gt;.&lt;filename&gt; for a virtual file. Otherwise &lt;filename&gt;.</li>
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
         <td><p>home_dir (-hd)</p>
<p><span style="font-weight: bold;">[O]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Home directory</span></p>         </td>
         <td><p>HTTP, SFTP and FTP only</p>
<p>VFD directory on which the first LIST command is processed just after the protocol connection</p>         </td>
         <td><p>Maximum 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>http_home_page (-hhp)</p>
<p><span style="font-weight: bold;">[O]</span></p>
<p><span style="font-style: italic;font-weight: bold;">HTTP home page</span></p>         </td>
         <td><p>HTTP only</p>
<p>Default HTTP home page that can be referenced through a symbolic link in the Gateway website HTML pages</p>         </td>
         <td><p>Maximum 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>http_host_name (-hhn)</p>
<p><span style="font-weight: bold;">(CGATEGROUP) [S]</span></p>
<p><span style="font-style: italic;font-weight: bold;">HTTP host name</span></p>         </td>
         <td><p>HTTP only</p>
<p>HTTP host name field for CGate selection</p>         </td>
         <td><p>Maximum 64 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>http_list_template (-hlt)</p>
<p><span style="font-weight: bold;">[O]</span></p>
<p><span style="font-style: italic;font-weight: bold;">HTTP list template</span></p>         </td>
         <td><p>HTTP only</p>
<p>Absolute file path pointing at an HTML page used for browsing the VFD directory tree</p>         </td>
         <td><p>Maximum 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>login_user (-lu)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Login user name</span></p>         </td>
         <td><ul>
<li>PeSIT HS: USERID from pre-connection message</li>
<li>FTP, SFTP and HTTP: the user name of the Client Station</li>
</ul>         </td>
         <td><p>Maximum 63 alphanumeric characters, including wildcards for generic pattern matching</p>         </td>
      </tr>
      <tr>
         <td><p>login_password (-lp)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Login password</span></p>         </td>
         <td><ul>
<li>PeSIT HS: PASSWORD from pre-connection message</li>
<li>FTP, SFTP and HTTP: the password associated with the user login field</li>
</ul>         </td>
         <td><p>Maximum 25 alphanumeric characters, including wildcards for generic pattern matching</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_rate (-max_downr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum downloads KB/min</span></p>         </td>
         <td><p>FTP security</p>
<p>To reduce the risk of hammer attacks, limit the size of downloaded data per minute.</p>         </td>
         <td><p>Integer (MB/min)</p>         </td>
      </tr>
      <tr>
         <td><p>max_download_requests_rate (-maxdownreqr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum downloads Requests/min</span></p>         </td>
         <td><p>FTP security</p>
<p>To reduce the risk of hammer attacks, limit the number of download requests per minute.</p>         </td>
         <td><p>Integer (number of requests /min)</p>         </td>
      </tr>
      <tr>
         <td><p>max_upload_rate (-max_upr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum uploads KB/min</span></p>         </td>
         <td><p>FTP security</p>
<p>To reduce the risk of hammer attacks, limit the size of uploaded data per minute.</p>         </td>
         <td><p>Integer (MB/min)</p>         </td>
      </tr>
      <tr>
         <td><p>max_upload_requests_rate (-maxupreqr)</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum uploads Requests/min</span></p>         </td>
         <td><p>FTP security</p>
<p>To reduce the risk of hammer attacks, limit the number of upload requests per minute.</p>         </td>
         <td><p>Integer (number of requests /min)</p>         </td>
      </tr>
      <tr>
         <td><p>max_upload_file_size</p>
<p><span style="font-style: italic;font-weight: bold;">Maximum upload file size</span></p>         </td>
         <td><p>FTP security</p>
<p>To reduce the risk of hammer attacks, limit the upload file size.</p>         </td>
         <td><p>Integer (MB)</p>         </td>
      </tr>
      <tr>
         <td><p>name (-n)</p>
<p><span style="font-style: italic;font-weight: bold;">Name</span></p>         </td>
         <td><p>CGate or CGateGroup unique identifier</p>         </td>
         <td><p>Maximum 21 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>parent_group (-pg)</p>
<p><span style="font-style: italic;font-weight: bold;">Parent CGateGroup</span></p>         </td>
         <td><p>CGate or CGateGroup parent group name</p>         </td>
         <td><p>Maximum 21 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>protocol (-pr)</p>
<p><span style="font-weight: bold;">(CGATEGROUP) [S]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Protocol</span></p>         </td>
         <td><p>CGateGroup associated protocol</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">FTP</span> = FTP</li>
<li><span style="font-weight: bold;">HTTP</span> = HTTP</li>
<li><span style="font-weight: bold;">FTP_HTTP</span> = FTP+HTTP</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">PEL</span> = PEL</li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li>RN_HTTP</li>
<li><span style="font-weight: bold;">*</span> = undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>recursive_mode (-rm)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Selecting a CGate/ CGateGroup</p>
<p>Flag indicating whether to apply the selection only to the CGate objects directly linked to the provided CGateGroup, or recursively to the whole hierarchy under the provided CGateGroup.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (yes)</li>
<li><span style="font-weight: bold;">N</span> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>remote_issuer_cert_alias (-risscerta)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Issuer certificate alias</span></p>         </td>
         <td><p>Remote certificate filter:</p>
<p>Certificate alias of the entity that issued and signed the subject certificate</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>remote_issuer_name_pattern (-rissnp)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Issuer name pattern</span></p>         </td>
         <td><p>Remote certificate filter:</p>
<p>Pattern to use to filter Issuer names.</p>         </td>
         <td><p>Use wildcard characters (? and *)</p>         </td>
      </tr>
      <tr>
         <td><p>remote_public_key_alias (-rpubka)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Public key alias</span></p>         </td>
         <td><p>SSH remote authentication:</p>
<p>Alias of the public key used to authenticate the partner</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>remote_public_key_group (-rpubkg)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Public key group</span></p>         </td>
         <td><p>SSH remote authentication:</p>
<p>Group name for the public key</p>         </td>
         <td><p>Maximum 15 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>remote_subject_cert_alias (-rsubcerta)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Subject certificate alias</span></p>         </td>
         <td><p>Remote certificate filter:</p>
<p>Alias of the partner certificate</p>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>remote_subject_name_pattern (-rsubnp)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Subject name pattern</span></p>         </td>
         <td><p>Remote certificate filter:</p>
<p>Name pattern to filter accepted subject certificates.</p>
<p>For example:</p>
<p>*O=Sopra,* CN=t*</p>         </td>
         <td><p>Can contain wildcard characters (* and ?)</p>         </td>
      </tr>
      <tr>
         <td><p>root_dir (-rd)</p>
<p><span style="font-weight: bold;">[O]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Root directory</span></p>         </td>
         <td><p>HTTP, SFTP and FTP only</p>
<p>VFD root directory of the connected user. Regardless of the VFD rights definition for the current CGate, the connected user only has access to the VFD directory tree under the root directory.</p>         </td>
         <td><p>Maximum 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>sap (sap)</p>
<p><span style="font-weight: bold;">(CGATEGROUP)[S]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Called SAP</span></p>         </td>
         <td><p>TCP/IP local connection port</p>         </td>
         <td><p>TCP/IP port with the following syntax:</p>
<ul>
<li>'<span style="font-weight: bold;">x</span>' for port x</li>
<li>'<span style="font-weight: bold;">x:y</span>' for port x to y</li>
<li>'<span style="font-weight: bold;">x y</span>' for port x and y</li>
</ul>
<p>Example: '23000:23010 24000 24002 25000:25010'</p>
<p>'<span style="font-weight: bold;">*</span>' = all SAPs</p>         </td>
      </tr>
      <tr>
         <td><p>server_ident (-si)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Server ID</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>Server connection partner identifier</p>         </td>
         <td><p>Maximum 31 alphanumeric characters, including wildcards for generic pattern matching</p>         </td>
      </tr>
      <tr>
         <td><p>server_password (-sp)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">Server password</span></p>         </td>
         <td><p>PeSIT HS E only</p>
<p>Server connection partner password returned to the connection partner</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>state (-s)</p>
<p><span style="font-style: italic;font-weight: bold;">State</span></p>         </td>
         <td><p>CGate or CGateGroup state</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = enabled</li>
<li><span style="font-weight: bold;">D</span> = disabled</li>
<li><span style="font-weight: bold;">U</span> = undefined (for CGateGroups only)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>template_site (-ts)</p>
<p><span style="font-weight: bold;">(CGATEGROUP) [S]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Template Site</span></p>         </td>
         <td><p>Alias of Template Site that represents the requesting client station</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>tls_client_auth (-tlscauth)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">TLS Client Authentication</span></p>         </td>
         <td><p>TLS connections only</p>
<p>Indicates whether or not client authentication is mandatory</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>tls_sprof (-tlss)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">TLS profile name</span></p>         </td>
         <td><p>TLS connections only</p>
<p>Incoming security profile name</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>tls_sprof_user_param (-tlssup)</p>
<p><span style="font-weight: bold;">(CGATE)</span></p>
<p><span style="font-style: italic;font-weight: bold;">TLS profile user parameter</span></p>         </td>
         <td><p>TLS connections only</p>
<p>User parameter taken from the incoming security profile name.</p>         </td>
         <td><p>Maximum 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>user_param1 (-usp1)</p>
<p>user_param2 (-usp2)</p>
<p><span style="font-weight: bold;">[A]</span></p>
<p><span style="font-style: italic;font-weight: bold;">Param 1 / Param 2</span></p>         </td>
         <td><p>User parameters used to customize VFD file availability and restrict visibility of routed files to defined clients.</p>         </td>
         <td><p>Maximum 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>vfd_right (-vr)</p>
<p><span style="font-weight: bold;">[A]</span></p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>List of VFD rights to associate with the CGate or CGateGroup that you create.</p>         </td>
         <td><p>Each rights definition follows the syntax:</p>
<p><span class="code">&lt;VFD_dir_path&gt;:</span> <span class="code">&lt;file_pattern&gt;:</span> <span class="code">&lt;file_rights&gt;:</span> <span class="code">&lt;directory_rights&gt;:</span> <span class="code">&lt;subdir_inheritance&gt;</span></p>
<p>where:</p>
<ul>
<li><span class="code">VFD_dir_path</span>: Up to 127 alphanumeric characters</li>
<li><span class="code">file_pattern</span>: Up to 127 alphanumeric characters</li>
<li><span class="code">file_rights</span>: One to three alphanumeric characters, any combination of <span style="font-weight: bold;">R</span>, <span style="font-weight: bold;">W</span>, <span style="font-weight: bold;">D</span></li>
<li><span class="code">directory_rights</span>: One to three alphanumeric characters, any combination of <span style="font-weight: bold;">R</span>, <span style="font-weight: bold;">C</span>, <span style="font-weight: bold;">L</span></li>
<li><span class="code">subdir_inheritance</span>: enumerated [Y | N]</li>
</ul>
<p>This parameter can contain multiple rights definitions, each separated by the semi-colon character (<span class="code" style="font-weight: bold;"> ;</span> ).</p>         </td>
      </tr>
      <tr>
         <td><p>vfd_right_file (vrf)</p>
<p><span style="font-weight: bold;">[A]</span></p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Text file that contains the VFD rights to associate with the CGate or CGateGroup that you create.</p>         </td>
         <td><p>Each line must contain a rights definition that follows the syntax described above.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with CGates (command line)](../)

[Working with CGateGroups (command line)](../working_with_cgategroups_cli)

[Working with CGates and CGateGroups](../../working_with_cgates_and_cgategroups_(gui))

[About CGates and CGateGroups](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
