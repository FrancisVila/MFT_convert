{
    "title": "STFS PeSIT related EL for AR ",
    "linkTitle": "STFS PeSIT related EL for AR",
    "weight": "330"
}The following table provides the STFS PeSIT related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Agent Env Variable</p>         </th>
<th class="HeadE-Column1-Header1"><p>Routing EL expression</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>pesitPIEnvVariables</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_senderID</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_senderID']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_senderID']}</p>         </td>
         <td><p>Provides the sender identification parameter in the message body.</p>
<ul>
<li><p>Example:</p></li>
</ul>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_senderID'] eq 'PARTNER-PESIT'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_recordLength</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordLength']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_recordLength']}</p>         </td>
         <td><p>Provides the record length parameter in the message body.</p>
<ul>
<li><p>Example:</p></li>
</ul>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordLength'] eq '2048'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_allocationUnit</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_allocationUnit']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_allocationUnit']}</p>         </td>
         <td><p>Provides the allocation unit parameter in the message body.</p>
<ul>
<li><p>Example:</p></li>
</ul>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_allocationUnit'] eq '0'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileName</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_fileName']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_fileName']}</p>         </td>
         <td><p>Provides the file name parameter in the message body.</p>
<ul>
<li><p>Example:</p></li>
</ul>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_fileName'].matches('IDF.*')}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_serviceParam</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_serviceParam']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_serviceParam']}</p>         </td>
         <td><p>Provides the service parameter in the message body.</p>
<p><em>Examples:</em></p>
<ul>
<li><p><em>No PI99</em></p></li>
</ul>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_serviceParam'] eq null}</code></p>
<ul>
<li><p>With PI99</p></li>
</ul>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_serviceParam'].matches('AloAlo')}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_receiverID</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_receiverID']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_receiverID']}</p>         </td>
         <td><p>Provides the receiver identification parameter in the message body.</p>
<p><em>Examples:</em></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_receiverID'] eq 'U1'}</code></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_receiverID'].matches('U.*')} </code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_priority</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_priority']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_priority']}</p>         </td>
         <td><p>Provides the priority parameter in the message body.</p>
<p><em>Examples:</em></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_priority']}</code> - will be evaluated to {1} which is the priority value</p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_priority']==1}</code> - will be evaluated to true</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_dataEncoding</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_dataEncoding']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_dataEncoding']}</p>         </td>
         <td><p>Provides the data encoding parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_dataEncoding'] eq '1'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_recordFormat</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordFormat']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_recordFormat']}</p>         </td>
         <td><p>Provides the record format parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordFormat']==0}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileLabel</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_fileLabel']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_fileLabel']}</p>         </td>
         <td><p>Provides the file label parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_fileLabel'].matches('file.*')}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_originalSenderID</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_originalSenderID']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_originalSenderID']}</p>         </td>
         <td><p>Provides the original sender identification parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_originalSenderID'] eq null}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_finalDestinationID</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_finalDestinationID']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_finalD<span class="code">e</span>stinationID']}</p>         </td>
         <td><p>Provides the final destination identification parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_finalDestinationID'] eq null}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_creationDateTime</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_creationDateTime']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_creationDateTime']}</p>         </td>
         <td><p>Provides the creation date and time parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_creationDateTime'] gt '140611093656'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_transferID</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_transferID']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_transferID']}</p>         </td>
         <td><p>Provides the transfer identification parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${!empty stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_transferID']}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_compressionType</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_compressionType']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_compressionType']}</p>         </td>
         <td><p>Provides the compression type parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_compressionType']==3}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_exchangeBufferSize</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_exchangeBufferSize']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_exchangeBufferSize']}</p>         </td>
         <td><p>Provides the exchange buffer size parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_exchangeBufferSize'] lt '8192'}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_recordLength</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordLength']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_recordLength']}</p>         </td>
         <td><p>Provides the record length parameter in the message body.</p>
<p><em>Example:</em></p>
<p><code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordLength'] &lt; 512}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PESIT_PI_fileOrganization</p>         </td>
         <td><p>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_recordLength']}</p>
<p>${stfs.attributes['pesitPIEnvVariables']['DXAGENT_PESIT_PI_recordLength']}</p>         </td>
         <td><p>Provides the file organization parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes.pesitPIEnvVariables['DXAGENT_PESIT_PI_fileOrganization'] eq '0'}</code>         </td>
      </tr>
      <tr>
         <td><code>recordsLength</code>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td><p>${stfs.attributes.recordsLength}</p>
<p>${stfs.attributes['recordsLength']}</p>         </td>
         <td><p>Provides the record length parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes['recordsLength'].matches('[I@.*')}</code>         </td>
      </tr>
      <tr>
         <td><code>endOfLineSymbol</code>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>${stfs.attributes.endOfLineSymbol}</p>
<p>${stfs.attributes['endOfLineSymbol']}</p>         </td>
         <td><p>Provides the end of line symbol parameter in the message body.</p>
<p><em>Example:</em></p>
<code>${stfs.attributes['endOfLineSymbol'].matches('n.*')} </code>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
