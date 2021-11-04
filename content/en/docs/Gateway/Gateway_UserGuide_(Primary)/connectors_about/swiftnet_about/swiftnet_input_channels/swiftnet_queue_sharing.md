{
    "title": "SWIFTNet queue sharing",
    "linkTitle": "SWIFTNet queue sharing",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#overview)

[Changing the queue sharing mode](#changing_queue_share_mode)

<span id="overview"></span>

## Overview

Output channels allow the opening of multiple sessions for the same queue (queue sharing).

This topic explains how to change the queue sharing mode from *exclusive* to *shared* or vice-versa.

<span id="changing_queue_share_mode"></span>

## Changing the queue sharing mode

You can change the queue sharing mode by sending a system message to SWIFT. To do this, create a SWIFTNet InterAct Store-and-Forward Transfer Request with an embedded message requesting the queue to change sharing mode. In Gateway you send the system message as a transfer requesting the queue to change the mode.

### Example message

The information provided here is an example of the message to send to SWIFT. Adapt the contents according to your own requirements.


    <SwInt:RequestPayload>
      <Ah:AppHdr xmlns:Ah="urn:swift:xsd:$ahV10">
        <Ah:MsgRef>REFERENCE</Ah:MsgRef>
        <Ah:CrDate>DATE</Ah:CrDate>
      </Ah:AppHdr>
      <Doc:Document xmlns:Doc="urn:swift:xsd:xsys.028.001.01">
        <Doc:xsys.028.001.01>
          <SwInt:Queue>QUEUE_NAME_TO_CHANGE_SHARING_MODE</SwInt:Queue>
          <Doc:ShrMd>SHARING_MODE</Doc:ShrMd>
        </Doc:xsys.028.001.01>
      </Doc:Document>
    </SwInt:RequestPayload>

In this message, you need to specify the following parameters:

-   **&lt;Ah:MsgRef>** – the message reference
-   **&lt;Ah:CrDate>** – the date, in the format yy-mm-ddThh:mm:ss (example: 11-06-14T11:40:30)
-   **&lt;SwInt:Queue>** – the name of the queue that you want to change
-   **&lt;Doc:ShrMd>** – the sharing mode:
    -   **Exclusive** - not using output channels
    -   **Shared** - using output channels

Create a Transfer Request, making sure that you use the *embedded* mode for the InterAct message.

### Example peltrans command


    peltrans
       -type MSG
       -direction O
       -mode I
       -file_component CHANGE_QUEUE_SHARING_MODE_SAMPLE_MODIFIED_FILE
       -org_alias LOCAL
       -dest_alias SWIFT
       -trade_org_alias MY_SWIFT_LOCAL
       -trade_dest_alias SWIFT_SYSTEM_SHAREQUEUE
       -appli FTP_B
       -sw_payload_type embedded

### Trading Partner

The destination Trading Partner SWIFT\_SYSTEM\_SHAREQUEUE to which the transfer is sent must contain:

-   DN = cn=system,o=swift,o=swift
-   Service name = swift.snf.system!x (for pilot network) or swift.snf.system (for live network)

### Error message on an acquired queue

You cannot change the queue sharing mode on an acquired queue. If the queue has already been acquired, you will get a message similar to:


    -- 2011/06/14 11:30:06 - ERROR from SwApiSwCallEx
    2011/06/14 11:30:06   Reponse:
    <?xml version="1.0" encoding="UTF-8"?><SwInt:ExchangeResponse><SwInt:SwiftRequestRef>SNL02026-2011-06-14T09:30:18.5748.000135Z</SwInt:SwiftRequestRef><SwGbl:Status>
    <SwGbl:StatusAttributes>
    <SwGbl:Severity>Transient</SwGbl:Severity>
    <SwGbl:Code>Sw.SnF.OutputSessionActive</SwGbl:Code>
    <SwGbl:Parameter>Level=1</SwGbl:Parameter>
    <SwGbl:Text>A session is active on the queue. The share mode cannot be changed while a session is open on the queue</SwGbl:Text>
    </SwGbl:StatusAttributes>
    </SwGbl:Status></SwInt:ExchangeResponse>

In this case, stop the Remote Site that makes use of the queue before modifying it.

Related topics

[SWIFTNet queues and output channels](../swiftnet_output_channels)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
