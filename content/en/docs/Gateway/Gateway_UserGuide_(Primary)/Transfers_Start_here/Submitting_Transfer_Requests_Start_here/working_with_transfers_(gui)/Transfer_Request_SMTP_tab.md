{
    "title": "New Transfer Request: SMTP tab",
    "linkTitle": "SMTP tab",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>email subject</p>         </td>
         <td><p>Enter the email subject.<br />
Maximum: 128 alphanumeric characters.<br />
This field is mandatory if Gateway must create the email. If you are sending a formatted email via a Gateway Transfer Request, do not complete this field manually.</p>
<p>To transmit parameters between two Gateway monitors, use the MIME header <strong>Subject</strong> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Attach file</p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span> = the file is not formatted as an email: Gateway creates an email and attaches the file</li>
<li><span style="font-weight: bold;">No</span> = the file is already formatted as an email: Gateway does not attach a file</li>
<li><span style="font-weight: bold;">Undefined</span> = Gateway must open the file to determine how to proceed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Add Gateway parameters to subject</p>         </td>
         <td><p>Set this option to <span style="font-weight: bold;">Yes</span> to add the following Gateway-specific parameters to the email subject:</p>
<ul>
<li><span style="font-weight: bold;">destination</span> (<span class="code">-dest</span>)</li>
<li><span style="font-weight: bold;">origin</span> (<span class="code">-org</span>)</li>
<li><span style="font-weight: bold;">protocol file name</span> (<span class="code">-file_name</span>)</li>
<li><span style="font-weight: bold;">application</span> (<span class="code">-appli</span>)</li>
</ul>
<p>Use the following syntax:</p>
<p>Subject: //XFB appli=appliName; DEST=destId; ORG=orgId FILENAME=fileName</p>         </td>
      </tr>
      <tr>
         <td><p>From</p>         </td>
         <td><p>This field is mandatory if you set the value of <span style="font-weight: bold;">Attach file</span> to <span style="font-weight: bold;">Yes</span>. If <span style="font-weight: bold;">Attach file</span> is set to <span style="font-weight: bold;">No</span>, the <span style="font-weight: bold;">From</span> field is already completed in the formatted email and you do not need to complete this field.</p>
<p>Enter the return email address.<br />
Maximum: 128 alphanumeric characters.<br />
If you do not specify an originating address in this field, Gateway uses the default email address that you specify in the Local Site associated with the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>To</p>         </td>
         <td><p>This field is mandatory if you set the value of <span style="font-weight: bold;">Attach file</span> to <span style="font-weight: bold;">Yes</span>. If <span style="font-weight: bold;">Attach file</span> is set to <span style="font-weight: bold;">No</span>, the <span style="font-weight: bold;">To</span> field is already completed in the formatted email and you do not need to complete this field.</p>
<p>Enter the main destination email address.<br />
There is no limitation on the number of characters you can enter in this field.<br />
If you do not specify a destination address, the default email address specified in the Remote Site is used.</p>
<p>If the length of the field is not large enough to contain the corresponding list, it is completed by " * " and the value is stored in an overflow block.</p>
<p>The overflow blocks are formatted as a character string. For example:</p>
<p>To: (options) "description" &lt;address@email&gt;,  ... \0 Cc: ... \0 Bcc: ... \0 \0</p>         </td>
      </tr>
      <tr>
         <td><p>Cc</p>         </td>
         <td><p>Enter the carbon copy destination addresses.<br />
There is no limitation on the number of characters that you can enter in this field.</p>         </td>
      </tr>
      <tr>
         <td><p>Bcc</p>         </td>
         <td><p>Enter the blind copy destination addresses.<br />
There is no limitation on the number of characters that you can enter in this field.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[About SMTP/POP3](../../../../protocols_about/smtp_pop3_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
