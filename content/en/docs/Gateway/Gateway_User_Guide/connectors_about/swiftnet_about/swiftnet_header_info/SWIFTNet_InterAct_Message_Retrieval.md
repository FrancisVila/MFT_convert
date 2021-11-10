{
    "title": "SWIFTNet InterAct Message Retrieval",
    "linkTitle": "SWIFTNet InterAct Message Retrieval",
    "weight": "320"
}[About SWIFTNet InterAct message retrieval](#top)

[Initiating retrieval request](#Initiati)

[Samples for retrieval request payload](#Samples)

[Receiving retrieval messages](#Receivin)

[Receiving retrieval report](#Receivin2)

[Incoming transfer parameters specific to SWIFTNet retrieved messages](#Incoming)

[New attributes for Decision Rules](#New)

[Retrieved message log](#Retrieve)

## About SWIFTNet InterAct message retrieval

Sent or received InterAct Store-and-Forward messages can be retrieved from the SWIFT network by initiating a retrieval request System Message, which has the request type "<span class="code">xsys.015.001.01</span>".

This retrieval service from SWIFT is very useful if you have lost some messages and want to recover them.

Previously sent or received messages could be recovered only if they were no older than 124 days for LIVE traffic or 4 days for pilot and ITB traffic.

The retrieved messages are delivered using the SWIFTNet store-and-forward service.

> **Note:**
>
>  

-   Only if you have been granted the "<span class="code">swift.snf.system"</span> / <span class="code">"OnlineRetriever</span>" RBAC role are you authorized to send retrieval requests.
-   Optionally, you can request a retrieval report which provides information about failed retrievals.

### Retrieved message flow

**Gateway side**: The user sends a retrieval request which has the request type “<span class="code">xsys.015.001.01</span>”, specifying in the payload data:

-   The retrieval criteria.
-   The store-and-forward queue to which the retrieved messages and optionally the retrieval report are to be queued.

> **Note:**
>
> The queue specified in the retrieval request must have been defined for service “swift.snf.system (!p, !x)”.

**SWIFTNet side**: The retrieval request is being processed and:

-   Retrieved messages are queued to the queue specified in the retrieval request.
-   If the optional retrieval report has also been requested, then the retrieval report, which has the request type “<span class="code">xsys.016.001.01</span>”, is queued to the same queue specified in the request payload.

**Gateway side**: The retrieved messages and the retrieval report are received by the user using the standard store-and-forward delivery mechanism.

The queue specified on the retrieval request must have been opened using an output channel with the element “Receive retrieved messages” set.

Gateway receives all retrieved messages for a request, even if the trading partner configuration has meanwhile been changed from the moment the message was sent or received.

The retrieved messages are distinguished from normal store-and-forward messages by:

-   Specific elements present on the primitive XML request received from SWIFT.
-   Specific transfer parameters added by Gateway.

These elements are detailed in the proceeding sections.

<span id="Initiati"></span>

## Initiating retrieval request

In order to receive a previously sent or received message, you have to submit a retrieval request system message which has the request type "<span class="code">xsys.015.001.01</span>".

For sending a system message to retrieve messages, you need:

**A remote trading partner with a specific configuration**  
For this you can:

-   Reuse the existing system message trading partner “SYSTEM\_MESSAGE” used to receive system messages, by adding a notification queue.

<!-- -->

-   When performing the transfer request for message retrieval, you have to overwrite the request type with "<span class="code">xsys.015.001.01</span>".

or

-   Create a new system message trading partner, similar to the SYSTEM\_MESSAGE trading partner, which is used for receiving system messages, but having:
    -   Request type "<span class="code">xsys.015.001.01</span>”
    -   A notification queue

> **Note:**
>
> For more details about the existing “SYSTEM\_MESSAGE” trading partner, see SYSTEM\_MESSAGES remote Trading Partner.

-   **Payload data specific to retrieval request system message**  
    The payload must contain:
    -   The retrieval criteria for the messages to retrieve.
    -   The Store-and-Forward queue to which the retrieved messages, and optionally the retrieval report, are to be queued.

      
    The <span class="code">xsys.015.001.01</span> retrieval request supports various options that allow you to:
    -   Request the optional retrieval report
    -   Specify the Store-and-Forward queue for retrieved messages
    -   Specify the start of the time range
    -   Retrieve a single message
    -   Retrieve a range of input messages sent
    -   Retrieve a range of output messages received
    -   Specify additional filter criteria

Refer to the SWIFT documentation when creating the payload data for retrieval request.

-   **To perform an InterAct transfer using the information mentioned above**  
    Note that the value for the parameter "payload type” must be “embedded”. This can be set on transfer request or in the remote trading partner used on transfer.

> **Note:**
>
> A single retrieval request can retrieve a range of SWIFTNet messages sent or received in a given 24-hour period. If retrievals are needed over a longer period of time, then multiple retrieval requests must be sent.

<span id="Samples"></span>

## Samples for retrieval request payload

Retrieval request payload for receiving a single message, previously received, with a specific <span class="code">SnFRef</span>:



    <SwInt:RequestPayload> 

    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.015.001.01"> 

    <Doc:xsys.015.001.01> 

    <Doc:RptCrit> 

    <Doc:RprtGnrtnOptn>Always</Doc:RprtGnrtnOptn> 

    <SwInt:Queue>ptsafrkk_generic!x</SwInt:Queue> 

    <Doc:FrTm>2014-03-04T00:00:00Z</Doc:FrTm>

    <Doc:SnglMsgCrit>

    <Doc:OutptCrit>

    <Sw:SnFRef>swi00001-2014-03-04T08:23:29.589.733431Z</Sw:SnFRef>
    </Doc:OutptCrit>

    </Doc:SnglMsgCrit>

    </Doc:RptCrit> 

    </Doc:xsys.015.001.01> 

    </Doc:Document> 

    </SwInt:RequestPayload>

Retrieval request payload for receiving a single message, previously sent, with a specific <span class="code">SnFRef</span>:



    <SwInt:RequestPayload>
    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.015.001.01">
    <Doc:xsys.015.001.01>
    <Doc:RptCrit>
    <Doc:RprtGnrtnOptn>Always</Doc:RprtGnrtnOptn>
    <SwInt:Queue>ptsafrkk_generic!x</SwInt:Queue>
    <Doc:FrTm>2014-03-04T00:00:00Z</Doc:FrTm>
    <Doc:SnglMsgCrit>
    <Doc:InptCrit>
    <Sw:SnFRef>swi00001-2014-03-05T07:20:09.123.66878381Z</Sw:SnFRef>
    </Doc:InptCrit>
    </Doc:SnglMsgCrit>
    </Doc:RptCrit>
    </Doc:xsys.015.001.01>
    </Doc:Document>
    </SwInt:RequestPayload>

Retrieval request payload for receiving multiple messages, based on a range of <span class="code">Sw:SnFOutputSeq</span> - starting sequence number and ending sequence number:



    <SwInt:RequestPayload>
    <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.015.001.01">
    <Doc:xsys.015.001.01>
    <Doc:RptCrit>
    <Doc:RprtGnrtnOptn>Always</Doc:RprtGnrtnOptn>
    <SwInt:Queue>ptsafrkk_generic!x</SwInt:Queue>
    <Doc:FrTm>2013-11-20T00:00:00Z</Doc:FrTm>
    <Doc:MltplMsgCrit>
    <Doc:MaxNm>200</Doc:MaxNm>
    <Doc:OutptSeqCrit>
    <Doc:FrSeq>1</Doc:FrSeq>
    <Sw:OutputChannel>ptsafrkk_rndkrottsfiafa!x</Sw:OutputChannel>
    <Doc:ToSeq>10900</Doc:ToSeq>
    </Doc:OutptSeqCrit>
    </Doc:MltplMsgCrit>
    </Doc:RptCrit>
    </Doc:xsys.015.001.01>
    </Doc:Document>
    </SwInt:RequestPayload>

<span id="Receivin"></span>

## Receiving retrieval messages

Retrieved messages are queued by SWIFT in the queue specified in the retrieval request and received using the standard Store-and-Forward delivery mechanism, like any other InterAct Store-and-Forward message.

You need to have a queue which can receive retrieved messages. It must be defined for service <span class="code">“swift.snf.system (!p, !x)</span>”. Moreover, you must use an output channel for starting the session on the queue, which has the option to receive retrieved messages activated. This can be done from the output channel configuration, from the [UI or command line](../../swiftnet_input_channels/swiftnet_output_channels#swift_op_ch_paras) .

Note that all retrieved messages are accepted by Gateway, regardless of whether the previous trading partner's configuration, used to send or receive the messages, has changed. No validation is made on the Gateway side for trading partner objects when receiving retrieved messages.

Previously sent or received messages are received by Gateway as incoming messages. The direction of the message is mentioned in the xml request from SWIFT.

While retrieved messages are delivered just like other Store-and-Forward messages, they are clearly marked as "retrieved message" by Gateway, after being received:

-   In [log messages](../../../../log_messages_about/swiftnet_messages_(snet)#SNET028I)
-   In incoming transfer parameters, by specifying also the type of the retrieved message (send or received)
-   In additional parameters file, by saving information specific to a retrieved message (<span class="code">Sw:RetrievedDescriptor</span>)

The transfers created for retrieved message entries are linked with the transfer generated for the retrieval request, if this transfer is present in the mailbox.

> **Note:**
>
> No duplicate checking is performed for retrieved messages (normal messages or retrieved messages).

<span id="Receivin2"></span>

## Receiving retrieval report

While performing the request for receiving retrieved messages, you may specify in the payload of the system message request that you want to receive a retrieval report. Depending on the number of retrieved messages matching the request criteria, you may receive one or more retrieval reports for a single retrieval request. The retrieval reports are queued to the same queue as the retrieved messages.

The retrieval reports, which have the request type “<span class="code">xsys.016.001.01</span>”, are received by Gateway due to the existing system message trading partner “<span class="code">SYSTEM\_MESSAGE</span>”, which accepts all types of system messages. If the configuration changed meanwhile, ensure that you have a trading partner for receiving these types of system messages.

The transfers created for retrieval report entries are linked with the transfer generated for the retrieval request, if this transfer is present in the mailbox.

<span id="Incoming"></span>

## Incoming transfer parameters specific to SWIFTNet retrieved messages

After an incoming SnF InterAct transfer is received, when viewing the corresponding transfers details from Gateway UI, parameters specific to retrieved messages are displayed in the Transfer Request dialog, SWIFTNet tab. It contains enough information to identify an InterAct Store and Forward retrieved transfer.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>InterAct sub-tab</p>
<p> </p>         </td>
      </tr>
      <tr>
         <td><p>Retrieved message</p>         </td>
         <td><p>Set only for incoming messages, specify if the received message is a retrieved message or not. Possible values:</p>
<ul>
<li>Yes (Sent) = retrieved message, previously sent</li>
<li>Yes (Received) = retrieved message, previously received</li>
<li>No = not a retrieved message</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>SnF sub-tab</p>         </td>
      </tr>
      <tr>
         <td><p>Response to xfer</p>         </td>
         <td><p>Retrieval request system message, if present in Mailbox</p>         </td>
      </tr>
      <tr>
         <td><p>SWIFTNet tab</p>         </td>
      </tr>
      <tr>
         <td><span class="bold_in_para">Retrieval info
(check box)
</span>         </td>
         <td>In the additional parameters file, the sub-primitive xml specific to a retrieved message is saved every time an incoming retrieved message is received. The name of the xml element is "<span class="code">Sw:RetrievedDescriptor</span>”.         </td>
      </tr>
   </tbody>
</table>

New parameters for retrieved message identification are also available in the command line when displaying transfer details, for example:

peldsp display\_ trans -i 121

\[…\]

x\_retrieval\_info='Y'

x\_sw\_retrieved\_message='Y’

x\_sw\_retrieved\_message\_direction=’sent’

### Specific output transfer parameters

<span class="code">x\_retrieval\_info</span>

-   "<span class="code">Y</span>" - indicates that the additional parameters file contains information specific to a retrieved message on the xml element "<span class="code">SwRetrievedDescriptor</span>”. This element was extracted from the incoming request primitive XML. When a retrieved message is received, this parameter must be set to "Y".
-   "<span class="code">N</span>" – indicates that the additional parameters file does not contain information specific to a retrieved message because it is a normal transfer.

<span class="code">x\_sw\_retrieved\_message</span>

-   "<span class="code">N</span>" – normal message
-   "<span class="code">Y</span>" – retrieved message

<span class="code">x\_sw\_retrieved\_message\_direction</span>

-   "received" – the retrieved message was previously received.
-   "sent" - the retrieved message was previously sent.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">x_retrieval_info</span></p>         </td>
         <td><ul>
<li>"<span class="code">Y</span>" - indicates that the additional parameters file contains information specific to a retrieved message on the xml element „<span class="code">SwRetrievedDescriptor</span>”. This element was extracted from the incoming primitive XML request. When a retrieved message is received, this parameter must be set to "Y".</li>
<li>"<span class="code">N</span>" – indicates that the additional parameters file does not contain information specific to a retrieved message because it is a normal transfer.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">x_sw_retrieved_message</span></p>         </td>
         <td><ul>
<li>"<span class="code">N</span>" – normal message</li>
<li>"<span class="code">Y</span>" – retrieved message</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">x_sw_retrieved_message_direction</span></p>         </td>
         <td><ul>
<li>"received" – the retrieved message was previously received.</li>
<li>"sent" - the retrieved message was previously sent.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="New"></span>

## New attributes for Decision Rules

New attributes for use with Decision Rules:

-   <span class="bold_in_para">sw retrieved message</span> Type: enum (Y, N).

This corresponds to the SWIFTNet <span class="code">sw\_retrieved\_message</span> transfer parameter, set after a message has been received.

-   <span class="bold_in_para">sw retrieved message direction</span> Type: enum (sent, received).

This corresponds to the SWIFTNet <span class="code">sw\_retrieved\_message</span> transfer parameter, set after a message has been received.

Examples of arguments for Decision Rules:

sw retrieved message = Y

sw retrieved message direction = sent

protocol = SWIFTNET

<span id="Retrieve"></span>

## Retrieved message log

For incoming SnF InterAct messages, the log message (SNET028I) informs you about receiving a retrieved message and mentions also the direction of the original message: [sent or received](../../../../log_messages_about/swiftnet_messages_(snet)#SNET028I).

Example:

028 SNET I MESGRECV RSWIFT(DCmp) \[28\] receiving from REMOTE\_TP, (retrieved, sent) message: C:\\retrmsg.

For more information about SWIFTNet InterAct Store-and-Forward message retrieval, refer to the SWIFT documentation.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
