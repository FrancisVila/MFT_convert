{
    "title": "New Transfer Request: X.420 tab",
    "linkTitle": "X.420 tab",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Managing Transfers

Use the **X.420** tab to define X.420-specific properties for the Transfer Request.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Override the originator X.400 address.</p>
<p>Click <span style="font-weight: bold;">Edit...</span> to configure the <a href="../../../../configuration_start_here/config_protocols_about/x400_or_address">O/R address</a>.</p>
<p>Click <span style="font-weight: bold;">Clear</span> to delete the displayed O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>Recipient</p>         </td>
         <td><p>Override the recipient X.400 address.</p>
<p>Click <span style="font-weight: bold;">Edit...</span> to configure the <a href="../../../../configuration_start_here/config_protocols_about/x400_or_address">O/R address</a>.</p>
<p>Click <span style="font-weight: bold;">Clear</span> to delete the displayed O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>Delivery notification request</p>         </td>
         <td><p>Select the type of delivery notification request:</p>
<ul>
<li><span style="font-weight: bold;">NDN</span> = Non Delivery Notification (default)</li>
<li><span style="font-weight: bold;">DN_NDN</span> = Delivery Notification and Non Delivery Notification</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Notification request</p>         </td>
         <td><p>Select the type of receipt request:</p>
<ul>
<li><span style="font-weight: bold;">None</span> (default)</li>
<li><span style="font-weight: bold;">NRN</span> = Non Receipt Notification</li>
<li><span style="font-weight: bold;">RN_NRN</span> = Receipt Notification and Non Receipt Notification</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Interpersonal messaging Id</p>         </td>
         <td><p>Define the IPM (Interpersonal Messaging) Identifier that uniquely identifies this IPM. Mandatory user relative identifier, which uniquely identifies the IPM.</p>         </td>
      </tr>
      <tr>
         <td><p>Subject</p>         </td>
         <td><p>Subject of the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Body part type</p>         </td>
         <td><p>Select the body part type to be used:</p>
<ul>
<li><span style="font-weight: bold;">ia5</span> (default)</li>
<li>g3facsimile</li>
<li>teletex</li>
<li>videotex</li>
<li>encrypted</li>
<li>bilaterallyDefined</li>
<li>externallyDefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Importance</p>         </td>
         <td><p>Specify the importance of the IPM:</p>
<ul>
<li>low</li>
<li><span style="font-weight: bold;">normal</span> (default)</li>
<li>high</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Sensitivity</p>         </td>
         <td><p>Specify the sensitivity of the IPM:</p>
<ul>
<li><span style="font-weight: bold;">unspecified</span> (default)</li>
<li>personal</li>
<li>private</li>
<li>companyConfidential</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Content Id</p>         </td>
         <td><p>Uniquely defines the message to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Message transfer system priority</p>         </td>
         <td><p>Define the priority level for the message:</p>
<ul>
<li>High</li>
<li>Normal</li>
<li>Low</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Reply request</p>         </td>
         <td><p>Select whether or not to request a reply:</p>
<ul>
<li><span style="font-weight: bold;">N</span> (default)</li>
<li>Y</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Replied to IPM Id</p>         </td>
         <td><p>Set the IPM identifier which identifies the message to which this message is the reply.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[About X.400](../../../../connectors_about/x400_about)

[Submitting an X.400 Transfer Request](../../../../connectors_about/x400_about/x400_working_with#submitting_x400_transfer_request)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)