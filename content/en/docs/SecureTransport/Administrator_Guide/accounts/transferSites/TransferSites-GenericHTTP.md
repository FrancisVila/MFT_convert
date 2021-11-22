{
    "title": "Generic HTTP transfer sites",
    "linkTitle": "Generic HTTP transfer sites",
    "weight": "230"
}The Generic HTTP transfer site enables file exchange via HTTP protocol with third-party partners over an authenticated connection.

The supported authentication methods are:

-   Basic – The client provides a user ID or user ID and password when exchanging files.
-   Form-Based – The client will send a request to a remote HTTP server to obtain an authentication cookie.
-   Certificate – A HTTPS client certificate is used for mutual authentication. The client certificate can be used in combination with basic or form-based authentications.

The Generic HTTP transfer site can be used with the Basic and {{< SecureTransport/advancedrouting  >}} applications for push and pull server-initiated transfers.

The following sections describe the Generic HTTP transfer site configuration options, provide basic sample push and pull flow configurations for Generic HTTP transfer sites, and information on the limited expression language supported by Generic HTTP transfer sites:

-   <a href="#Configur" class="MCXref xref">Settings for Generic HTTP transfer sites</a>
-   <a href="#List" class="MCXref xref">Sample configuration — List files and download</a>
-   <a href="#Download" class="MCXref xref">Sample configuration — Download file</a>
-   <a href="#Upload" class="MCXref xref">Sample configuration — Upload file</a>
-   <a href="#Push" class="MCXref xref">Sample configuration — Push file to SecureTransport user using Form Authentication</a>
-   <a href="#Supporte" class="MCXref xref">Supported expression language</a>

<span id="Configur"></span>

## Settings for Generic HTTP transfer sites

The configuration for Generic HTTP transfer site includes the following groups of settings:

-   <a href="#Server" class="MCXref xref">Server settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Transfer" class="MCXref xref">Transfer settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#List2" class="MCXref xref">List settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#File" class="MCXref xref">File download settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Receive" class="MCXref xref">Receive actions
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Upload2" class="MCXref xref">Upload settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Send" class="MCXref xref">Send actions
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Login" class="MCXref xref">Login settings
    for Generic HTTP(S) Transfer sites</a>
-   <a href="#Advanced" class="MCXref xref">Advanced settings
    for Generic HTTP(S) Transfer sites</a>

<span id="Server"></span>

### Server settings for Generic HTTP(S) Transfer sites

The following table describes the server settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadE-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Specify partner using hostname (IP address) and port number         </td>
         <td>When selected, the partner will be specified using the partner hostname and port number.         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>The host name or IP address of the remote host to connect to for file transfers.         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>The port on the remote host to be used for file transfers.         </td>
      </tr>
      <tr>
         <td>Specify partner using URL         </td>
         <td>When selected, the partner will be specified using an URL.         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>A URL that specifies the partner host. It can also include the port and a directory.</p>
<p>Examples:</p>
<ul>
<li><code>http://example.com</code></li>
<li><code>https://example.com:443</code></li>
<li><code>https://example.com:443/websealjun/</code></li>
</ul>         </td>
      </tr>
      <tr>
         <td>Zone         </td>
         <td><p>The network zone that defines the proxies to use for transfers through this site.</p>
<ul>
<li>Select <strong>none</strong> to connect directly to the remote HTTP server.</li>
<li>Select <strong>any</strong> to allow {{< SecureTransport/componentshortname  >}} to select the proxy connection using a network zone that enables an HTTP proxy.</li>
<li>Select <strong>Default</strong> to use the default network zone proxy configuration. If no default network zone is defined, transfers from this transfer site fail.</li>
<li>Select a specific network zone to use the proxy configuration defined for that zone.</li>
</ul>
<p>For more information, see <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify2" class="MCXref xref">Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer"></span>

### Transfer settings for Generic HTTP(S) Transfer sites

The following table describes the transfer settings for defining a Generic HTTP transfer site.

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
         <td>Use HTTPS         </td>
         <td><p>A check box indicating if the connection should be secured or not.</p>
