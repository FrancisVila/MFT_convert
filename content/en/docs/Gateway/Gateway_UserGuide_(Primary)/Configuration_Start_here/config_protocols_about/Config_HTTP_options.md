{
    "title": "Configuring protocols: HTTP options",
    "linkTitle": "HTTP options",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Configuration

This topic lists the HTTP parameters that you can modify in the *HTTP options* window. Gateway opens this window if you click the **Options...** button when you configure an HTTP-type protocol.

Complete the fields of the <span style="font-style: italic;">HTTP options</span> window:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Directory listing</p>         </td>
      </tr>
      <tr>
         <td><p>Default template file</p>         </td>
         <td><p>Not for RosettaNet HTTP or EDIINT/AS2</p>
<p>Enter the full path of the HTML page used as a template to display directory content.</p>         </td>
      </tr>
      <tr>
         <td><p>Server identification</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Method"></span>Method</p>         </td>
         <td><p>Select the identification method accepted by the HTTP server:</p>
<ul>
<li><span style="font-weight: bold;">Web</span></li>
<li><span style="font-weight: normal;">CGI session id (seen <strong>note</strong> below)</span></li>
<li><span style="font-weight: normal;">CGI user password (seen <strong>note</strong> below)</span></li>
<li><span style="font-weight: bold;">Cookie session id</span></li>
<li><span style="font-weight: bold;">Partner-Dependant identification</span></li>
<li><span style="font-weight: bold;">Cookie user password</span></li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The server identification methods CGI session id and CGI user password are insecure by design and should not be used. These identification methods are deprecated, and are due to be removed in a future version of the product.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Server ID</p>         </td>
         <td><p>Gateway displays this field if you select <span style="font-style: italic;">Web</span> in the <span style="font-weight: bold;">Method</span> field.</p>
<p>Enter the name that the server sends when Web authentication is required.</p>         </td>
      </tr>
      <tr>
         <td><p>User found</p>         </td>
         <td><p>Gateway displays this field if you select any identification method other than <span style="font-style: italic;">Web</span> in the <span style="font-weight: bold;">Method</span> field.</p>
<p>Use this field to retrieve the content of the <span style="font-style: italic;">User</span> field in a CGI.</p>         </td>
      </tr>
      <tr>
         <td><p>Password found</p>         </td>
         <td><p>Gateway displays this field if you select any identification method other than <span style="font-style: italic;">Web</span> in the <span style="font-weight: bold;">Method</span> field.</p>
<p>Use this field to retrieve the content of the <span style="font-style: italic;">Password</span> field in a CGI.</p>         </td>
      </tr>
      <tr>
         <td><p>Session found</p>         </td>
         <td><p>Gateway displays this field if you select <span style="font-style: italic;"><span style="font-style: italic;">Cookie session id</span> </span>or<span style="font-style: italic;"> CGI session id</span> the <span style="font-weight: bold;">Method</span> field. (In the Method field above, see note about deprecated parameter CGI session id)</p>
<p>Use this field to retrieve the content of the <span style="font-style: italic;">sessionId</span> field in a CGI.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced connection behavior</p>         </td>
      </tr>
      <tr>
         <td><p>Do not keep alive</p>         </td>
         <td><p>Select this option to close the connection at the end of each request.</p>         </td>
      </tr>
      <tr>
         <td><p>Max packet size</p>         </td>
         <td><p>Enter the maximum number of bytes sent in an outgoing packet of data.</p>         </td>
      </tr>
      <tr>
         <td><p>Max list loop</p>         </td>
         <td><p>Not for RosettaNet HTTP or EDIINT/AS2</p>
<p>Enter the maximum number of consecutive LIST entries to return to the client.</p>         </td>
      </tr>
      <tr>
         <td><p>Max CGI size</p>         </td>
         <td><p>Enter the maximum number of bytes from which the server tries to retrieve information (such as user, password and so on). Internal services do not accept requests that exceed this value.</p>         </td>
      </tr>
   </tbody>
</table>

Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.

Click <span style="font-weight: bold;">OK</span> to confirm the <span style="font-style: italic;">HTTP options.</span>

**Note:** You can limit the number of simultaneous open sessions for a user. Refer to the <span class="code">sid\_limit</span> parameter in the Gateway [advanced parameters](../../config_gateway_paras#Advanced_parameters).

Related topics

[Configuring protocols](../config_protocols)

[About HTTP](../../../protocols_about/http_about)

[Using HTTP in server mode](../../../protocols_about/http_about/http_using_in_server_mode)

[Using HTTP in client mode](../../../protocols_about/http_about/http_using_in_client_mode)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
