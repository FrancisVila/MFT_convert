{
    "title": "New Remote Site: POP3 tab",
    "linkTitle": "POP3 tab",
    "weight": "260"
}{{< Gateway/componentlongname  >}}: Managing Partners

Gateway displays this tab if you select either of the following protocols in the [General tab](../remote_site_general_tab):

-   POP3
-   AS1\_POP3

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Authentication method</p>         </td>
         <td><p>Enables you to define the authentication mechanism (AUTH) to use when connecting to the POP3 server.</p>
<p>Select one of the following values:</p>
<ul>
<li><strong>Auto</strong>: Gateway automatically selects an authentication method that the POP3 server supports (in the following order: APOP, CRAM, BASIC)</li>
<li><span style="font-weight: bold;">Basic</span>: the use of USER and PASS in clear text (default)</li>
<li><span style="font-weight: bold;">CRAM</span> (Challenge Response Authentication Method): user and password are transmitted in encrypted form, as specified in RFC 2195</li>
<li><span style="font-weight: bold;">Apop</span> (&lt;user&gt; &lt;digest-MD5&gt;): user id is transmitted in plain text, but the password is transmitted in MD5 digest, as specified in RFC 2449</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Login identification</p>
<p>(mandatory)</p>         </td>
         <td><p>Enter the user login name to connect to the POP3 server account.<br />
Maximum: 24 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Set Login password</p>
<p>(mandatory)</p>         </td>
         <td><p>Opens a dialog box to enter the user login password to connect to the POP3 server account.<br />
Maximum: 14 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Application method</p>         </td>
         <td><p>Select the method to use to retrieve the Application object:</p>
<ul>
<li><span style="font-weight: bold;">User exit</span>: select this option if the Application name is not in the Remote Site definition, or when you need additional information to identify the Application name</li>
<li><span style="font-weight: bold;">User message field</span>: not supported</li>
<li><span style="font-weight: bold;">File name</span>: not supported</li>
</ul>
<p><span style="font-weight: bold;">Note:</span> If you do not define an Application method, the Transfer Request is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Extract file</p>         </td>
         <td><p>Check this option to indicate that there is a file attachment to extract on reception.</p>
<p>If you also set this value in the Application object, the Application definition overrides the value that you set here.</p>         </td>
      </tr>
      <tr>
         <td><p>Polling options</p>         </td>
      </tr>
      <tr>
         <td><p>Polling interval (in minutes)</p>         </td>
         <td><p>Specify the time to wait before starting the next polling cycle. Specify this value in minutes in the format <span style="font-style: italic;">MM</span>. Default = 10.</p>         </td>
      </tr>
      <tr>
         <td><p>Activated</p>         </td>
         <td><p>Check this option to activate polling.</p>         </td>
      </tr>
      <tr>
         <td><p>acknowledgment option</p>         </td>
         <td><p>Select one of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span></li>
<li><span style="font-weight: bold;">Not to ack</span></li>
<li><span style="font-weight: bold;">By monitor</span></li>
<li><span style="font-weight: bold;">By user</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Mail disposition on error</p>         </td>
         <td><p>Select one of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span></li>
<li><span style="font-weight: bold;">Leave</span></li>
<li><span style="font-weight: bold;">Delete</span></li>
<li><span style="font-weight: bold;">Recover</span> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SMIME</p>         </td>
         <td><p>Only for POP3 (not for AS1_POP3)</p>
<p>Check this option to activate S/MIME security functions.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About SMTP/POP3](../../../../protocols_about/smtp_pop3_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
