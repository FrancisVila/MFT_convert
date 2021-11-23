{
    "title": "Gateway objects for TARGET2 exchanges",
    "linkTitle": "Summary of Gateway objects for TARGET2 exchanges",
    "weight": "370"
}The following table lists the Gateway objects you require for TARGET2 exchanges, and indicates if they are provided in the installation package or if you must create them.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Object</p>         </th>
<th class="HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comments</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Remote Sites</strong></p>
<p>You import the four Remote Site objects listed in this section: You then modify the objects, depending on your network configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_IN1</p>         </td>
         <td><p>JMS Remote Site.</p>
<p>Sender only</p>
<p>Links to the Queue where CRISTAL put the request</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be configured.</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_OUT1</p>         </td>
         <td><p>JMS Remote Site.</p>
<p>Receiver only</p>
<p>Links to the Queue where Gateway put the OK response received from SSP</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be configured.</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_ERR1</p>         </td>
         <td><p>JMS Remote Site.</p>
<p>Receiver only</p>
<p>Links to the Queue where Gateway put its internal Error report</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be configured.</p>         </td>
      </tr>
      <tr>
         <td><p>CRISTAL_FILE1</p>         </td>
         <td><p>PeSIT remote Site.</p>
<p>Receiver only</p>
<p>The destination of the SSP answer when it is sent as a file.</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be configured.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Local and Remote Trading Partners</strong></p>
<p>You import the five Trading Partner objects listed in this section: You then modify the objects, setting the appropriate name, service and request type.</p>         </td>
      </tr>
      <tr>
         <td><p>QT2_TP_LOCAL1</p>         </td>
         <td><p>The local SWIFTNet Trading Partner.</p>
<ul>
<li>Alias: Use the BIC Code as alias.</li>
<li>Name: Use the DN name.</li>
<li>Direction allowed: update_tradepart -a [use the BIC Code as the alias] -dir_all B</li>
<li>Mode allowed: update_tradepart -a [use the BIC Code as the alias] -mod_all B</li>
</ul>         </td>
         <td><p>Provided in the packaging.</p>
<p>To be modified.</p>
<p>Use the BIC Code as the alias.</p>         </td>
      </tr>
      <tr>
         <td><p>QT2_TP_REMOTE_SSP</p>         </td>
         <td><p>Remote SWIFTNet Trading Partner for InterAct.</p>
<p>The Payload_Type Option must be set to embedded for the InterAct Trading Partner.</p>
<ul>
<li>Alias: Use the BIC Code as alias.</li>
<li>Name: use the DN name.</li>
<li>Service name: Use the appropriate service name InterAct.</li>
<li>Request type: Use the appropriate Request type.</li>
<li>Direction allowed: update_tradepart -a [use the BIC Code as the alias] -dir_all B</li>
<li>Mode allowed: update_tradepart -a [use the BIC Code as the alias] -mod_all B</li>
<li>Payload type option: peladm update_tradepart -a [use the BIC Code as alias]-pto embedded</li>
<li>Receipt request synchronized: update_tradepart -a [use the BIC Code as the alias] -rrs Y</li>
<li>…</li>
</ul>
<p><strong>Note:</strong> Make sure the Remote SSP partner is in pull-mode - if not: update_tradepart -a [your SWIFTNet remote Trading Partner -rrs Y:].</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>
<p>Use the BIC Code as the alias.</p>         </td>
      </tr>
      <tr>
         <td><p>QT2_TP_REMOTE_FILE_SSP</p>         </td>
         <td><p>Remote SWIFTNet Trading Partner for FileAct.</p>
<ul>
<li>Alias: Use the BIC Code as alias</li>
<li>Name: Use the DN name</li>
<li>Service name: Use the appropriate FileAct service name</li>
<li>Request type: Use the appropriate Request type</li>
<li>Receipt DN: Use the appropriate Receipt DN</li>
<li>Receipt request type: Use the appropriate request type.</li>
</ul>
<p><strong>Note:</strong> Make sure that the Request type of the Remote FILE SSP partner is set.</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>QT2_TP_REMOTE_SSP_TET</p>         </td>
         <td><p>SSP InterAct - Customer Test Environment</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>QT2_TP_REMOTE_FILE_SSP_TET</p>         </td>
         <td><p>SSP FileAct - Customer Test Environment</p>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Decision Rules</strong></p>
