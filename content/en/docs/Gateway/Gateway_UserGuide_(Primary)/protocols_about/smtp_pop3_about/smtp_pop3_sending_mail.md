{
    "title": "SMTP/POP3: sending an email",
    "linkTitle": "Sending email SMTP/POP3",
    "weight": "260"
}{{< Gateway/componentlongname  >}}: Protocols

[Creating an SMTP transfer](#creating_smtp_transfer)

[Sending an acknowledgement (EERP) message](#sending_ack_eerp_message)

[Resuming a transfer](#resuming_transfer)

[Supported SMTP extensions](#supported_smtp_extensions)

<span id="creating_smtp_transfer"></span>

## Creating an SMTP transfer

Gateway sends email-type transfers in the same way as file transfers via any of the other Gateway protocols. To send an email, you must create a Transfer Request. Refer to [Managing Transfers](../../../transfers_start_here).

<span id="Managing_recipient_addresses"></span>

### Managing recipient addresses

#### Recipients list

You can specify either a single recipient or a *list of recipients* with an email. This list comprises:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Recipient</p>         </td>
         <td><p>Field</p>         </td>
      </tr>
      <tr>
         <td><p>Direct</p>         </td>
         <td><p>To</p>         </td>
      </tr>
      <tr>
         <td><p>Copied</p>         </td>
         <td><p>Cc</p>         </td>
      </tr>
      <tr>
         <td><p>Blind copy</p>         </td>
         <td><p>Bcc</p>         </td>
      </tr>
   </tbody>
</table>

**Note:** If you do not define a recipient, by default Gateway uses the email address of the Remote Site that represents the SMTP server. Recipients defined in the Transfer Request overwrite this default address. Where no recipient is defined in either the Site or the Transfer Request, the transfer is rejected and an error is logged.

#### Multiple email recipients

Unlike the Gateway <span style="font-style: italic;">Diffusion List</span>, SMTP allows you to send the same message to several recipients while physically sending the email only once to the server. Only one Mailbox record is created to monitor the SMTP send operation. This record contains the list of recipients and the acknowledgement counters (positive/negative) in the overflow zone.

#### Return address

You can also specify the return address (**From**) in the transfer. In the absence of a return address, Gateway uses the email address of the Local Site associated with the Remote Site.

<span style="font-weight: bold;">Note:</span> If neither of these addresses is defined, the transfer is rejected and an error is logged.

#### Address field length

The transfer record length is limited to 128 characters for each field (To, Cc, Bcc). If the field is insufficient to contain the corresponding list, Gateway completes the field with asterisks (**\***) and the value is stored in the overflow zone in the Mailbox record.

<span id="Completing_the_Subject_field"></span>

### Completing the Subject field

In addition to the email <span style="font-weight: bold;">Subject</span> field, you can specify additional details in the <span style="font-weight: bold;">Add Gateway parameters to subject</span> field.

When you complete the <span style="font-weight: bold;">Subject</span> field via online commands, enclose the subject value in quotation marks (").

#### Adding Gateway parameters to the subject

You can define and transmit specific Gateway parameters (**Application**, **Origin** and **Destination**) in the MIME header Subject field when transferring an unformatted email (**Attach file** **= Yes**).

<span style="font-weight: bold;">Note:</span> When Gateway sends a pre-formatted email (**Attach file = No**), it does not use the **Subject** parameter and so does not take into account the values set for either the **Subject** or the <span style="font-weight: bold;">Add Gateway parameters to subject</span><span class="code"> (-gxs)</span> parameters.

When you send an unformatted email via a Gateway Transfer Request, you can add parameters in the **Subject** field either manually or automatically when Gateway creates the email or the user message. The table below indicates the values to set for each field.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Add Gateway parameters to subject <span class="code">(-gxs)</span></p>         </td>
         <td><p>Subject</p>         </td>
      </tr>
      <tr>
         <td><p>Manual</p>         </td>
         <td><p>No</p>         </td>
         <td><p>Subject: <span class="code">//XFB appli=appliName; ORG=orgId; DEST=destId</span></p>         </td>
      </tr>
      <tr>
         <td><p>Automatic</p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>Leave empty</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Completing_the_attach_file_field"></span>

### Completing the **Attach file** field

You can set the value for the **Attach file** parameter in these Gateway objects (taken into account in the following order of precedence):

-   Transfer Request
-   Application associated with the Transfer Request
-   Model used to deposit the Transfer Request
-   Site

If the values of all these parameters are undefined, the default value will be that of the **Attach file** parameter of the Remote Site.

### Sending a pre-formatted email (**Attach file** = *No*)

Setting the **Attach file** to *No* indicates that the file transmitted is already formatted as an email. This functionality allows Gateway to act as an SMTP connector, transferring an email from an SMTP client to an SMTP server.

When Gateway sends a pre-formatted email, it does not modify the email that it is sending. Consequently:

-   Gateway does not use the **Subject** parameter. It therefore cannot add transfer attributes to the **Subject** field. The <span style="font-weight: bold;">Add Gateway parameters to subject</span><span class="code"> (-gxs)</span> parameter is set to *No* or *Undefined.*
-   You cannot request an application acknowledgement (MDN). The source application is responsible for sending the MDN. If the acknowledgement option is set to *TO\_ACK*, only the SMTP protocol acknowledgement (DSN) is requested.
-   You must specify the origin and destination addresses in the Transfer or Remote Site, since the deposited file is not parsed.
-   Gateway does not add the fields **To**, **Cc** and **Bcc** to the email. However, the SMTP protocol will use these fields to define the destination mailboxes. Only the **To** field is mandatory.

<span style="font-weight: bold;">Note:</span> If the **Attach file / Extract file** parameter is set to *No,* all the parameters except **To:** and **From:** in the new Transfer Request become unavailable.

<span id="Sending_a_file_and_a_user_message"></span>

### Sending a file and a user message (**Attach file** = Yes)

When you send a file that is not formatted as an email, Gateway:

-   Creates the email (the user message)
-   Attaches the file to the email

To send a file as an attachment to an email, set the **Attach file** attribute of the transfer to *Yes*.

Use the parameters in the following table to send a file by email (as a user message with an email attachment).

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>Required value</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer type</p>
<p>(<strong>-type</strong>)</p>         </td>
         <td><p>TRANS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Attach file / Extract file</p>
<p>(<span class="code">-<strong>attach_file</strong></span>)</p>         </td>
         <td><p>yes</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Remote Site</p>
<p>(<span class="code">-<strong>remote_agent</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Site used to connect to the SMTP server. If no Site is defined, the default SMTP Site is used. (Refer to <a href="../smtp_config#Defining_Remote_Site">Defining a Remote Site (-remote_agent)</a> for more information.)</p>         </td>
      </tr>
      <tr>
         <td><p>File</p>
<p>(<strong>-file_component</strong>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>File to attach to the email</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>
<p>(<span class="code">-<strong>appli</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Application to use for reading this file</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol file name</p>
<p>(<span class="code">-<strong>file_name</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Name to assign to the file that you send</p>         </td>
      </tr>
      <tr>
         <td><p>Recipients</p>
<p>(<strong>-to</strong>, <strong><span class="code">-cc</span></strong>, <strong>-bcc</strong>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>If no recipient is defined on creation of the transfer, the electronic address of the Remote Site (representing the SMTP server) is used as the unique destination address</p>         </td>
      </tr>
      <tr>
         <td><p>Originating address</p>
<p>(<strong>-from</strong>)</p>         </td>
         <td><p> </p>         </td>
         <td><p>If no address is defined when you create the transfer, the electronic address of the Local Site associated with the Remote Site is used.</p>         </td>
      </tr>
      <tr>
         <td><p>Email subject</p>
<p>(<span class="code">-<strong>mail_subject</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>application</p>
<p>(<span class="code">-<strong>appli</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>(<span class="code">-<strong>generate_xfb_subject</strong></span>)</p>
<p>destination (<span class="code">-<strong>dest</strong></span>)</p>
<p>origin (<span class="code">-<strong>org</strong></span>)</p>         </td>
         <td><p>Y</p>         </td>
         <td><p>Additional transfer attributes to add to the email subject</p>         </td>
      </tr>
      <tr>
         <td><p>Acknowledgement request</p>
<p>(<span class="code">-<strong>acknowledgment_option</strong></span>)</p>         </td>
         <td><p>=TO_ACK</p>         </td>
         <td><p>Request for application (MDN) and protocol (DSN) acknowledgments</p>         </td>
      </tr>
      <tr>
         <td><p>User message</p>
<p>(<span class="code">-<strong>snd_msg</strong></span>)</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Sending_a_user_message__MSG_"></span>

### Sending a user message (MSG)

Use the same syntax and parameters as described in [Sending a file and a user message](#Sending_a_file_and_a_user_message), modifying the following values:

-   Set the transfer type (<span class="code" style="font-weight: bold;">-type</span>) to *MSG*
-   Do not define a file (<span class="code" style="font-weight: bold;">-file\_component</span>)

<span id="sending_ack_eerp_message"></span>

## Sending an acknowledgment (EERP) message

An acknowledgment is an email sent to indicate whether a file was received successfully or with errors. To send an acknowledgment in SMTP, the acknowledgment must be linked to a received email (a POP3 transfer).

The acknowledgments you can send are application type (MDN) acknowledgments. Since Gateway is not an SMTP server, the last SMTP server that receives the email must manage the acknowledgments.

To send an acknowledgement via the GUI:

1.  Identify the transfer that you want to acknowledge.
2.  Right-click **Transfer** in the left pane and select **Ack a transfer** from the context menu.
3.  Complete the **Transfer Id to ack** field with the Transfer identifier.

To send an acknowledgement using the <span class="code" style="font-weight: bold;">peltrans</span> online command, use the following parameters:

-   Transfer type (<span class="code">-type</span>): EERP
-   POP3 transfer identifier to acknowledge (<span class="code">-reply\_to</span>)
-   Acknowledgement type: positive (<span class="code">-nack\_option=NO</span>) or negative (<span class="code">-nack\_option=YES</span>)
-   SMTP Site to use: destination alias (<span class="code">-dest</span>)

For syntax details, refer to [Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list).

When Gateway sends the transfer, the acknowledgement is created automatically and sent to the return acknowledgement address indicated on the selected transfer (the <span class="code">-ack\_to</span> field of the POP3 transfer).

<span id="resuming_transfer"></span>

## Resuming a transfer

SMTP and POP3 do not support the resumption of interrupted transfers. Where an incomplete transfer is recommenced, Gateway restarts from the beginning of the file.

<span id="supported_smtp_extensions"></span>

## Supported SMTP extensions

The following table summarizes the SMTP extensions supported in Gateway:

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Extensions</p>         </td>
         <td><p>Syntax</p>         </td>
         <td><p>Description</p>         </td>
         <td><p>Supported by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>DSN</p>         </td>
         <td><p>RET= ENVID= ORCPT= NOTIFY=</p>         </td>
         <td><p>Send a request for protocol acknowledgement</p>         </td>
         <td><p>X</p>         </td>
      </tr>
      <tr>
         <td><p>SIZE</p>         </td>
         <td><p>SIZE=000</p>         </td>
         <td><p>Pre-allocation</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>STARTTLS</p>         </td>
         <td><p>STARTTLS</p>         </td>
         <td><p>TLS implementation</p>         </td>
         <td><p>X</p>         </td>
      </tr>
      <tr>
         <td><p>AUTH</p>         </td>
         <td><p>AUTH (SASL)</p>         </td>
         <td><p>Identification mechanisms</p>         </td>
         <td><p>X</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>CHECKPOINT</p>         </td>
         <td><p>Resuming a transfer</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>DELIVERBY</p>         </td>
         <td><p>Requesting a transfer within a specified time period</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
