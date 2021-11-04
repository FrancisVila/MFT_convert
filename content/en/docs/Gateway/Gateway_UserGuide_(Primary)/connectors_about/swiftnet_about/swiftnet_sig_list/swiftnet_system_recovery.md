{
    "title": "SWIFTNet system recovery",
    "linkTitle": "SWIFTNet system recovery",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#overview)

[Automatic system recovery](#automatic)

[Selecting marked transfers](#select)

[Displaying transfer details](#display)

[Manually resending lost transfers](#resending_lost)

<span id="overview"></span>

## Overview

System recovery ensures that all SWIFTNet Store-and-Forward transfers are successfully sent to the partner even in case of a SWIFT network crash.

Gateway has an automatic mechanism to detect a potential SWIFT crash based on output session events and the last replication time on the SWIFT side. When Gateway detects a system recovery from SWIFT, it performs a scan of all SWIFT SnF outgoing transfers to see if there is a risk that they were made after the last SWIFT database replication and marks them accordingly.

You can then manually re-send the files that were detected by using a specific algorithm (manually setting possible duplicates, using the right creation time, and so on).

<span id="automatic"></span>

## Automatic system recovery

Automatic system recovery is triggered by the following actions:

-   Each time Gateway starts: Gateway automatically asks SWIFT for the replication history and triggers the system recovery procedure if a crash occurred while it was offline.
-   When Gateway receives a message from SWIFT that an output session was closed, after the SnF infrastructure is back online (signaled by the ability to open a new output session) Gateway asks SWIFT for the replication history and triggers the system recovery procedure if a crash occurred when the output session was closed.

<span id="manual"></span>

## Manual system recovery

In addition to the automatic system recovery detection, you can trigger the detection procedure manually using the `pelctl detect_swift_recovery` command.

<span id="select"></span>

## Selecting marked transfers

When selecting transfers using the <span class="codeBold_in_para">peldsp select\_trans</span> command, you can use the selection filter <span class="code">-sw\_marked\_by\_system\_recovery (-swmksysrec) { U | Y | N }</span> where:

-   U = Undefined (default)
-   Y = Transfers marked by system recovery
-   N = Transfers that were not marked

<span id="display"></span>

## Displaying transfer details

Use the <span class="codeBold_in_para">peldsp display\_trans</span> command to display the details of a transfer.

In the details, Gateway displays information about system recovery such as:

<span class="code">x\_sw\_marked\_by\_system\_recovery='Y|N'</span>

<span id="resending_lost"></span>

## Manually resending lost transfers

You must manually resend each lost transfer detected during the system recovery procedure using the <span class="codeBold_in_para">peltrans</span> command. In addition to the original parameters of each transfer, manually set the following parameters:

-   The Possible Duplicate indicator <span class="code">sw\_pd\_indication</span>
-   Exactly the same message id as the original transfer
-   Exactly the same creation time as the original transfer with the <span class="code">sw\_creation\_time</span> parameter

Related topics

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../swiftnet_connector/swiftnet_working_with)

[Possible Duplicate management for SWIFTNet](../../swiftnet_backup_sites/swiftnet_possible_duplicate)

[Transfers: Parameters List](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