<p>Deselect this check box to use HTTP instead of HTTPS.</p>         </td>
      </tr>
      <tr>
         <td>Verify certificate for this Site         </td>
         <td><p>Select to verify that the remote system is trusted. This field is displayed when <strong>Use HTTPS</strong> is selected.</p>         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Restrict HTTPS to use only FIPS 140-2 Level 1 certified cryptographic libraries. This field is displayed when <strong>Use HTTPS</strong> is selected.</p>
<p>The sender and the recipient must use the ciphers and ciphers suites listed in <a href="../../../c_st_fipstransfermode#Appendix_FIPS_3980222383_1010689" class="MCXref xref">FIPS transfer mode</a>. If the sender and the recipient do not provide the required ciphers and ciphers suites {{< SecureTransport/componentshortname  >}} does not complete the transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="List2"></span>

### List settings for Generic HTTP(S) Transfer sites

The following table describes the list settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>List settings</strong>         </td>
      </tr>
      <tr>
         <td>Enable list         </td>
         <td>A check box indicating if the Generic HTTP transfer site will operate in the single file download mode or will list files and then perform the download operation(s). If checked, the Generic HTTP transfer site will take as an input the result of the configured request and use it as a source for retrieving a list of files to be downloaded. It will then will use the <em>File download settings</em> to download each file from the list.         </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>The HTTP server path that will be used to list files on the remote server:</p>
<ul>
<li>A server absolute path when the partner is specified using a hostname (IP address) and port number.<br />
Example:<br />
<code>/list.php</code></li>
<li>A server relative path when the partner is specified using an URL.<br />
Example:<br />
<code>list.php</code></li>
</ul>
<p>The limited expression language can be used to specify the URL.</p>
<p>Example:</p>
<p>If the value in <strong>Specify partner using URL</strong> is <code>https://‹host›:‹port›/downloads/</code> and the value for <strong>URL path</strong> is <code>/list.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/list.php</code>. This occurs because <code>/list.php</code> is an absolute path and not a relative path. If the value for <strong>URL path</strong> is <code>list.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/downloads/list.php</code>.</p>
<p>This field is displayed when <strong>Enable list</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>File expression         </td>
         <td><p>The expression for the file names that will be applied on the response for the list request to extract the files list. A Java regular expression and the {{< SecureTransport/componentshortname  >}} expression language can be used to specify a pattern to match the files that need to be downloaded.</p>
<p>It is possible to use () parenthesis in the file expression and everything within the parenthesis will be considered the file name.</p>
<p>Example:</p>
<p>Filename= <code>(/something/folder/file\\d.txt)</code></p>
<p>If they are not used, the matched expression will be the file name.</p>
<p>The limited expression language can be used to specify the file name.</p>
<p>This field is displayed when <strong>Enable list</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>The HTTP method to be used for listing the files on the remote server. Either <strong>GET</strong> or <strong>POST</strong> can be selected.</p>
<p>This field is displayed when <strong>Enable list</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>The HTTP headers that will be added in the HTTP request for listing files on the remote server.</p>
<p>To add a header, click <strong>Add Header</strong> and complete the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To edit a header, click the <strong>Edit</strong> (<img src="/Images/SecureTransport/EditIcon.png" />) icon and change the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To delete a header, select the header to delete and click <strong>Delete</strong>.</p>
<p>This Header option is displayed when <strong>Enable list</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>The body of the request for listing files on the remote server. This field is displayed when the selected list Method is <strong>POST</strong>.</p>
<p>The limited expression language can be used to specify the file name.</p>
<p>The body can be any of the following types:</p>
<ul>
<li><strong>form-data</strong> - When selected the body will be transmitted as <code>multipart/form-data</code>.</li>
<li><strong>form-urlencoded</strong> - When selected the body will be transmitted as <code>application/x-www-form-urlencoded</code>.</li>
<li><strong>raw</strong> – When selected the body can be any text.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>When the selected body content type is form-data or form-urlencoded the body should be formed of key-value pairs on separate lines. Example:param1=value1param2=value2</p>
</blockquote>
<p>This field is displayed when <strong>Enable list</strong> is checked and <strong>POST</strong> is the selected Method.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="File"></span>

