{
    "title": "PeSIT related EL for AR",
    "linkTitle": "PeSIT related EL for AR",
    "weight": "300"
}The following table provides the PeSIT related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Agent Env Variable         </th>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_DESTINATION</p>         </td>
         <td><p>pesit.file.destination</p>         </td>
         <td><p>Provides the file destination.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_FILENAME</p>         </td>
         <td><p>pesit.file.filename</p>         </td>
         <td>Provides the file name.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_ORIGINATOR</p>         </td>
         <td><p>pesit.file.originator</p>         </td>
         <td><p>Provides the originator of the file.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_RECEIVER</p>         </td>
         <td><p>pesit.file.receiver</p>         </td>
         <td><p>Provides the receiver for the file.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_SENDER</p>         </td>
         <td><p>pesit.file.sender</p>         </td>
         <td><p>Provides the sender of the file.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_FILETYPE</p>         </td>
         <td><p>pesit.file.filetype</p>         </td>
         <td><p>Provides a description of the file type.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_FILE_TRANSFERID</p>         </td>
         <td><p>pesit.file.transferID</p>         </td>
         <td><p>Provides the transfer ID of the file.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_CRC</p>         </td>
         <td><p>pesit.pi.crc</p>         </td>
         <td><p>Provides the cyclic redundancy check (CRC) parameters in the message body.</p>
<p>Example:</p>
<p>Outgoing</p>
<p><code>${!pesit.pi.crc}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_DIAGCODE</p>         </td>
         <td><p>pesit.pi.diagCode</p>         </td>
         <td><p>Provides the diagnostic code parameters in the message body.</p>
<p>Example:</p>
<p>Outgoing</p>
<p><code>${pesit.pi.callerID.toLowerCase() eq account.user.loginName}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_senderID</p>         </td>
         <td><p>pesit.pi.senderID</p>         </td>
         <td><p>Provides the sender identification parameters in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.senderID.toLowerCase() eq 'target'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_receiverID</p>         </td>
         <td><p>pesit.pi.receiverID</p>         </td>
         <td><p>Provides the receiver identification parameters in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.receiverID.toLowerCase() eq account.name}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_callerPassword</p>         </td>
         <td><p>pesit.pi.<br />
callerPassword</p>         </td>
         <td>Provides the caller password parameters in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_serverPassword</p>         </td>
         <td><p>pesit.pi.<br />
serverPassword</p>         </td>
         <td>Provides the server password parameters in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_version</p>         </td>
         <td><p>pesit.pi.version</p>         </td>
         <td><p>Provides the version parametes in the message body.</p>
<p>Example:</p>
<p>Outgoing</p>
<p><code>${pesit.pi.version == 2}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_exchangeBufferSize</p>         </td>
         <td><p>pesit.pi.<br />
exchangeBufferSize</p>         </td>
         <td><p>Provides the exchange buffer size parameters in the message body.</p>
<p>Example:</p>
<code>${!empty pesit.pi.exchangeBufferSize}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_totalRecords</p>         </td>
         <td><p>pesit.pi.totalRecords</p>         </td>
         <td>Provides the number of total records parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_file<br />
Organization</p>         </td>
         <td><p>pesit.pi.<br />
fileOrganization</p>         </td>
         <td><p>Provides the file organization parameter in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.fileOrganization == 0}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_recordLength</p>         </td>
         <td><p>pesit.pi.recordLength</p>         </td>
         <td><p>Provides the record length parameter in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.recordLength == 2048}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_keyLength</p>         </td>
         <td><p>pesit.pi.keyLength</p>         </td>
         <td>Provides the key length parameter in the message body         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_allocationUnit</p>         </td>
         <td><p>pesit.pi.<br />
allocationUnit</p>         </td>
         <td><p>Provides the number of allocation units parameter in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.allocationUnit == 0}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_creationDateTime</p>         </td>
         <td><p>pesit.pi.<br />
creationDateTime</p>         </td>
         <td><p>Provides the creation date and time parameter in the message body.</p>
<p>Example:</p>
<code>${!empty pesit.pi.creationDateTime}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_originalSenderID</p>         </td>
         <td><p>pesit.pi.<br />
originalSenderID</p>         </td>
         <td><p>Provides the original sender identification parameter in the message body.</p>
<p><em>Example:</em></p>
<p>Store</p>
<p><code>${pesit.pi.originalSenderID eq 'CFT1'} </code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_msgData</p>         </td>
         <td><p>pesit.pi.msgData</p>         </td>
         <td>Provides the message data parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_checkPoint<br />
Interval</p>         </td>
         <td><p>pesit.pi.<br />
checkPointInterval</p>         </td>
         <td><p>Provides the check point interval parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.checkPointInterval == 1024}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_checkPoint<br />
