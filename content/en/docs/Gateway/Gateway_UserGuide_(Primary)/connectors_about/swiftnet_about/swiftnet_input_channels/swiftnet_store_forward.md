{
    "title": "SWIFTNet Store-and-Forward Cold Start",
    "linkTitle": "SWIFTNet Cold Start",
    "weight": "320"
}## Overview

SWIFTNet Store-and-Forward Cold Start is an exceptional situation in which SWIFT has to restore the Store-and-Forward service from an empty state. When a SWIFTNet Cold Start occurs, all traffic and data in the Store-and-Forward system is lost, queues are reset to Exclusive mode and non-generic input channels and non-default output channels are deleted.

Gateway offers mechanisms allowing you to detect the occurrence of a Cold Start, and offers guidelines on how to resume normal operation.

> **Note:**
>
> Currently, SWIFTNet Store-and-Forward messaging is exclusively housed in the European SWIFTNet zone. If this zone is subjected to a Cold Start, Store-and-Forward traffic will be lost for all SWIFTNet zones.

## After a Cold Start

After the SWIFTNet Store-and-Forward system resumes its operation following a Cold Start, its state is as follows:

-   The transfers awaiting delivery in the intended recipients queues in the Store-and-Forward system are lost (including positively acknowledged messages and files). It is the responsibility of each sending partner to take action in re-sending the transfers with an uncertain delivery status, marked as Possible Duplicates. SWIFT makes no further delivery attempts for these messages and files.
-   Historical data related to message receipts or message delivery before the Cold Start is lost.
-   The SWIFTNet queues are reset to an Exclusive share mode. All non-default output channels and all non-generic input channels are removed.
-   All Input Sequence Numbers on the generic input channels, and all Output Sequence Numbers on the default output channels are reset to 0.
-   The database identifier specified in the `Sw:SnFInputTime` changes, as if the BIC was reassigned to a new database.
-   The SWIFTNet infrastructure resumes its operation in the default post-Cold Start configuration, i.e. the users can connect, send and receive files and messages using the generic output channels and default input channels.

In effect, you must perform the following actions to resume operation:

