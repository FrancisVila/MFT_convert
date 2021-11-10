{
    "title": "New Application Message: General tab",
    "linkTitle": "General tab",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Originator Site alias</p>         </td>
         <td><p>Optional</p>
<p>If you do not enter an Originator Site alias, Gateway automatically provides information from your Local Site definition.</p>
<p>Enter the alias of the Site that is the source of the file transfer.<br />
Maximum: 31 alphanumeric characters.</p>
<p>Alternatively, you can select an originator Site from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination Site alias</p>         </td>
         <td><p>Enter the alias of the Site that is the file transfer destination. If you specify a Diffusion List in this field, Gateway submits the Transfer to several destinations.<br />
Maximum: 31 alphanumeric characters.</p>
<p>Alternatively, select a destination Site from the drop-down list.</p>
<p>Destination Sites must support PeSIT. The predefined PeSIT Sites delivered with Gateway by default are:</p>
<ul>
<li>TPHSD</li>
<li>TPHSE</li>
<li>PHSD</li>
<li>PHSE</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File Name</p>         </td>
         <td><p>Enter a name to identify the Message transfer. After the transfer operation, Gateway displays this name in the File Name column of the Mailbox record for the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message in file</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message in file</p>         </td>
         <td><p>If the message to send is stored in an external file, select this option. Then complete the following fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Message file path</p>         </td>
         <td><p>Enter the complete file and path of the external file that contains the message to send.</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>Select a local Application to read the file specified in the <span style="font-weight: bold;">Message file path</span> field.</p>
<p>Alternatively, enter the Application name manually.<br />
Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message</p>         </td>
         <td><p>If the message to send is not contained in an external file, select this option. Then complete the following fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Message text</p>         </td>
         <td><p>Enter the text of the message to send directly in the text field.<br />
Maximum: 512 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Message data code</p>         </td>
         <td><p>Select the local data code for the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer data code</p>         </td>
         <td><p>Select the data code for the transferred message.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Application Messages](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