<p>You can optionally import any of the Decision Rule objects listed in this section: You then modify the objects, depending on you production requirements.</p>         </td>
      </tr>
      <tr>
         <td><p>FROM_BO_TO_SSP1</p>         </td>
         <td><p>Selects incoming requests received through the CRISTAL_IN Site to route them to the SSP via the Model FROM_BO_TO_SSP.</p>
<p>Selection criteria:</p>
<ul>
<li>mode = R (Responder)</li>
<li>direction =I (input)</li>
<li>originator alias = CRISTAL_IN1</li>
<li>property_RequestType # *xxx*</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>INCOMING_GETFILE_SSP1</p>         </td>
         <td><p>Selects the incoming TARGET2 files received from SSP through a Get FileAct, and routes them to CRISTAL via the script tg2file.sh/tg2file.bat. Uses TO_BO_QT2_FILE_OK1 TO_BO_QT2_FILEMSG_KO_P1 /home/swiftrdq/cristal/</p>
<p>Selection criteria:</p>
<ul>
<li>direction=I (input)</li>
<li>protocol=SWIFTNET</li>
<li>trade destination alias=QT2_TP_LOCAL1</li>
<li>trade service= trgt.*</li>
<li>type=TRANS (FileAct)</li>
<li>State= E or W (Ended or waiting for Ack)</li>
<li>userProcess=N</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>INCOMING_GETFILE_SSP_KO1</p>         </td>
         <td><p>Selects TARGET2 FileAct Get requests that failed and sends an error report to CRISTAL_err by directly invoking the Model TO_BO_QT2_FILEMSG_KO</p>
<p>Selection criteria:</p>
<ul>
<li>direction=I (input)</li>
<li>protocol=SWIFTNET</li>
<li>State=C or F or X (cancelled, frozen, NACKed)</li>
<li>trade destination alias=QT2_TP_LOCAL1</li>
<li>trade service= trgt.*</li>
<li>type=TRANS (FileAct)</li>
<li>userProcess=N</li>
</ul>         </td>
         <td><p>Not provided in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>INCOMING_SSP_IA_REQUEST1</p>         </td>
         <td><p>This is used only for Simulation.</p>
<p>Selects requests and routes them to the dedicated script ssp_pull_s.sh and lauches the Model FROM_BO_TO_SSP1.</p>
<p>Selection criteria:</p>
<ul>
<li>direction=I (Input)</li>
<li>mode=I (Responder)</li>
<li>protocol=SWIFTNET</li>
<li>state=W (Ended_to_ack)</li>
<li>type=MSG (InterAct)</li>
<li>userProcess=N</li>
</ul>         </td>
         <td><p>Provided in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>INCOMING_SSP_IA_RESPONSE1</p>         </td>
         <td><p>Selects the incoming answers received via an InterAct reception from the SSP, and routes them to the dedicated script tg2msg by using</p>
<p>TO_BO_QT2_OK TO_BO_QT2_FILEMSG_KO</p>
<p>Selection criteria:</p>
<ul>
<li>direction=I (input)</li>
<li>mode=R (Responder)</li>
<li>protocol=SWIFTNET</li>
<li>trade originator alias=QT2_TP_LOCAL1</li>
<li>trade service= trgt.*</li>
<li>type=MSG (InterAct)</li>
<li>state= E or C (Ended or Cancelled)</li>
<li>userProcess=N</li>
</ul>         </td>
         <td><p>Provided in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>OUTGOING_SSP_IA_REQ_KO1</p>         </td>
         <td><p>Selects outgoing InterAct requests that fail locally and automatically sends CRISTAL a report error via JMS. It launches the Model TO_BO_QT2_FILEMSG_KO.</p>
<p>Selection criteria:</p>
<ul>
<li>direction=O (output)</li>
<li>mode=I (Initiator)</li>
<li>protocol=SWIFTNET</li>
<li>State=C (cancelled)</li>
<li>trade originator alias=QT2_TP_LOCAL1</li>
<li>trade service= trgt.*</li>
<li>type=MSG (InterAct)</li>
<li>userProcess=N</li>
</ul>         </td>
         <td><p>Provided in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>TG2DIR_GETFILE_SSP1</p>         </td>
         <td><p>Selects the requests sent by CRISTAL to get the TARGET2 directory file and routes them to SSP through the TG2DIR_GETFILE_SSP Model, called by the tg2file script</p>