-   Update queue sharing modes to reflect the pre-Cold Start state. For more information, see [SWIFTNet queue sharing](../swiftnet_queue_sharing).
-   Recreate the non-default output channels and the non-generic input channels, according to the pre-Cold Start configuration. The [SWIFTNet queues and output channels](../swiftnet_output_channels) and [Controlling output channels](../swiftnet_output_channels#control_op) sections describe how to create output channels using Gateway. For creating input channels, see [SWIFTNet input channels](../).
-   Resend transfers with an uncertain delivery status, marked as Possible Duplicates.

For more information, see [Resuming Normal Operations](#Resuming).

## Detecting a SWIFTNet Store-and-Forward Cold Start

A SWIFTNet Store-and-Forward Cold Start follows a period in which Gateway was unable to communicate with the SWIFT system. However, it is important to differentiate between a Cold Start and normal connectivity issues (including those generating a system recovery).

In the case of prolonged SWIFTNet unavailability, you can go to the SWIFT page (www.swift.com) and check for information, or contact the SWIFT support. It is thus possible to obtain the information that a Cold Start just occurred over the Store-and-Forward infrastructure, in this way.

Another method of detecting a Store-and-Forward Cold Start is the receipt of an Unsolicited Undelivered Traffic Report system message (xsys.005.002.01). SWIFT will queue an Unsolicited Undelivered Traffic Report system message after a Cold Start for the generic queue of each BIC8. For more information, see [Unsolicited Undelivered Traffic Reports](#Unsolici).

Gateway receives and logs these system messages, as long as the generic queue is successfully acquired or its associated output channel is successfully opened. For this, a SWIFT Remote Site must be configured with the generic queue, and must be started after the SWIFTNet system’s operation recovers after encountering connectivity issues. Failure to do this could result in the inability to detect a Cold Start situation, and perform the operations required to correctly resume normal operation.

## Example of Gateway logging an incoming Unsolicited Undelivered Traffic Report

<span class="code">SNET044I 15.10.2013 19:37:01 SAGLIVEGTW(rnd9\_mp)</span> Unsolicited Undelivered Traffic Report system message identified at check-in (looking for Trading Partner).

<span class="code">SNET143W 15.10.2013 19:37:01 SAGLIVEGTW(rnd9\_mp) \[117\]</span> received Unsolicited Undelivered Traffic Report (xsys.005.002.01) generated after Cold Start. ReportOption: CS; Page number: 1; is last page: Yes; execution status: Success.

In cases where a Store-and-Forward Cold Start was detected, appropriate actions should be taken before resuming normal operations, as described in the following sections.

If the SWIFTNet unavailability was not related to a Cold Start, none of the described actions should be taken.

If the SWIFTNet connectivity is lost for extended periods, it is recommended to stop the SWIFTNet Remote Sites until SWIFT is functional again. This is to avoid repeated attempts to reestablish the connection. The SWIFTNet system availability should be determined either by periodically attempting to restart a SWIFT Remote Site, by using the <span class="code">sag\_test\_connect</span> tool provided by RAHA installation, or by checking with SWIFT.

This would be done regardless of what caused the connectivity loss, as before reestablishing connectivity it is not possible to determine if a Cold Start occurred (except if communicated by SWIFT).

<span id="Unsolici"></span>

## Unsolicited Undelivered Traffic Reports

Immediately after a Store-and-Forward Cold Start, SWIFTNet queues the Unsolicited Undelivered Traffic Reports system message (xsys.005.002.01) to the generic queues of each BIC8. In order to receive this system message, after regaining SWIFTNet connectivity the generic queue corresponding to your BIC must be acquired, or its associated output channel must be opened.

To receive an Unsolicited Undelivered Traffic Report system message after a connectivity loss:

1.  Ensure the SWIFTNet Store-and-Forward system is available. This can be done by starting a SWIFTNet Remote Site which has a queue or a default open channel configured. If the Remote Site starts successfully and it acquires the queue or opens the default output channel, SWIFTNet Store-and-Forward system can be considered functional.
2.  Acquire the BIC8’s generic queue, or open its default output channel. Note that after a Cold Start, the queue sharing mode is reset to Exclusive. If it remains in the Shared mode (if previously set), this would be an indication that a Cold Start has not occurred.  
    Opening the default output channel of the generic queue with the System subset would ensure that only system messages are delivered. This way Unsolicited Undelivered Traffic Reports and other Cold Started-related system messages can be received and fully processed before receiving business-related messages.  
    It is possible to receive the Unsolicited Undelivered System Messages on a non-default output channel. For this, you would have to change the generic queue sharing mode to Shared, and (re)create non-default output channels for the generic queue before attempting to open the output channel.  
    After a successful acquire of the BIC8’s generic queue or open of its associated output channel, in the event of a Cold Start, an Unsolicited Undelivered Traffic Report (xsys.005.002.01), system message should be received.

### Recommendations regarding the shared generic queue configuration

There are situations in which more than one Messaging Interface (Gateway) would use the same BIC8, and might share the associated generic queue. However, after a Cold Start the generic queue is in Exclusive mode, and only its default output channel exists.

It is recommended to designate a single Messaging Interface for receiving Unsolicited Undelivered Traffic Reports. The designated Messaging Interface could be configured to open the default output channel of the generic queue with the System subset, which would work in either Shared or Exclusive modes.

Configuring more than one Messaging Interface (Gateways) to receive Unsolicited Undelivered Traffic Reports is possible, but not recommended. In any case, you must know precisely which Messaging Interfaces can receive Cold Start-related system messages and monitor them accordingly.

## Processing Unsolicited Undelivered Traffic Report (xsys.005.002.01) system messages.

Gateway does not automatically process Undelivered Traffic Report system messages. However, it detects and logs receipt allowing manual actions to be taken to ensure the correct resumption of the normal operations following a Cold Start.

The Undelivered Traffic Report system messages contain an Undelivered Message List, with a sequence of Undelivered Message information. For a complete description of the structure of an Undelivered Traffic Report and an Undelivered Message List, please consult the SWIFTNet documentation.

The information logged by Gateway includes:

-   The transfer identifier associated with the Unsolicited Undelivered Traffic Report system message
-   The type of system message
-   The page number
-   Whether it's the last page
-   The report option

The transfer identifier associated with the Unsolicited Undelivered Traffic Report system message can be used to retrieve the payload which contains the system message itself (and the Undelivered Message List)

If there are too many Undelivered Messages, the Unsolicited Undelivered Traffic Report will be split into multiple pages, and a system message will be received for each page. The page number and the last page indicator can be used to recompose the complete Undelivered Message List.

For an Unsolicited Undelivered Traffic Report generated by a Store-and-Forward Cold Start operation, the report option field will be ‘CS’.

> **Note:**
>
> The payload file(s) must to be shared with all the message interfaces belonging to the company (share the same BIC8), because the restore actions involve all of them, not only the message interface acquiring the generic queue or opening his (default) output channel. For more information, see Undelivered Traffic Report payload and Processing the Undelivered Traffic Report payload.

### Solicited and Unsolicited Undelivered Traffic Report system messages.

SWIFTNet offers the possibility of interrogating the Store-and-Forward system about the Undelivered Traffic - files and messages sent but not yet delivered. This is done by sending an Undelivered Traffic Report Request (xsys.004.001.01) system message to the SWIFTNet Store-and-Forward system.

There are however differences between the Solicited (xsys.005.001.01) and the Unsolicited (xsys.005.002.01) Undelivered Traffic Reports regarding which information they retrieve. Additionally, there is no system message to request an Unsolicited Undelivered Traffic Report.

The Unsolicited Undelivered Traffic Report contains information about undelivered traffic (associated with a BIC8) which was in the Store-and-Forward system before a Cold Start event occurred, ignoring the pending traffic initiated after the Cold Start. This system message is automatically queued to each BIC8 generic queue after the Store-and-Forward system resumes operation.

In contrast with the Unsolicited Undelivered Traffic Report, the *Solicited* Undelivered Traffic Report can be requested by sending a request (xsys.004.001.01) to SWIFTNet. It also contains information about the current pending traffic. If requested after a Cold Start, this report contains information about the pending Store-and-Forward traffic initiated after the Cold Start. No information about the traffic lost due to the Cold Start is provided.

<span id="Undelive"></span>

### Undelivered Traffic Report payload

An Undelivered Traffic Report contains a sequence of Undelivered Message information (this can be missing if there is no undelivered traffic to report).

You should monitor Gateway’s log, detect the receipt of the Unsolicited Undelivered Traffic Report system message(s), reformat the full Undelivered Message list (if the report is sent in more than one page) and forward the information to an appropriate authority, for processing.

Note that the situation may arise where pieces of reports are received by different message interfaces (if the generic queue has assigned output channels opened by multiple message interfaces). In this case the reports should be centralized for processing.

<span id="Processi"></span>

### Processing the Undelivered Traffic Report payload

Processing the Undelivered Traffic Report payload involves determining which traffic should be resent.

If re-queuing a message or a file to be sent is decided, the corresponding transfer will have to be marked as a Possible Duplicate. For more information, see [Possible Duplicate management for SWIFTNet](../../swiftnet_backup_sites/swiftnet_possible_duplicate).

<span id="Resuming"></span>

## Resuming Normal Operations

In order to completely resume normal operations following a SWIFTNet Store-and-Forward Cold Start, the following procedure must be followed by all message interfaces:

-   Detect the availability of Store-and-Forward: confirm that the Store-and-Forward system is operational, by:
    1.  verifying that the Gateway SWIFTNet processes are running and connected to SWIFT

    <!-- -->

    1.  checking that at least one queue was acquired, or at least one output channel was successfully opened
-   Re-create the non-generic input channels and the non-default output channels (output channels with a name other than that of a corresponding queue) according to the pre-Cold Start configuration.
-   Set the Shared mode for queues which were shared before the Cold Start. Changing a queue sharing mode is described in [SWIFTNet queue sharing](../swiftnet_queue_sharing).
-   Resume normal operations.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
