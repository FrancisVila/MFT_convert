{
    "title": "New Transfer Request: Details tab",
    "linkTitle": "Details tab",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User</p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>Enter the user parameter 1.<br />
Maximum: 40 alphanumeric characters.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
         <td><p>Enter the user parameter 2.<br />
Maximum: 40 alphanumeric characters.</p>
<p>Gateway uses the values you enter in this parameter locally. It does not transfer the values to your transfer partner. Use this parameter to locally store values that you can reuse via Decision Rules, Models and batch procedures.</p>         </td>
      </tr>
      <tr>
         <td><p>Message to send</p>         </td>
         <td><p>Enter a user message.</p>
<ul>
<li>FTP:<br />
User message to transmit at the connection phase.
This message can be a list of special commands to send to the remote server using <code>SITE</code> or <code>QUOTE</code> FTP commands.</li>
<li>HTTP:<br />
User message to transmit at the connection phase. The user message enables you to add CGI parameters or <a href="../../../../protocols_about/http_about/http_client_non_std_headers">non-standard HTTP headers</a> to the Transfer Request.<br />
For CGI parameters you must also check the <strong>Send transfer attributes</strong> option on the <strong>HTTP</strong> tab in the Remote Site. Use the format: <code>xfer_param1=value1&amp;xfer_param2=value2</code>.<br />
For non-standard HTTP headers, use the format: <code>[xs4hh]X-Id1=v1&amp;X-Id2=v2[/xs4hh]</code>.</li>
<li>OFTP, PEL, PeSIT, EDIINT:<br />
User message to transmit at the connection phase.<br />
</li>
<li>SWIFTNet FileAct:<br />
[0 - 255]: Transfer description, supplied by the initiator. Free-text description of the transfer.<br />
[256 - 511]: Transfer information, supplied by the initiator. Structured information concerning the transfer. For more details, refer to the SWIFT documentation.</li>
<li>SWIFTNet InterAct:<br />
[0 - 511]: User message</li>
</ul>
<p>Maximum:</p>
<ul>
<li>8 alphanumeric characters (OFTP)</li>
<li>256 alphanumeric characters for each part (SWIFTNet FileAct)</li>
<li>512 alphanumeric characters (FTP, HTTP, PeSIT, EDIINT, SWIFTNet InterAct)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Retry and Timing</p>         </td>
      </tr>
      <tr>
         <td><p>Interval</p>         </td>
         <td><p>Depending on the protocol, complete this field as follows:</p>
<ul>
<li>PEL: specify the interval between two Remote Site polls (LOTS and POLL commands)</li>
<li>PeSIT HS: for cyclic selection requests only - in case of selection failure, specify the repetition interval in seconds</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of retries</p>         </td>
         <td><p>Enter the maximum number of times Gateway tries to submit the Transfer Request.<br />
Integer.</p>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>Select the Transfer priority:</p>
<ul>
<li><strong>Normal</strong></li>
<li><span style="font-weight: bold;">High</span></li>
<li><span style="font-weight: bold;">Low</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Frozen state</p>         </td>
         <td><p>This option allows you to create the Transfer in <span style="font-style: italic;">frozen state</span>.</p>
<p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span></li>
<li><span style="font-weight: bold;">No</span></li>
<li><span style="font-weight: bold;">(Empty)</span></li>
</ul>
<p>The value that you set here overrides the value that you set in the Model definition.</p>
<p>After creating a Transfer in frozen state, it remains available for submission at a later date. To submit a Transfer that is in frozen state, select <span style="font-weight: bold;">Restart a transfer</span>.</p>
<p>Alternatively, use the command <span class="code" style="font-weight: bold;">pelctl control_trans -a R</span></p>
<p><strong>Note</strong>: it is not possible to create a Diffusion list transfer in frozen state.</p>         </td>
      </tr>
      <tr>
         <td><p>Earliest start date</p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
         <td><p>Click the check-box to activate the field. Then click the day, month or year units to select them and enter the earliest date to begin the transfer.<br />
Alternatively, click the down arrow to open a calendar window from which you can select the date.</p>         </td>
      </tr>
      <tr>
         <td><p>Time</p>         </td>
         <td><p>Click the check-box to activate the field. Then click the hours, minutes or seconds units to select them, and enter the earliest time to begin the transfer.<br />
Alternatively, click the unit and then click the up and down arrows to select the time.</p>         </td>
      </tr>
      <tr>
         <td><p>Latest start date</p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
         <td><p>Select the latest date to start the transfer.</p>
<p>Use this field to define the validity period for the transfer. If the transfer has not taken place or is in progress when this period expires, it is considered timed out and is canceled.</p>
<p>Click the check-box to activate the field. Then click the day, month or year units to select them and enter the latest valid date for the transfer.<br />
Alternatively, click the down arrow to open a calendar window from which you can select the date.</p>         </td>
      </tr>
      <tr>
         <td><p>Time</p>         </td>
         <td><p>Select the latest time to start the transfer.</p>
<p>Click the check-box to activate the field. Then click the hours, minutes or seconds units to select them, and enter the latest valid time to begin the transfer.<br />
Alternatively, click the unit and then click the up and down arrows to select the time.</p>         </td>
      </tr>
      <tr>
         <td><p>Routing/Reply</p>         </td>
      </tr>
      <tr>
         <td><p>Route from (Transfer ID)</p>         </td>
         <td><p>Enter the local identifier of the Request from which the Transfer is routed.</p>         </td>
      </tr>
      <tr>
         <td><p>Reply to (Transfer ID)</p>         </td>
         <td><p>acknowledgment Requests only</p>
<p>Enter the local identifier of the acknowledged Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p>Sentinel</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer filter</p>         </td>
         <td><p>Use this option to send a record of Transfer state changes to Sentinel.<br />
Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">All</span>: Sends all Transfer state changes to Sentinel</li>
<li><span style="font-weight: bold;">Summary</span>: Sends a summary of Transfer state changes. Summary Transfer states are: canceled, ended, acked, created, to begin.</li>
<li><span style="font-weight: bold;">None</span>: Sends no Transfer state changes</li>
<li><span style="font-weight: bold;">Undefined</span>: Gateway searches for the definition in the Application, then the Remote Site. If the <span style="font-weight: bold;">Sentinel Transfer Filter</span> field is set to <span style="font-weight: bold;">Undefined</span> in both of these objects, Gateway uses the value set in the configuration menu.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
