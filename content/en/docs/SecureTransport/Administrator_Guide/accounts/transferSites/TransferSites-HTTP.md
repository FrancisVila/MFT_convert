{
    "title": "HTTP(S) transfer sites",
    "linkTitle": "HTTP(S) transfer sites",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server provides support for guaranteed delivery and restart for transfers using the HTTP protocol when the remote server is a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.

The *Add Transfer Site* page for HTTP(S) sites presents several sets of options.

## Server settings for HTTP(S) Transfer sites

The following table describes the general options for a HTTP(S) transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td><p>Select <strong>Specify partner using hostname (IP address) and port number</strong> to enable this field.</p>
<p>Enter either the <em>host name</em> or <em>IP address</em> of the remote host to connect to for file transfers. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.</p>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td><p>Select <strong>Specify partner using hostname (IP address) and port number</strong> to enable this field.</p>
<p>Enter the port number on the remote host to be used for file transfers. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.</p>         </td>
      </tr>
      <tr>
         <td>Alternative addresses         </td>
         <td><p>This set of options allow you to add, delete and set a priority order of alternative endpoints. These endpoints act as backup alternatives to the configured Server-Port Site Settings and are particularly useful in cases of transfer failures. Specifying alternative endpoints as backup servers provides a way to temporarily reroute pending transfers and minimize the risk of transfer failure. As with the Server-Port site settings, the connection to each alternative endpoint is defined by its host name (or IP address) and port number.</p>
<ul>
<li>To add an alternative server endpoint, click <strong>New Address</strong>. The Alternative Addresses table expands with a new row, that allows you to enter a hostname (or IP address), a port number and save these changes.</li>
<li>To delete an alternative server endpoint, select the corresponding check-box on the same row and click <strong>Delete</strong>.</li>
<li>To reorder the list of alternative endpoints, click <strong>Reorder</strong>. A new option (upward and downward arrow) appears next to each entry. You must hover with the mouse pointer over this newly appeared option and the mouse pointer will assume the "move" shape: a four-directional arrow pointer. This indicates which alternative endpoint is in focus. You can now drag &amp; drop it up and down to the order number you want it at. Perform this action with other alternative endpoints until the list is ordered according to your needs. When you are done, click <strong>Save Order</strong> to keep the newly changed order.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Visibility of this option is controlled with the value set for the TransferSite.AlternativeAddresses.retryPolicy configuration option. It allows you to set a "retry policy" with a list of alternative endpoints (presented in IP address: Port number pairs or hostname) you define on this screen. But before you are able to do so, you must go to Operations &gt; Server Configuration and set the policy type using either of the following values:</p>
</blockquote>
<ul>
<li><code>AllHostsOnEachRetry</code> – with this policy <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> iterates through each endpoint, one by one, starting with the first in the list. If connection not successful, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will continue trying each endpoint one after another until the maximum number of retries is reached. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.</li>
<li><code>OneHostOnEachRetry</code> – with this policy <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> tries to connect to the first endpoint in the list. If connection not successful, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will continue trying that endpoint until the maximum number of retries is reached; and then will move to the next one in the list. Following that same pattern, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will try each endpoint until success; or until end of list. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.</li>
<li><code>Disabled</code> (default) – this is the default value that keeps the table with endpoints entirely hidden from view.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>Select <strong>Specify partner using URL</strong> to enable this field. Note that with this selection, the <em>Alternative addresses</em> grid moves under this option on the screen.</p>
<p>Enter a URL that specifies the partner host. It can also include the port and a path (directory).</p>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>The network zone that defines the proxies to use for transfers through this site.</p>
<ul>
<li>Select <strong>none</strong> to connect directly to the remote HTTP server.</li>
<li>Select <strong>any</strong> to allow <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to select the proxy connection using a network zone that enables an HTTP proxy.</li>
<li>Select <strong>Default</strong> to use the default network zone proxy configuration. If no default network zone is defined, transfers from this transfer site fail.</li>
<li>Select a specific network zone to use the proxy configuration defined for that zone.</li>
</ul>
<p>For more information, see <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify2" class="MCXref xref">Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer"></span>

## Transfer settings for HTTP(S) Transfer sites

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
      </tr>
      <tr>
         <td>Download Folder         </td>
         <td><p>The folder on the remote server from which the file is transferred.</p>
<p>To use the expression language to append dates:</p>
<p>The download folder will be evaluated using the current date when the transfer site is being executed. For example <code>folder_20210130</code>.</p>
<p>Example:</p>
<p><code>folder_${date("yyyyMMdd")}</code></p>         </td>
      </tr>
      <tr>
         <td>Download Pattern         </td>
         <td><p>The pattern used to match file names to determine whether a file is downloaded. Asterisk (<code>*</code>) matches zero or more characters and question mark (<code>?</code>) matches one character.</p>
<p>To evaluate the download pattern using dates:</p>
<p>The download pattern will be evaluated using the current date when the transfer site is being executed. For example <code>*_20210130.txt</code>. This will match all files ending with <code>_20210130.txt</code>.</p>
<p>Example:</p>
<p><code>*_${date("yyyyMMdd")}.txt</code></p>         </td>
      </tr>
      <tr>
         <td>Allow Overwrite         </td>
         <td><p>Taken into account when the site is used by the Send To Partner step. If checked the value of "Upload folder" will be overwritten with the value of "Overwrite upload folder". For more details see <a href="../../../c_st_advanced_routing" class="MCXref xref">Advanced Routing</a>.</p>         </td>
      </tr>
      <tr>
         <td>Upload Folder         </td>
         <td>The folder on the remote server to which files are transferred.         </td>
      </tr>
      <tr>
         <td>Transfer Mode         </td>
         <td><p>Specify whether data is transferred as ASCII or binary. You can also choose to have <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> automatically determine the correct transfer mode.</p>
<p>For more information about automatically determining transfer mode, see <a href="../../../c_st_advancedaccountadministration/c_st_clientinitiatedandserverinitiatedtransfers/c_st_transfer_mode_for_server-initiated_transfers#Advanced_Accounts_2036285406_1242761" class="MCXref xref">Transfer mode for server-initiated transfers</a>.</p>         </td>
      </tr>
      <tr>
         <td>Use HTTPS         </td>
         <td>Deselect this check box to use HTTP instead of HTTPS.         </td>
      </tr>
      <tr>
         <td>Verify certificate for the Site         </td>
         <td>Select to verify that the remote system is trusted. This field is displayed when <strong>Use HTTPS</strong> is selected.         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Restrict HTTPS to use only FIPS 140-2 Level 1 certified cryptographic libraries. This field is displayed when <strong>Use HTTPS</strong> is selected.</p>
<p>When you enable FIPS transfer mode, the panel expands with an additional field that lets you specify the desired set of cipher suites to be used in FIPS mode for server-initiated transfers through this site. By default, this set is populated with the cipher suites as defined in the <code>Https.FIPS.SIT.Ciphers</code> configuration option.</p>
<p>You can add or remove cipher suites. The supported FIPS cipher suites from which you can select when adding a new one are listed in <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>. Note that both the sender and the recipient must use supported FIPS ciphers suites. Otherwise, the transfer will fail.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Site"></span>

## Site login credentials for HTTP(S) Transfer sites

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Site Login Credentials</strong>         </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td>Username used to log in to the HTTP server. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td>Select to use a password to log in to the HTTP server.         </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>Password used to log in to the HTTP server. Switching the toggle provides the ability to use Expression Language for evaluating the password.         </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td><p>A private certificate for SecureTransport used to log in to the FTP server. You can select a certificate or import a certificate. This field is displayed when Use HTTPS is selected.</p>
<p>When <strong>Use Expression Language</strong> is enabled, you can set the certificate dynamically by choosing the scope (account or server level) and providing a valid expression that will be evaluated to the name of an available certificate.</p>
<p>By default, the usage of expired X509 certificates is allowed for SIT transfers. To forbid it, set the <code>SIT.allowExpiredCertificates </code>to <code>false</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Post"></span>

## Post transmission Send options for HTTP(S) Transfer sites

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Post-transmission Settings – Send Options</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name.         </td>
      </tr>
      <tr>
         <td>On Temporary Failure         </td>
         <td>A temporary failure can occur when the transfer is incomplete and a retry occurs. Select one of the three choices: <strong>No Action</strong>, <strong>Delete Destination File</strong>, or <strong>Move File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete Destination File</strong> removes the file from the new location. Selecting <strong>Move File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td>On Failure         </td>
         <td>A failure occurs when the transfer is incomplete and all retry attempts were unsuccessful. Select one of the three choices: <strong>No Action</strong>, <strong>Delete Destination File</strong>, or <strong>Move File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete Destination File</strong> removes the file from the new location. Selecting <strong>Move File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
   </tbody>
</table>

<span id="Post2"></span>

## Post transmission Receive options for HTTP(S) Transfer sites

The Receive options subtab allows you to define post transmission actions on file receive success and failure. Click **Receive Options** to view these settings.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Post-transmission Settings – Receive Options</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name when the transfer is received. You can use the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific variable <code>${stenv.site_target}</code> which takes the value from the remote file path. See <a href="../../../c_st_expressionlanguage#Appendix_Exp_Lang_Rules_3592148187_1031337" class="MCXref xref">Expression Language</a> for information on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>-specific variables.         </td>
      </tr>
      <tr>
         <td>On Failure         </td>
         <td>A failure occurs when the transfer is incomplete and all retry attempts were unsuccessful. Select one of the three choices: <strong>No Action</strong>, Delete Source File, or <strong>Move File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the original location. If another file with the same name is transferred to this location, the original file is overwritten. Selecting Delete Source File removes the file from the original location. Selecting <strong>Move File To</strong> requires you to specify a directory in the location where you are transferring the files from and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td>On Success         </td>
         <td>Select one of the three choices: <strong>No Action</strong>, Delete Source File, or <strong>Move File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the original location. If another file with the same name is transferred to this location, the original file is overwritten. Selecting Delete Source File removes the file from the original location. Selecting <strong>Move File To</strong> requires you to specify a directory in the location where you are transferring the files from and to provide an expression used to rename the file.         </td>
      </tr>
   </tbody>
</table>

<span id="Advanced"></span>

## Advanced SSL settings for SSH Transfer sites

Advanced SSL settings allow you to define Cipher suites and SSL protocols with your current HTTP(S) Transfer Site. Select **Show Advanced SSL Settings** to expand the pane with available options.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Show Advanced SSL Settings</strong>         </td>
      </tr>
      <tr>
         <td>Cipher suites         </td>
         <td><p>The set of cipher suites available with the current HTTPS transfer site for secure SIT connection. By default this set is populated with the cipher suites as defined in the <code>Https.SIT.Ciphers</code> configuration option.</p>
<p>To reset to default values, click the button next to the tooltip.</p>         </td>
      </tr>
      <tr>
         <td>Enabled SSL protocols         </td>
         <td><p>The available SSL protocols for secure SIT connection with the current HTTPS transfer site. By default this option uses the SSL protocols as defined in the <code>Https.SIT.EnabledProtocols</code> configuration option.</p>
<p>To reset to default values, click the button next to the tooltip.</p>         </td>
      </tr>
   </tbody>
</table>

 

> **Note:**
>
> To preserve the original file name when using the Move File To option, use the ${stenv.target} or ${stenv\['target'\]} expressions.

> **Note:**
>
> When Single Sign-On (SSO) for end-users is enabled, you can not transfer files over HTTP(S).

> **Note:**
>
> SecureTransport will not be able perform server initiated file pushes or pulls over HTTP to and from another SecureTransport instance if the second requires SSO authentication for the users as the HTTP transfer site cannot handle the SSO authentication.

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>