### File download settings for Generic HTTP(S) Transfer sites

The following table describes the file download settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>File download</strong>         </td>
      </tr>
      <tr>
         <td>File download settings         </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>The HTTP server path used to download file(s):</p>
<ul>
<li>A server absolute path when the partner is specified using a hostname (IP address) and port number.<br />
Example:<br />
<code>/download.php</code></li>
<li>A server relative path when the partner is specified using an URL.<br />
Example:<br />
<code>download.php</code></li>
</ul>
<p>If <strong>Enable list</strong> is checked, this URL will be used to download file(s) extracted from the list operation.</p>
<p>The limited expression language can be used to specify the URL.</p>
<p>The available environment variables are:</p>
<ul>
<li><code>${env['ts_relative_path']}</code>- The relative path of the file that will be downloaded.</li>
<li><code>${env['ts_target']}</code> - The file name of the file that will be downloaded.</li>
</ul>
<p>Example:</p>
<p>If the value in <strong>Specify partner using URL</strong> is <code>https://‹host›:‹port›/downloads/</code> and the value for <strong>URL path</strong> is <code>/download.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/download.php</code>. This occurs because <code>/download.php</code> is an absolute path and not a relative path. If the value for <strong>URL path</strong> is <code>download.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/downloads/download.php</code>.</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td>The HTTP method to be used for the file download operation. Either <strong>GET</strong> or <strong>POST</strong> can be selected. If <strong>Enable list</strong> is checked, this method will be used when performing all download operations for the files listed on the remote server.         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>The HTTP headers that will be added in the HTTP download request. If <strong>Enable list</strong> is checked, these headers will be added in all the HTTP download requests for the files listed on the remote server.</p>
<p>To add a header, click <strong>Add Header</strong> and complete the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To edit a header, click the <strong>Edit</strong> (<img src="/Images/SecureTransport/EditIcon.png" />) icon and change the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To delete a header, select the header to delete and click <strong>Delete</strong>.</p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>The body of the download request. This field is displayed when the selected download Method is <strong>POST</strong>. If <strong>Enable list</strong> is checked, the body will be added in all the HTTP download requests.</p>
<p>The limited expression language can be used to specify the body.</p>
<p>The body can be any of the following types:</p>
<ul>
<li><strong>form-data</strong> - When selected the body will be transmitted as <code>multipart/form-data</code>.</li>
<li><strong>form-urlencoded</strong> - When selected the body will be transmitted as <code>application/x-www-form-urlencoded</code>.</li>
<li><strong>raw</strong> – When selected the body can be any text.</li>
</ul>
<p>The available environment variables are:</p>
<ul>
<li><code>${env['ts_content-disposition']}</code> - The value of the content disposition header presented from the remote HTTP server (if available).</li>
<li><code>  ${env['ts_relative_path']}</code> - The relative path of the file that will be downloaded.</li>
<li><code>  ${env['ts_target']}</code> - The file name of the file that will be downloaded.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>When the selected body content type is form-data or form-urlencoded the body should be formed of key-value pairs on separate lines. Example:param1=value1param2=value2</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

<span id="Receive"></span>

### Receive actions for Generic HTTP(S) Transfer sites

The following table describes the receive actions for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Receive actions</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td><p>Select the check box to enable renaming the received file and to specify a value to be used to rename the file.</p>
<p>The limited expression language can be used to specify the file name.</p>
<p>Examples:</p>
<ul>
<li><code>${env['ts_content-disposition']}</code></li>
<li><code>${env['ts_relative_path']}</code></li>
<li><code>${env['ts_target']}</code></li>
<li><code>${env['ts_target']}_${random()}</code></li>
<li><code>${date('yyyyddMMHHmmss')}</code></li>
</ul>
<p>The available environment variables are:</p>
<ul>
<li><code>${env['ts_content-disposition']}</code> - The value of the content disposition header presented from the remote HTTP server (if available).</li>
<li><code>${env['ts_relative_path']}</code> - The relative path of the file that will be downloaded.</li>
<li><code>${env['ts_target']}</code> - The file name of the file that will be downloaded</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Upload2"></span>

