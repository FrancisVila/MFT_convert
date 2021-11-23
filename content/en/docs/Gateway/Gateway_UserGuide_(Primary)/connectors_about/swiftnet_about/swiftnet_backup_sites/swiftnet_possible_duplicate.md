{
    "title": "Possible Duplicate management for SWIFTNet",
    "linkTitle": "Possible Duplicate management",
    "weight": "290"
}{{< Gateway/componentlongname  >}}: Connectors

[About Possible Duplicate management](#about)

[Overview of parameters for SWIFTNet Possible Duplicate](#parameters)

[Specifying Possible Duplicate parameters](#specifying_paras)

[Using online commands](#online_commands)

[GikAPI](#GikAPI)

[Possible Duplicate management log messages](#log_messages)

<span id="about"></span>

## About Possible Duplicate management

When transferring files (or messages) it can happen that a file is transferred more than once. Gateway enables you to manage SWIFTNet Possible Duplicate transfers in real-time mode, by setting various parameters.

For outgoing SWIFTNet transfers, Gateway enables you (the initiator) to warn the responder that a file or message is a *Possible Duplicate*. To do this, you include Possible Duplicate parameters when creating a Transfer Request. The responder must then save these parameters and decide whether to keep the original file or use the new file.

For incoming transfers, a configuration parameter enables you to control the acceptance or rejection of Possible Duplicates.

This function is also known as PDE (Possible Duplicate Emission).

<span id="parameters"></span>

## Overview of parameters for SWIFTNet Possible Duplicate

To manage situations in which Possible Duplicate transfers may occur, you need to:

-   Specify certain transfer parameters
-   Set a configuration parameter

### Transfer parameters

For outgoing transfers, the following optional parameters in the Transfer Request are used to indicate a Possible Duplicate:

-   SWIFTNet **Message id** parameter  
    If provided explicitly by the user, the value of this parameter overwrites the message id created by Gateway in the Transfer Request. The UUID should be used.
-   <span style="font-weight: bold;">Possible duplicate</span> parameter  
    The initiator of a transfer can set this parameter to make the responder aware that the incoming transfer may be a duplicate of another transfer

These parameters are used for both FileAct and InterAct transfers. They can be exploited by Decision Rules, Models and end-of-transfer procedures.

An additional parameter is available when creating Transfer Requests using the <span class="codeBold_in_para">peltrans</span> command:

-   Empty message id parameter  
    Sometimes the sender might want to mark a transfer as a Possible Duplicate but *not* generate a message id for it. In such cases the empty message id parameter should be used to prevent Gateway from automatically generating a message id. For details of how to use this parameter, refer to [Using online commands](#online_commands) below.

### Configuration parameter

For incoming FileAct transfers, the configuration parameter <span style="font-weight: bold;">Accept possible duplicate transfers</span> controls the acceptance/rejection of Possible Duplicates. Depending on the value of this parameter, Gateway behaves in two different ways:

1.  <span style="font-weight: bold;">Accept possible duplicate transfers</span> <span style="font-style: italic;">not</span> selected: Gateway rejects Possible Duplicate transfers  
    Gateway checks if the incoming request corresponds to a request in its Mailbox.  
    The fields used to identify a request are: message id, requester DN, responder DN, service, request type and protocol file name, SWIFT LogicalName. If this original request exists, Gateway rejects the duplicate request (returning "duplicated" to the request initiator). Otherwise it accepts the transfer.
2.  <span style="font-weight: bold;">Accept possible duplicate transfers</span> <span style="font-style: italic;">selected</span>: Gateway accepts Possible Duplicate transfers  
    Gateway checks its Mailbox to see if a transfer exists with the same parameters as mentioned above. If one is found, Gateway accepts it and warns the user about the possible duplicate transfer via a log message and the <span style="font-weight: bold;">Possible duplicate</span> parameter

This parameter affects FileAct transfers only. In InterAct, no validation is made (all messages are accepted).

The incoming SWIFTNet Possible Duplicate parameters (possible duplicate indication and SWIFTNet message id) are used to set the corresponding Gateway parameters (at responder), in order to be exploited by Decision Rules, Models and end-of-transfer procedures.

### SWIFTNet message id

In this version of Gateway, the SWIFTNet message id and the transfer identifier (<span class="code">xfer\_ident</span>) are set to the same value.

For <span style="font-style: italic;">outgoing</span> SWIFTNet requests, both parameters are set to a Universal Unique IDentifier (UUID) calculated by Gateway. The message id is no longer set to the local transfer identifier. This greatly reduces the risk of having two outgoing requests with the same message id in the receiver Mailbox.

For <span style="font-style: italic;">incoming</span> SWIFTNet requests, the SWIFTNet message id and the transfer identifier are set to the value of the SWIFTNet &lt;Sw:MsgId> tag.

<span id="specifying_paras"></span>

## Specifying Possible Duplicate parameters

### Transfer Request parameters

You can set the SWIFTNet message id of the new transfer and the Possible Duplicate transfer indicator in the Transfer Request.

In the <span style="font-weight: bold;">[SWIFTNet](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)</span> tab of the <span style="font-style: italic;">New Transfer Request</span> window, on the <span style="font-weight: bold;">E2E</span> (End To End) tab, complete the following parameters:

-   **Message id** – Set the SWIFTNet message id of the new transfer to the message id of the initial transfer
-   **Possible duplicate** – Select this option

These parameters are received by the responder. They can be exploited by Decision Rules, exits, etc.

You can view these Transfer Request parameters in the <span style="font-weight: bold;">SWIFTNet</span> tab of the <span style="font-style: italic;">Transfer Request (Read only)</span> window.

### Setting the configuration parameter for accepting/rejecting Possible Duplicates

You can enable or disable the option to accept SWIFTNet Possible Duplicate transfers (for FileAct) in the Gateway configuration menu.

1.  In the [configuration menu](../../../../configuration_start_here/config_procedure#Configuring_Gateway), select:  
    <span style="font-weight: bold;">Connectivity > Axway Connectivity > SWIFTNet</span>
2.  Check or uncheck the option <span style="font-weight: bold;">Accept possible duplicate transfers</span>.
3.  Click OK.

The modification is taken into account only after restarting Gateway.

### New attributes for Models and Decision Rules

New attributes for use with Models and Decision Rules:

-   <span style="font-weight: bold;">swift message id</span> Type: string.  
    This corresponds to the SWIFTNet transfer identifier.  
    Related symbolic variable: <span style="font-weight: bold;">&(sw\_message\_id)</span>
-   <span style="font-weight: bold;">possible duplicate</span> Type: enum (Y, y, N, n).  
    This corresponds to the Transfer Request <span style="font-weight: bold;">Possible duplicate</span> parameter.  
    Related symbolic variable: <span style="font-weight: bold;">&(sw\_pd\_indication)</span>

### Model attributes for Transfer Requests

Examples of arguments (and values) for the General Model:

-   <span style="font-weight: bold;">possible duplicate (Y)</span>
-   <span style="font-weight: bold;">swift message id (&lt;message id>)</span>

### Decision Rules attributes for incoming/outgoing transfers

Examples of arguments for Decision Rules:

-   possible duplicate = N
-   protocol = SWIFTNET
-   swift message id = &lt;message id>

<span id="online_commands"></span>

## Using online commands

### Setting Transfer Request parameters using the peltrans command

Use the <span class="code" style="font-weight: bold;">peltrans</span> command to create a Transfer Request and indicate a possible duplicate transfer. Refer to the following table for parameter details.

#### Transfer Request parameters specific to Possible Duplicate

In this table, the corresponding field name (if available) in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Meaning         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="_sw_empty_message_id"></span>-sw_empty_message_id (-swemptymsgid)</p>
<p>(None)</p>         </td>
         <td><p>Empty message id parameter.</p>
<p>Use this parameter to prevent Gateway from automatically generating a message id.</p>
<p>This is useful if you want to mark a transfer as a Possible Duplicate but <em>not</em> generate a message id for it, because it is unknown.</p>
<p><strong>Note:</strong> Do not use this parameter in combination with the <span class="code">sw_message_id</span> parameter! If you specify both parameters, then the <span class="code">sw_empty_message_id</span> parameter is not taken into account.</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">Y</span> – Prevent Gateway from automatically generating a message id</li>
<li><span class="code" style="font-weight: bold;">N</span> – Gateway automatically generates a message id (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="_swmsgid"></span>-sw_message_id (-swmsgid)</p>
<p>Message id</p>         </td>
         <td><p>SWIFTNet message id.</p>
<p>The value of this parameter overwrites the message id created by Gateway in the Transfer Request.</p>
<p>Enter the SWIFTNet message id of the new transfer. This should be a Universal Unique IDentifier (UUID).</p>
<p>If the transfer is a Possible Duplicate, enter the message id of the initial transfer.</p>         </td>
         <td><p>Maximum: 40 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span id="_swpdind"></span>-sw_pd_indication (-swpdind)</p>
<p>Possible duplicate</p>         </td>
         <td><p>Possible Duplicate indicator</p>         </td>
         <td><ul>
<li><span class="code" style="font-weight: bold;">Y</span> – Select this value to indicate to the responder that the transfer is a Possible Duplicate.</li>
<li><span class="code" style="font-weight: bold;">N</span> (default)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

For details of all other Transfer Request parameters, refer to [Transfers: Parameters List](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list).

#### Examples



    peltrans  -da REMOTE_SITE  -tradeoa LOCAL_TP  -tradeda REMOTE_TP  -ap FTP_A
       -fc c:\info.txt  –swmsgid 467246F2-5C7E-1D36-302A-6B4100000017
    peltrans  -da REMOTE_SITE  -tradeoa LOCAL_TP  -tradeda REMOTE_TP  -ap FTP_A
       -fc c:\info.txt  -swpdind Y
    peltrans  -da REMOTE_SITE  -tradeoa LOCAL_TP  -tradeda REMOTE_TP -ap FTP_A
       -fc c:\info.txt  -swmsgid 467246F2-5C7E-1D36-302A-6B4100000017  –swpdind N

### Setting Transfer Request parameters using peladm create\_model or peladm update\_model

You can add the two attributes <span style="font-weight: bold;">swift message id</span> and<span style="font-weight: bold;"> possible duplicate</span> to general Models and/or SWIFTNet Models using the <span class="code">swmsgid</span> and <span class="code">swpdind</span> parameters.

#### Examples

General Model:

peladm create\_model  -ml PD\_MODEL  -pr GENERAL  -swpdind Y

   -swmsgid "&(sw\_message\_id)"

SWIFTNet Model:

peladm create\_model  -ml PD\_MODEL  -pr SWIFTNET  -swpdind Y

   -swmsgid "&(sw\_message\_id)"

### Setting Transfer Request parameters in Decision Rules using peladm create\_decisionrule or peladm update\_decisionrule

The attribute names for use in Decision Rules are: <span class="code">-sw\_pd\_indication</span> (possible duplicate) and <span class="code">-sw\_message\_id</span> (SWIFTNet message id).

#### Example

peladm create\_decisionrule  -n PD\_DECRULE  -type XFER\_CHANGE\_STATE

   -et MODEL  -ml PD\_MODEL  -ca "sw\_pd\_indication=Y;

   -sw\_message\_id=467246F2-5C7E-1D36-302A-6B4100000019; protocol=SWIFTNET"

<span id="GikAPI"></span>

## GikAPI

Two new parameters have been added to the <span class="code">gikapic.h</span> header to allow your applications to set the possible duplicate flag and overwrite the message id with a Universal Unique IDentifier (UUID):

-   GIK\_T\_SW\_PD\_INDICATION:
    -   int: use GikSet/GetInt;
    -   values: ITP\_NO / ITP\_YES;
-   GIK\_T\_SW\_MESSAGE\_ID:
    -   string: use GikSet/GetString;
    -   maximum size: 40 characters

<span id="log_messages"></span>

## Possible Duplicate management log messages

Log messages (SNET102E and SNET103W) inform you about possible duplicate transfers in the following situations:

-   The initiator sends a Transfer Request and gets an answer from the responder that the transfer was rejected because it is a duplicate. For example:  
    RSWIFT(DCmp) \[29\] Server rejected the transfer: duplicated request.
-   The responder receives a possible duplicate transfer and the configuration option <span style="font-weight: bold;">Accept possible duplicate transfers</span> is selected: a warning message is displayed and the transfer is accepted. For example:  
    RSWIFT(DCmp) Duplicated incoming request, with message id "467246F2-5C7E-1D36-302A-6B4100000017", accepted. The configuration option "accept\_possible\_duplicate" is set.  
    Otherwise (if <span style="font-weight: bold;">Accept possible duplicate transfers</span> is not selected), an error message is displayed and the transfer is rejected. For example:  
    RSWIFT(DCmp) Duplicated incoming request, with message id "467246F2-5C7E-1D36-302A-6B4100000017", rejected.

Related topics

[SWIFTNet connector](../../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../swiftnet_connector/swiftnet_working_with)

[Transfers: Parameters List](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

[About C API](../../../../customizing_gw_about/c_api_about)

[SWIFTNet (SNET) log messages](../../../../log_messages_about/swiftnet_messages_(snet))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
