{
    "title": "XFBTransfer Sentinel/Gateway correspondence",
    "linkTitle": "XFBTransfer correspondence",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

The table in this section identifies the correspondence between Sentinel XFBTransfer object attributes and Gateway transfer properties.

In Axway Sentinel, use XFBTransfer to monitor and to respond to Gateway file transfers. Each attribute of this Tracked Object corresponds, in most cases, to a single Gateway transfer property.

To use the names of Axway Sentinel attributes to identify the corresponding Gateway properties, refer to the table below.

-   <span style="font-style: italic;">Axway Sentinel</span>: This column displays the names of the XFBTransfer attributes in alphabetical order.
-   <span style="font-style: italic;"><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span></span>: For the attributes in the <span style="font-style: italic;">Axway Sentinel</span> column, this column displays the names of the corresponding Gateway properties.

The XFBTransfer object describes all types of Axway Managed File Transfer. Therefore some XFBTransfer attributes do not correspond to any Gateway properties. Such XFBTransfer attributes are not listed in this table.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Axway Sentinel         </th>
<th class="HeadD-Column1-Header1"><span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>appli</p>         </td>
      </tr>
      <tr>
         <td><p>BlockSize</p>         </td>
         <td><p>block_size</p>         </td>
      </tr>
      <tr>
         <td><p>CGateUserParameter1</p>         </td>
         <td><p>cgate_user_param1</p>         </td>
      </tr>
      <tr>
         <td><p>CGateUserParameter2</p>         </td>
         <td><p>chanteuse</p>         </td>
      </tr>
      <tr>
         <td><p>CiphEntityObjectId</p>         </td>
         <td><p>ciphEntity.object_id</p>         </td>
      </tr>
      <tr>
         <td><p>CiphEntityObjectType</p>         </td>
         <td><p>ciphEntity.object_type</p>         </td>
      </tr>
      <tr>
         <td><p>CommandType</p>         </td>
         <td><p>Depends on<span class="code"> type</span></p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>compression</p>         </td>
      </tr>
      <tr>
         <td><p>CreationDate</p>         </td>
         <td><p>Date from<span class="code"> hist_create_date</span></p>         </td>
      </tr>
      <tr>
         <td><p>CreationTime</p>         </td>
         <td><p>Time from<span class="code"> hist_create_date</span></p>         </td>
      </tr>
      <tr>
         <td><p>CycleId</p>         </td>
         <td><p>this_cycle_id</p>         </td>
      </tr>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>direction</p>         </td>
      </tr>
      <tr>
         <td><p>EarliestDate</p>         </td>
         <td><p>Date from<span class="code"> date_to_begin</span></p>         </td>
      </tr>
      <tr>
         <td><p>EarliestTime</p>         </td>
         <td><p>Time from<span class="code"> date_to_begin</span></p>         </td>
      </tr>
      <tr>
         <td><p>EndDate</p>         </td>
         <td><p>Date from<span class="code"> date_to_end</span></p>         </td>
      </tr>
      <tr>
         <td><p>EndTime</p>         </td>
         <td><p>Time from<span class="code"> date_to_end</span></p>         </td>
      </tr>
      <tr>
         <td><p>EotProcedure</p>         </td>
         <td><p>end_xfer_scriptpath</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5AuthType</p>         </td>
         <td><p>auth_type</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5CiphType</p>         </td>
         <td><p>ciph_type</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5IdBank</p>         </td>
         <td><p>id_banque</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5IdBankSec</p>         </td>
         <td><p>id_banque_sec</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5IdClient</p>         </td>
         <td><p>id_client</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5IdClientSec</p>         </td>
         <td><p>id_client_sec</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5MemoType</p>         </td>
         <td><p>memo_type</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5Paraf_used</p>         </td>
         <td><p>paraf_used</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5RSign1Used</p>         </td>
         <td><p>rsign1_used</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5RSign2Used</p>         </td>
         <td><p>rsign2_used</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5SealType</p>         </td>
         <td><p>seal_type</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5SignType</p>         </td>
         <td><p>sign_type</p>         </td>
      </tr>
      <tr>
         <td><p>Etb5UserArea</p>         </td>
         <td><p>userarea</p>         </td>
      </tr>
      <tr>
         <td><p>FileName</p>         </td>
         <td><p>Built from<span class="code"> dir_path</span> and<span class="code"> file_component</span></p>         </td>
      </tr>
      <tr>
         <td><p>FileOrganisation</p>         </td>
         <td><p>file_org</p>         </td>
      </tr>
      <tr>
         <td><p>FileSize</p>         </td>
         <td><p>file_size</p>         </td>
      </tr>
      <tr>
         <td><p>FileType</p>         </td>
         <td><p>file_type</p>         </td>
      </tr>
      <tr>
         <td><p>FinalReceiverId</p>         </td>
         <td><p>destination</p>         </td>
      </tr>
      <tr>
         <td><p>GroupName</p>         </td>
         <td><p>group_name</p>         </td>
      </tr>
      <tr>
         <td><p>InternalCycleId</p>         </td>
         <td><p>this_extended_cycle_id</p>         </td>
      </tr>
      <tr>
         <td><p>IsEnd</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">1</span> if<span class="code"> state</span> is<span class="code"> ACKED</span> or<span class="code"> ENDED</span></li>
<li><span class="code" style="font-weight: bold;">0</span> otherwise</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>IsPermanent</p>         </td>
         <td><p>permanent</p>         </td>
      </tr>
      <tr>
         <td><p>IsServer</p>         </td>
         <td><p>mode</p>         </td>
      </tr>
      <tr>
         <td><p>IsSSL</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">1</span> if<span class="code"> tls_sprof</span> is set</li>
<li><span class="code" style="font-weight: bold;">0</span> otherwise</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>LatestDate</p>         </td>
         <td><p>Date from<span class="code"> date_to_end</span></p>         </td>
      </tr>
      <tr>
         <td><p>LatestTime</p>         </td>
         <td><p>Time from<span class="code"> date_to_end</span></p>         </td>
      </tr>
      <tr>
         <td><p>LocalId</p>         </td>
         <td><p>local_ident</p>         </td>
      </tr>
      <tr>
         <td><p>Location</p>         </td>
         <td><p>local_site_alias</p>         </td>
      </tr>
      <tr>
         <td><p>Machine</p>         </td>
         <td><p><span class="code">"GTW-UNIX"</span> or<span class="code"> "GTW-NT"</span></p>         </td>
      </tr>
      <tr>
         <td><p>Monitor</p>         </td>
         <td><p>"GTW"</p>         </td>
      </tr>
      <tr>
         <td><p>MonitorVersion</p>         </td>
         <td><p>Version, plus SP number where applicable.</p>         </td>
      </tr>
      <tr>
         <td><p>OriginalSenderId</p>         </td>
         <td><p>originator</p>         </td>
      </tr>
      <tr>
         <td><p>PositionNumber</p>         </td>
         <td><p>sequence</p>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>priority</p>         </td>
      </tr>
      <tr>
         <td><p>ProductIpAddr</p>         </td>
         <td><p><span class="code">sentinel_product_ip_addr</span> (configuration parameter)</p>         </td>
      </tr>
      <tr>
         <td><p>ProductName</p>         </td>
         <td><p>local_site_alias</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>protocol</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileLabel</p>         </td>
         <td><p>file_label</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileName</p>         </td>
         <td><p>file_name</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolId</p>         </td>
         <td><p>xfer_ident</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolMessage</p>         </td>
         <td><p><span class="code">rcv_msg</span> or<span class="code"> snd_msg (</span>if the transfer is of type message)</p>
<p>Note: on PeSIT, only the message sent in transfer-related phases is visible in the tracked object updates sent to Sentinel</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolParameter</p>         </td>
         <td><p><span class="code">rcv_msg</span> or<span class="code"> snd_msg</span> (if the transfer is of type transfer). See note for ProtocolMessage above.</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolSelectParameter</p>         </td>
         <td><p><span class="code">rcv_msg</span> (if the transfer is: outgoing, PeSit or SWIFTNet, and of type transfer). See note for ProtocolMessage above.</p>         </td>
      </tr>
      <tr>
         <td><p>RAppl</p>         </td>
         <td><p>rcv_appli</p>         </td>
      </tr>
      <tr>
         <td><p>ReceiverId</p>         </td>
         <td><p><span class="code">remote_agent_ident</span> or<span class="code"> local_agent_ident</span></p>         </td>
      </tr>
      <tr>
         <td><p>RecordFormat</p>         </td>
         <td><p>xfer_rec_fmt</p>         </td>
      </tr>
      <tr>
         <td><p>RecordNumber</p>         </td>
         <td><p>rec_count</p>         </td>
      </tr>
      <tr>
         <td><p>RecordSize</p>         </td>
         <td><p>rec_len</p>         </td>
      </tr>
      <tr>
         <td><p>RequestCreationDate</p>         </td>
         <td><p>Date from<span class="code"> date_create</span></p>         </td>
      </tr>
      <tr>
         <td><p>RequestCreationTime</p>         </td>
         <td><p>Time from<span class="code"> date_create</span></p>         </td>
      </tr>
      <tr>
         <td><p>RequestType</p>         </td>
         <td><p>Depends on<span class="code"> type</span></p>         </td>
      </tr>
      <tr>
         <td><p>RequestUserId</p>         </td>
         <td><p>username</p>         </td>
      </tr>
      <tr>
         <td><p>RetryMaxNumber</p>         </td>
         <td><p>retry_count_max</p>         </td>
      </tr>
      <tr>
         <td><p>RetryNumber</p>         </td>
         <td><p>retry_count</p>         </td>
      </tr>
      <tr>
         <td><p>ReturnCode</p>         </td>
         <td><p><span class="code">last_end_reason</span>, <span class="code">last_end_diag</span>, and <span class="code">last_end_err</span></p>         </td>
      </tr>
      <tr>
         <td><p>ReturnMessage</p>         </td>
         <td><p>Message corresponding to<span class="code"> last_end_reason</span></p>         </td>
      </tr>
      <tr>
         <td><p>RUser</p>         </td>
         <td><p>rcv_user</p>         </td>
      </tr>
      <tr>
         <td><p>SAppl</p>         </td>
         <td><p>snd_appli</p>         </td>
      </tr>
      <tr>
         <td><p>SendDate</p>         </td>
         <td><p>date_create</p>         </td>
      </tr>
      <tr>
         <td><p>SenderId</p>         </td>
         <td><p><span class="code">remote_agent_ident</span> or<span class="code"> local_agent_ident</span></p>         </td>
      </tr>
      <tr>
         <td><p>SessionTag</p>         </td>
         <td><p>session_tag</p>         </td>
      </tr>
      <tr>
         <td><p>SignEntityObjectId</p>         </td>
         <td><p>signEntity.object_id</p>         </td>
      </tr>
      <tr>
         <td><p>SignEntityObjectType</p>         </td>
         <td><p>signEntity.object_type</p>         </td>
      </tr>
      <tr>
         <td><p>Site</p>         </td>
         <td><p>remote_agent</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpAckTo</p>         </td>
         <td><p>receipt_req_to</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpAef</p>         </td>
         <td><p>attach_extract_file</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpBcc</p>         </td>
         <td><p>smtp_bcc</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpCc</p>         </td>
         <td><p>smtp_cc</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpFrom</p>         </td>
         <td><p>smtp_from</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpSubject</p>         </td>
         <td><p>smtp_subject</p>         </td>
      </tr>
      <tr>
         <td><p>SmtpTo</p>         </td>
         <td><p>smtp_to</p>         </td>
      </tr>
      <tr>
         <td><p>SSLAuth</p>         </td>
         <td><ul>
<li>"Serveur" if<span class="code"> tls_server_auth</span> is set</li>
<li>"Both" if<span class="code"> tls_server_auth</span> and<span class="code"> tls_client_auth</span> are set</li>
<li>"None" otherwise</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SSLCypher</p>         </td>
         <td><p>tls_cipher_suite</p>         </td>
      </tr>
      <tr>
         <td><p>StartDate</p>         </td>
         <td><p>Date from<span class="code"> date_to_begin</span></p>         </td>
      </tr>
      <tr>
         <td><p>StartTime</p>         </td>
         <td><p>Time from<span class="code"> date_to_begin</span></p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>Combination of: <span class="code">state</span>, <span class="code">direction</span>, <span class="code">mode</span>, <span class="code">user_processed</span> and <span class="code">route_state</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>SUser</p>         </td>
         <td><p>snd_user</p>         </td>
      </tr>
      <tr>
         <td><p>SwPossibleDuplicateInd</p>         </td>
         <td><p>sw_pd_indication</p>         </td>
      </tr>
      <tr>
         <td><p>TpmDeaId</p>         </td>
         <td><p>dea_id</p>         </td>
      </tr>
      <tr>
         <td><p>TradeCompressing</p>         </td>
         <td><p>trade_compress</p>         </td>
      </tr>
      <tr>
         <td><p>TradeCompressionAlgo</p>         </td>
         <td><p>trade_compress_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDeliveryMode</p>         </td>
         <td><p>trade_delivery_mode</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDestination</p>         </td>
         <td><p>trade_dest</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDestinationAlias</p>         </td>
         <td><p>trade_dest_alias</p>         </td>
      </tr>
      <tr>
         <td><p>TradeDestinationRemote</p>         </td>
         <td><p>trade_remote_destination</p>         </td>
      </tr>
      <tr>
         <td><p>TradeEncrypting</p>         </td>
         <td><p>trade_encrypt</p>         </td>
      </tr>
      <tr>
         <td><p>TradeEncryptionAlgo</p>         </td>
         <td><p>trade_ciphering_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeFileEncoded</p>         </td>
         <td><p>trade_file_encoded</p>         </td>
      </tr>
      <tr>
         <td><p>TradeFormat</p>         </td>
         <td><p>trade_format</p>         </td>
      </tr>
      <tr>
         <td><p>TradeKeyEncryptionAlgo</p>         </td>
         <td><p>trade_key_ciphering_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeMessageId</p>         </td>
         <td><p>message_id</p>         </td>
      </tr>
      <tr>
         <td><p>TradeNonRepudiation</p>         </td>
         <td><p>trade_non_repudiation</p>         </td>
      </tr>
      <tr>
         <td><p>TradeNotifQueue</p>         </td>
         <td><p>trade_notif_queue</p>         </td>
      </tr>
      <tr>
         <td><p>TradeOriginator</p>         </td>
         <td><p>trade_org</p>         </td>
      </tr>
      <tr>
         <td><p>TradeOriginatorAlias</p>         </td>
         <td><p>trade_org_alias</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptMessageId</p>         </td>
         <td><p>trade_receipt_message_id</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptMic</p>         </td>
         <td><p>trade_receipt_mic</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptMicAlgo</p>         </td>
         <td><p>trade_compression_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptRecipient</p>         </td>
         <td><p>trade_receipt_recipient</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptSigningAlgo</p>         </td>
         <td><p>trade_receipt_sign_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptSmimeContentType</p>         </td>
         <td><p>trade_receipt_content_type</p>         </td>
      </tr>
      <tr>
         <td><p>TradeReceiptSmimeSignature</p>         </td>
         <td><p>trade_receipt_signature</p>         </td>
      </tr>
      <tr>
         <td><p>TradeRequestType</p>         </td>
         <td><p>trade_request_type</p>         </td>
      </tr>
      <tr>
         <td><p>TradeService</p>         </td>
         <td><p>trade_service</p>         </td>
      </tr>
      <tr>
         <td><p>TradeSigning</p>         </td>
         <td><p>trade_sign</p>         </td>
      </tr>
      <tr>
         <td><p>TradeSigningAlgo</p>         </td>
         <td><p>trade_sign_algo</p>         </td>
      </tr>
      <tr>
         <td><p>TradeState</p>         </td>
         <td><p>trade_state</p>         </td>
      </tr>
      <tr>
         <td><p>TransferTag</p>         </td>
         <td><p>local_ident</p>         </td>
      </tr>
      <tr>
         <td><p>Transcoding</p>         </td>
         <td><p><span class="code">data_code</span>, plus<span class="code"> "T"</span> if<span class="code"> xfer_data_code</span> is not equal to<span class="code"> data_code</span>, in other words when there is transcoding</p>         </td>
      </tr>
      <tr>
         <td><p>TransferType</p>         </td>
         <td><p>Depends on type</p>         </td>
      </tr>
      <tr>
         <td><p>TransmissionDuration</p>         </td>
         <td><p><span class="code">f(date_end – date_begin)</span></p>         </td>
      </tr>
      <tr>
         <td><p>TransmittedBytes</p>         </td>
         <td><p>x_bytes</p>         </td>
      </tr>
      <tr>
         <td><p>UserId</p>         </td>
         <td><p>username</p>         </td>
      </tr>
      <tr>
         <td><p>UserParameter1</p>         </td>
         <td><p>param1</p>         </td>
      </tr>
      <tr>
         <td><p>UserParameter2</p>         </td>
         <td><p>param2</p>         </td>
      </tr>
      <tr>
         <td><p>UserProcessed</p>         </td>
         <td><p>user_processed</p>         </td>
      </tr>
      <tr>
         <td><p>UserState</p>         </td>
         <td><p>user_state</p>         </td>
      </tr>
      <tr>
         <td><p>VirtualDirName</p>         </td>
         <td><p>dir_name</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[XFBTransfer Tracked Object](../sentinel_xfbtransfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