### Upload settings for Generic HTTP(S) Transfer sites

The following table describes the upload settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Upload</strong>         </td>
      </tr>
      <tr>
         <td>Upload settings         </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>The HTTP server path to be used for uploading files to the remote server:</p>
<ul>
<li>A server absolute path when the partner is specified using a hostname (IP address) and port number.<br />
Example:<br />
<code>/upload.php</code></li>
<li>A server relative path when the partner is specified using an URL.<br />
Example:<br />
<code>upload.php</code></li>
</ul>
<p>The limited expression language can be used to specify the URL.</p>
<p>The available environment variable is:</p>
<ul>
<li><code>${env['ts_target']}</code> - The file name of the file that will be uploaded.</li>
</ul>
<p>Example:</p>
<p>If the value in <strong>Specify partner using URL</strong> is <code>https://‹host›:‹port›/uploads/</code> and the value for <strong>URL path</strong> is <code>/upload.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/upload.php</code>. This occurs because <code>/upload.phpt</code> is an absolute path and not a relative path. If the value for <strong>URL path</strong> is <code>upload.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/uploads/upload.php</code>.</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>The HTTP method used when uploading files to a remote server. Either <strong>PUT</strong> or <strong>POST</strong> can be selected.</p>
<p>This field is displayed when <strong>Enable list</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>The HTTP headers that will be added in the HTTP request for upload.</p>
<p>To add a header, click <strong>Add Header</strong> and complete the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To edit a header, click the <strong>Edit</strong> (<img src="/Images/SecureTransport/EditIcon.png" />) icon and change the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To delete a header, select the header to delete and click <strong>Delete</strong>.</p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>The body of the request for uploading files on the remote server. This option is displayed when the selected upload Method is <strong>POST</strong>.</p>
<p>The limited expression language can be used to specify the body.</p>
<p>The available environment variables are:</p>
<ul>
<li><code> ${env['ts_target']}</code> - The file name of the file that will be uploaded.</li>
<li><code>${env['ts_file_form_parameter_name']}</code> - The name of the form input element with file type on the remote server.</li>
</ul>
<p>The body can be of the following type:</p>
<ul>
<li><strong>form-data</strong> – When selected the body will be transmitted as a <code>multipart/form-data</code>.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The body should be formed as key-value pairs on separate lines. Example:
param1=value1param2=value2</p>
</blockquote>
<p>Example of how to use the environment variables in the body:</p>
<p><code>filename=${env['ts_target']}</code></p>
<p><code>${env['ts_file_form_parameter_name']}=myDoc</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Send"></span>

### Send actions for Generic HTTP(S) Transfer sites

The following table describes the send actions for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Send actions</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Select the check box to send the file with a different name and specify the file name.</p>
<p>The limited expression language can be used to specify the file name.</p>
<p>The available environment variable is:</p>
<ul>
<li><code>${env['ts_target']}</code> - The file name of the file that will be sent.</li>
</ul>
<p>Examples:</p>
<ul>
<li><code>${env['ts_target']}</code></li>
<li><code>${env['ts_target']}_${random()}</code></li>
<li><code>${date('yyyyddMMHHmmss')}</code></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Login"></span>

### Login settings for Generic HTTP(S) Transfer sites

The following table describes the login settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Authentication</strong>         </td>
      </tr>
      <tr>
         <td>Login Settings         </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td>The client certificate to be used for mutual authentication.         </td>
      </tr>
      <tr>
         <td>Basic authentication settings         </td>
      </tr>
      <tr>
         <td>User name         </td>
         <td>The user name to be used to log into a remote HTTP server.         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td><p>Select to use a password to log into the remote HTTP server.</p>
