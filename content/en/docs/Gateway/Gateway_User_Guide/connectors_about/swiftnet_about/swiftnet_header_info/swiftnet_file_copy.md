{
    "title": "SWIFTNet File and Message Copy",
    "linkTitle": "SWIFTNet File and Message Copy",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About SWIFTNet File and Message Copy](#about)

[File and Message Copy support in Gateway](#support_in_gw)

[Using Copy services when sending files or messages](#sending_files)

[Selecting copy destinations for T-Copy and Y-Copy](#third_party_list)

[Receiving files and messages containing Copy service information](#receiving_files)

[GikAPI support for File and Message Copy](#GikAPI)

[Considerations](#considerations)

<span id="about"></span>

## About SWIFTNet File and Message Copy

SWIFTNet File and Message Copy enables the sending of a file or a message to one or more third parties in addition to sending the full file or message to the intended recipient.

-   For InterAct: the entire copied message is sent to the specified third parties.
-   For FileAct: depending on the service configuration, either the full file or just the request header is sent to the specified third parties.

File and Message Copy is only used for services operating in Store-and-Forward mode.

### Copy modes

There are two File and Message Copy modes:

-   Y-Copy: The third party is the first recipient of the sent/copied file or message. The third party authorizes (or not) SWIFT to send the file or message to the final recipient. If the third party refuses to send the file or message to the recipient, a system message refusal notification is sent by SWIFT SnF to the sender party. If the third party accepts to send the file or message, the sender only receives a system message if the authorization notification option has been set, either in the request or at the service level.
-   T-Copy: The request is sent to the destination and to one or more third parties. The actual destination receives the full information and the third parties receive the entire message (InterAct) or, depending on the service configuration, the full file or just the header (FileAct).

In both modes, if the delivery of the copy to the third party fails, a non-delivery notification is sent to the sender ("Failed" or "Rejected" status).

The File and Message Copy services rely on the FileAct [Header Info](../#Overview) structure and on the use of the [Signature List](../../swiftnet_sig_list#Overview) structure to transport the signature information.

<span id="support_in_gw"></span>

## File and Message Copy support in Gateway

The Gateway SWIFTNet connector can act as Sender or Receiver in a File or Message Copy exchange:

-   Send Transfer Requests marked with CopyIndicator, AuthNotifIndication (Sender)
-   Receive and acknowledge a non-delivery notification from the Third Party (Sender)
-   Receive and acknowledge an Authorization notification (Sender)
-   Receive and acknowledge a Refusal notification (Sender)
-   Receive a file or message and retrieve the Copy information (Receiver)

<span id="sending_files"></span>

## Using Copy services when sending files or messages

The parameters described in this section enable you to specify how to work with Copy services.

### Transfer Request parameters

When creating a Transfer Request, use the following<span class="code" style="font-weight: bold;"> peltrans</span> parameters:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_copy_indicator (-ci)</span></p>
<p>Request copy</p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a copy of the file or message to be sent to a third party defined at the service level.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_auth_indicator (-ai)</span></p>
<p>Request authorisation notification</p>         </td>
         <td><p>SWIFTNet Authorization notification indicator.</p>
<p>Select this option to receive Authorization system messages for files or messages sent over Y-copy services.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Trading Partner parameters

When creating a Trading Partner, use the following <span class="code" style="font-weight: bold;">peladm create\_tradepart</span> parameters:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_copy_indicator (-ci)</span></p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a copy of the file or message to be sent to a third party defined at the service level.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_auth_indicator (-ai)</span></p>         </td>
         <td><p>SWIFTNet Authorization notification indicator.</p>
<p>Select this option to receive Authorization system messages for files or messages sent over Y-copy services.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Model parameters

When creating a Model, use the following<span class="code" style="font-weight: bold;"> peladm create\_model</span> parameters:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_copy_indicator (-ci)</span></p>         </td>
         <td><p>SWIFTNet File or Message Copy service indicator.</p>
<p>Select this option to request a copy of the file or message to be sent to a third party defined at the service level.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">-sw_auth_indicator (-ai)</span></p>         </td>
         <td><p>SWIFTNet Authorization notification indicator.</p>
<p>Select this option to receive Authorization system messages for files or messages sent over Y-copy services.</p>         </td>
         <td><p>One of:</p>
<ul>
<li><span class="code" style="font-weight: bold;">Y</span> = yes</li>
<li><span class="code" style="font-weight: bold;">N</span> = no (default)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Decision Rule parameters

The following Decision Rule condition parameters are available:

<span class="code">sw\_copy\_indicator</span>

<span class="code">sw\_auth\_indicator</span>

### End-of-transfer parameters

The following end-of-transfer parameters are available:

<span class="code">x\_sw\_copy\_indicator</span>

<span class="code">x\_sw\_auth\_indicator</span>

<span class="code">x\_sw\_auth\_by\_xfer</span> (link the original sender transfer with the authorization transfer)

<span class="code">x\_sw\_auth\_to\_xfer</span> (link SnF InterAct authorization transfer with the original message)

### Receiving Y-Copy Authorization/Refusal notifications

Authorization notifications are SWIFTNet InterAct SnF system messages. You need a Trading Partner that allows the reception of these system message types. For information about the default Trading Partner used to receive system messages, refer to [SYSTEM\_MESSAGES remote Trading Partner](../../swiftnet_connector/swiftnet_configuring#sys_messages_tp). For information about request type values associated with different system message types, refer to the SWIFTNet documentation.

#### Example


    peladm create_tradepart  -f SWIFTNET  -a SWIFT_SYSTEM_AUTH_OK
      -name cn=system,o=swift,o=swift  -loc N
      -sc swift.snf.system!x  -rqt xsys.002.001.01  -ro ACK_BY_MONITOR
      -signl /home/users/user/SignListAckResponse.txt
     
    peladm create_tradepart  -f SWIFTNET  -a SWIFT_SYSTEM_AUTH_K0
      -name cn=system,o=swift,o=swift  -loc N
      -sc swift.snf.system!x  -rqt xsys.003.001.01  -ro ACK_BY_MONITOR
      -signl /home/users/user/SignListAckResponse.txt

or:


    peladm create_tradepart  -f SWIFTNET  -a SWIFT_SYSTEM_AUTH_OK
      -name cn=system,o=swift,o=swift  -loc N
      -sc swift.snf.system!x  -rqt AnyRequestType  -ro ACK_BY_MONITOR
      -signl /home/users/user/SignListAckResponse.txt

Authorization system messages have the<span class="code"> sw\_auth\_indicator</span> parameter set.

The Authorization/Refusal notification business payload is available as the file component of the SnF InterAct system message.

<span id="third_party_list"></span>

## Selecting copy destinations for T-Copy and Y-Copy

### T-Copy

For T-Copy, a transfer can be sent to one or several copy destinations. If the service definition (ASP) allows the sender to specify the copy destinations then the message or file is sent to those partners. This can be achieved by making a normal SWIFT SnF Copy transfer but specifying the third parties in an XML file on the sender side. The minimum number of third parties defined in the XML file is one. The maximum number is defined in the SWIFT documentation.

### Y-Copy

For Y-Copy, a transfer can be sent to only one copy destination (authorization / central bank). Not all Y-Copy services allow the sender to specify the copy destination (central bank), they are simply hard-coded in the service definition at SWIFT. Y-Copy services that allow the user to select the copy destination from a list of available copy destinations actually require the sender to specify it. Failing to do so would result in the Transfer Request being rejected by SWIFT. The Y-Copy third party destination is specified in an XML file in the same way as for T-Copy, however there can be only one copy destination.

### Completing the Transfer Request

In the Transfer Request, specify the full path of the local physical file containing Third Party List information. In the Gateway GUI, use the **Additional params** parameter on the **SWIFTNet** tab.

Alternatively, use the <span class="codeBold_in_para">peltrans</span> command:

peltrans -sw\_add\_params (-swaddpar) &lt;file reference to additional SWIFTNet structures>

### Typical XML file containing Third Party List: sender side

The XML tag: &lt;Sw:ThirdPartyDN> contains the DN to send to. You can specify up to 10 distinguished DNs.


    <SwThirdPartyDNList>
      <Out>
        <Sw:CopyThirdPartyList>
          <Sw:ThirdPartyDN>cn=tcop-cid1,o=swcibeap,o=swift</Sw:ThirdPartyDN>
          <Sw:ThirdPartyDN>cn=tcop-cid2,o=swcibeap,o=swift</Sw:ThirdPartyDN>
          <Sw:ThirdPartyDN>cn=test1,o=swhqnlnl,o=swift</Sw:ThirdPartyDN>
        </Sw:CopyThirdPartyList>
      </Out>
    </SwThirdPartyDNList>

### Typical XML file containing Third Party List: receiver side

The receiver of a copied transfer should expect a Copied Third Party List in the addSwParams. Note the use of &lt;In> tags instead of &lt;Out> tags in the XML file. For example:


    <SwThirdPartyDNList>
      <In>
        <Sw:CopiedThirdPartyList>
          <Sw:ThirdPartyDN>cn=tcop-cid1,o=swcibeap,o=swift</Sw:ThirdPartyDN>
          <Sw:ThirdPartyDN>cn=tcop-cid2,o=swcibeap,o=swift</Sw:ThirdPartyDN>
          <Sw:ThirdPartyDN>cn=test1,o=swhqnlnl,o=swift</Sw:ThirdPartyDN>
        </Sw:CopiedThirdPartyList>
      </In>
    </SwThirdPartyDNList>

<span id="receiving_files"></span>

## Receiving files and messages containing Copy service information

If the file from SWIFT SnF, received in push-mode, contains a Sw:Copy element in the FileDescriptor, the transfer is marked with the <span class="code">copy\_indicator</span>. The CopyType and CopyState elements are recovered and saved on the transfer, available as end-of-transfer parameters and Decision Rule condition parameters.

### Decision Rule parameters

The following Decision Rule condition parameters are available:

sw\_copy\_indicator

sw\_copy\_type

sw\_copy\_state

### End-of-transfer parameters

The following end-of-transfer parameters are available:

x\_sw\_copy\_indicator

x\_sw\_copy\_type

x\_sw\_copy\_state

<span class="code">x\_sw\_third\_party\_dn</span>

### ThirdPartyToReceiver information

The ThirdPartyToReceiver information, if present, is deposited in the SWIFT parameter file. The parameter<span class="code"> sw\_add\_parameters</span> contains the filename and directory path. For an example of a file containing ThirdPartyToReceiver information, refer to [SWIFTNet dump to XML](../../swiftnet_backup_sites/swiftnet_dump_to_xml).

<span id="GikAPI"></span>

## GikAPI support for File and Message Copy

The following parameters can be found in the <span class="code">gikapic.h</span> header:

-   GikSetUChar(xferParams, GIK\_T\_SW\_COPY\_IND, ITP\_SWIFTNET\_YES)
-   GikSetUChar(xferParams, GIK\_T\_SW\_AUTH\_IND, ITP\_SWIFTNET\_NO)

When creating a transfer, use the values <span class="code">ITP\_SWIFTNET\_YES</span> and <span class="code">ITP\_SWIFTNET\_NO</span> (uses <span class="code">XferRequest\_t</span>).

For <span class="code">XferUpdate</span> and <span class="code">XferGet</span>, use boolean values {0, 1} for the parameters (uses <span class="code">XferRecord\_t</span>).

### Example in C


    #define GIK_T_SW_COPY_IND           386   /* Uchar */
    #define GIK_T_SW_AUTH_IND           387   /* Uchar */
     
    #define GIK_T_SW_THIRD_DN           390   /* String */
    #define GIK_T_SW_COPY_STATE         391   /* Uchar - SwCopyTypeEnm */
    #define GIK_T_SW_COPY_TYPE          392   /* Uchar - SwCopyStateEnm */
     
    /* GikXferPut and GikXferUpdate */
     
    GikSetUChar(xferParams, GIK_T_SW_COPY_IND, ITP_SWIFTNET_YES)
    GikSetUChar(xferParams, GIK_T_SW_AUTH_IND, ITP_SWIFTNET_NO)
     
    /* GikXferGet */
     
    /* Get values: 1 = TRUE; 0 = FALSE  */
     
    GikGetUChar(xferParams, GIK_T_SW_COPY_IND, &copy_indicator);
    GikGetUChar(xferParams, GIK_T_SW_COPY_IND, &copy_indicator);
     
    if (GikGetUChar(xferParams, GIK_T_SW_COPY_STATE, &copy_state))
                         printf("   Error GikGetUChar : %s\n\n",GikErrMsg());
       else
          {
                         char s_copy_state[30] = {0};
     
                         switch (copy_state)
                         {
                            case ITP_SW_COPY_STATE_ACTIVE:
                               strcpy(s_copy_state, "Active");
                                                break;
                            case ITP_SW_COPY_STATE_BYPASS:
                               strcpy(s_copy_state, "Bypass");
                                                break;
                            case ITP_SW_COPY_STATE_FALLBACK: 
                               strcpy(s_copy_state, "TCopyFallback");
                                                break;
                            case ITP_SW_COPY_NONE: 
                               strcpy(s_copy_state, "none");
                               break;
                            default:
                               strcpy(s_copy_state, "Unknown Value!");
                         }
     
                         printf("   copy_state = %s\n", s_copy_state);
          }
     
       /* Copy Type - checked */
       if (GikGetUChar(xferParams, GIK_T_SW_COPY_TYPE, &copy_type))
                         printf("   Error GikGetUChar : %s\n\n",GikErrMsg());
       else
          {
                         char s_copy_type[30] = {0};
     
                         switch (copy_type)
                         {
                            case ITP_SW_COPY_TYPE_FULL:
                               strcpy(s_copy_type, "Full");
                               break;
                            case ITP_SW_COPY_TYPE_HEADER:
                               strcpy(s_copy_type, "Header");
                               break;
                            case ITP_SW_COPY_NONE:
                               strcpy(s_copy_type, "none");
                               break;
                            default:
                               strcpy(s_copy_type, "Unknown Value!");
                         }
     
                         printf("   copy_type = %s\n", s_copy_type);
          }
     
    if ( GikGetString(xferParams, GIK_T_SW_THIRD_DN, third_party_dn, sizeof(third_party_dn)) )
                         printf("   Error GikGetString : %s\n\n",GikErrMsg());
       else printf("   third_party_dn = %s\n", third_party_dn);
     

<span id="considerations"></span>

## Considerations

When non-repudiation is requested on an SnF Copy service, the sender Transfer Request must be signed using a Signature List.

When using File or Message Copy parameters, the SWIFT service configuration must be compatible with the Copy options selected:

-   File or Message Copy must only be used over SnF service
-   The Copy indicator must be allowed on the service
-   The Auth notif indication must be allowed on the service

If the SWIFT configuration is not correct, the request will generate an error at SNL level. This error will appear in the Gateway log.

Related topics

[SWIFTNet connector](../../swiftnet_connector)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../swiftnet_connector/swiftnet_working_with)

[New Transfer Request: SWIFTNet tab](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)

[SWIFTNet Header Info](../)

[SWIFTNet Signature List](../../swiftnet_sig_list)

[SWIFTNet Distribution List](../swiftnet_distribution_list)

[SWIFTNet dump to XML](../../swiftnet_backup_sites/swiftnet_dump_to_xml)

[About C API](../../../../customizing_gw_about/c_api_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
