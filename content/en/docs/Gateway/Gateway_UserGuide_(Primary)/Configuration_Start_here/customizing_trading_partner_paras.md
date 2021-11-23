{
    "title": "Configuring trading Partner parameters",
    "linkTitle": "Customizing Trading Partner parameters",
    "weight": "100"
}{{< Gateway/componentlongname  >}}: Configuration

This topic lists and describes the configuration parameters that you can use to customize Gateway behavior when managing certain trading file management situations.

For the procedure to follow, refer to [Configuration: Gateway parameters - Advanced parameters and Trace levels](../config_gateway_paras#Advanced_parameters).

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>trade_mic_generation_method</p>         </td>
         <td><p>Defines the EDIINT MIC calculation method when sending files:</p>
<ul>
<li><strong>0</strong>: MIC is always calculated (default)</li>
<li><span style="font-weight: bold;">1</span>: MIC is only calculated if receipt is requested signed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_allow_remote_duplicate</p>         </td>
         <td><p>Only available for messages received for remote partners (To:).</p>
<p>Defines whether or not to allow duplicate messages:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: reject duplicate messages (default)</li>
<li><span style="font-weight: bold;">1</span>: skip search for duplicate messages</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_remove_duplicated_files</p>         </td>
         <td><p>Defines how to manage files containing messages that were already received:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: keep file</li>
<li><span style="font-weight: bold;">1</span>: remove file (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_unknown_receipt_ended</p>         </td>
         <td><p>Defines how to handle the receipt of an unknown transfer:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: receipt canceled (default)</li>
<li><span style="font-weight: bold;">1</span>: receipt ended</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>trade_recipient_check</p>         </td>
         <td><p>Defines whether to check the "Final-Recipient" field of the acknowledgement against the originator’s name of the acknowledged transfer:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: ignore Final-Recipient field</li>
<li><span style="font-weight: bold;">1</span>: check Final-Recipient (default)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