<p>Disabled when <strong>Form authentication</strong> is selected.</p>         </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td><p>Password used to log into the remote HTTP server.</p>
<p>Disabled when <strong>Form authentication</strong> is selected.</p>         </td>
      </tr>
      <tr>
         <td>Form authentication         </td>
         <td><p>Select to use form authentication. If <strong>Form authentication</strong> is enabled, the transfer site will use form authentication to connect to the remote HTTP server.</p>
<p>If username and password in the <em>Basic authentication settings</em> pane are set, they will be mapped to the environment variables <code>${env['ts_form_auth_username']}</code> and <code>${env['ts_form_auth_password']}</code> and can be used in the body of the form authentication request.</p>         </td>
      </tr>
      <tr>
         <td>Form authentication settings         </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>The HTTP server path used for sending the form authentication request:</p>
<ul>
<li>A server absolute path when the partner is specified using a hostname (IP address) and port number.<br />
Example:<br />
<code>/form.php</code></li>
<li>A server relative path when the partner is specified using an URL.<br />
Example:<br />
<code>form.php</code></li>
</ul>
<p>The limited expression language can be used to specify the URL.</p>
<p>Example:</p>
<p>If the value in <strong>Specify partner using URL</strong> is <code>https://‹host›:‹port›/auth/</code> and the value for <strong>URL path</strong> is <code>/form.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/form.php</code>. This occurs because <code>/form.php</code> is an absolute path and not a relative path. If the value for <strong>URL path</strong> is <code>form.php</code>, the final URI that will be resolved is <code>https://‹host›:‹port›/auth/form.php</code>.</p>
<p>This field is displayed when <strong>Form authentication</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>The HTTP method to be used for the form authentication to the remote server. Either <strong>GET</strong> or <strong>POST</strong> can be selected.</p>
<p>This field is displayed when <strong>Form authentication</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>The HTTP headers that will be added in the HTTP request for form authentication.</p>
<p>To add a header, click <strong>Add Header</strong> and complete the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To edit a header, click the <strong>Edit</strong> (<img src="/Images/SecureTransport/EditIcon.png" />) icon and change the <strong>Header</strong> and <strong>Value</strong> fields.</p>
<p>To delete a header, select the header to delete and click <strong>Delete</strong>.</p>
<p>Displayed when <strong>Form authentication</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>The body of the form authentication request. This field is displayed when the selected authentication Method is <strong>POST</strong>.</p>
<p>The limited expression language can be used to specify the body.</p>
<p>The available environment variables are:</p>
<p><code>${env['ts_form_auth_username']}</code> - Represents the user name specified in the <em>Basic authentication settings</em> pane.</p>
<p><code>${env['ts_form_auth_password']}</code> - Represents the password specified in the <em>Basic authentication settings</em> pane.</p>
<p>The body can be any of the following types:</p>
<ul>
<li><strong>form-data</strong> – When selected the body will be transmitted as <code>multipart/form-data</code>.</li>
<li><strong>form-urlencoded</strong> – When selected the body will be transmitted as <code>application/x-www-form-urlencoded</code>.</li>
<li><strong>raw</strong> – When selected the body can be any text.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>When the selected body content type is form-data or form-urlencoded the body should be formed as key-value pairs on separate lines.Example:param1=value1param2=value2</p>
</blockquote>
<p>Example of how to use the environment variables in the body:</p>
<p><code>user=${env['ts_form_auth_username']}</code></p>
<p><code>password=${env['ts_form_auth_password']}</code></p>
<p>This field is displayed when <strong>Form authentication</strong> is checked.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Advanced"></span>

### Advanced settings for Generic HTTP(S) Transfer sites

The following table describes the advanced settings for defining a Generic HTTP transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Advanced settings</strong>         </td>
      </tr>
      <tr>
         <td>Show Advanced Settings         </td>
         <td>Select the check box to display the advanced settings.         </td>
      </tr>
      <tr>
         <td>File list maximum response size         </td>
         <td><p>The maximum size in KB of the file list response to handle. If the response exceeds this value, only the specified number of bytes will be processed.</p>
