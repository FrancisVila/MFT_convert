{
    "title": "System to Human transfer sites",
    "linkTitle": "System to Human transfer sites",
    "weight": "270"
}You can use a System to Human transfer site to send files to email recipients. {{< SecureTransport/componentshortname  >}} sends a notification email to the recipients from the email address specified in the **Email Contact** field of the user settings. If the email is not set, {{< SecureTransport/componentshortname  >}} does not send the notification email and logs an error.

A recipient of a notification email retrieves the file based on the security level specified. In some cases, the recipient clicks a link in the notification email to retrieve the file. In other words, the recipient must log in to ST Web Client or one of the {{< SecureTransport/companyname  >}} Email Plug-ins and the user logs in to {{< SecureTransport/componentshortname  >}} to retrieve the files. The notification email is from the email address specified in the **Email Contact** field of the user settings. If the email is not set, the If the security level allows, {{< SecureTransport/componentshortname  >}} enrolls the user, creating an account.

You can use hardcoded values, expressions in the supported expression language, or a
combination of both to complete the fields indicated by a vertical yellow bar. For more information about expressions, see <a href="../../../c_st_expressionlanguage" class="MCXref xref">Expression Language</a>.

The following table describes the System to Human options for a transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Delivery Method         </td>
         <td><p>Controls user enrollment:</p>
<ul>
<li><strong>Anonymous</strong> – The recipient clicks a link in the email and can retrieve the files.</li>
<li><strong>Challenge</strong> – When the recipient clicks the link in the email to retrieve the files, the recipient must answer a secret question correctly.</li>
<li><strong>Existing Account</strong> – The recipient must have a {{< SecureTransport/componentshortname  >}} accounts.</li>
<li><strong>Enroll Unlicensed</strong> – {{< SecureTransport/componentshortname  >}} enrolls the recipient as an unlicensed user, if necessary.</li>
<li><strong>Enroll Licensed</strong> – {{< SecureTransport/componentshortname  >}} enrolls the recipients as licensed users, if necessary.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Secret Question         </td>
         <td>This field is displayed when the <strong>Delivery Method</strong> is <code>Challenge</code>. Type the question that the email recipient must answer to retrieve the files.         </td>
      </tr>
      <tr>
         <td>Answer<br />
Re-enter Answer         </td>
         <td>These fields are displayed when the <strong>Delivery Method</strong> is <code>Challenge</code>. Type the answer to the question.         </td>
      </tr>
      <tr>
         <td>Email Notification Template         </td>
         <td>Select <code>Default</code> or an email template that {{< SecureTransport/componentshortname  >}} uses to compose the file transfer notification and status emails. You specify the email templates on the <em>Mail Template Repository</em> page. You specify the default email notification template on the <em>AdHoc Settings</em> page.         </td>
      </tr>
      <tr>
         <td>Expiration Interval         </td>
         <td>The number of days before the message expires. The choices are: 1 Day, 7 Days, 30 Days, 60
Days, and Never.         </td>
      </tr>
      <tr>
         <td>To         </td>
         <td>Type values that can include expressions for the email addresses of the main recipients. Use a semicolon (<code>;</code>) to separate email addresses.         </td>
      </tr>
      <tr>
         <td>Cc         </td>
         <td>Type values that can include expressions for the email addresses of the copy recipients. Use a semicolon (<code>;</code>) to separate email addresses.         </td>
      </tr>
      <tr>
         <td>Bcc         </td>
         <td>Type values that can include expressions for the email addresses of the blind copy recipients. Use a semicolon (<code>;</code>) to separate email addresses.         </td>
      </tr>
      <tr>
         <td>Subject         </td>
         <td>Type a value that can include expressions for the subject of the file transfer emails.         </td>
      </tr>
      <tr>
         <td>Text         </td>
         <td>In the unlabeled email body field, type a value that can include expressions for the text of the notification emails.         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td><p>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name.</p>
<p>For example, when a file arrives in a H2S file transfer, {{< SecureTransport/componentshortname  >}} renames the file by prepending a unique ID to the file name. If the file it routed to an H2S transfer site to forward it, the expression, <code>${stenv.target.replace('^.{66}', '')}</code>, removes the ID.</p>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>
