{
    "title": "Defining Decision Rule conditions",
    "linkTitle": "Defining Decision Rule conditions",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[About Decision Rule conditions](#About)

[Condition parameters](#Condition_parameters)

[Operators](#Operators)

[SMTP values in Decision Rule conditions](#SMTP_values_in_Decision_Rule_conditions)

[Completing the Value field](#Completing_the_Value_field)

[Using symbolic variables](#Using_symbolic_variables)

[Using user functions](#Using_user_functions)

[Case-insensitive conditions](#Case_insensitive_conditions)

<span id="About"></span>

## About Decision Rule conditions

Each Decision Rule condition that you define is an expression that comprises:

-   <span style="font-weight: bold;">Argument</span>: To complete the Argument component of an expression, click the arrow on the <span style="font-weight: bold;">Argument</span> selection box and then select an argument from the drop-down list. The arguments displayed vary according to the type of Decision Rule you are creating or modifying, and, in the case of Transfers, the type of Transfer. The list contents vary to take into account, for example:
    -   The CGate selected on input
    -   The use of a VFD
    -   A transfer via an Axway Messaging connector

      
    Argument values in Decision Rules can comprise a combination of string values, user functions and [symbolic variables](#Using_symbolic_variables). User functions can also be called inside one another, as long as the returned values are compatible with the argument expected in the upper function.  
    This substitution mechanism applies to:
    -   Model names, when the selected <span style="font-weight: bold;">Execution type</span> is <span style="font-weight: bold;">Model</span>
    -   Directory paths and file patterns in the Trading Partner configuration

      
    <span style="font-weight: bold;">Note:</span> The number of functions you can nest is limited.  
    The complete list of possible values for non-XMS (Axway Messaging) events is provided in [Condition parameters](#Condition_parameters) below. In the case of Axway Messaging, the attribute list is derived dynamically from the processed message. It is therefore not possible to provide all potential elements of the list in this documentation.
-   <span style="font-weight: bold;">Operator</span>: To complete the Operator component of an expression, click the arrow on the <span style="font-weight: bold;">Operator</span> selection box and then select an operator from the drop-down list that is displayed. The available operators (<span style="font-weight: bold;">=</span>, <span style="font-weight: bold;">&gt;</span>, <span style="font-weight: bold;">&lt;</span> and so on) vary according to the type of Argument you selected. The complete list of operators is given in [Operators](#Operators) below.
-   [Value](#Completing_the_Value_field): A value of variable length. This value can be a symbolic variable.

#### Example

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Argument</p>         </th>
<th class="HeadE-Column1-Header1"><p>Operator</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>appli</p>         </td>
         <td><p>=</p>         </td>
         <td><p>FTP_A</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> A condition is identified within a given Decision Rule via the name <span style="font-style: italic;">Argument</span> of the input argument to test. This means that a condition involving a given input argument can only be used once in a given Decision Rule condition.

<span id="Condition_parameters"></span>

## Condition parameters

Each time you enter a value, Gateway checks that the string entered is syntactically correct and that it corresponds to the data type of the field. For example, it checks that a string only contains numeric characters for a field of the type integer. This type checking is only applicable to static strings, that is, that do not contain symbolic variables.

The following table lists the parameters you can use in Decision Rule conditions.

<span style="font-weight: bold;">Note:</span> Parameters for use specifically with SWIFTNet are listed in a separate table.

#### Transfer Change State Decision Rule condition parameters

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Real type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">acknowledgement_option</span></p>         </td>
         <td><p>Select from:</p>
<ul>
<li>TO_ACK</li>
<li>NOT_TO_ACK</li>
</ul>         </td>
         <td><p>option for the acknowledgment of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">appli</span></p>         </td>
         <td><p>Allocation unit</p>         </td>
         <td><p>Application name</p>         </td>
      </tr>
      <tr>
         <td><p>appli_user_param1</p>         </td>
         <td><p> </p>         </td>
         <td><p>User variables that relate to the Application</p>         </td>
      </tr>
      <tr>
         <td><p>appli_user_param2</p>         </td>
      </tr>
      <tr>
         <td><p>block_size</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Block size</p>         </td>
      </tr>
      <tr>
         <td><p>called_address</p>         </td>
         <td><p> </p>         </td>
         <td><p>Output of CGate or CGateGroup</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">called_SAP</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>Output of CGate or CGateGroup</p>         </td>
      </tr>
      <tr>
         <td><p>cgate_user_param1</p>         </td>
         <td><p> </p>         </td>
         <td><p>User variables that relate to the selected CGate</p>         </td>
      </tr>
      <tr>
         <td><p>cgate_user_param2</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">content_id</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p>content_type</p>         </td>
         <td><p>String[12]</p>         </td>
         <td><p>Mime content type of the attached file</p>
<p>So far, only available for EDIINT and S/MIME files.</p>         </td>
      </tr>
      <tr>
         <td><p>data_code</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Data character set</p>         </td>
      </tr>
      <tr>
         <td><p>dest_alias</p>         </td>
         <td><p>String[25]</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>String[25]</p>         </td>
         <td><p>Protocol destination name</p>         </td>
      </tr>
      <tr>
         <td><p>dir_path</p>         </td>
         <td><p>String[128]</p>         </td>
         <td><p>Directory path</p>         </td>
      </tr>
      <tr>
         <td><p>direction</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>In</li>
<li>Out</li>
</ul>         </td>
         <td><p>Direction.</p>
<p>Since Decision Rule processing can apply to both input and output Transfers, it is highly recommended that you set this parameter to specify whether to apply the Rule to the incoming or outgoing Transfer. If you do not set the direction parameter, the Decision Rule will loop continuously on both the input and output Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>dir_name</p>         </td>
         <td><p>String[254]</p>         </td>
         <td><p>VFD deposit directory</p>         </td>
      </tr>
      <tr>
         <td><p>f_bytes</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Number of file data bytes transferred</p>         </td>
      </tr>
      <tr>
         <td><p>file_component</p>         </td>
         <td><p>String[127]</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>file_label</p>         </td>
         <td><p>String[80]</p>         </td>
         <td><p>File description</p>         </td>
      </tr>
      <tr>
         <td><p>file_name</p>         </td>
         <td><p>String[128]</p>         </td>
         <td><p>Logical file name</p>         </td>
      </tr>
      <tr>
         <td><p>file_org</p>         </td>
         <td><p> </p>         </td>
         <td><p>File organization</p>         </td>
      </tr>
      <tr>
         <td><p>file_size</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>File size in octets</p>         </td>
      </tr>
      <tr>
         <td><p>file_type</p>         </td>
         <td><p>String[17]</p>         </td>
         <td><p>File type (protocol)</p>         </td>
      </tr>
      <tr>
         <td><p>full_state</p>         </td>
         <td><p> </p>         </td>
         <td><p>Full transfer state value</p>         </td>
      </tr>
      <tr>
         <td><p>group</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>http_host_name</p>         </td>
         <td><p> </p>         </td>
         <td><p>CGate and CGateGroup output</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param1</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>User variables set by the C or Perl exit</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param2</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param3</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param4</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param5</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">ipmid_user_id</span></p>         </td>
         <td><p>String</p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">last_end_reason</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Last end reason for transfer</p>         </td>
      </tr>
      <tr>
         <td><p>local_agent</p>         </td>
         <td><p>String[32]</p>         </td>
         <td><p>Local Site</p>         </td>
      </tr>
      <tr>
         <td><p>message_id</p>         </td>
         <td><p>String[256]</p>         </td>
         <td><p>Mime Message-Id of the attached file</p>
<p>Presently, only available for EDIINT and S/MIME files.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">mail_xpriority</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>SMTP/POP3 X-Priority</p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>Initiator</li>
<li>Responder</li>
<li>Both</li>
</ul>         </td>
         <td><p>Mode</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">mts_id</span></p>         </td>
         <td><p>String</p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">multi_nb_ok</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>The number of successful child transfers of a Multi-transfer.</p>
<p>Refer to<a href="../../protocols_about/ftp_about/ftp_multiple_file_transfer" class="MCXref xref">Transferring multiple files with FTP</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">multi_nb_total</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>The total number of child transfers of a Multi transfer.</p>
<p>Refer to<a href="../../protocols_about/ftp_about/ftp_multiple_file_transfer" class="MCXref xref">Transferring multiple files with FTP</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">multi_state</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>State of a Multi transfer.</p>
<p>Refer to<a href="../../protocols_about/ftp_about/ftp_multiple_file_transfer" class="MCXref xref">Transferring multiple files with FTP</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">newline_convention (-nlc)</span></p>         </td>
         <td><p>Select from:</p>
<ul>
<li>U(nix)</li>
<li>W(indows)</li>
</ul>         </td>
         <td><p>SFTP only.</p>
<p>Line feed convention for transfer, depending on remote system type</p>         </td>
      </tr>
      <tr>
         <td><p>org_alias</p>         </td>
         <td><p>String[25]</p>         </td>
         <td><p>Origin</p>         </td>
      </tr>
      <tr>
         <td><p>originator</p>         </td>
         <td><p>String[32]</p>         </td>
         <td><p>Protocol name originator</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p1.originator</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p1.recipient</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p2.ipmId.user</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p2.bodyPartType</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p2.importance</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">p2.sensitivity</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p>padding</p>         </td>
         <td><p> </p>         </td>
         <td><p>Padding character code</p>         </td>
      </tr>
      <tr>
         <td><p>param1</p>         </td>
         <td><p>String[41]</p>         </td>
         <td><p>User parameter no. 1</p>         </td>
      </tr>
      <tr>
         <td><p>param2</p>         </td>
         <td><p>String[41]</p>         </td>
         <td><p>User parameter no. 2</p>         </td>
      </tr>
      <tr>
         <td><p>protocol</p>         </td>
         <td><p> </p>         </td>
         <td><p>Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_appli</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receiver Application name</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_msg</p>         </td>
         <td><p> </p>         </td>
         <td><p>Received message</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_text</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receiver free text</p>         </td>
      </tr>
      <tr>
         <td><p>rcv_user</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receiver user name</p>         </td>
      </tr>
      <tr>
         <td><p>rec_count</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Number of records</p>         </td>
      </tr>
      <tr>
         <td><p>rec_fmt</p>         </td>
         <td><p> </p>         </td>
         <td><p>Record format</p>         </td>
      </tr>
      <tr>
         <td><p>rec_len</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Record length</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_nack_msg</p>         </td>
         <td><p>String[512]</p>         </td>
         <td><p>Receipt negative or warning description</p>
<p>Only available for EDIINT and S/MIME files.</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_reply_by_xfer</p>         </td>
         <td><p> </p>         </td>
         <td><p>Local identifier for the receipt sent for the current transfer</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_reply_to_xfer</p>         </td>
         <td><p> </p>         </td>
         <td><p>Local identifier for the message that the current receipt acknowledges</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_request</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receipt request option used for transfer</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_request_sync</p>         </td>
         <td><p> </p>         </td>
         <td><p>Receipt requested synchronously</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_request_to</p>         </td>
         <td><p>String[256]</p>         </td>
         <td><p>Receipt return address</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_sent_mode</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>MANUAL</li>
<li>AUTOMATIC</li>
</ul>         </td>
         <td><p>Receipt send mode</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_subtype</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>WARNING</li>
<li>ERROR</li>
<li>FAILURE</li>
</ul>         </td>
         <td><p>Receipt sub type</p>         </td>
      </tr>
      <tr>
         <td><p>receipt_type</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>SUCCESS</li>
<li>FAILURE</li>
</ul>         </td>
         <td><p>Receipt type</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">recipient_receipt_notif_request</span></p>         </td>
         <td><p>Select from:</p>
<ul>
<li>None</li>
<li>NRN</li>
<li>RN_NRN</li>
</ul>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">recipient_reply_request</span></p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>X.420 parameter</p>         </td>
      </tr>
      <tr>
         <td><p>remote_agent</p>         </td>
         <td><p>String[32]</p>         </td>
         <td><p>Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">route_state</span></p>         </td>
         <td><p>Select from:</p>
<ul>
<li>FAILED</li>
<li>NOT_ROUTED</li>
<li>PROCESSING</li>
<li>TO_ROUTE</li>
<li>ROUTED</li>
</ul>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>signed_eerp</p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>Is signed EERP required? (for OFTP R2.0)</p>         </td>
      </tr>
      <tr>
         <td><p>sap</p>         </td>
         <td><p> </p>         </td>
         <td><p>TCP/IP local connection port</p>         </td>
      </tr>
      <tr>
         <td><p>site_user_param1</p>         </td>
         <td><p> </p>         </td>
         <td><p>User variables that relate to the Local Site</p>         </td>
      </tr>
      <tr>
         <td><p>site_user_param2</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_bcc</p>         </td>
         <td><p> </p>         </td>
         <td><p><span style="font-style: italic;">Bcc</span> header field of the received SMTP message, when a single addressee is specified.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_cc</p>         </td>
         <td><p> </p>         </td>
         <td><p><span style="font-style: italic;">Cc</span> header field of the received SMTP message, when a single addressee is specified.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_from</p>         </td>
         <td><p> </p>         </td>
         <td><p><span style="font-style: italic;">From</span> header field of the received SMTP message.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_subject</p>         </td>
         <td><p> </p>         </td>
         <td><p><span style="font-style: italic;">Subject</span> header field of the received SMTP message.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to</p>         </td>
         <td><p> </p>         </td>
         <td><p><span style="font-style: italic;">To</span> header field of the received SMTP message, when a single addressee is specified.</p>         </td>
      </tr>
      <tr>
         <td><p>snd_appli</p>         </td>
         <td><p> </p>         </td>
         <td><p>Sender Application name</p>         </td>
      </tr>
      <tr>
         <td><p>snd_text</p>         </td>
         <td><p> </p>         </td>
         <td><p>Sender free text</p>         </td>
      </tr>
      <tr>
         <td><p>snd_user</p>         </td>
         <td><p> </p>         </td>
         <td><p>Sender user name</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param1</p>         </td>
         <td><p>String</p>         </td>
         <td><p>User variables set by the C or Perl exit</p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param2</p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param3</p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param4</p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param5</p>         </td>
      </tr>
      <tr>
         <td><p>text_file</p>         </td>
         <td><p>Unsigned character</p>         </td>
         <td><p>Text file: Yes / No</p>         </td>
      </tr>
      <tr>
         <td><p>time_of_last_access</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tls_cipher_suite</p>         </td>
         <td><p> </p>         </td>
         <td><p>TLS cipher suite</p>         </td>
      </tr>
      <tr>
         <td><p>tls_client_auth</p>         </td>
         <td><p> </p>         </td>
         <td><p>Client authentication</p>         </td>
      </tr>
      <tr>
         <td><p>tls_server_auth</p>         </td>
         <td><p> </p>         </td>
         <td><p>Server authentication</p>         </td>
      </tr>
      <tr>
         <td><p>tls_sprof</p>         </td>
         <td><p> </p>         </td>
         <td><p>Security profile</p>         </td>
      </tr>
      <tr>
         <td><p>tmp_dea_id</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Trading partner management DEA identifier</p>         </td>
      </tr>
      <tr>
         <td><p>trade_compress</p>         </td>
         <td><p> </p>         </td>
         <td><p>File is compressed</p>         </td>
      </tr>
      <tr>
         <td><p>trade_compress_algo</p>         </td>
         <td><p>ZLIB</p>         </td>
         <td><p>Compression algo</p>         </td>
      </tr>
      <tr>
         <td><p>trade_delivery_mode</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>RT</li>
<li>SNF</li>
</ul>         </td>
         <td><p>Indicates the delivery mode of the file or message</p>         </td>
      </tr>
      <tr>
         <td><p>trade_dest</p>         </td>
         <td><p>String[128]</p>         </td>
         <td><p>Destination trading partner name</p>         </td>
      </tr>
      <tr>
         <td><p>trade_dest_alias</p>         </td>
         <td><p>String[31]</p>         </td>
         <td><p>Destination trading partner alias</p>         </td>
      </tr>
      <tr>
         <td><p>trade_encrypt</p>         </td>
         <td><p> </p>         </td>
         <td><p>File is encrypted</p>         </td>
      </tr>
      <tr>
         <td><p>trade_encrypt_dn</p>         </td>
         <td><p>String[100]</p>         </td>
         <td><p>Name used for encryption in Initiator mode.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">trade_encryption_algo</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>File encryption algorithm</p>         </td>
      </tr>
      <tr>
         <td><p>trade_file_encoded</p>         </td>
         <td><p> </p>         </td>
         <td><p>File is in trade format or not</p>         </td>
      </tr>
      <tr>
         <td><p>trade_format</p>         </td>
         <td><p> </p>         </td>
         <td><p>Trading format used</p>         </td>
      </tr>
      <tr>
         <td><p>trade_key_encryption_algo</p>         </td>
         <td><p>RSA</p>         </td>
         <td><p>Key encryption algo</p>         </td>
      </tr>
      <tr>
         <td><p>trade_org</p>         </td>
         <td><p>String[128]</p>         </td>
         <td><p>Originator trading partner name</p>         </td>
      </tr>
      <tr>
         <td><p>trade_org_alias</p>         </td>
         <td><p>String[31]</p>         </td>
         <td><p>Originator trading partner alias</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_content_type</p>         </td>
         <td><p>String[256]</p>         </td>
         <td><p>Content type returned in receipt (S/MIME only)</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_message_id</p>         </td>
         <td><p>String[256]</p>         </td>
         <td><p>Message ID acknowledged by the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_mic</p>         </td>
         <td><p>String[40]</p>         </td>
         <td><p>MIC of the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_mic_algo</p>         </td>
         <td><p> </p>         </td>
         <td><p>MIC calculation algorithm requested for the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_recipient</p>         </td>
         <td><p>String[128]</p>         </td>
         <td><p>Recipient acknowledged by the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_request_type</p>         </td>
         <td><p>String[30]</p>         </td>
         <td><p>Type of acknowledgement request.</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_sign_algo</p>         </td>
         <td><p> </p>         </td>
         <td><p>Signing algorithm requested for the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>trade_receipt_signature</p>         </td>
         <td><p>String[1024]</p>         </td>
         <td><p>Signature returned in receipt (S/MIME only)</p>         </td>
      </tr>
      <tr>
         <td><p>trade_remote_destination</p>         </td>
         <td><p> </p>         </td>
         <td><p>Destination partner is a remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>trade_request_type</p>         </td>
         <td><p>String[30]</p>         </td>
         <td><p>Type of request</p>         </td>
      </tr>
      <tr>
         <td><p>trade_sign</p>         </td>
         <td><p> </p>         </td>
         <td><p>File is signed</p>         </td>
      </tr>
      <tr>
         <td><p>trade_sign_algo</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>MD5withRSA</li>
<li>SHA1withRSA</li>
</ul>         </td>
         <td><p>Signing algo</p>         </td>
      </tr>
      <tr>
         <td><p>trade_sign_dn</p>         </td>
         <td><p>String[100]</p>         </td>
         <td><p>Name used for signing in Initiator mode. Otherwise the securityDN (supplied by SNL) is used.</p>         </td>
      </tr>
      <tr>
         <td><p>trade_state</p>         </td>
         <td><p> </p>         </td>
         <td><p>Trading process state</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">type</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>Request type (value in the condition: TRANS, EERP and so on)</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">ua_rn_id</span></p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>unprocessed_dir_path</p>         </td>
         <td><p> </p>         </td>
         <td><p>Directory path of the unprocessed file (clear file that is not yet encapsulated in EDIINT)</p>         </td>
      </tr>
      <tr>
         <td><p>unprocessed_file_component</p>         </td>
         <td><p> </p>         </td>
         <td><p>File name of the unprocessed file</p>         </td>
      </tr>
      <tr>
         <td><p>username</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>user_processed</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes or No</p>         </td>
      </tr>
      <tr>
         <td><p>user_state</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>virtual_file_desc</p>         </td>
         <td><p>free text</p>         </td>
         <td><p>Virtual file description (for OFTP R2.0)</p>         </td>
      </tr>
      <tr>
         <td><p>x_bytes</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Number of bytes transferred</p>         </td>
      </tr>
      <tr>
         <td><p>x_data_code</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transferred data code</p>         </td>
      </tr>
      <tr>
         <td><p>x_rec_fmt</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer format</p>         </td>
      </tr>
      <tr>
         <td><p>x_rec_len</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Transfer record length</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_data_code</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_duplicated</p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>Used to filter duplicate incoming SwiftNet FileAct RealTime transfers. The "xfer_duplicated" argument is linked with the "duplicated from xfer" transfer parameter: "xfer_duplicated=Y" means that "duplicated from xfer" is set in the transfer.</p>
<p><strong>Note</strong>:The "xfer_duplicate=Y" does not necessarily mean that the transfer is a duplicate. For example, a put at disposal permanent transfer will generate outgoing child transfers with "duplicate from xfer" pointing to the permanent put at disposal transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_ident</p>         </td>
         <td><p>String[48]</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>xfer_rec_fmt</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer record format</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_rec_len</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Transfer record length</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">yday</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>Day of the current year of the transfer</p>         </td>
      </tr>
   </tbody>
</table>

### Additional Decision Rule condition parameters for SWIFTNet

The following Decision Rule condition parameters are specifically for use with SWIFTNet:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Real type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>header_info</p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>Has Header Info?</p>         </td>
      </tr>
      <tr>
         <td><p>sw_add_params</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Additional SwiftNet parameters file</p>         </td>
      </tr>
      <tr>
         <td><p>sign_list</p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>Has Signature List?</p>         </td>
      </tr>
      <tr>
         <td><p>sw_auth_indicator</p>         </td>
         <td><p> </p>         </td>
         <td><p>Refer to <a href="../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">SWIFTNet File and Message Copy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_copy_indicator</p>         </td>
         <td><p> </p>         </td>
         <td><p>Refer to <a href="../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">SWIFTNet File and Message Copy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_copy_state</p>         </td>
         <td><p> </p>         </td>
         <td><p>Refer to <a href="../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">SWIFTNet File and Message Copy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_copy_type</p>         </td>
         <td><p> </p>         </td>
         <td><p>Refer to <a href="../../connectors_about/swiftnet_about/swiftnet_header_info/swiftnet_file_copy">SWIFTNet File and Message Copy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_message_id</p>         </td>
         <td><p>String[40]</p>         </td>
         <td><p>Overwrite the message id with specified value.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_pd_indication</p>         </td>
         <td><p> </p>         </td>
         <td><p>Make the responder aware that the incoming transfer may be a duplicate of another transfer.</p>
<p>Refer to <a href="../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate">Possible Duplicate management for SWIFTNet</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>trade_non_repudiation</p>         </td>
         <td><p> </p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
      </tr>
      <tr>
         <td><p>trade_notif_queue</p>         </td>
         <td><p>String[30]</p>         </td>
         <td><p>Reception queue for Store-and-Forward delivery notifications.</p>         </td>
      </tr>
      <tr>
         <td><p>sw_retrieved_message</p>         </td>
         <td><p>Y or N</p>         </td>
         <td><p>Is a Retrieved Message?</p>         </td>
      </tr>
      <tr>
         <td><p>sw_retrieved_message_direction</p>         </td>
         <td><p>Select from:</p>
<ul>
<li>received</li>
<li>sent</li>
</ul>         </td>
         <td><p>Retrieved Message direction</p>         </td>
      </tr>
      <tr>
         <td><p>sw_third_party_dn</p>         </td>
         <td><p>String</p>         </td>
         <td><p>Third-Party DN</p>         </td>
      </tr>
      <tr>
         <td><p>trade_service</p>         </td>
         <td><p>String[30]</p>         </td>
         <td><p>SWIFT business service name.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Operators"></span>

## Operators

This section describes the set of operators that you can use in Decision Rule expressions. The operators available depend on the type of argument that you set in the <span style="font-weight: bold;">Argument</span> field.

Since SMTP fields typically contain a list of string values, the way Gateway handles Decision Rule expressions that contain SMTP arguments is slightly different. Refer to [SMTP values in Decision Rule conditions](#SMTP_values_in_Decision_Rule_conditions).

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Operator</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value field type</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>=</p>         </td>
         <td><p>equals</p>         </td>
         <td><ul>
<li>string: the value can contain wildcard characters "*" and "?"</li>
<li>enumerated</li>
<li>numeric</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>#</p>         </td>
         <td><p>does not equal</p>         </td>
         <td><ul>
<li>string: the value can contain wildcard characters "*" and "?"</li>
<li>enumerated</li>
<li>numeric</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&lt;</p>         </td>
         <td><p>less than</p>         </td>
         <td><p><span style="font-weight: bold;">Comparison operators:</span></p>
<ul>
<li>string: compare alphabetic order</li>
<li>numeric</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&gt;</p>         </td>
         <td><p>greater than</p>         </td>
      </tr>
      <tr>
         <td><p>=&lt;</p>         </td>
         <td><p>equal to or less than</p>         </td>
      </tr>
      <tr>
         <td><p>&gt;=</p>         </td>
         <td><p>greater than or equal to</p>         </td>
      </tr>
      <tr>
         <td><p>= NULL</p>         </td>
         <td><p>is null</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p># NULL</p>         </td>
         <td><p>is not null</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>&lt; &gt;</p>         </td>
         <td><p>includes a set of values</p>         </td>
         <td><ul>
<li>string</li>
<li>enumerated</li>
<li>numeric</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>&gt; &lt;</p>         </td>
         <td><p>excludes a set of values</p>         </td>
         <td><ul>
<li>string</li>
<li>enumerated</li>
<li>numeric</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[ ]</p>         </td>
         <td><p>ArgumentIn must be greater than or equal to the first value in the list and less than or equal to the second value</p>         </td>
         <td><p>numeric: the list must include two values separated by a comma (<span style="font-weight: bold;">,</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>] [</p>         </td>
         <td><p>ArgumentIn must be less than the first value or greater than the second value in the list</p>         </td>
         <td><p>numeric: the list must include two values separated by a comma (<span style="font-weight: bold;">,</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>exist</p>         </td>
         <td><p>JMS only</p>
<p>exists</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>not exist</p>         </td>
         <td><p>JMS only</p>
<p>does not exist</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="SMTP_values_in_Decision_Rule_conditions"></span>

## SMTP values in Decision Rule conditions

Since SMTP fields typically contain a list of string values, the condition is valid (or invalid in the case of a negative operator), if <span style="font-style: italic;">one</span> of the SMTP values corresponds to the value of the expression.

The following table describes how Gateway processes Decision Rule conditions, where the <span class="code" style="font-weight: bold;">smtp\_to</span> field in the incoming Transfer contains the values <span style="font-style: italic;">Smith, Jones</span> and <span style="font-style: italic;">Black</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Decision Rule condition</p>         </th>
<th class="HeadE-Column1-Header1"><p>Valid</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>smtp_to = Smith</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>Smith is one of the values in the incoming Transfer smtp_to field.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to = Lloyd</p>         </td>
         <td><p>NO</p>         </td>
         <td><p>Lloyd is not a value listed in the incoming Transfer smtp_to field.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to # Lloyd</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>No name in the smtp_to field of the incoming Transfer is equal to Lloyd.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to # Smith</p>         </td>
         <td><p>NO</p>         </td>
         <td><p>Smith is one of the names in the incoming Transfer smtp_to field.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to &lt;&gt; Smith,Lloyd,Swanson</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>One of the values in the incoming Transfer corresponds to one of the values in the Decision Rule expression (Smith).</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to &lt;&gt; Lloyd,Swanson,Kye</p>         </td>
         <td><p>NO</p>         </td>
         <td><p>No smtp_to value in the incoming Transfer corresponds to any of the values in the Decision Rule expression.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to &gt;&lt; Lloyd,Swanson,Kye</p>         </td>
         <td><p>YES</p>         </td>
         <td><p>None of the names specified corresponds to any value in the smtp_to field in the incoming Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>smtp_to &gt;&lt; Jones,Lloyd,Kye</p>         </td>
         <td><p>NO</p>         </td>
         <td><p>Jones is one of the smtp_to values in the incoming Transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Completing_the_Value_field"></span>

## Scheduling Decision Rule condition parameters

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Real type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">integer_user_param1</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>User variables set by the C or Perl exit</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param2</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param3</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param4</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param5</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param1</span></p>         </td>
         <td><p>String</p>         </td>
         <td><p>User variables set by the C or Perl exit</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param2</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param3</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param4</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param5</span></p>         </td>
      </tr>
   </tbody>
</table>

## Directory Scanning Decision Rule condition parameters

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Real type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">file_name</span></p>         </td>
         <td><p>String[255]</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">file_size</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>File size in bytes</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param1</span></p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>User variables set by the C or Perl Exit</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param2</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param3</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param4</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">integer_user_param5</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param1</span></p>         </td>
         <td><p>String</p>         </td>
         <td><p>User variables set by the C or Perl Exit</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param2</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param3</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param4</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">string_user_param5</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">last_modification</span></p>         </td>
         <td><p>Datetime</p>         </td>
         <td><p>Time of the last data change in the monitored folder</p>         </td>
      </tr>
   </tbody>
</table>

## Completing the Value field

To complete the <span style="font-weight: bold;">Value</span> field, you can:

-   Enter a value directly
-   Select a defined object, such as a Site, from the drop-down list
-   Select a symbolic variable from the drop-down list
-   Use user functions

<span id="Using_symbolic_variables"></span>

### Using symbolic variables

To retrieve a value from the current Transfer Request, you can use <span style="font-style: italic;">symbolic variables</span>. Gateway replaces the symbolic variable with the corresponding value in the current Transfer.

The syntax is <span style="font-weight: bold;">&(Variable\_name)</span>

For example, if you set the condition: <span style="font-weight: bold;">Destination # &(Originator)</span>, Gateway:

-   Identifies the originator Site in the current Transfer
-   Replaces the variable <span style="font-weight: bold;">&(Originator)</span> with this value
-   Checks that the destination Site is not the same as the originator Site

In particular, it is recommended that you use symbolic variables in the Model definition if you set the <span style="font-weight: bold;">Execution type</span> to <span style="font-weight: bold;">Model</span>. For example:

-   file\_component = &(dir\_path)/&(file\_component)
-   application = &(appli)
-   destination\_alias = &(dest\_alias)

To retrieve the system date and time, use the following symbolic variables:

-   <span style="font-weight: bold;">&(DATE)</span>: to retrieve the system date, for example: 20070121
-   <span style="font-weight: bold;">&(TIME)</span>: to retrieve the system time, for example: 101402

### Symbolic variables for Transfer Change State Decision Rules

You can use the following values as symbolic variables for Transfer Change State Decision Rules:

-   acknowledgment\_option
-   alloc\_count
-   alloc\_size
-   alloc\_unit
-   append
-   appli
-   application
-   appli\_user\_param1
-   appli\_user\_param2
-   attach\_extract\_file
-   block\_size
-   called\_addr
-   cgate\_user\_param1
-   cgate\_user\_param2
-   compression
-   content\_id
-   content\_type
-   counts\_0
-   counts\_1
-   counts\_2
-   counts\_3
-   counts\_4
-   counts\_5
-   counts\_6
-   counts\_7
-   counts\_8
-   counts\_9
-   create\_date
-   data\_code
-   DATE
-   date\_begin
-   date\_create
-   date\_end
-   date\_to\_begin
-   date\_to\_end
-   destination
-   dest\_alias
-   direction
-   dir\_name
-   dir\_path
-   dir\_type
-   dn\_request
-   dup\_from\_xfer
-   etb5\_auth\_type
-   etb5\_ciph\_type
-   etb5\_id\_bank
-   etb5\_id\_bank\_sec
-   etb5\_id\_client
-   etb5\_id\_client\_sec
-   etb5\_memo\_type
-   etb5\_paraf\_used
-   etb5\_rsign1\_used
-   etb5\_rsign2\_used
-   etb5\_seal\_type
-   etb5\_sign\_type
-   etb5\_userarea
-   exch\_id
-   extract\_date
-   file\_ciphered
-   file\_component
-   file\_label
-   file\_name
-   file\_org
-   file\_size
-   file\_sys\_dep\_param
-   file\_type
-   ftp\_command
-   full\_state
-   f\_bytes
-   generate\_xfb\_subject
-   group
-   header\_info
-   http\_host\_name
-   ident
-   integer\_user\_param1
-   integer\_user\_param2
-   integer\_user\_param3
-   integer\_user\_param4
-   integer\_user\_param5
-   interval
-   ipmid\_user\_id
-   key\_len
-   key\_offset
-   last\_end\_diag
-   last\_end\_err
-   last\_end\_reason
-   local\_agent
-   local\_ident
-   mail\_xpriority
-   master
-   max\_alloc\_size
-   max\_file
-   max\_files
-   max\_request
-   max\_requests
-   message\_id
-   mode
-   model
-   msg1
-   msg2
-   mts\_id
-   multi\_nb\_ok
-   multi\_nb\_total
-   multi\_state
-   nack\_action
-   nb\_canceled
-   nb\_ended
-   nb\_frozen
-   nb\_progressing\_servicing
-   nb\_suspended
-   nb\_total
-   nb\_to\_begin
-   newline\_convention
-   next\_xfer
-   org\_alias
-   originator
-   padding
-   param1
-   param2
-   path\_name
-   permanent
-   prev\_xfer
-   priority
-   protocol
-   proto\_spec\_str
-   purge\_option
-   rcv\_appli
-   rcv\_msg
-   rcv\_text
-   rcv\_user
-   receipt\_nack\_msg
-   receipt\_reply\_by\_xfer
-   receipt\_reply\_to\_xfer
-   receipt\_request
-   receipt\_request\_sync
-   receipt\_request\_to
-   receipt\_sent\_mode
-   receipt\_subtype
-   receipt\_type
-   recipient\_receipt\_notif\_request
-   recipient\_reply\_request
-   rec\_count
-   rec\_fmt
-   rec\_fmt
-   rec\_len
-   rec\_len
-   remote\_agent
-   reply\_by\_xfer
-   reply\_to\_xfer
-   request\_method
-   response\_code
-   response\_request\_sync
-   response\_to\_xfer
-   retry\_count
-   retry\_count\_max
-   route\_from\_xfer
-   route\_state
-   route\_to\_xfer
-   sap
-   select\_req
-   sentinel\_transfer\_filter
-   sentinel\_xferident
-   sentinel\_xferobjectname
-   sequence
-   sign\_list
-   site\_user\_param1
-   site\_user\_param2
-   smtp\_bcc
-   smtp\_cc
-   smtp\_from
-   smtp\_subject
-   smtp\_to
-   snd\_appli
-   snd\_msg
-   snd\_text
-   snd\_user
-   state
-   string\_user\_param1=
-   string\_user\_param2=
-   string\_user\_param3=
-   string\_user\_param4=
-   string\_user\_param5=
-   sw\_add\_params
-   sw\_auth\_by\_xfer
-   sw\_auth\_indicator
-   sw\_auth\_to\_xfer
-   sw\_copy\_indicator
-   sw\_copy\_stateone
-   sw\_copy\_typeone
-   sw\_message\_id
-   sw\_payload\_type
-   sw\_pd\_indication
-   sw\_retrieved\_message
-   sw\_retrieved\_message\_direction
-   sw\_third\_party\_dn
-   sys\_dep
-   text\_file
-   TIME
-   tls\_cipher\_suite
-   tls\_client\_auth
-   tls\_server\_auth
-   tls\_sprof
-   total\_files
-   total\_requests
-   tpm\_dea\_id
-   tpm\_local\_dea\_id
-   trade\_compress
-   trade\_compress\_algo
-   trade\_delivery\_mode
-   trade\_dest
-   trade\_dest\_alias
-   trade\_encrypt
-   trade\_encryption\_algo
-   trade\_encrypt\_dn
-   trade\_fdacenter
-   trade\_fdasubmissiontype
-   trade\_file\_encoded
-   trade\_format
-   trade\_key\_encryption\_algo
-   trade\_non\_repudiation
-   trade\_notif\_queue
-   trade\_org
-   trade\_org\_alias
-   trade\_processing\_error
-   trade\_receipt\_content\_type
-   trade\_receipt\_message\_id
-   trade\_receipt\_mic
-   trade\_receipt\_mic\_algo
-   trade\_receipt\_recipient
-   trade\_receipt\_request\_type
-   trade\_receipt\_signature
-   trade\_receipt\_sign\_algo
-   trade\_remote\_destination
-   trade\_request\_type
-   trade\_rn\_business\_code
-   trade\_rn\_document\_name
-   trade\_rn\_document\_type
-   trade\_rn\_message\_id
-   trade\_rn\_mic
-   trade\_rn\_process\_id
-   trade\_rn\_transaction\_id
-   trade\_rn\_version
-   trade\_service
-   trade\_sign
-   trade\_sign\_algo
-   trade\_sign\_dn
-   trade\_state
-   truncating\_allowed
-   type
-   ua\_rn\_id
-   unique\_filename
-   uniq\_filename
-   unprocessed\_dir\_path
-   unprocessed\_file\_component
-   username
-   user\_processed
-   user\_state
-   xfer\_duplicated
-   xfer\_ident
-   xfer\_rec\_fmt
-   xfer\_rec\_len
-   xntf\_filter
-   xntf\_profile
-   x\_bytes
-   x\_data\_code
-   yday

<span id="Using_user_functions"></span>

### 

### Symbolic variables for Scheduling Decision Rules

You can use the following values as symbolic variables for Scheduling Decision Rules:

-   rule\_table\_id
-   event\_occur\_time
-   DATE
-   <span class="code">TIME
    </span>
-   <span class="code">Yday</span>
-   integer\_user\_param1
-   integer\_user\_param2
-   integer\_user\_param3
-   integer\_user\_param4
-   integer\_user\_param5
-   string\_user\_param1
-   string\_user\_param2
-   string\_user\_param3
-   string\_user\_param4
-   string\_user\_param5

## Symbolic variables for Directory Scanning Decision Rules

You can use the following values as symbolic variables for Directory Scanning Decision Rules:

-   DATE
-   TIME
-   yday
-   dir\_name
-   dir\_path
-   file\_component
-   file\_name
-   file\_size
-   integer\_user\_param1
-   integer\_user\_param2
-   integer\_user\_param3
-   integer\_user\_param4
-   integer\_user\_param5
-   last\_modification
-   rule\_table\_id
-   string\_user\_param1
-   string\_user\_param2
-   string\_user\_param3
-   string\_user\_param4
-   string\_user\_param5

## Using user functions

You can use the following user functions to complete the Decision Rule <span style="font-weight: bold;">Value</span> field:

-   <span class="code">[strrep()](#strrep)</span>
-   <span class="code">[substr()](#substr)</span>
-   <span class="code">[substring()](#substring)</span>
-   <span class="code">[sepstring()](#sepstring)</span>
-   <span class="code">[uppercase()](#uppercase)</span>
-   <span class="code">[lowercase()](#lowercase)</span>

These functions are described in the following tables:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="3" class="HeadD-Column1-Header1"><span id="strrep"></span><span class="code">strrep()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td>This function enables you to replace a substring of a source string with another substring. All the occurrences of the substring in the source string are replaced.         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p><span class="code">strrep(source, old_substring, new_substring) </span></p>
<p>where:</p>
<ul>
<li><em>source</em> = the source data to be searched<br />
<em>source</em> must be in the format &amp;(var_name) where var_name is a symbolic variable name representing a field in the transfer record. There must be no embedded space in the expression &amp;(var_name). At run time, &amp;(var_name) is substituted by its actual data.</li>
<li><em>old_substring</em> = substring to be replaced from the initial source string (one or more characters)</li>
<li><em>new_substring</em> = substring replacing all the occurrences (one or more characters)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Examples</span></p>         </td>
         <td>In the following examples, <span class="code">&amp;(var)</span> has the value: <span class="code">e:/program files/axway/Gateway/v613/bin/test.exe</span>         </td>
      </tr>
      <tr>
         <td>Enter:         </td>
         <td>The function returns:         </td>
      </tr>
      <tr>
         <td><span class="code">strrep(&amp;(var), "/", "\")</span>         </td>
         <td><span class="code">e:\program files\axway\Gateway\v613\bin\test.exe</span>         </td>
      </tr>
      <tr>
         <td><span class="code">strrep(&amp;(var), ''!', '@')</span>         </td>
         <td><span class="code">e:/program files/axway/Gateway/v613/bin/test.exe</span>         </td>
      </tr>
      <tr>
         <td><span class="code">strrep(&amp;(var), '.exe', '.ini')</span>         </td>
         <td><span class="code">e:/program files/axway/Gateway/v613/bin/test.in</span>i         </td>
      </tr>
      <tr>
         <td><span class="code">strrep(&amp;(var), "/", "//*)</span>         </td>
         <td><span class="code">e://program files//axway//Gateway//v613//bin//test.exe</span>         </td>
      </tr>
      <tr>
         <td><span class="code">strrep(&amp;(var), "program files", "")</span>         </td>
         <td><span class="code">e://axway/Gateway/v613/bin/test.exe</span>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="3" class="HeadD-Column1-Header1"><span id="substr"></span><span class="code">substr()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td><p>This function enables you to extract a sub-section of a source string.</p>
<p>The function extracts a substring of the variable that you specify in the <span style="font-style: italic;">source</span> parameter, starting from the position that you indicate via the <span style="font-style: italic;">from</span> parameter and stopping at the position that you indicate via the <span style="font-style: italic;">to</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p>substr(<span style="font-style: italic;">source</span>, <span style="font-style: italic;">from</span>, <span style="font-style: italic;">to</span>)</p>
<p>where:</p>
<ul>
<li><span style="font-style: italic;">source</span> = the source data to be searched<span style="font-style: italic;"><br />
source</span> must be in the format &amp;(var_name) where var_name is a symbolic variable name representing a field in the transfer record. There must be no embedded space in the expression &amp;(var_name). At run time, &amp;(var_name) is substituted by its actual data.</li>
<li><span style="font-style: italic;">from</span> = the starting position in the source from which to extract the substring</li>
<li><span style="font-style: italic;">to</span> = the end position in the source for the substring extraction</li>
</ul>
<p>The <span style="font-style: italic;">from</span> and <span style="font-style: italic;">to</span> expressions must take one of the following two formats:</p>
<ul>
<li>A numeric expression: <span style="font-style: italic;">n, -n, +n</span>, *<br />
<span style="font-style: italic;">n</span> denotes the position relative to the beginning of the <span style="font-style: italic;">source</span> (Relative to 1)<br />
<span style="font-style: italic;">-n</span> denotes the position relative to the end of the <span style="font-style: italic;">source</span> (-1 is the last position of the source, -2 is next before last, and so on)<br />
<span style="font-style: italic;">+n</span> denotes the length of the characters to be copied, starting from a previously evaluated position. It has meaning only in the <span style="font-style: italic;">to</span> expression. In the <span style="font-style: italic;">from</span> expression, it is equivalent to <span style="font-style: italic;">n</span><br />
* denotes the end of the <span style="font-style: italic;">source</span></li>
<li>A string expression: <span style="font-style: italic;">+n'string-to-search'</span><br />
'<span style="font-style: italic;">string-to-search</span>' comprises one or more characters denoting the string-pattern to search. It must be enclosed between a pair of single quotes (<span class="code">'</span>) or double quotes (<span class="code">"</span>).<br />
<span style="font-style: italic;">n</span> is optional. If present, it denotes the next n<span style="vertical-align: Super;">th</span> occurrence of <span style="font-style: italic;">string-to-search</span> within the <span style="font-style: italic;">source.</span> Otherwise the first occurrence is assumed. If <span style="font-style: italic;">n</span> is *, then the last occurrence is searched.<br />
+ is optional. If present, the <span style="font-style: italic;">string-to-search</span> is also included in the substring returned, otherwise it is not included.<br />
In the <span style="font-style: italic;">from</span> expression, the search starts from the beginning of the source. In the <span style="font-style: italic;">to</span> expression, the search starts at the last position located in the <span style="font-style: italic;">from</span> expression.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Examples</span></p>         </td>
         <td><p>In the following examples, &amp;(var) has the value:</p>
<p>e:/program files/axway/Gateway/v613/bin/test.exe</p>         </td>
      </tr>
      <tr>
         <td><p>Enter:</p>         </td>
         <td><p>The function returns:</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), 1, *)</p>         </td>
         <td><p>e:/program files/axway/Gateway/v613/bin/test.exe</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), 1, 2)</p>         </td>
         <td><p>e:</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), +2'/', +'/')</p>         </td>
         <td><p>/axway/</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), *"/", *)</p>         </td>
         <td><p>test.exe</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), '/bin/', *)</p>         </td>
         <td><p>test.exe</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), -3, *)</p>         </td>
         <td><p>exe</p>         </td>
      </tr>
      <tr>
         <td><p>substr(&amp;(var), -8, -5)</p>         </td>
         <td><p>test</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="substring"></span><span class="code">substring()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td><p>This function extracts a substring of the variable name that you specify, starting from the position that you indicate via the startIndex parameter and stopping at the position that you indicate via the stopIndex parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p>substring(&amp;(variableName), startIndex, stopIndex)</p>
<p>or</p>
<p>substring(&amp;(variableName), startIndex)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Examples</span></p>         </td>
         <td><p>If the Destination in the current Transfer is FTP_DEST, the function:</p>
<p>substring(&amp;(destination), 2, 5)</p>
<p>returns: <span class="code">TP_D</span></p>         </td>
      </tr>
      <tr>
         <td><p>If the Destination in the current Transfer is FTP_DEST, the function:</p>
<p>substring(&amp;(destination), 2)</p>
<p>returns: <span class="code">TP_DEST</span></p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="sepstring"></span><span class="code">sepstring()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td><p>This function extracts a substring from the variable name that you specify. sepstring extracts all, from <span style="font-style: italic;">n</span>th occurrence of the specified separator up to the end.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p>sepstring(&amp;(variableName), separator, nb_occurrence)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Example</span></p>         </td>
         <td><p>If the Destination in the current Transfer is <span class="code">/run_time/etc/file.txt</span>, the function:</p>
<p>sepstring(&amp;(destination), '/', 3)</p>
<p>returns: <span class="code">file.txt</span></p>
<p>The function extracts all characters following the third separator<span class="code"> /</span>.</p>
<p><span style="font-weight: bold;">Note:</span> The separator parameter must be enclosed in single quotes (<span class="code">'</span>).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="uppercase"></span><span class="code">uppercase()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td><p>This function converts the string that you specify to upper case characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p>uppercase(&amp;(variableName))</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Example</span></p>         </td>
         <td><p>If the Destination in the current Transfer is ftp_dest, the function:</p>
<p>uppercase(&amp;(destination))</p>
<p>returns: <span class="code">FTP_DEST</span></p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <thead>
      <tr>
<th style="text-align: left;" colspan="2" class="HeadD-Column1-Header1"><span id="lowercase"></span><span class="code">lowercase()</span>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Purpose</span></p>         </td>
         <td><p>This function converts the string that you specify to lower case characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Syntax</span></p>         </td>
         <td><p><span class="code">lowercase(&amp;(variableName))</span></p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Example</span></p>         </td>
         <td><p>If the Destination in the current Transfer is FTP_DEST, the function:</p>
<p>lowercase(&amp;(destination))</p>
<p>returns: <span class="code">ftp_dest</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Case_insensitive_conditions"></span>

## Case-insensitive conditions

You can define case-insensitive conditions in Decision Rules.

#### Example

You may want to reject any incoming files that are potentially dangerous. The type of file concerned is executable and of the type:<span class="code"> \*.bat</span>, <span class="code">\*.bin</span>, <span class="code">\*.cmd</span>, <span class="code">\*.dll</span>, <span class="code">\*.exe</span> and so on. However, you cannot be sure if the file name is in lowercase, uppercase or mixed.

This example enables you to define a Decision Rule condition that selects all files with a name of the format <span class="code">\*.exe</span>, <span class="code">\*.bin</span>, <span class="code">\*.bat</span>, including: <span class="code">filename.EXE</span>, <span class="code">filename.Exe</span> and <span class="code">filename.eXe</span>.

Create a Decision Rule condition with the following parameters:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Argument</p>         </th>
<th class="HeadE-Column1-Header1"><p>Operator</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>file_name</p>         </td>
         <td><p>&lt; &gt;</p>         </td>
         <td><p>*.[eE][xX][eE], *.[bB][iI][nN], *.[bB][aA][tT]</p>         </td>
      </tr>
   </tbody>
</table>

You can then call a script to delete these files.

Related topics

[Overview: Event management](../../ov_gateway/ov_events)

[Working with Rule Tables and Decision Rules](../working_with_rule_tables_and_decision_rules(gui))

[Working with Decision Rules (command line)](../working_with_decision_rules_cli)

[Working with Rule Tables (command line)](../working_with_decision_rules_cli/working_with_rule_tables_cli)

[Decision Rules and Rule Tables: Parameters List](../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

[Command syntax for Scheduling Event Models](../working_with_decision_rules_cli/scheduling_event_model_command_syntax) (date syntax)

[Usage example: Routing](../decision_rule_example_routing)

[Usage example: Directory Scanning](../decision_rule_example_routing/decision_rule_example_dir_scan)

[Usage example: Scheduling](../decision_rule_example_routing/decision_rule_example_scheduling)

[User exits and Rule Tables](../../customizing_gw_about/user_exits_about/user_exits_internal/user_exits_rule_tables)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