<p>Example:</p>
<p>If the response is 120 KB and the maximum size is set up to 100 KB, only the first 100 KB from the response will be processed.</p>
<p>The default value is <code>100</code> KB.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Cipher suites         </td>
         <td><p>The cipher suites to be used for the SSL connection. The cipher suites must be comma separated.</p>
<p>By default this set is populated with the cipher suites as defined in the <code>Https.SIT.Ciphers</code> configuration option.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>SSL protocol         </td>
         <td><p>The SSL protocol to be used for the SSL connection. The default value is <code>TLS</code>.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Enabled SSL protocols         </td>
         <td><p>The enabled SSL protocols. The protocols must be comma separated.</p>
<p>By default this list is populated with the SSL protocols as defined in the <code>Https.SIT.EnabledProtocols</code> configuration option.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Receive timeout         </td>
         <td><p>The socket timeout in seconds. Any non-zero time out will block the input stream associated with the socket for this amount of time. A timeout of zero is interpreted as an infinite timeout.</p>
<p>The default value is <code>25</code> seconds.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Connect timeout         </td>
         <td><p>The connection timeout in seconds. A timeout of zero is interpreted as an infinite timeout. The connection will then block until established or an error occurs.</p>
<p>The default value is <code>25</code> seconds.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
      <tr>
         <td>Max redirects         </td>
         <td><p>The maximum number of redirects to be followed. The limit on the number of redirects is intended to prevent infinite loops.</p>
<p>The default value is <code>1</code> redirect.</p>
<p>This field is displayed when <strong>Show Advanced Settings</strong> is checked.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="List"></span>

## Sample configuration — List files and download

Sample configuration for a Generic HTTP transfer site to list specific files on an Apache HTTP server and download them:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>General Settings</strong>         </td>
      </tr>
      <tr>
         <td>Site Name         </td>
         <td><code>GHTTP_list</code>         </td>
      </tr>
      <tr>
         <td>Site Type         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>Access Level         </td>
         <td>Private         </td>
      </tr>
      <tr>
         <td>Transfer Protocol         </td>
         <td>Generic-HTTP(S)         </td>
      </tr>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Specify partner using hostname (IP address) and port number         </td>
         <td>Selected         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td><code>10.232.15.114</code>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td><code>443</code>         </td>
      </tr>
      <tr>
         <td>Specify partner using URL         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>none</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
      </tr>
      <tr>
         <td>Use HTTPS         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Verify certificate for this Site         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>List</strong>         </td>
      </tr>
      <tr>
         <td>List settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Enable list         </td>
         <td>Selected         </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p><code>/uploads</code></p>         </td>
      </tr>
      <tr>
         <td>File expression         </td>
         <td><p><code>&lt;a href=\"(([^?].*?)\"&gt;</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>GET</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>File download</strong>         </td>
      </tr>
      <tr>
         <td>File download settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p><code>${env['ts_relative_path']}/${env['ts_target']}</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td>GET         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Receive actions</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Upload</strong>         </td>
      </tr>
      <tr>
         <td>Upload settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>PUT</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Send actions</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Authentication</strong>         </td>
      </tr>
      <tr>
         <td>Login Settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td>(Select Key) - No key selected         </td>
      </tr>
      <tr>
         <td>Basic authentication settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User name         </td>
         <td><code>acc</code>         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>Form authentication         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Advanced settings</strong>         </td>
      </tr>
      <tr>
         <td>Show Advanced Settings         </td>
         <td>Not selected         </td>
      </tr>
   </tbody>
</table>

<span id="Download"></span>

## Sample configuration — Download file

