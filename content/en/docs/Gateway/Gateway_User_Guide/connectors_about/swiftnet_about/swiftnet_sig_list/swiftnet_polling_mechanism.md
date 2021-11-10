{
    "title": "SWIFTNet polling mechanism",
    "linkTitle": "SWIFTNet polling mechanism",
    "weight": "330"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#Overview)

[Detecting transfers stuck in intermediary states](#Detectin)

[Performing a GetFileStatus operation](#Performi)

[Configuration parameters](#Configur)

The following sections describe how the SWIFTNet FileAct TransferStatus polling mechanism enables <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to detect transfers stuck in process and update their states accordingly.

<span id="Overview"></span>

## Overview

With help from a file handler application that is part of Swift RA, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> starts a file transfer after sending a request to, or receiving a request from, Swift. File events inform <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> about transfer processing states (Swift TransferStatus). <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> updates the transfer states as necessary after receiving each file event. A transfer reaches a final state when <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> receives a final file event with a TransferState of Completed, Aborted, Failed, Unknown, Rejected or Duplicated.

Rarely, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> cannot receive and process a final file event (for example, because of a high-load network connectivity issue). Then, the transfer state is not updated, and the transfer remains in an intermediary state.

The role of the polling mechanism is to:

-   Detect transfers stuck in intermediary states by determining that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> has stopped receiving file events (FileEvent).
-   Use a parallel Swift-provided mechanism (GetFileStatus) to interrogate Swift about the transfer status.

<span id="Detectin"></span>

## Detecting transfers stuck in intermediary states

A missed file event can result in one of the following states for an in-process transfer:

-   TO\_BEGIN
-   TO\_RESTART
-   CREATED
-   SERVICING
-   PROGRESSING

A transfer can be in the TO\_BEGIN or TO\_RESTART state without being considered stuck.

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> polls, at a user configurable interval, the list of transfers in intermediary states. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> selects for a GetFileStatus operation only transfers that meet the following conditions:

-   Initiated (file request sent to Swift) or received (file request received from Swift)
-   Not in a final state (for example, ENDED, ENDED\_TO\_ACK, CANCELLED).
-   No file events have been received recently. The time to elapse before a transfer is deemed stuck is configurable.

Transfer list polling is a fast method of scanning the transfer list directly from memory, rather than accessing a mailbox file. However, you can enable and disable polling dynamically. The default is disabled.

Even when transfer list polling is disabled, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> at startup scans the transfer list once and updates transfers in intermediary states. However, initiator transfers in TO\_BEGIN or TO\_RESTART states are scheduled for reprocessing and are not selected for GetFileStatus operations.

<span id="Performi"></span>

## Performing a GetFileStatus operation

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> sends a GetFileStatus request to Swift for each selected transfer in a GetFileStatus operation. In return, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> receives the actual TransferState, as if received via a file event. A GetFileStatus request is the equivalent of receiving a file event, resulting in recovering the stuck transfer.

The following are examples of log events for a GetFileStatus operation:

SNET080W 10.05.2011 15:43:31 SAGLIVEGTW(rnd9\_mp) \[100\] Checking status for pending FileAct transfer.

SNET080W 10.05.2011 15:45:12 SAGLIVEGTW(rnd9\_mp) \[100\] Swift status for pending FileAct transfer is: Completed; updating transfer state

<span id="Configur"></span>

## Configuration parameters

The transfer status polling interval parameter specifies the frequency <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> scans the transfer list. The transfer status polling delay parameter specifies the time to elapse before a transfer is deemed stuck. The following provides more details:

-   <span class="bold_in_para">Transfer status polling interval</span>. The interval in seconds the transfer list is scanned for GetFileStatus operation candidates. A value of <span class="bold_in_para">0</span> disables polling.
-   <span class="bold_in_para">Transfer status polling delay</span>. Seconds elapsed since the last file event.

SWIFT keeps a history of completed transfer information, but there are limitations on the number and age of stored transfers. The polling mechanism might be triggered for a transfer that no longer has FileStatus information available. If so, the transfer is canceled and an error writes to the log.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