Window</p>         </td>
         <td><p>pesit.pi.<br />
checkPointWindow</p>         </td>
         <td><p>Provides the check point window parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.checkPointWindow == 4}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileType</p>         </td>
         <td><p>pesit.pi.fileType</p>         </td>
         <td><p>Provides the file type parameter in the message body.</p>
<p>Example:</p>
<p><code>${pesit.pi.fileType == 0}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileName</p>         </td>
         <td><p>pesit.pi.fileName</p>         </td>
         <td><p>Provides the file name parameter in the message body.</p>
<p>Example:</p>
<p><code>${pesit.pi.fileName.toLowerCase() eq 'idf'}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_transferID</p>         </td>
         <td><p>pesit.pi.transferID</p>         </td>
         <td><p>Provides the transfer identification parameter in the message body.</p>
<p>Example:</p>
<code>${!empty pesit.pi.transferID}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileAttributes</p>         </td>
         <td><p>pesit.pi.<br />
fileAttributes</p>         </td>
         <td>Provides the file attributes parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_restart</p>         </td>
         <td><p>pesit.pi.restart</p>         </td>
         <td><p>Provides the restart parameter in the message body.</p>
<p><em>Example:</em></p>
<p>Outgoing</p>
<p><code>${!pesit.pi.restart}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_dataEncoding</p>         </td>
         <td><p>pesit.pi.dataEncoding</p>         </td>
         <td><p>Provides the data encoding parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${pesit.pi.dataEncoding lt 3}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_priority</p>         </td>
         <td><p>pesit.pi.priority</p>         </td>
         <td><p>Provides the priority parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.priority == 1}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_restartCheckPoint</p>         </td>
         <td><p>pesit.pi.<br />
restartCheckPoint</p>         </td>
         <td>Provides the restart check point parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_cancelCode</p>         </td>
         <td><p>pesit.pi.cancelCode</p>         </td>
         <td>Provides the cancel code parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_checkPoint<br />
Number</p>         </td>
         <td><p>pesit.pi.<br />
checkPointNumber</p>         </td>
         <td>Provides the check point number parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_compressed</p>         </td>
         <td><p>pesit.pi.compressed</p>         </td>
         <td><p>Provides the compression parameter in the message body.</p>
<p><em>Example:</em></p>
<p>Outgoing</p>
<p><code>${!pesit.pi.compressed}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_compression<br />
Type</p>         </td>
         <td><p>pesit.pi.<br />
compressionType</p>         </td>
         <td><p>Provides the compression type parameter in the message body.</p>
<p>Example:</p>
<code>${pesit.pi.compressionType eq 3}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_accessType</p>         </td>
         <td><p>pesit.pi.accessType</p>         </td>
         <td>Provides the access type parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_resyncAllowed</p>         </td>
         <td><p>pesit.pi.resyncAllowed</p>         </td>
         <td><p>Provides the resync allowed parameter in the message body.</p>
<p><em>Example:</em></p>
<p>Outgoing</p>
<p><code>${pesit.pi.resyncAllowed == 0}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_totalBytes</p>         </td>
         <td><p>pesit.pi.totalBytes</p>         </td>
         <td>Provides the total bytes parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_diagnosticText</p>         </td>
         <td><p>pesit.pi.<br />
diagnosticText</p>         </td>
         <td>Provides the diagnostic text parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_recordFormat</p>         </td>
         <td><p>pesit.pi.recordFormat</p>         </td>
         <td><p>Provides the record format parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.recordFormat eq 128}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileLabel</p>         </td>
         <td><p>pesit.pi.fileLabel</p>         </td>
         <td><p>Provides the file label parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${pesit.pi.fileLabel eq transfer.target}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_keyOffset</p>         </td>
         <td><p>pesit.pi.keyOffset</p>         </td>
         <td>Provides the key offset parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_allocationSize</p>         </td>
         <td><p>pesit.pi.<br />
allocationSize</p>         </td>
         <td><p>Provides the allocation size parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.allocationSize == 195}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_extractionDateTime</p>         </td>
         <td><p>pesit.pi.<br />
extractionDateTime</p>         </td>
         <td>Provides the extraction date and time parameter in the message body.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_final<br />
DestinationID</p>         </td>
         <td><p>pesit.pi.<br />
finalDestinationID</p>         </td>
         <td><p>Provides the final destination identification parameter in the message body.</p>
<p><em>Example:</em></p>
<p>Store and Forward</p>
<p><code>${pesit.pi.finalDestinationID eq 'CFT2'} </code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_serviceParam</p>         </td>
         <td><p>pesit.pi.serviceParam</p>         </td>
         <td><p>Provides the service parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${pesit.pi.serviceParam eq 'X'}</code></p>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
