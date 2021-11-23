{
    "title": "Using an FTP proxy",
    "linkTitle": "Using an FTP proxy",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Protocols

[About the Proxy object](#About_the_Proxy_object)

[Completing Proxy object parameters](#Completing_Proxy_object_parameters)

[Generic FTP Proxy definitions](#Generic_FTP_Proxy_definitions)

[Disabling the defense against bounce attacks](#disable_bounce_defense)

<span id="About_the_Proxy_object"></span>

## About the Proxy object

The Proxy object is used exclusively in client mode for contacting a proxy server. The protocol settings of a Proxy must contain the TCP address details for the connection server, including the set of connection parameters (for example, the user name and corresponding password).

<span id="Completing_Proxy_object_parameters"></span>

## Completing Proxy object parameters

Define the Proxy object using the GUI or the `peladm` online command.

The Proxy object contains the following fields:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>name</strong> (<span class="code">-name</span>)</p>         </td>
         <td><p>Name of the Proxy</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">protocol</span> (<span class="code">-protocol</span>)</p>         </td>
         <td><p>FTP or SOCKS4</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">address</span> (<span class="code">-address</span>)</p>         </td>
         <td><p>Host and port (address = "host/port")</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">user</span> (<span class="code">-login_user</span>)</p>         </td>
         <td><p>User name (optional)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">password</span> (<span class="code">-login_password</span>)</p>         </td>
         <td><p>Password (optional)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">type</span> (<span class="code">-type</span>) (User script)</p>         </td>
         <td><p>Mandatory for FTP (otherwise ignored)</p>
<p>Name of a standard <a href="#Predefined_proxy_scripts">predefined proxy script</a> or <span style="font-style: italic;">USER</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">script</span> (<span class="code">-script</span>)</p>         </td>
         <td><p>Script, if <span style="font-style: italic;">USER</span> is the selected <span style="font-weight: bold;">type</span>. References the name of a text file by indicating <span class="code">file=&lt;script_filename&gt;.txt</span>.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

peladm create\_proxy  -name x\_proxy  –protocol FTP  -address proxy/21

   -user user  -password password  -type user

   -script file=script\_filename.txt

Use the commands <span class="code" style="font-weight: bold;">pelbase import\_proxy</span> and <span class="code" style="font-weight: bold;">pelbase export\_proxy</span> to work directly on a text file.

<span id="Generic_FTP_Proxy_definitions"></span>

## Generic FTP Proxy definitions

The FTP Proxy **type** must describe the <span style="font-style: italic;">connection sequence at the session level</span>. The description must include an ordered list of commands to send. A command consists of a line of text including the FTP command and its parameters (possibly variables).

This syntax follows the ABNF format where:

-   line = command \[ SP \*( symbol / VCHAR ) \]
-   command = "USER" / "PASS" / "ACCT" / "SITE" / "OPEN"
-   symbol = "&(proxy\_user)" / "&(proxy\_password)" / "&(user)" /
-   "&(password)" / "&(host\_port)"

<span style="font-weight: bold;">Note:</span> Lines can be separated by either ‘<span class="code" style="font-weight: bold;">;</span>’ or ‘<span class="code" style="font-weight: bold;">\\n</span>’ and reserved characters must be preceded by ‘<span class="code" style="font-weight: bold;">\\</span>’ to be escaped.

<span id="Predefined_proxy_scripts"></span>

### Predefined proxy scripts

The standard proxy scripts available in Gateway use these variables:

-   <span class="code" style="font-weight: bold;">&(proxy\_user)</span>: user name for the Proxy
-   <span class="code" style="font-weight: bold;">&(proxy\_password)</span>: password for the Proxy
-   <span class="code" style="font-weight: bold;">&(user)</span>: user name for the server
-   <span class="code" style="font-weight: bold;">&(password)</span>: password for the server
-   <span class="code" style="font-weight: bold;">&(host)</span>: server host name (can be an IP address)
-   <span class="code" style="font-weight: bold;">&(port)</span>: server port number
-   <span class="code" style="font-weight: bold;">&(host\_port)</span>: server host name and port number, separated by a colon ‘<span class="code">:</span>’ if the port value is given

The following table contains descriptions of the available predefined proxy scripts that you can specify in the **type** field. To customize your proxy script, enter *User script* in the **type** field.

### Selecting a predefined proxy script

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type field options         </th>
<th class="HeadD-Column1-Header1">Parameters         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>USER_AT_SITE</p>         </td>
         <td><p>USER &amp;(user)@&amp;(host_port)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>USER_PASS_ACCT</p>         </td>
         <td><p>USER &amp;(user)@&amp;(host_port) &amp;(proxy_user)</p>
<p>PASS &amp;(password)</p>
<p>ACCT &amp;(proxy_password)</p>         </td>
      </tr>
      <tr>
         <td><p>SITE</p>         </td>
         <td><p>USER &amp;(proxy_user)</p>
<p>PASS &amp;(proxy_password)</p>
<p>SITE &amp;(host_port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>USER_OPEN</p>         </td>
         <td><p>USER &amp;(proxy_user)</p>
<p>PASS &amp;(proxy_password)</p>
<p>OPEN &amp;(host_port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>OPEN</p>         </td>
         <td><p>OPEN &amp;(host_port)</p>
<p>USER &amp;(user)</p>
<p>PASS &amp;(password)</p>         </td>
      </tr>
      <tr>
         <td><p>USER (User script)</p>         </td>
         <td><p>Undefined. Enter a script.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="disable_bounce_defense"></span>

## Disabling the defense against bounce attacks

The remote IP address of a proxy control session may be different from the remote address of its data session. This is not normally allowed in Gateway for protection against bounce attacks. Use the <span class="code">change\_data\_addr</span> parameter in the Proxy object to allow different IP addresses. When this parameter is set to <span style="font-style: italic;">Yes</span>, FTP no longer checks if the remote IP address is the same for the control session and data session.

You can set this parameter in the Proxy and also in the Remote Site. Refer to [Defending against bounce attacks](../ftp_responder_mode#Defending_against_bounce_attacks) for more information.

Related topics

[Working with Proxies](../../../managing_partners_start_here/proxies_about/managing_proxies)

[Working with Proxies (command line)](../../../managing_partners_start_here/proxies_about/managing_proxies_cli)

[Working with Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

<a href="#" class="selected">Using FTP in Responder mode</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