Configuration for a Generic HTTP transfer site to download a file from an Apache HTTP server:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Selection or entry         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>General Settings</strong>         </td>
      </tr>
      <tr>
         <td> Site Name         </td>
         <td><code>GHTTP_download</code>         </td>
      </tr>
      <tr>
         <td>Site Type         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>Access Level         </td>
         <td>Private         </td>
      </tr>
      <tr>
         <td>Transfer Protocol         </td>
         <td>Generic-HTTP(S)         </td>
      </tr>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Specify partner using hostname (IP address) and port number         </td>
         <td>Selected         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td><code>10.232.14.182</code>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td><code>443</code>         </td>
      </tr>
      <tr>
         <td>Specify partner using URL         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>none</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
      </tr>
      <tr>
         <td>Use HTTPS         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Verify certificate for this Site         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>List</strong>         </td>
      </tr>
      <tr>
         <td>List settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Enable list         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td><strong>File download</strong>         </td>
      </tr>
      <tr>
         <td>File download settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td> URL path         </td>
         <td><p><code>/download.txt</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td>GET         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Receive actions</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Upload</strong>         </td>
      </tr>
      <tr>
         <td>Upload settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>PUT</p>         </td>
      </tr>
      <tr>
         <td> Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Send actions</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Authentication</strong>         </td>
      </tr>
      <tr>
         <td>Login Settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td>(Select Key) - No key selected         </td>
      </tr>
      <tr>
         <td>Basic authentication settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User name         </td>
         <td><code>acc</code>         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td> Password         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>Form authentication         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Advanced settings</strong>         </td>
      </tr>
      <tr>
         <td>Show Advanced Settings         </td>
         <td>Not selected         </td>
      </tr>
   </tbody>
</table>

<span id="Upload"></span>

## Sample configuration — Upload file

Configuration for a Generic HTTP transfer site to upload a file to an Apache HTTP server:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Selection or entry         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>General Settings</strong>         </td>
      </tr>
      <tr>
         <td>Site Name         </td>
         <td><code>GHTTP_upload</code>         </td>
      </tr>
      <tr>
         <td>Site Type         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>Access Level         </td>
         <td>Private         </td>
      </tr>
      <tr>
         <td>Transfer Protocol         </td>
         <td>Generic-HTTP(S)         </td>
      </tr>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Specify partner using hostname (IP address) and port number         </td>
         <td>Selected         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td><code>10.232.14.182</code>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td><code>443</code>         </td>
      </tr>
      <tr>
         <td>Specify partner using URL         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
      </tr>
      <tr>
         <td>Use HTTPS         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Verify certificate for this Site         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>List</strong>         </td>
      </tr>
      <tr>
         <td>List settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Enable list         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td><strong>File download</strong>         </td>
      </tr>
      <tr>
         <td>File download settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td>GET         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Receive actions</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Upload</strong>         </td>
      </tr>
      <tr>
         <td>Upload settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p><code>/upload.php</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>POST</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>Header = <code>header1</code></p>
<p>Value = <code>value1</code></p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>Select <strong>form-data</strong>.</p>
<p><code>${env['ts_file_form_parameter_name']}=filename</code></p>
<p><code>filename=${env['ts_target']}</code></p>         </td>
      </tr>
      <tr>
         <td><strong>Send actions</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Authentication</strong>         </td>
      </tr>
      <tr>
         <td>Login Settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td>(Select Key) - No key selected         </td>
      </tr>
      <tr>
         <td>Basic authentication settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User name         </td>
         <td><code>acc</code>         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>Form authentication         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Advanced settings</strong>         </td>
      </tr>
      <tr>
         <td>Show Advanced Settings         </td>
         <td>Not selected         </td>
      </tr>
   </tbody>
</table>

<span id="Push"></span>

## Sample configuration — Push file to SecureTransport user using Form Authentication

