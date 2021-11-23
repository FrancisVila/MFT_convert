{
    "title": "Processing email after retrieval",
    "linkTitle": "Processing email after retrieval",
    "weight": "290"
}{{< Gateway/componentlongname  >}}: Protocols

<span id="Mapping_and_mailbox_fields"></span>

## Mapping the Mailbox fields

Gateway extracts parameters (`DEST`, `ORG`, `APPLI`) from the subject (`//XFB`) if **Attach file / Extract file** in the Application or the Remote Site object is set to *Yes*.

<span id="Identifying_the_email"></span>

### Identifying an email

The **message-id** field identifies the email. Each message identifier must be unique as Gateway rejects any email whose message identifier corresponds to that of an email already received.

If the **message-id** field is missing, Gateway generates a hash on the fields **From**, **To**, **Orig-date**, **Subject** and **Cc**, and uses this as the message-id.

<span id="Processing_the_different_email_types"></span>

### Processing different email types

Gateway processes the various email formats as described in the following table:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Email type</p>         </td>
         <td><p>Gateway treatment</p>         </td>
      </tr>
      <tr>
         <td><p><strong>XFER</strong> Single attached file</p>         </td>
         <td><p>Processes the body of the message, as a user message that accompanies the transfer. The attachment is considered to be the <strong>file</strong> transferred. Gateway extracts, decodes and saves the attached file in a physical file, disregarding all other elements.</p>
<p>Gateway decodes and saves only the content of the email.</p>
<p>If a technical error occurs during processing, Gateway:</p>
<ul>
<li>assigns <em>Canceled</em> status to the Transfer Record, if it is already created</li>
<li>ignores the email, but does not delete it from the POP3 server</li>
<li>processes the next email</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Multiple attached files</p>         </td>
         <td><p>Rejects</p>         </td>
      </tr>
      <tr>
         <td><p><strong>MSG</strong> No attached files</p>         </td>
         <td><p>Extracts and decodes the body of the message. If the message is less than 254 characters in length, Gateway stores the message in the request itself. Otherwise, it saves the message in a physical file.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>extract_file=</strong><em>no</em></p>         </td>
         <td><p>Saves the entire email (header and the content), without decoding it. Gateway updates the request in question at the end of the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>DNS/MDN</p>         </td>
         <td><p>Since Gateway only supports POP3 and SMTP in client mode, the acknowledgement mechanism for these protocols is different from that used for other protocols. When Gateway sends an acknowledgement in SMTP, the notification is received in POP3.</p>
<p>Gateway extracts each notification and updates the corresponding SMTP transfer records in the Mailbox.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
