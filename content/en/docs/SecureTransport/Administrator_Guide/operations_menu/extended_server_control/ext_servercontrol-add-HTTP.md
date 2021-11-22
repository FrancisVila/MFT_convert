{
    "title": "Manage the HTTP server",
    "linkTitle": "Manage the HTTP server",
    "weight": "110"
}In this topic you will learn how to:

-   <a href="#Add" class="MCXref xref">Add an HTTP server</a>
-   <a href="#Start" class="MCXref xref">Start and stop an HTTP server</a>
-   <a href="#Edit" class="MCXref xref">Edit HTTP server settings</a>
-   <a href="#Delete" class="MCXref xref">Delete an HTTP server</a>

<span id="Add"></span>

## Add an HTTP server

To add an HTTP server, go to the *Server Control* page and on the *HTTP Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new HTTP server.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>General         </td>
      </tr>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.         </td>
      </tr>
      <tr>
         <td>Enable HTTP         </td>
         <td>Select to enable HTTP transfers.         </td>
      </tr>
      <tr>
         <td>Enable HTTPS         </td>
         <td>Select to enable HTTPS transfers.         </td>
      </tr>
      <tr>
         <td>Enable HSTS         </td>
         <td><p>Select to enable HSTS to always send the <code>"Strict-Transport-Security"</code> HTTPS response header to redirect plain HTTP connections to HTTPS.</p>
<p>With this functionality, two dedicated Server Configuration options for HSTS are added:</p>
<ul>
<li><code>Http.Security.Hsts.enabled</code> - Enable or disable HSTS for the HTTP server. Serves the same purpose as the check-box. Possible values are: <strong>true</strong> or <strong>false</strong>. It is only editable from the <em>Server Configuration</em> page. The default value is <strong>true</strong>.</li>
<li><code>Http.Security.Hsts.max-age</code> - HSTS header maximum age attribute value for the HTTP server measured in seconds. The default value is 6-months which is equivalent to <strong>15768000 seconds</strong>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode">FIPS transfer mode</a> for HTTPS connections.
<p>By selecting this option, the <strong>Enabled FIPS Ciphers</strong> field becomes editable.</p>         </td>
      </tr>
      <tr>
         <td>HTTP Port         </td>
         <td>Enter the port number of your HTTP listener.         </td>
      </tr>
      <tr>
         <td>HTTPS Port         </td>
         <td>Enter the port number of your HTTPS listener.         </td>
      </tr>
      <tr>
         <td>Login Format         </td>
         <td><p>Select the authentication format for end-user login:</p>
<ul>
<li>HTML – for user login using the ST Web Client login form</li>
<li>BA – basic authentication</li>
<li>ERR – must use config/auth agents</li>
<li>PREAUTH – config/auth agents + HTML login page in case of failed login</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Redirect hostname         </td>
         <td>Enter a redirect host name or IP address. When you set this value, all requests to the ST Web Client, subsequent to the first one, will be bound to that hostname. Use this option in the case where a DNS switch occurs to avoid requests getting split across different nodes.         </td>
      </tr>
      <tr>
         <td>SSL Settings         </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td><p>This drop-down list presents the options to define support for certificate use for HTTP authentication. Possible values are:</p>
<ul>
<li><code>Disabled</code> – no certificate authentication is required</li>
<li><code>Required</code> – the client must authenticate using a certificate</li>
<li><code>Optional</code> – the client can authenticate either using a certificate or a password</li>
</ul>         </td>
      </tr>
      <tr>
         <td>SSL Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>HTTPd</code>.         </td>
      </tr>
      <tr>
         <td>SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with {{< SecureTransport/securetransportname  >}} running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>Enabled SSL Protocols         </td>
         <td><p>Enter a comma-separated list of SSL protocol versions to be enabled.</p>
<p>Default value for newly created HTTPS servers after updating to SecureTransport 5.5-20210930: <code>TLSv1.2, TLSv1.3</code>.</p>
<p>Default value for existing HTTPS servers: <code>TLSv1, TLSv1.1, TLSv1.2</code>.<br />
For instructions on how to enable TLSv1.3 protocol support, refer to the {{< SecureTransport/componentshortname  >}} {{< SecureTransport/releasenumber  >}} <em>Security guide</em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td><p>Enter the cipher suites to be used with your HTTPS server.</p>
<p>For more information on Cipher suites, refer to <strong>SecureTransport cipher suites</strong> in the <em>SecureTransport Security Guide</em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td><p>Modify the cipher suite set to be used with your HTTP server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant TLS cipher suites supported by {{< SecureTransport/securetransportname  >}}. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default HTTP server, the list of allowed cipher suites in FIPS mode is determined by the <code>Http.FIPS.Ssl.EnabledCipherSuites</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>Authentication Parameters         </td>
      </tr>
      <tr>
         <td>Allowed Authentication Parameters         </td>
         <td>Enter the allowed HTTP Authentication parameters, separated by a semi-colon (;).         </td>
      </tr>
      <tr>
         <td>Allowed Authentication Parameters Max Size         </td>
         <td>Enter the allowed HTTP Authentication parameters maximum size in bytes.         </td>
      </tr>
      <tr>
         <td>Content Security Policy         </td>
         <td>Enter the value of the <code>Content-Security-Policy</code> header.         </td>
      </tr>
      <tr>
         <td>XSS Protection         </td>
         <td>Enter the value of the <code>X-XSS-Protection</code> header.         </td>
      </tr>
      <tr>
         <td>Content Type Options         </td>
         <td>Enter the value of the <code>X-Content-Type-Options</code> header, for example: <code>nosniff</code>.         </td>
      </tr>
      <tr>
         <td>Referrer Policy         </td>
         <td>Enter the value of the <code>Referrer-Policy</code> header. Accepted values are: <code>no-referrer, no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url</code>         </td>
      </tr>
      <tr>
         <td>Expect CT         </td>
         <td>Enter the value of the <code>Expect-CT</code> (certificate transparency) header. Accepted values are: <code>max-age=&lt;age&gt;</code>; <code>enforce</code>; <code>report-uri=&lt;uri&gt;</code>. The <code>enforce </code>and <code>report-uri</code> directives are optional.         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your HTTP server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

<span id="Start"></span>

## Start and stop an HTTP server

You can easily start and stop your HTTP server.

-   Start your server by clicking the "play" icon: ![](/Images/SecureTransport/play-icon.png)  
    A box with a success message pops up on your screen and your server status changes to Running.
-   To stop your server, click the "stop" icon. ![](/Images/SecureTransport/stop-icon.png)  
    A box with a success message pops up on your screen and your server status changes to Stopped.

You can only start the HTTP daemon once the Http Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of HTTP, an "enabled server" means that you have at least selected either option: **Enable HTTP** or **Enable HTTPS**.

<span id="Edit"></span>

## Edit HTTP server settings

You can change any of the HTTP server property values. Note that you can change the server name only when the server is stopped. To update an HTTP server, click the corresponding "gear" icon: ![](/Images/SecureTransport/gearwheel-icon.png)  
A new modal box with the HTTP settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

<span id="Delete"></span>

## Delete an HTTP server

> **Note:**
>
> You cannot delete or change the name of the "Http Default" server from the SecureTransport Administration Tool.

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](/Images/SecureTransport/trashcan-icon.png)

[Back to Top](#)