Configuration for a Generic HTTP transfer site to push file to a {{< SecureTransport/securetransportname  >}} user using form authentication:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>General Settings</strong>         </td>
      </tr>
      <tr>
         <td>Site Name         </td>
         <td><code>GHTTP_form</code>         </td>
      </tr>
      <tr>
         <td>Site Type         </td>
         <td>Unspecified         </td>
      </tr>
      <tr>
         <td>Access Level         </td>
         <td>Private         </td>
      </tr>
      <tr>
         <td>Transfer Protocol         </td>
         <td>Generic-HTTP(S)         </td>
      </tr>
      <tr>
         <td><strong>Server Settings</strong>         </td>
      </tr>
      <tr>
         <td>Specify partner using hostname (IP address) and port number         </td>
         <td>Selected         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td><code>10.232.15.114</code>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td><code>443</code>         </td>
      </tr>
      <tr>
         <td>Specify partner using URL         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Address         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>none</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
      </tr>
      <tr>
         <td>Use HTTPS         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Verify certificate for this Site         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>List</strong>         </td>
      </tr>
      <tr>
         <td>List settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Enable list         </td>
         <td>Not selected         </td>
      </tr>
      <tr>
         <td><strong>File download</strong>         </td>
      </tr>
      <tr>
         <td>File download settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p>—</p>         </td>
      </tr>
      <tr>
         <td> Method         </td>
         <td>GET         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>No headers</p>         </td>
      </tr>
      <tr>
         <td><strong>Receive actions</strong>         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Upload</strong>         </td>
      </tr>
      <tr>
         <td>Upload settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p><code>/api/v1.4/files?transferMode=BINARY</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>POST</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>Header=<code>Referer</code></p>
<p>Value=<code>123</code></p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>Select <strong>form-data</strong>.</p>
<p><code>${env['ts_file_form_parameter_name']}=filename</code></p>
<p><code>filename=${env['ts_target']}</code></p>         </td>
      </tr>
      <tr>
         <td><strong>Send actions</strong>         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Not selected</p>         </td>
      </tr>
      <tr>
         <td><strong>Authentication</strong>         </td>
      </tr>
      <tr>
         <td>Login Settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate         </td>
         <td>(Select Key) - No key selected         </td>
      </tr>
      <tr>
         <td>Basic authentication settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User name         </td>
         <td><code>user1</code>         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td>Form authentication         </td>
         <td><p>Selected</p>         </td>
      </tr>
      <tr>
         <td>Form authentication settings         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>URL path         </td>
         <td><p><code>/template/login</code></p>         </td>
      </tr>
      <tr>
         <td>Method         </td>
         <td><p>POST</p>         </td>
      </tr>
      <tr>
         <td>Headers         </td>
         <td><p>Header=<code>User-Agent</code></p>
<p>Value=<code>Mozilla/5.0</code></p>         </td>
      </tr>
      <tr>
         <td>Body         </td>
         <td><p>Select <strong>form-urlencoded</strong>.</p>
<p><code>switch=Log In</code></p>
<p><code>user=${env['ts_form_auth_username']}</code></p>
<p><code>password=${env['ts_form_auth_password']}</code></p>         </td>
      </tr>
      <tr>
         <td><strong>Advanced settings</strong>         </td>
      </tr>
      <tr>
         <td>Show Advanced Settings         </td>
         <td>Not selected         </td>
      </tr>
   </tbody>
</table>

<span id="Supporte"></span>

## Supported expression language

This topic outlines the limited expression language supported by Generic HTTP transfer sites.

### Predefined variables

The predefined variable that is supported:

-   `${timestamp}`

### Predefined functions

The predefined functions that are supported:

-   Functions related to a date. For example: `${date("yyyyMMdd")}`
-   Functions related to a Random ID. For example: `${random()}`
-   Functions related to a String representation. For example: `${concat('str', 'ing')}`

> **Note:**
>
> Expression variables and functions related to file name and the SecureTransport environment are not supported.

### Added expression variables

On download and list, the following environment variables are added:

-   `${env[‘ts_content-disposition’]}` – If a remote HTTP server presents a content disposition header, its filename value will be preserved into this variable.
-   `${env['ts_relative_path']}` – The relative path of the file that will be downloaded.
-   `${env['ts_target']}` – The file name of the file that will be downloaded or uploaded.

On upload, the following environment variables are added:

-   `${env['ts_target']}` – The file name of the file that will be downloaded or uploaded.
-   `${env['ts_file_form_parameter_name']}` – Represents the name of the form input element with file type on the remote server.

On form authentication, the following environment variables are added:

-   `${env['ts_form_auth_username']}` – Represents the user name specified in the *Basic authentication settings* pane.
-   `S{env['ts_form_auth_password']}` – Represents the password specified in the *Basic authentication settings* pane.

**Related topics**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>