<p>Selection criteria:</p>
<ul>
<li>mode = R (Responder)</li>
<li>direction =I (input)</li>
<li>originator alias = CRISTAL_IN1</li>
<li>state=E</li>
<li>service=*xxx*</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>For retrieving files in the TARGET2 directory.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Models</strong></p>
<p>You can change the name of the Remote Site, and use the routing of your choice. Seven Models are available. They are provided in the package but must be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>FROM_BO_TO_SSP1</p>         </td>
         <td><p>Sends the Get Request received from CRISTAL to the SSP via InterAct. This Model sets the SWIFTNet transfer parameters by using the JMS transfer parameters including the JMS properties.</p>
<p>This Model is automatically activated by Gateway on reception of the CRISTAL JMS request</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT_A</li>
<li>dest_alias=[SWIFTNet Remote site]</li>
<li>direction=O (output)</li>
<li>file_component=&amp;(path_name)</li>
<li>mode=I (initiator)</li>
<li>org_alias=[Local Site]</li>
<li>param1=&amp;(property_RequestRef)</li>
<li>trade_dest_alias=&amp;(property_RemotePartner)</li>
<li>trade_org_alias=&amp;(property_LocalPartner)</li>
<li>trade_request_type=&amp;(property_RequestType)</li>
<li>trade_service=&amp;(property_Service)</li>
<li>type=MSG (InterACt)</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>TG2DIR_GETFILE_SSP1</p>         </td>
         <td><p>Gets the TARGET2 directory file via FileAct. This Model sets the SWIFTNet transfer parameters by using the JMS transf parameters.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT_A</li>
<li>dest_alias=[SWIFTNet Remote site]</li>
<li>direction=I (Input)</li>
<li>File_Name=&amp;(property_FileName)</li>
<li>mode=I (initiator)</li>
<li>org_alias=[Local Site]</li>
<li>param1=&amp;(property_RequestRef)</li>
<li>trade_dest_alias=&amp;(property_LocalPartner)</li>
<li>trade_org_alias=&amp;(property_RemotePartner)</li>
<li>trade_request_type=&amp;(property_RequestType)</li>
<li>trade_service=&amp;(property_Service)</li>
<li>type=TRANS (FileAct)</li>
</ul>         </td>
         <td><p>Provided in the package</p>
<p>For retrieving files in the TARGET2 directory.</p>         </td>
      </tr>
      <tr>
         <td><p>TO_BO_QT2_FILE_OK1</p>         </td>
         <td><p>Sends CRISTAL the final answer received from the SSP via a Get FileAct. It is called by the tg2file script through a peltrans command. The Model name and other parameters are passed in the peltrans command to set the transfer parameters that depend on the parameters of the initial Get FileAct request.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT</li>
<li>dest_alias=CRISTAL_FILE1</li>
<li>direction=O</li>
<li>property=BodyType=text</li>
<li>file_component=&amp;(path_name)</li>
<li>file name=QT2ANSW</li>
<li>mode=I</li>
<li>org_alias=[Local Site]</li>
<li>snd msg= &amp;(param1)</li>
<li>type=TRANS</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>TO_BO_QT2_FILEMSG_KO1</p>         </td>
         <td><p>Sends CRISTAL error reports related to failure of a TARGET2 Get request, or related to a local failure of a TARGET2 InterAct request. This Model sets the JMS transfer parameters by using the SWIFTNet transfer parameters.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT</li>
<li>dest_alias=CRISTAL_ERR1</li>
<li>direction=O (Output)</li>
<li>file_component=[ /swiftrdq/users/swiftrdq/Axway/qt2/ objExports\..\aupver]</li>
<li>property=LocalPartner=&amp;(trade_dest_alias)</li>
<li>property=RemotePartner=&amp;(trade_org_alias)</li>
<li>property=RequestType=&amp;(trade_request_type)</li>
<li>property=Service=&amp;(trade_service)</li>
<li>property=RequestRef=&amp;(param1)</li>
<li>property_ReportStatus=&amp;(last_end_diag)-&amp;(last_end_err)-&amp;(last_end_reason)</li>
<li>property=bodyType=string</li>
<li>mode=I</li>
<li>org_alias=[Local Site]</li>
<li>type=TRANS</li>
</ul>         </td>
         <td><p>Provided in the package</p>         </td>
      </tr>
      <tr>
         <td><p>TO_BO_QT2_FILEMSG_KO_P1</p>         </td>
         <td><p>Sends CRISTAL error reports related to failure of a TARGET2 Get request, or related to a local failure of a TARGET2 InterAct request. This Model sets the JMS transfer parameters by using the SWIFTNet transfer parameters.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT</li>
