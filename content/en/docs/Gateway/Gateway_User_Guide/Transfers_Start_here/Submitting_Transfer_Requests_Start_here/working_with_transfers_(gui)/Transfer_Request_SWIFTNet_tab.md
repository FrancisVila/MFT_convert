{
    "title": "New Transfer Request: SWIFTNet tabs",
    "linkTitle": "SWIFTNet tab",
    "weight": "230"
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
         <td><p>Destination partner</p>         </td>
         <td><p>Enter the Trading Partner alias that represents the file destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Delivery mode</p>         </td>
         <td><p>Select the delivery mode for the file or message:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span> (default)</li>
<li><span style="font-weight: bold;">Real time</span> = Immediate</li>
<li><span style="font-weight: bold;">Store and forward</span> = Send and then store in the queue in the SWIFTNet domain (SnF)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Destination DN</p>         </td>
         <td><p>Enter the name of the destination partner of the trading partner exchange.<br />
Maximum: 128 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="compress"></span>Compress</p>         </td>
         <td><p>Select the compressing option:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span> = Use the compression algorithm when sending a file or message to a partner</li>
<li><span style="font-weight: bold;">No</span> = No compression</li>
<li><span style="font-weight: bold;">(empty)</span> = Use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Originator partner</p>         </td>
         <td><p>Enter the Trading Partner alias that is the file originator.</p>         </td>
      </tr>
      <tr>
         <td><p>Originator DN</p>         </td>
         <td><p>Enter the name of the originating partner of the trading partner exchange.<br />
Maximum: 128 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Service name</p>         </td>
         <td><p>Enter the SWIFT business service name (as specified in the XML header).<br />
Maximum: 30 alphanumeric characters.</p>
<p>If you do not complete this field, Gateway uses the value set in the destination Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Request type</p>         </td>
         <td><p>Enter the type of request (as specified in the XML header).<br />
Maximum: 30 alphanumeric characters.</p>
<p>If you do not complete this field, Gateway uses the value set in the destination Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Receipt sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Receipt request</p>         </td>
         <td><p>Select the receipt request option:</p>
<ul>
<li><span style="font-weight: bold;">Signed</span> = Request receipt</li>
<li><span style="font-weight: bold;">None</span> = No receipt</li>
<li><span style="font-weight: bold;">Undefined</span> = Use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Receipt DN</p>         </td>
         <td><p>FileAct, Real Time mode only, if you have selected <span style="font-weight: bold;">Request receipt</span></p>
<p>DN = Distinguished Name</p>
<p>Enter the name of the receipt reception address. This is the address to which the receiving partner sends the receipt.</p>
<p>If you do not complete this field, the default value is the originator name.</p>         </td>
      </tr>
      <tr>
         <td><p>Receipt request type</p>         </td>
         <td><p>FileAct, Real Time mode only, if you have selected <span style="font-weight: bold;">Request receipt</span></p>
<p>Type of acknowledgment request<br />
Maximum: 30 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>E2E (End To End) sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Message id</p>         </td>
         <td><p>The value of this parameter overwrites the message id created by Gateway in the Transfer Request.</p>
<p>Enter the SWIFTNet message id of the new transfer. This should be a Universal Unique IDentifier (UUID).</p>
<p>If the transfer is a <a href="../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate">Possible Duplicate</a>, enter the message id of the initial transfer.</p>
<p>Maximum: 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Possible duplicate</p>         </td>
         <td><p>Select this option to indicate to the responder that the transfer is a <a href="../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate">Possible Duplicate</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Header info</p>         </td>
         <td><p>Reference to file on disk containing Header Info. This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info#XML_File_structure">specific structure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Security sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Sign</p>         </td>
         <td><p>Select the signing option:</p>
<ul>
<li>Yes</li>
<li>No</li>
<li><span style="font-weight: bold;">(empty)</span> = Use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Encrypt</p>         </td>
         <td><p>InterAct only</p>
<p>Select the encryption method:</p>
<ul>
<li>Yes</li>
<li>No</li>
<li><span style="font-weight: bold;">(empty)</span> = use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Non repudiation</p>         </td>
         <td><p>Select this option to request SWIFT to keep proof of sending (availability depends on the service used).</p>         </td>
      </tr>
      <tr>
         <td><p>Sign DN</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for signing in Initiator mode. Otherwise the securityDN (supplied by SNL) is used.<br />
Maximum: 100 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Encrypt DN</p>         </td>
         <td><p>InterAct only</p>
<p>If specified, name used for encryption in Initiator mode.<br />
Maximum: 100 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Signature list</p>         </td>
         <td><p>Reference to file on disk containing a Signature List. This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_sig_list#XML_File_structure">specific structure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Other sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Additional params</p>         </td>
         <td><p>Reference to file on disk containing additional SWIFTNet structures (for example, Header Info and/or Signature List). This file must respect a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info#XML_File_structure">specific structure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>InterAct sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message</p>         </td>
         <td><p>Select this option to send a text message in InterAct.</p>
<p>Enter the message in the text frame.<br />
Maximum: 512 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Payload type</p>         </td>
         <td><p>Select the payload format:</p>
<ul>
<li>Undefined</li>
<li>Text</li>
<li>Embedded</li>
</ul>
<p>On the <span style="font-style: italic;">Initiator</span> side, you can use this parameter to overwrite the <span style="font-weight: bold;">Payload type</span> parameter defined in the Trading Partner.</p>
<p>On the <span style="font-style: italic;">Responder</span> side, when using the <span style="font-weight: bold;">Receipt request synchronized</span> option you can respond with a custom payload type. Even if you saved the request payload as embedded in the Trading Partner, you can answer back with text mode.</p>         </td>
      </tr>
      <tr>
         <td><p>SnF sub-tab <span style="font-weight: normal;">[for Store and forward Delivery mode]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Notification queue</p>         </td>
         <td><p>Name of the SWIFTNet queue for receiver delivery notifications for the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Overdue time</p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
         <td><p>SWIFTNet <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_overdue">OverdueTime</a></p>
<p>To set a date value for the OverdueTime, check this option and select the required date using the drop-down calendar.</p>
<p>When the option is unchecked, no OverdueTime will be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Time</p>         </td>
         <td><p>SWIFTNet <a href="../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_overdue">OverdueTime</a></p>
<p>To set a time value for the OverdueTime, check this option and set the required hours and minutes (the seconds are truncated to '00' when sending).</p>
<p>When the option is unchecked, but <strong>Date</strong> is checked, the OverdueTime sent is the date with time '00:00:00'.</p>
<p>When both <strong>Time</strong> and <strong>Date</strong> are unchecked, no OverdueTime will be sent.</p>
<p><strong>Note:</strong> If you use the <strong>Time</strong> option, you must also set the <strong>Date</strong> option.</p>         </td>
      </tr>
      <tr>
         <td><p>Copy services</p>         </td>
      </tr>
      <tr>
         <td><p>Request copy</p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">copy of the file</a> to be sent to a third party defined at the service level.</p>         </td>
      </tr>
      <tr>
         <td><p>Request authorisation notification</p>         </td>
         <td><p>SWIFTNet Authorization notification indicator.</p>
<p>Select this option to receive Authorization system messages for files sent over <a href="../../../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">Y-copy services</a>.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[Using pre/post transfer compression for SWIFTNet](../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_compression)

[Possible Duplicate management for SWIFTNet](../../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_working_with)

<a href="#" class="selected">SWIFTNet File and Message Copy</a>

[SWIFTNet OverdueTime](../../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_overdue)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
