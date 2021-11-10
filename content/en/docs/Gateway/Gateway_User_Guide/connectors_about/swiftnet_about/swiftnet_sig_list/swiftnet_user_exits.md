{
    "title": "SWIFTNet-specific user exits",
    "linkTitle": "SWIFTNet-specific user exits",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <span style="color: #8b0000;font-weight: bold;"><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">customizing user exits</span></span><strong>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

[About SWIFTNet-specific user exits](#about)

[Source files and compilation](#source_files)

[Configuring the use of SWIFTNet-specific user exits](#configuring)

[Managing user exit errors](#managing_errors)

[SWIFTNet exit to control outgoing requests: SwiftNetOutgoingXferRequest](#SwiftNetOutgoingXferRequest)

[SWIFTNet exit to control incoming requests: SwiftNetIncomingXferRequest](#SwiftNetIncomingXferRequest)

[Enabling logging inside user exit code](#logging)

<span id="about"></span>

## About SWIFTNet-specific user exits

Gateway can use Java user-defined functions to obtain some of the SWIFTNet outgoing and incoming Transfer Request parameters from external sources (for example PassPort PM).

Two user exits are available:

-   Control of outgoing requests and provision of the parameters to add to the SWIFTNet outgoing request
-   Control of incoming requests and provision of the parameters to add to the SWIFTNet outgoing response

If you want to use this feature, you must first configure the use of SWIFTNet-specific user exits as described below.

<span id="source_files"></span>

## Source files and compilation

The JAVA source files are installed in:

&lt;Gateway installation directory>/src/javasrc/com/axway/gateway/userexit

This directory contains the following files:

-   <span class="code">GwUserExit.java</span>  –  JAVA interface
-   <span class="code">SwiftNetIncomingXferRequest.java</span>  –  SWIFTNet exit to control incoming requests
-   <span class="code">SwiftNetOutgoingXferRequest.java</span>  –  SWIFTNet exit to control outgoing requests

After modifying the files as required, compile them (javac) and replace the original source file:

&lt;Gateway installation directory>/run\_time/exithelper/userexit.jar

A sample user exit is provided in:

&lt;Gateway installation directory>/samples/exithelper/

Afterwards, <span style="font-weight: bold;">restart</span> Gateway.

<span id="configuring"></span>

## Configuring the use of SWIFTNet-specific user exits

1.  In the configuration menu, select <span style="font-weight: bold;">Connectivity > Axway Connectivity > SWIFTNet</span>.  
    For full details of the following parameters, refer to [Configuration: Connectors](../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet).
2.  Activate (or deactivate) <span style="font-weight: bold;">Activate user exit</span>.
3.  Check, and if necessary modify, the following parameters:
    -   Address
    -   Port
    -   Timeout

<span id="managing_errors"></span>

## Managing user exit errors

When initiating SWIFTNet transfers, and the <span style="font-weight: bold;">Activate user exit</span> option is enabled, a transfer:

-   <span style="font-weight: bold;">Starts</span> if all mandatory parameters for starting a transfer are provided to the user exit, or recovered from the user exit.
-   <span style="font-weight: bold;">Fails</span> if the mandatory parameters needed by the user exit are not all present.

Consult the log for detailed error messages.

<span id="SwiftNetOutgoingXferRequest"></span>

## SWIFTNet exit to control outgoing requests: SwiftNetOutgoingXferRequest

#### Purpose

If the SWIFTNet <span style="font-weight: bold;">Activate user exit</span> option is enabled, then the exit controls the <span style="font-style: italic;">outgoing</span> requests and provides the undefined parameters to include in the SWIFTNet outgoing request.

The communication between Gateway (SWIFTNet) and the user exit is done using a JAVA helper process. The data exchanged between these two entities is in XML format.

#### Syntax

The input XML (received by the user exit) has the following structure:


    <%transfer_mandatory_param%>...</%transfer_mandatory_param%>
    <%transfer_optional_param%>...</%transfer_optional_param%>
    <%transfer_informative_param%>...</%transfer_informative_param%>

The output XML (sent by the user exit) must have the following structure:


    <acceptation_code>...</acceptation_code>
    <rejection_message>...</rejection_message>
    <%transfer_optional_param%>...</%transfer_optional_param%>

where:

<span class="code">&lt;%transfer\_mandatory\_param%></span> - The parameters that must be provided to the user exit.

<span class="code">&lt;%transfer\_optional\_param%></span> - The parameters that can be recovered from the user exit if they were undefined in Gateway. The user exit will know that one of the optional parameters was undefined if it is not present in the XML data (the related tag will be missing). If an optional parameter was provided in Gateway as Transfer Request parameter, it will be sent to the user exit, but its value should not be overridden with another exit value.

<span class="code">%transfer\_informative\_param%</span> - The parameters sent to user exit only as additional information about the transfer.

The table below describes the input and output XML tags for transmitting the outgoing transfer parameters to the exit and for receiving the transfer status and some transfer parameters from the exit.

<span id="input_output_xml_tags"></span>

#### Input and output XML tags

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadE-Column1-Header1">XML Tag Name         </th>
<th class="HeadE-Column1-Header1">Comments         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Output</p>
<p>Mandatory</p>         </td>
         <td><p><span class="code">&lt;acceptation_code&gt;</span></p>         </td>
         <td><p>User exit answer about rejection or acceptance of outgoing Transfer Request.</p>         </td>
         <td><ul>
<li>TRUE (transfer accepted)</li>
<li>FALSE (transfer rejected)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Output</p>
<p>Optional</p>         </td>
         <td><p><span class="code">&lt;rejection_message&gt;</span></p>         </td>
         <td><p>If <span class="code">acceptation_code</span> is FALSE, a short message with the rejection reason is sent by the user exit.</p>         </td>
         <td><p>Alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;file_pattern&gt;</span></p>         </td>
         <td><p>FileAct Get (initiator) only</p>
<p>Specify a file name format to enable you to identify the received file in the specified directory. The file name pattern can contain symbolic variables.</p>         </td>
         <td><p>Maximum: 256 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;dir_path&gt;</span></p>         </td>
         <td><p>FileAct Get (initiator) only</p>
<p>Specify the local physical path of the directory where received files are to be stored.</p>         </td>
         <td><p>Maximum: 256 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_attribute&gt;</span></p>         </td>
         <td><p>InterAct only</p>
<p>Specify payload attributes in the following format:</p>
<p><span class="code">attrib1=\"value1\"</span></p>         </td>
         <td><p>Maximum: 80 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_compress_info&gt;</span></p>         </td>
         <td><p>InterAct only</p>
<p>Specify payload compression information.</p>         </td>
         <td><ul>
<li>dt=\"GZIP-Base64\"</li>
<li>dt=\"ZLIB-Base64\"</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_type_option&gt;</span></p>         </td>
         <td><p>InterAct only</p>
<p>Specify the payload format.</p>         </td>
         <td><ul>
<li>text</li>
<li>embedded</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Input</p>
<p>Mandatory</p>         </td>
         <td><p><span class="code">&lt;type&gt;</span></p>         </td>
         <td><p>Transfer type</p>         </td>
         <td><ul>
<li>TRANS</li>
<li>MSG</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;mode&gt;</span></p>         </td>
         <td><p>Connection mode for the Transfer</p>         </td>
         <td><ul>
<li>I (= Initiator)</li>
<li>R (= Responder)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;direction&gt;</span></p>         </td>
         <td><p>Transfer direction</p>         </td>
         <td><ul>
<li>I (= In)</li>
<li>O (= Out)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_org_alias&gt;</span></p>         </td>
         <td><p>The originator/local organization alias, linked to the collaboration profile</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_dest_alias&gt;</span></p>         </td>
         <td><p>The destination/remote organization alias, linked to the collaboration profile</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;service&gt;</span></p>         </td>
         <td><p>SWIFT business service name</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;request_type&gt;</span></p>         </td>
         <td><p>Type of request</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>Input/ Output</p>
<p>Optional</p>         </td>
         <td><p><span class="code">&lt;file_name&gt;</span></p>         </td>
         <td><p>FileAct only</p>
<p>Logical file name.</p>         </td>
         <td><p>Maximum: 76 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;snd_msg&gt;</span></p>         </td>
         <td><p>FileAct only</p>
<p>[0 - 255]: Transfer description, supplied by the initiator. Free-text description of the transfer.</p>
<p>[256 - 511]: Transfer information, supplied by the initiator. Structured information concerning the transfer.</p>         </td>
         <td><p>SWIFTNet FileAct: Max 256 alphanumeric characters for each part. Total: 512 chars.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;rcv_msg&gt;</span></p>         </td>
         <td><p><em>FileAct only</em></p>
<p>[0 - 255]: File description, supplied by the sender. Free-text description of the file.</p>
<p>[256 - 511]: File information, supplied by the sender. Structured information concerning the transfer. For more details, refer to the SWIFT documentation.</p>         </td>
         <td><p>Maximum: 256 + 256 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;priority&gt;</span></p>         </td>
         <td><p>Transfer priority</p>         </td>
         <td><ul>
<li>Urgent</li>
<li>Normal</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request&gt;</span></p>         </td>
         <td><p>A return receipt is required when sending a file to a partner</p>         </td>
         <td><ul>
<li>none</li>
<li>signed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_dn&gt;</span></p>         </td>
         <td><p>Only if receipt_request is signed.</p>
<p>Receipt DN</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request_type&gt;</span></p>         </td>
         <td><p>FileAct, RealTime only</p>
<p>Only if receipt_request is signed.</p>
<p>Type of acknowledgment request</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_org&gt;</span></p>         </td>
         <td><p>DN of the originating partner.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_dest&gt;</span></p>         </td>
         <td><p>DN of the destination partner.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign&gt;</span></p>         </td>
         <td><p>Transfer is signed.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign_dn&gt;</span></p>         </td>
         <td><p>InterAct only</p>
<p>Sent only if <span class="code">trade_sign</span> is Y or non repudiation is Y.</p>
<p>If specified, name used for signing in Initiator mode. Otherwise the securityDN (supplied by SNL) is used.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_encrypt&gt;</span></p>         </td>
         <td><p>InterAct only</p>
<p>Transfer is encrypted.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_encrypt_dn&gt;</span></p>         </td>
         <td><p><span style="font-style: italic;">InterAct only</span></p>
<p>Sent only if <span class="code">trade_encrypt</span> is Y.</p>
<p><span style="font-style: italic;">Mandatory</span> if<span class="code"> trade_encrypt</span> is Y.</p>
<p>If specified, name used for encryption in Initiator mode.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;non_repudiation&gt;</span></p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_delivery_mode&gt;</span></p>         </td>
         <td><p>The delivery mode of the file or message.</p>         </td>
         <td><ul>
<li>RT</li>
<li>SNF</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_notif_queue&gt;</span></p>         </td>
         <td><p>Only if <span class="code">trade_delivery_mode</span> is SNF.</p>
<p>Reception queue for Store-and-Forward delivery notifications.</p>
<p>It can be empty. If no value is specified, the tag is not added to the XML.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_compress&gt;</span></p>         </td>
         <td><p>Use compression when sending a file or message to a partner.</p>         </td>
         <td><ul>
<li>Y = Use compression</li>
<li>N = No compression</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Input</p>
<p>Informative</p>         </td>
         <td><p><span class="code">&lt;dest_alias&gt;</span></p>         </td>
         <td><p>Destination Site alias.</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;org_alias&gt;</span></p>         </td>
         <td><p>Originator Site alias.</p>         </td>
         <td><p>Maximum: 31 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;user_ref&gt;</span></p>         </td>
         <td><p>User reference of the request/ response.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_type&gt;</span></p>         </td>
         <td><p>Specify the type of receipt to return to the initiator of the received transfer.</p>         </td>
         <td><ul>
<li>SUCCESS</li>
<li>ERROR</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> The XML Tag names are the same as the [Transfer Request parameter names](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list). The maximum length for each string parameter can be found in<span class="code"> &lt;Gateway installation directory>/inc/itpdefs.h</span>.

### Example: User exit for an outgoing transfer

In this example, not all parameters needed to initiate a SWIFTNet transfer are given in the command line, but they are recovered from the user exit (for example, <span class="code">trade\_dest</span> and <span class="code">trade\_org</span>).

peltrans  -ap FTP\_A  -oa LOCAL\_SITE  -da REMOTE\_SITE  -tradeoa ORIG\_ORGANIZ

-tradeda DEST\_ORGANIZ  -fc c:\\test.txt  -sc swift.devsup.fa!x1

-rqt dc00.0000.0000

Gateway sends to user exit:


    <type>TRANS</type>
    <mode>I</mode>
    <direction>O</direction>
    <tr>ORIG_ORGANIZ</trade_org_alias>
    <tr>DEST_ORGANIZ</trade_dest_alias>
    <service>swift.devsup.fa!x1</service>
    <request_type>dc00.0000.0000</request_type>
    <file_name>FTP_A</file_name>
    <org_alias>LOCAL_SITE</org_alias>
    <dest_alias>REMOTE_SITE</dest_alias>

Gateway receives from user exit:


    <acceptation_code>TRUE</acceptation_code>
    <priority>Normal</priority>
    <tr>ou=p1,o=test,o=swift</trade_org>
    <tr>ou=p2,o=test,o=swift</trade_dest>
    <tr>Y</trade_sign>
    <non_repudiation>Y</non_repudiation>

The user exit accepts the outgoing transfer and all basic parameters for initiating a transfer are available.

<span id="SwiftNetIncomingXferRequest"></span>

## SWIFTNet exit to control incoming requests: SwiftNetIncomingXferRequest

#### Purpose

If the SWIFTNet <span style="font-weight: bold;">Activate user exit</span> is enabled, then the exit controls the <span style="font-style: italic;">incoming</span> requests and updates some of the transfer parameters to include in the SWIFTNet outgoing response.

The communication between Gateway (SWIFTNet) and the user exit is done using a JAVA helper process. The data exchanged between these two entities is in XML format.

#### Syntax

The input XML (received by the user exit) has the following structure:


    <%input_transfer_param%>...</%input_transfer_param%>

The output XML (sent by the user exit) must have the following structure:


    <acceptation_code>...</acceptation_code>
    <rejection_description>...</rejection_description>
    <rejection_info>...</rejection_info>
    <%output_transfer_param%>...</%output_transfer_param%>

where:

<span class="code">%input\_transfer\_param%</span> - The same tags as specified in the [Input and output XML tag table](#input_output_xml_tags), except that the<span class="code"> &lt;trade\_org\_alias></span> and<span class="code"> &lt;trade\_dest\_alias></span> parameters are not present.

<span class="code">%output\_transfer\_param%</span> - The output parameters depend on the transfer type. Refer to the tables below:

-   [FileAct PUT](#output_paras_fileact_put)
-   [FileAct GET](#output_paras_fileact_get)
-   [InterAct](#output_paras_interact)

For all incoming XML, the user exit should send an XML response that contains the following tags:

<span id="xml_response_tags"></span>

#### XML response tags

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>XML Tag Name</p>         </th>
<th class="HeadE-Column1-Header1"><p>Comments</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">&lt;acceptation_code&gt;</span></p>         </td>
         <td><p>Mandatory</p>
<p>Incoming transfer is accepted or rejected by the exit.</p>         </td>
         <td><ul>
<li>Accepted</li>
<li>Rejected</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;rejection_description&gt;</span></p>         </td>
         <td><p><span style="font-style: italic;">FileAct</span>: Use to set the Sw:RejectDescription parameter.</p>
<p><span style="font-style: italic;">InterAct</span>: Short message with the rejection reason.</p>         </td>
         <td><p>Alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;rejection_info&gt;</span></p>         </td>
         <td><p>FileAct only</p>
<p>Use to set the Sw:RejectInfo parameter.</p>         </td>
         <td><p>Alphanumeric characters</p>         </td>
      </tr>
   </tbody>
</table>

<span id="output_paras_fileact_put"></span>

#### Output transfer parameters for FileAct PUT transfers

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>XML Tag Name</p>         </th>
<th class="HeadE-Column1-Header1"><p>Comments</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">&lt;trade_org_alias&gt;</span></p>         </td>
         <td><p>The originator/local organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_dest_alias&gt;</span></p>         </td>
         <td><p>The destination/remote organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign&gt;</span></p>         </td>
         <td><p>Transfer is signed.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;non_repudiation&gt;</span></p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;file_pattern&gt;</span></p>         </td>
         <td><p>Specify a file name format to enable you to identify the received file in the specified directory. The file name pattern can contain symbolic variables.</p>         </td>
         <td><p>Maximum: 256 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;dir_path&gt;</span></p>         </td>
         <td><p>Specify the local physical path of the directory where received files are to be stored.</p>         </td>
         <td><p>Maximum: 256 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_option&gt;</span></p>         </td>
         <td><p>Determines how acknowledgments are handled.</p>         </td>
         <td><ul>
<li>ACK_BY_MONITOR</li>
<li>ACK_BY_USER</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;appli&gt;</span></p>         </td>
         <td><p>Application name.</p>         </td>
         <td><p>Any valid application name</p>         </td>
      </tr>
   </tbody>
</table>

<span id="output_paras_fileact_get"></span>

#### Output transfer parameters for FileAct GET transfers

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>XML Tag Name</p>         </th>
<th class="HeadE-Column1-Header1"><p>Comments</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">&lt;trade_org_alias&gt;</span></p>         </td>
         <td><p>The originator/local organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_dest_alias&gt;</span></p>         </td>
         <td><p>The destination/remote organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign&gt;</span></p>         </td>
         <td><p>Transfer is signed.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;non_repudiation&gt;</span></p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;appli&gt;</span></p>         </td>
         <td><p>Application name.</p>         </td>
         <td><p>Any valid application name</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request&gt;</span></p>         </td>
         <td><p>A return receipt is required when sending a file to a partner.</p>         </td>
         <td><ul>
<li>none</li>
<li>signed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_dn&gt;</span></p>         </td>
         <td><p>Only if<span class="code"> receipt_request</span> is signed</p>
<p>Receipt DN.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request_type&gt;</span></p>         </td>
         <td><p>Only if<span class="code"> receipt_request</span> is signed</p>
<p>Type of acknowledgement request.</p>         </td>
         <td><p>Maximum: 30 alphanumeric characters</p>         </td>
      </tr>
   </tbody>
</table>

<span id="output_paras_interact"></span>

#### Output transfer parameters for InterAct transfers

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>XML Tag Name</p>         </th>
<th class="HeadE-Column1-Header1"><p>Comments</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">&lt;trade_org_alias&gt;</span></p>         </td>
         <td><p>The originator/local organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_dest_alias&gt;</span></p>         </td>
         <td><p>The destination/remote organization alias, linked to the collaboration profile.</p>         </td>
         <td><p>Maximum: 128 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign&gt;</span></p>         </td>
         <td><p>Transfer is signed.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_sign_dn&gt;</span></p>         </td>
         <td><p>Name used for signing the response. Otherwise the securityDN (supplied by SNL) is used.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_encrypt&gt;</span></p>         </td>
         <td><p>Transfer is encrypted.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;trade_encrypt_dn&gt;</span></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span> if <span class="code">trade_encrypt</span> is Y.</p>         </td>
         <td><p>Maximum: 100 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;non_repudiation&gt;</span></p>         </td>
         <td><p>Request SWIFT to keep proof of sending.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request&gt;</span></p>         </td>
         <td><p><span style="font-style: italic;">InterAct SnF only</span></p>
<p>A return receipt is required when sending a file to a partner.</p>         </td>
         <td><ul>
<li>none</li>
<li>signed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_attribute&gt;</span></p>         </td>
         <td><p>Specify payload attributes in the following format:</p>
<p><span class="code">attrib1=\"value1\"</span></p>         </td>
         <td><p>Maximum: 80 characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_compress_info&gt;</span></p>         </td>
         <td><p>Specify payload compression information.</p>         </td>
         <td><ul>
<li>dt=\"GZIP-Base64\"</li>
<li>dt=\"ZLIB-Base64\"</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;file_component&gt;</span></p>         </td>
         <td><p>Name of the local file containing the default reply message.</p>         </td>
         <td><p>Maximum: 256 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;receipt_request_sync&gt;</span></p>         </td>
         <td><p><span style="font-style: italic;">InterAct RT only</span></p>
<p>Activate the waiting period for a Transfer receipt containing the reply message.</p>         </td>
         <td><ul>
<li>Y</li>
<li>N</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;payload_type_option&gt;</span></p>         </td>
         <td><p>Specify the payload format.</p>         </td>
         <td><ul>
<li>text</li>
<li>embedded</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">&lt;appli&gt;</span></p>         </td>
         <td><p>Application name.</p>         </td>
         <td><p>Any valid application name</p>         </td>
      </tr>
   </tbody>
</table>

<span id="i_o_para_examples"></span>

### Examples: User exits for incoming transfers

#### Example 1: FileAct PUT

peltrans  -ap FTP\_A  -oa LOCAL\_SITE  -da REMOTE\_SITE

   -tradeoa ORIG\_ORGANIZ  -tradeda DEST\_ORGANIZ  -fc c:\\out.txt

   -sc swift.devsup.fa!x1  -rqt dc00.0000.0000

<span style="font-weight: bold;">   -tradeo ou=p1,o=test,o=swift  -traded ou=p2,o=test,o=swift</span>

Gateway sends the incoming transfer parameters to the user exit:


    <type>TRANS</type>
    <mode>R</mode>
    <direction>I</direction>
    <service>swift.devsup.fa!x1</service>
    <request_type>dc00.0000.0000</request_type>
    <tr>ou=p1,o=test,o=swift</trade_org>
    <tr>ou=p2,o=test,o=swift</trade_dest>
    <tr>N</trade_sign>
    <tr>N</trade_encrypt>
    <non_repudiation>N</non_repudiation>

Gateway receives from the user exit:


    <acceptation_code>Accepted</acceptation_code>
    <tr>Y</trade_sign>
    <non_repudiation>Y</non_repudiation>

#### Example 2: FileAct GET

This example uses two <span class="code" style="font-weight: bold;">peltrans</span> commands. First, the Server/Responder makes the file available, then the Client/Initiator takes the file.

Responder side:

peltrans  -ty TRANS  -dir O  -mode R  -ap FTP\_A  -oa ITEM-51537

   -da RSWIFT  -tradeoa ORGANIZ\_ORIG  -tradeda ORGANIZ\_DEST

<span style="font-weight: bold;">   -fc c:\\out.txt  -sc swift.devsup.fa!x1  -rqt dc00.0000.0000</span>

Initiator side:

peltrans  -ty TRANS  -dir I  -mode I  -ap FTP\_A  -oa RSWIFT

   -da ITEM-51537  -tradeoa ORGANIZ\_DEST  -tradeda ORGANIZ\_ORIG

   -sc swift.devsup.fa!x1  -rqt dc00.0000.0000

<span style="font-weight: bold;">   -tradeo ou=p1,o=test,o=swift  -traded ou=p2,o=test,o=swift</span>

 

Gateway sends the incoming transfer parameters to the user exit:


    <type>TRANS</type>
    <mode>R</mode>
    <direction>O</direction>
    <service>swift.devsup.fa!x1</service>
    <request_type>dc00.0000.0000</request_type>
    <tr>ou=p1,o=test,o=swift</trade_org>
    <tr>ou=p2,o=test,o=swift</trade_dest>
    <tr>N</trade_sign>
    <tr>N</trade_encrypt>
    <non_repudiation>N</non_repudiation>

Gateway receives from the user exit:


    <acceptation_code>Accepted</acceptation_code>
    <tr>Y</trade_sign>
    <receipt_request>signed</receipt_request>
    <receipt_request_type>dc11.1111.1111</receipt_request_type>
    <non_repudiation>Y</non_repudiation>

<span id="logging"></span>

## Enabling logging inside user exit code

Standard output and standard errors of the user exit are, by default, redirected to the null device (messages printed via system.out interface are discarded). Therefore, if you need to write logging information regarding the processing of user exits, it is recommended to use log4j or a similar logging facility. A log4j configuration sample is provided in the samples.

To enable logging inside user exit code:

1.  Copy the <span class="code">log.properties</span> sample in the user exit directory.
2.  Append the path to the <span class="code">log.properties</span> file in the <span class="code">userexit\_command</span> parameter (<span class="code">-Dlog4j.configuration=&lt;path to log.properties></span>).
3.  Use <span class="codeBold_in_para">peluconf get</span> to retrieve the old command from the userexit section:  
    (<span class="codeBold_in_para">peluconf get -s userexit userexit\_command</span>) and copy it in a text editor.
4.  Append the path to the command and write the new string in the configuration with <span class="codeBold_in_para">peluconf</span>:  
    (<span class="codeBold_in_para">peluconf set -s userexit\_command "&lt;new value>"</span>).

Related topics

[Configuration: Connectors](../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[Transfers: Parameters List](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

[About user exits](../../../../customizing_gw_about/user_exits_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
