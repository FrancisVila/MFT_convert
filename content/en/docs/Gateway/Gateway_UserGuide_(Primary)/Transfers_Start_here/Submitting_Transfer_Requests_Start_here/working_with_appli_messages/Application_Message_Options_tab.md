{
    "title": "Options tab",
    "linkTitle": "Options tab",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Transfers

The **Options** tab is identical for both **Application Message** Requests and **Acknowledgement Message** Requests.

Use this tab to specify a date and time, or a range of dates and times, when the message can be sent. If you leave all of these fields empty, Gateway sends the message immediately.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Timing</p>         </td>
      </tr>
      <tr>
         <td><p>Earliest start date</p>         </td>
         <td><p>Use this field to defer the start date for the Transfer.</p>
<p>Select the earliest start date for the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>time</p>         </td>
         <td><p>Select the earliest start time for the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Relative time</p>         </td>
         <td><p>The time that you specify here is relative to the current time. Specify the time in the format: <span style="font-weight: bold;">HH:MM</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Latest start date</p>         </td>
         <td><p>Use this field to set a time limit on the Transfer.</p>
<p>Select the latest date to start the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>time</p>         </td>
         <td><p>Select the latest time to start the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Relative time</p>         </td>
         <td><p>Time relative to the current time. Specify the time in the format: <span style="font-weight: bold;">HH:MM</span>.</p>
<p>For example, enter 01:10 to indicate one hour and ten minutes from the present time.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of restarts</p>         </td>
         <td><p>Enter the maximum number of Transfer restarts.</p>
<p>Integer: <span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">99</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>Select one of the following Transfer priority values:</p>
<ul>
<li>High</li>
<li>Normal (default)</li>
<li>Low</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>User information</p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>Use these two fields to enter user parameters.<br />
Maximum 40 alphanumeric characters in each field.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Application Messages](../)

[Working with Acknowledgement Messages](../../working_with_ack_messages)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
