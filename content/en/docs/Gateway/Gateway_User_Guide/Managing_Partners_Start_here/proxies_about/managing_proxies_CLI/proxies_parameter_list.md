{
    "title": "Proxies: Parameters List",
    "linkTitle": "Proxies: Parameters List",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

The following table lists all Proxy command parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in <span style="font-style: italic;font-weight: bold;">italics</span>.

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
         <td><p>address (-addr)</p>
<p>IP address</p>         </td>
         <td><p>Proxy TCP/IP address</p>         </td>
         <td><p>&lt;host&gt;/&lt;port&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>change_data_addr (-cda)</p>
<p>Allow different IP addresses for control and data sessions</p>         </td>
         <td><p>Disable protection against FTP bounce attacks</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p>Comments</p>         </td>
         <td><p>Comment field</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>login_password (-lp)</p>
<p>Password</p>         </td>
         <td><p>Proxy password</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>login_user (-lu)</p>
<p>User</p>         </td>
         <td><p>Proxy user name</p>         </td>
         <td><p>Maximum: 25 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>name (-n)</p>
<p>Name</p>         </td>
         <td><p>Proxy name</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>protocol (-pr)</p>
<p>Protocol</p>         </td>
         <td><p>Protocol for the Proxy</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li>FTP</li>
<li>SOCKS4</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>script (-s)</p>
<p>Script</p>         </td>
         <td><p>User script if you specified USER as the Proxy type</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>type (-ty)</p>
<p>Type</p>         </td>
         <td><p>FTP only</p>
<p>Define the connection sequence at the session level</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li>USER_AT_SITE</li>
<li>USER_PASS_ACCT</li>
<li>SITE</li>
<li>OPEN</li>
<li>USER_OPEN</li>
<li>USER</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Proxies (command line)](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
