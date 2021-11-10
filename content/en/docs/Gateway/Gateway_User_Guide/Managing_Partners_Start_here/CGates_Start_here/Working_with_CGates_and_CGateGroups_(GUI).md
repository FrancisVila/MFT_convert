{
    "title": "Working with CGates and CGateGroups",
    "linkTitle": "Working with CGates and CGateGroups",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[Creating a CGateGroup or CGate](#Creating_new_CGate_and_CGateGroup_objects)

[Modifying a CGate](#Modifying_a_CGate_object)

[Modifying a CGateGroup](#Modifying_a_CGateGroup_object)

[Viewing CGate attributes](#Viewing_CGate_attributes)

[Viewing CGateGroup attributes](#Viewing_CGateGroup_attributes)

[Deleting a CGate](#Deleting_a_CGate_object)

[Deleting a CGateGroup](#Deleting_a_CGateGroup_object)

## Overview

All CGate objects must belong to a CGateGroup parent object. You must therefore create the CGateGroup before you can create a CGate object.

CGateGroup and CGate objects share many of the same parameters, displayed on the following tabs:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>CGateGroup tab</p>         </td>
         <td><p>CGate tab</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#CGateGroup_General">General</a></p>         </td>
         <td><p><a href="#CGate_General">General</a></p>         </td>
         <td><p>Different parameters for CGate and CGateGroup objects</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Output_parameters">Output parameters</a></p>         </td>
         <td><p>Identical parameters for both CGate and CGateGroup objects</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#VFD_Rights">VFD Rights</a></p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Calling_Address_Controls">Calling Address Controls</a></p>         </td>
      </tr>
      <tr>
         <td><p>–</p>         </td>
         <td><p><a href="#CGate_Security">Security</a></p>         </td>
         <td><p>CGate objects only</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Creating_new_CGate_and_CGateGroup_objects"></span>

## Creating new CGate and CGateGroup objects

To create a new root CGateGroup object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>

Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window. Complete this window to define the characteristics of your new CGateGroup.

<span style="font-weight: bold;">To create a new CGateGroup object within another parent CGateGroup:</span>

1.  Right-click an existing CGateGroup in which you want to create a new CGateGroup.
2.  Select <span style="font-weight: bold;">New > CGateGroup</span> from the context menu to display the <span style="font-style: italic;">New CGateGroup</span> window. Complete this window to define the characteristics of your new CGateGroup.

<span style="font-weight: bold;">To create a new CGate object:</span>

1.  Right-click the parent CGateGroup where you want to create the CGate.
2.  Select <span style="font-weight: bold;">New > CGate</span> from the context menu to display the <span style="font-style: italic;">New CGate</span> window. Complete this window to define the characteristics of your new CGate.

<span id="CGateGroup_General"></span>

### CGateGroup: General tab

Complete the fields on the CGateGroup <span style="font-weight: bold;">General</span> tab as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a unique name for the CGateGroup.<br />
Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Parent CGateGroup</p>         </td>
         <td><p>This field displays the name of the parent CGateGroup with which the new object is associated. This field is grayed out and is non-modifiable. If the new object is the root CGateGroup, this field remains blank.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>
<p>(optional)</p>         </td>
         <td><p>Enter a free-text description for the object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>Select the state of the object:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span>: Gateway takes into account the State definition from the next CGateGroup or CGate object in the hierarchy</li>
<li><span style="font-weight: bold;">Enabled</span>: all CGateGroups and CGates below this object in the hierarchy are also enabled, regardless of the State setting for those objects</li>
<li><span style="font-weight: bold;">Disabled</span>: all CGateGroups and CGates below this object in the hierarchy are also disabled, regardless of the State setting for those objects</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Identification</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li>All</li>
<li>PeSIT D</li>
<li>PeSIT E</li>
<li>FTP</li>
<li>HTTP</li>
<li>FTP/HTTP</li>
<li>PEL</li>
<li>OFTP</li>
<li>SFTP</li>
<li>AS2</li>
<li>AS3</li>
<li>RosettaNet HTTP</li>
</ul>
<p>CGate identification does not apply to SMTP and POP3 protocols since they do not support server mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Called address</p>
<p>(optional)</p>         </td>
         <td><p>Enter the called TCP/IP address for this CGateGroup. You can only specify this address once in a given hierarchy.</p>
<p>Maximum: 64 alphanumeric characters, including wildcards.</p>         </td>
      </tr>
      <tr>
         <td><p>Called SAP</p>         </td>
         <td><p>Specify the TCP/IP local connection port. Use the following syntax:</p>
<ul>
<li><span style="font-weight: bold;">x</span> for port x</li>
<li><span style="font-weight: bold;">x:y</span> for port x to y</li>
<li><span style="font-weight: bold;">x y</span> for ports x and y</li>
<li><span style="font-weight: bold;">*</span> for all SAPs</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>HTTP host name</p>         </td>
         <td><p>HTTP only</p>
<p>Specify the HTTP host name for this CGate selection. You can only specify this Host Name once in a given hierarchy.</p>
<p>Maximum: 64 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Use Dynamic Site</p>         </td>
      </tr>
      <tr>
         <td><p>Template Site</p>         </td>
         <td><p>Select the Template Site that you want Gateway to use to create a dynamic Site.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="CGate_General"></span>

### CGate: General tab

Complete the fields on the CGate <span style="font-weight: bold;">General</span> tab as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a unique identifier for the new object.<br />
Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Parent CGateGroup</p>         </td>
         <td><p>This field displays the name of the parent CGateGroup with which the new object is associated. This field is grayed out and is non-modifiable.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>
<p>(optional)</p>         </td>
         <td><p>Enter a free-text description for the object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>Select the state of the object:</p>
<ul>
<li>Enabled</li>
<li>Disabled</li>
</ul>
<p>The CGateGroup State definition overrides the value that you set for the CGate. The value that you set here is only taken into account if the CGateGroup State definition is set to <span style="font-weight: bold;">Undefined</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP / FTP / SFTP / PeSIT pre-connection</p>
<p>Identification / Checking</p>         </td>
      </tr>
      <tr>
         <td><p>Login user name</p>         </td>
         <td><p>Enter the user login depending on the protocol:</p>
<ul>
<li>FTP / HTTP / SFTP: enter the user name of the Client Station</li>
<li>PeSIT HS: enter the USERID from the pre-connection message</li>
</ul>
<p>Maximum: 63 alphanumeric characters, including wildcards for generic pattern matching.</p>         </td>
      </tr>
      <tr>
         <td><p>Change password</p>         </td>
         <td><p>Define password modification rights for a user connected to this CGate:</p>
<ul>
<li><span style="font-weight: bold;">Never</span>: a connected user can never modify the password</li>
<li><span style="font-weight: bold;">Forced</span>: a connected user must modify the password for this CGate on next connection</li>
<li><span style="font-weight: bold;">Allowed</span>: a connected user can modify the password</li>
</ul>
<p>The syntax for changing the password is <code>oldpass:newpass:newpass</code></p>         </td>
      </tr>
      <tr>
         <td><p>Set login password</p>         </td>
         <td><p>Opens a dialog box to enter the login password depending on the protocol:</p>
<ul>
<li>HTTP/FTP/SFTP: enter the password associated with the user login field</li>
<li>PeSIT: enter the PASSWORD from the pre-connection message</li>
</ul>
<p>Maximum: 64 alphanumeric characters, including wildcards for generic pattern matching.</p>         </td>
      </tr>
      <tr>
         <td><p>PHSE</p>
<p>Identification / Checking</p>         </td>
      </tr>
      <tr>
         <td><p>Client ID</p>         </td>
         <td><p>Enter the PeSIT client identifier.<br />
Maximum: 31 alphanumeric characters, including wildcards for generic pattern matching.</p>         </td>
      </tr>
      <tr>
         <td><p>Server ID</p>         </td>
         <td><p>Enter the PeSIT server identifier.<br />
Maximum: 31 alphanumeric characters, including wildcards for generic pattern matching.</p>         </td>
      </tr>
      <tr>
         <td><p>Set client password</p>         </td>
         <td><p>Opens a dialog box to enter the PeSIT client password.<br />
Maximum: 31 alphanumeric characters, including wildcards for generic pattern matching.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="CGate_Security"></span>

### CGate: Security tab

The fields on the <span style="font-weight: bold;">Security</span> tab are only relevant to TLS connections and SSH connections for SFTP.

Complete the fields as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>TLS remote authentication</p>         </td>
      </tr>
      <tr>
         <td><p>TLS Client Authentication</p>         </td>
         <td><p>Check this box to indicate that TLS client authentication is mandatory.</p>         </td>
      </tr>
      <tr>
         <td><p>TLS profile name</p>         </td>
         <td><p>Enter the incoming TLS Profile name.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>TLS profile user parameter</p>         </td>
         <td><p>Specify the user parameter taken from the incoming security profile name.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>SSH remote authentication</p>
<p>If you select to authenticate the partner by a certificate, you do not need to complete the <span style="font-weight: bold;">Public key alias</span> or <span style="font-weight: bold;">Public key group</span> fields. If you select to authenticate the partner by a public key, you do not need to complete the <span style="font-weight: bold;">Remote certificate</span> fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Public key alias</p>         </td>
         <td><p>Select a public key alias.</p>
<p>The public key allows you to check the signature of the partner (encrypted with its private key). The only reliable way to guarantee the identity of a partner is to keep a copy of the partners public key in the Gateway database.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Public key group</p>
<p>(optional)</p>         </td>
         <td><p>Enter a group name for the public key used to authenticate the partner.<br />
Default = GDEFAULT.<br />
Maximum: 15 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>TLS (only FTP/HTTP) and SSH remote certificate filter</p>         </td>
      </tr>
      <tr>
         <td><p>Subject certificate alias</p>         </td>
         <td><p>Select the certificate alias used to authenticate the partner.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Issuer certificate alias</p>         </td>
         <td><p>Select the issuer certificate alias from the drop-down list. This is the alias of the CA certificate used to sign and issue the partner certificate.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Subject name pattern</p>         </td>
         <td><p>To filter accepted Subject certificate names, you can optionally enter a pattern using wildcard characters (* and ?).</p>
<p>For example, if you specify the name pattern: <span style="font-weight: bold;">*O=Sopra,* CN=t*</span>, Gateway accepts all certificates from the organization Sopra with a certificate name that begins with the letter <span style="font-weight: bold;">t</span>.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Issuer name pattern</p>         </td>
         <td><p>To filter accepted Issuer certificate names, you can optionally enter an Issuer name pattern using wildcard characters (* and ?).</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Remote PassPort PS partner entity filter</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>When Gateway operates in server mode with a partner defined in PassPort, enter the identity of the PassPort partner.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Output_parameters"></span>

### CGate/CGateGroup: Output parameters tab

Use the <span style="font-weight: bold;">Output parameters</span> tab to define parameters for the current connection. The fields on this tab are identical for both CGateGroup and CGate objects.

Complete the fields as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>General information</p>         </td>
      </tr>
      <tr>
         <td><p>Root directory</p>         </td>
         <td><p>HTTP and FTP only</p>
<p>Select the VFD root directory of the connected user. Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree below the root directory.<br />
Maximum: 256 alphanumeric characters.</p>
<p>Use the <span style="font-weight: bold;">Browse</span> button to display the VFD directory tree.</p>
<p>The value that you enter in this field is overwritten by any root directory value that you specify in a parent CGateGroup.</p>         </td>
      </tr>
      <tr>
         <td><p>Home directory</p>         </td>
         <td><p>HTTP and FTP only</p>
<p>Select the VFD directory on which the first LIST command is processed following protocol connection.</p>
<p>Maximum: 256 alphanumeric characters.</p>
<p>Use the <span style="font-weight: bold;">Browse</span> button to display the VFD directory tree.</p>
<p>The value that you enter in this field is overwritten by any home directory value that you specify in a parent CGate.</p>         </td>
      </tr>
      <tr>
         <td><p>User parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>User parameters 1 and 2 are additive parameters that allow you to customize VFD logical file availability and restrict file visibility to defined clients. To make a Transfer visible from a given client, the parameter settings must match one of the user parameters in the selected CGate hierarchy.</p>
<p>These parameters also exist in the Gateway Mailbox record (this data is duplicated in the corresponding VFD Item or logical file). You can implicitly set these parameters from a Remote Site by using RP1=param1 and RP2= param2 as a user message in the SEND command. The outgoing Transfer inherits these parameter values from the incoming Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP specific</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP home page</p>         </td>
         <td><p>Enter the default HTTP home page that is referenced via a symbolic link in the Gateway website HTML pages.<br />
Maximum: 256 alphanumeric characters.</p>
<p>Use the <span style="font-weight: bold;">Browse</span> button to display the VFD directory tree.</p>
<p>This value is overwritten by any value that you specify in a parent CGate.</p>         </td>
      </tr>
      <tr>
         <td><p>HTTP list template</p>         </td>
         <td><p>Enter the absolute file path that points to an HTML page used for browsing the VFD directory tree.<br />
Maximum: 256 alphanumeric characters.</p>
<p>This value is overwritten by any value that you specify in a parent CGateGroup.</p>         </td>
      </tr>
      <tr>
         <td><p>FTP quotas</p>
<p>Use the quotas section to defend against hammer attacks. A hammer attack can occur when a user floods the server with requests until it can no longer respond to any other users.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum uploads</p>
<p>KB/min</p>         </td>
         <td><p>Set the maximum number of Kbytes that you can upload per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum uploads</p>
<p>Requests /min</p>         </td>
         <td><p>Set the maximum number of Transfer Requests that you can upload per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum file size</p>         </td>
         <td><p>Set the maximum file size in megabytes.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum downloads</p>
<p>KB/min</p>         </td>
         <td><p>Set the maximum number of Kbytes that you can download per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum downloads</p>
<p>Requests /min</p>         </td>
         <td><p>Set the maximum number of Transfer Requests that you can download per minute.</p>         </td>
      </tr>
      <tr>
         <td><p>Command sensitivity</p>         </td>
         <td><p>Move the sensitivity cursor to the level of sensitivity required.</p>
<p>This parameter allows you to define the number of commands that you can pass during a session. Each command corresponds to a certain credit, depending on how costly the command is in terms of memory and system resources. The higher the sensitivity, the fewer commands you can pass.</p>         </td>
      </tr>
      <tr>
         <td><p>PHSE specific</p>         </td>
      </tr>
      <tr>
         <td><p>Server password</p>         </td>
         <td><p><span style="font-style: italic;">CGate only</span></p>
<p>Enter the server connection partner password that is returned to the server.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>FTPCS</p>         </td>
      </tr>
      <tr>
         <td><p>FTPCS List fields</p>         </td>
         <td><p>In Responder mode, define which columns to send to FTPCS clients in the <span class="code" style="font-weight: bold;">LIST</span> command.</p>
<p>Check the <span style="font-weight: bold;">FTPCS</span> option.</p>
<p>Then click the <span style="font-weight: bold;">FTPCS List fields</span> button to display the list of fields that you can send to the FTPCS client. By default, all columns are listed.</p>
<p>Regardless of the field order that you specify, fields are always sent in the same predefined order (as listed below).</p>
<p>Check one or more of the following:</p>
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
</ul>
<p>If the item described in the list is not a virtual file, the only significant fields are GTYPE, RIGHTS, FILENAME, SFILENAME, DATE and SIZE. The Gateway FTP server completes these fields.</p>
<p>LOCID and GTYPE are required fields and are always sent to the client.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="VFD_Rights"></span>

### 

When receiving files, the specified directory must be relative to the home directory or root directory. If the path specified in the transfer is not present on the target VFD, the transfer is stored in home directory (or root directory if home directory is not present).

### CGate/CGateGroup: VFD Rights tab

Use the <span style="font-weight: bold;">VFD Rights</span> tab to define user access to the Virtual File Directory tree. VFD rights are additive parameters: all VFD rights that you define within a given CGate hierarchy are taken into account. The fields on this tab are identical for both CGate and CGateGroup objects.

1.  Complete the fields as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Directory path</p>         </td>
         <td><p>Use the <span style="font-weight: bold;">Browse</span> button to display the VFD directory tree and select a directory.</p>
<p>Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree below the root directory.</p>
<p>Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>File pattern</p>         </td>
         <td><p>Use this field to further refine the VFD rights to specific file types. For example, enter <span class="code" style="font-weight: bold;">*.txt</span> in this field to apply the VFD rights only to<span class="code"> .txt</span> files within the specified directory.</p>         </td>
      </tr>
      <tr>
         <td><p>General information</p>         </td>
      </tr>
      <tr>
         <td><p>Subdirectory inheritance</p>         </td>
         <td><p>Check this box to indicate that all sub-directories inherit the parameters that you set here.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory rights</p>         </td>
      </tr>
      <tr>
         <td><p>Directory rights</p>         </td>
         <td><p>Check one or more of the following boxes to define the type of operations users can perform on VFD directories:</p>
<ul>
<li>List</li>
<li>Create</li>
<li>Remove</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File rights</p>         </td>
      </tr>
      <tr>
         <td><p>File rights</p>         </td>
         <td><p>Check one or more of the following boxes to define the type of operations users can perform on VFD files:</p>
<ul>
<li>Read</li>
<li>Delete</li>
<li>Write</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

1.  After completing this tab, click the <span style="font-weight: bold;">Add</span> button to add the VFD rights definition in the upper part of the window.

<span id="Calling_Address_Controls"></span>

### CGate/CGateGroup: Calling Address Controls tab

Use the <span style="font-weight: bold;">Calling Address Controls</span> tab to authorize or deny access from specific TCP/IP calling addresses. The fields on this tab are identical for both CGate and CGateGroup objects.

1.  Complete the fields as follows:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Calling address</p>         </td>
         <td><p>Enter the TCP/IP calling address for which you want to authorize or deny access.<br />
You can use wildcard characters (<span style="font-weight: bold;">*</span> and <span style="font-weight: bold;">?</span>).</p>
<p>Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Access allowed</p>         </td>
         <td><p>Check this box to authorize access from the specified calling address. If you do not check this box, access is denied.</p>         </td>
      </tr>
   </tbody>
</table>

1.  After completing this tab, click the <span style="font-weight: bold;">Add</span> button to add your definition to the list displayed in the upper part of the window.

<span id="Modifying_a_CGate_object"></span>

## Modifying a CGate object

To modify an existing CGate via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; CGate

Gateway displays all existing CGateGroups in the tree structure of the left pane.

1.  Click to select the CGateGroup that contains the CGate you want to modify.

Gateway displays all CGates that comprise the CGateGroup in the right (display) pane.

1.  In the right pane, right-click to select the CGate that you want to modify.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">Modify</span> from the context menu.

Gateway opens the <span style="font-style: italic;">CGate</span> editing window.

1.  Use the <span style="font-style: italic;">CGate</span> editing window to modify the CGate characteristics, and then click <span style="font-weight: bold;">OK</span> to confirm the changes.

<span id="Modifying_a_CGateGroup_object"></span>

## Modifying a CGateGroup object

To modify an existing CGateGroup via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">CGate</span> node.

Gateway lists all existing CGateGroups in the right (display) pane.

1.  In the right pane, right-click to select the CGateGroup that you want to modify.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">Modify</span> from the context menu.

Gateway opens the <span style="font-style: italic;">CGateGroup</span> editing window.

1.  Use the <span style="font-style: italic;">CGateGroup</span> editing window to modify the CGateGroup characteristics, and then click <span style="font-weight: bold;">OK</span> to confirm the changes.

<span id="Viewing_CGate_attributes"></span>

## Viewing CGate attributes

To view the attributes of an existing CGate object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; CGate

Gateway displays all existing CGateGroups in the tree structure of the left pane.

1.  Click to select the CGateGroup that contains the CGate you want to view.

Gateway displays all CGates that comprise the CGateGroup in the right (display) pane.

1.  In the right pane, right-click to select the CGate that you want to view.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">View</span> from the context menu.

Gateway opens the <span style="font-style: italic;">CGate (read only)</span> window. This window provides you with a view of all attributes for the selected CGate.

1.  After viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Viewing_CGateGroup_attributes"></span>

## Viewing CGateGroup attributes

To view the attributes of an existing CGateGroup object via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">CGate</span> node. Gateway lists all existing CGateGroups in the right (display) pane.
3.  In the right pane, right-click to select the CGateGroup that you want to modify.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">View</span> from the context menu.

Gateway opens the <span style="font-style: italic;">CGateGroup (read only)</span> window. This window provides you with a view of all attributes for the selected CGateGroup.

1.  After viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Deleting_a_CGate_object"></span>

## Deleting a CGate object

To delete an existing CGate object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; CGate

Gateway displays all existing CGateGroups in the tree structure of the left pane.

1.  Click to select the CGateGroup that contains the CGate you want to delete.

Gateway displays all CGates that comprise the CGateGroup in the right (display) pane.

1.  In the right pane, right-click to select the CGate that you want to delete.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">Delete...</span> from the context menu.

Gateway displays a confirmation dialog box.

1.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.

Gateway deletes the CGate object from the data base and removes the entry from the display window.

<span id="Deleting_a_CGateGroup_object"></span>

## Deleting a CGateGroup object

<span style="font-weight: bold;">Note:</span> Before you can delete a CGateGroup, you must delete all of the CGates that the CGateGroup contains.

To delete an existing CGateGroup object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">CGate</span> node.

Gateway lists all existing CGateGroups in the right (display) pane.

1.  In the right pane, right-click to select the CGateGroup that you want to delete.

Gateway displays a context menu.

1.  Select <span style="font-weight: bold;">Delete...</span> from the context menu.

Gateway displays a confirmation dialog box.

1.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.

Gateway deletes the CGateGroup object from the database and removes the entry from the display window (right pane) and from the directory tree (left pane).

Related topics

[Working with CGates (command line)](../working_with_cgates_cli)

[Working with CGateGroups (command line)](../working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](../working_with_cgates_cli/cgates_parameter_list)

[About CGates and CGateGroups](../)

[Overview: Connection Gates](../../../ov_gateway/ov_connection_gates)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
