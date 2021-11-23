{
    "title": "New Remote Site: OFTP tab",
    "linkTitle": "OFTP tab",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Data windows</p>         </td>
         <td><p>Enter the maximum number of buffers that you can send or receive before the Site puts a synchronization point into the Mailbox.</p>
<p>Integer: 1 - 999. Default = 100.</p>         </td>
      </tr>
      <tr>
         <td><p>Network credit</p>         </td>
         <td><p>Enter the number of Data Exchange Buffers the sender can send before the end of the file or the credit value is reached. The sender must then wait for an acknowledgment (a CDT response) before sending more DATA commands.</p>
<p>Integer: 0 - 99. Default = 4.<br />
0 = no synchronization points used.</p>         </td>
      </tr>
      <tr>
         <td><p>Set password to send/ to check</p>         </td>
         <td><p><em>Optional</em></p>
<p>Open dialog boxes to enter the connection password to send (from the Initiator) and the connection password to check (received from the Responder).</p>         </td>
      </tr>
      <tr>
         <td><p>User message</p>         </td>
         <td><p><em>Optional</em></p>
<p>Enter a user message to transmit during the connection phase.<br />
Maximum: 254 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Max. size for received files (KB)</p>         </td>
         <td><p>Enter the maximum size allowed for received files. Specify the value in KB.</p>
<p>Integer: 0 - 999 999 999.<br />
0 = no limit.</p>         </td>
      </tr>
      <tr>
         <td><em>Max number of sessions</em>         </td>
         <td><p>Maximum number of sessions (IN + OUT) for each remote site.</p>
<p>Please note that Gateway supports per-partner granularity for selecting the template when using {{< Gateway/passportname  >}} PM.</p>
<ul>
<li>If a remote site with alias = <code>SSIDCODE.SIOICD+SSIDCODE.SIOORG </code>exists in Gateway, this site is selected as the template site.</li>
<li>If not, the default configured template site is used (<code>TODT</code>).</li>
</ul>
<p>If the value is <code style="font-weight: bold;">0</code>, then the max number of simultaneous sessions it is not directly checked. It will be indirectly limited by the site's in/out connection max settings ("Maximum number of simultaneous connections to/from this Site" from the <strong>Options</strong> tab.)</p>         </td>
      </tr>
      <tr>
         <td><p>acknowledgment option</p>         </td>
         <td><p>Select the acknowledgment option:</p>
<ul>
<li><strong>Undefined</strong>: acknowledgment behavior not known (default)</li>
<li><span style="font-weight: bold;">Not to ack</span>: no reply expected</li>
<li><span style="font-weight: bold;">By monitor</span>: Gateway automatically sends an acknowledgment request</li>
<li><span style="font-weight: bold;">By user</span>: the user must send an acknowledgment request</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>EERP Style</p>         </td>
         <td><p>An OFTP session has two acknowledgment modes (French and International). The difference between these two modes is that the destination and originator fields in End-to-End-Response (EERP) and File Protocol Data Unit (FPDU) are inverted.</p>
<p>Select the acknowledgment style:</p>
<ul>
<li>French</li>
<li>International</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Application method</p>         </td>
         <td><p>Select the method to use to retrieve the Application object:</p>
<ul>
<li><span style="font-weight: bold;">User exit</span></li>
<li><span style="font-weight: bold;">File name</span></li>
<li><span style="font-weight: bold;">User message field</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Restart allowed</p>         </td>
         <td><p>Check this box to enable the restart function.</p>
<p>The restart function allows you to restart interrupted Transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Compression allowed</p>         </td>
         <td><p>Check this box to enable file compression.</p>
<p>OFTP allows horizontal data compression (the deletion of repeated characters in a record).</p>         </td>
      </tr>
      <tr>
         <td><p>Special Logic Coding</p>         </td>
         <td><p>Check this box to enable special logic coding.</p>
<p>Special logic coding is an OFTP protocol feature used to detect and correct errors, in particular with less reliable asynchronous connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Authentication method</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the authentication method to use:</p>
<ul>
<li><span style="font-weight: bold;">None</span>: No authentication required</li>
<li><span style="font-weight: bold;">EncryptedData</span>: AUCH is CMS EncryptedData</li>
<li><span style="font-weight: bold;">EnvelopedData</span>: AUCH is CMS EnvelopedData</li>
</ul>
<p>Since this is not a negotiable feature, contact your partner to agree on the method used.</p>         </td>
      </tr>
      <tr>
         <td><p>Authentication certificate:<br />
Type</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the type of authentication certificate to use:</p>
<ul>
<li>SEC_ALIAS</li>
<li>Passport PS entity</li>
<li>Passport PS certificate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Authentication certificate:<br />
Name</p>         </td>
         <td><p>OFTP R2.0 only</p>
<p>Specify the authentication certificate to use.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Working with Remote Sites (command line)](../../managing_local_sites_cli/managing_remote_sites_cli)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About OFTP](../../../../protocols_about/oftp_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