<li>dest_alias=CRISTAL_ERR1</li>
<li>direction=O (Output)</li>
<li>file_component[/swiftrdq/users/swiftrdq/Axway/qt2/ objExports\..\aupver]</li>
<li>property=bodyType=string</li>
<li>mode=I</li>
<li>org_alias=[Local Site]</li>
<li>type=TRANS</li>
</ul>         </td>
         <td><p>Provided in the package</p>         </td>
      </tr>
      <tr>
         <td><p>TO_BO_QT2_GETFILE_KO1</p>         </td>
         <td><p>Sends CRISTAL the final answer received from the SSP via a Get FileAct. It is called by the tg2file script through a peltrans command. The Model name and other parameters are passed in the peltrans command to set the transfer parameters that depend on the parameters of the initial Get FileAct request.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT</li>
<li>dest_alias=CRISTAL_ERR1</li>
<li>direction=O (Output)</li>
<li>file_component=[ /swiftrdq/users/swiftrdq/Axway/qt2/ objExports\..\aupver]</li>
<li>property=LocalPartner=&amp;(trade_dest_alias)</li>
<li>property=RemotePartner=&amp;(trade_org_alias)</li>
<li>property=RequestType=&amp;(trade_request_type)</li>
<li>property=Service=&amp;(trade_service)</li>
<li>property=RequestRef=&amp;(param1)</li>
<li>property_ReportStatus=&amp;(last_end_diag)-&amp;(last_end_err)-&amp;(last_end_reason)</li>
<li>property=bodyType=string</li>
<li>mode=I</li>
<li>org_alias=[Local Site]</li>
<li>type=TRANS</li>
</ul>         </td>
         <td><p>Provided in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>TO_BO_QT2_OK1</p>         </td>
         <td><p>Sends to CRISTAL the final answer received from the SSP through InterAct. This model sets the default JMS transfer parameters. It is called by the tg2msg script through a peltrans command. Model name and other parameters are passed in the peltrans command in order to set the transfer parameters that depend on the parameters of the initial Get InterAct request.</p>
<p>Model parameters:</p>
<ul>
<li>appli=DEFAULT</li>
<li>dest_alias=CRISTAL_OUT1</li>
<li>direction=O (Output)</li>
<li>&amp;(path_name)</li>
<li>property=bodyType=string</li>
<li>mode=I</li>
<li>org_alias=[Local Site]</li>
<li>type=TRANS</li>
</ul>         </td>
         <td><p>Provided in the package.</p>
<p>To be modified.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Scripts</strong></p>
<p>The following scripts are provided in the package and must be modified.</p>         </td>
      </tr>
      <tr>
         <td><p>tg2msg</p>         </td>
         <td><p>Launched by the INCOMING_SSP_IA_RESPONSE Decision Rule to process the answers returned by the SSP via a Get InterAct.</p>         </td>
         <td><p>Provided in the package</p>
<p>To modify, add the Initial transfer parameters to the peltrans commands</p>         </td>
      </tr>
      <tr>
         <td><p>Tg2file</p>         </td>
         <td><p>Launched by the Decision Rule INCOMING_GETFILE_SSP to process the answers returned by the SS via a Get FileAct.</p>         </td>
         <td><p>Provided in the package</p>
<p>To modify, add the Initial transfer parameters to the peltrans commands</p>         </td>
      </tr>
      <tr>
         <td><p>ssp_pull</p>         </td>
         <td><p>Launched by the Decision Rule INCOMING_SSP_IA_REQUEST to simulate a request to the SSP by using the Model FROM_BO_TO_SSP.</p>         </td>
         <td><p>Provided in the package</p>
<p>To modify, add the Initial transfer parameters to the peltrans commands</p>         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
