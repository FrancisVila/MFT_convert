{
    "title": "SWIFTNet state transitions ",
    "linkTitle": "SWIFTNet state transitions",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About SWIFTNet state transitions in Gateway](#about)

[State transitions in current version of Gateway](#current_version)

[State transitions in Gateway 6.11](#6_11_version)

[Backwards compatibility](#backwards_compatibility)

[State transitions for duplicate transfers](#duplicates)

<span id="about"></span>

## About SWIFTNet state transitions in Gateway

In Gateway, final state transitions for SWIFTNet transfers are different from those in other protocols. This is because SWIFTNet is not really a protocol implemented in Gateway but a connector to the SWIFT network. The internal states of SWIFTNet transfers are fundamentally different and more complex than for the other protocols supported by Gateway. This is why an internal state has been chosen for each relevant step of the internal SWIFTNet transitions.

The SWIFTNet way of handling transfers is quite different from that used by the protocols originally implemented in Gateway. Experience has shown that the SWIFTNet state transition behavior in Gateway 6.11 was not ideal. Therefore from Gateway 6.12 onwards some of the SWIFTNet state transitions have been changed to be more coherent. Note however that the behavior is not backward compatible with 6.11. This topic explains the main differences.

This topic also explains the special case of state transitions for duplicate transfers.

<span id="current_version"></span>

## State transitions in current version of Gateway

In theory, all transfers that do not require an acknowledgement should end in the ENDED state. However, due to the particularities of SWIFTNet this is not always the case.

Transfers that do require acknowledgement only use the ENDED\_TO\_ACK and ACKNOWLEDGED states.

### FileAct / Real Time

All transfers (incoming and outgoing) that do not require an acknowledgement remain in the ENDED state.

Transfers (incoming and outgoing) that require acknowledgement do not use the ENDED state. They remain in the ENDED\_TO\_ACK state until the acknowledgement is received or sent and then they switch to ACKNOWLEDGED or NACK BY XFB/ NACK BY USER.

### FileAct / Store-and-Forward

For Store-and-Forward messages, the acknowledgement is mandatory and does not have the same meaning as for Real Time. In this case the acknowledgement should not be used for business logic but only to inform the SWIFT network that the file has been safely stored. This is why all incoming transfers skip the ENDED state and go directly to ENDED\_TO\_ACK and then to ACKNOWLEDGED.

For outgoing transfers the situation is slightly different. If the sender does not require acknowledgement it does not wait for it and SWIFT will not send a delivery notification after the receiver has successfully retrieved the file. This means that Store-and-Forward transfers that do not require acknowledgement simply remain in the ENDED state. Store-and-Forward transfers that do require acknowledgement go directly to ENDED\_TO\_ACK and then to ACKNOWLEDGED.

<span id="6_11_version"></span>

## State transitions in Gateway 6.11

### Outgoing

For outgoing transfers there is no difference in behavior between Gateway 6.11 and this version of Gateway.

### Incoming FileAct/ Real Time

There are differences for incoming FileAct/ Real Time transfers that require acknowledgement and use **Receipt option** = *Ack by monitor* in the Trading Partner. In Gateway 6.11 these transfers used all the final states: ENDED, then ENDED\_TO\_ACK, and then ACKNOWLEDGED.

### Incoming FileAct/ Store-and-Forward

There are also differences for all incoming FileAct/ Store-and-Forward transfers. In Gateway 6.11 these transfers went directly to ENDED state.

<span id="backwards_compatibility"></span>

## Backwards compatibility

### Previous and current SWIFTNet transfer state transitions for incoming transfers

This table summarizes the different SWIFTNet transfer state transition behavior for incoming transfers between Gateway versions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">SWIFTNet message type and mode         </th>
<th class="HeadE-Column1-Header1">Acknowledgement?         </th>
<th class="HeadE-Column1-Header1">Transfer state         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">6.11         </th>
<th style="text-align: center;" class="HeadD-Column1-Header1">6.12 onwards         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>FileAct / Real Time         </td>
         <td>No Ack         </td>
         <td>E         </td>
         <td>YES         </td>
         <td>YES         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>Ack By Monitor         </td>
         <td>E         </td>
         <td>YES         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>YES         </td>
         <td>YES         </td>
      </tr>
      <tr>
         <td>Ack By User         </td>
         <td>E         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>YES         </td>
         <td>YES         </td>
      </tr>
      <tr>
         <td>FileAct / Store-and-Forward         </td>
         <td>No Ack         </td>
         <td>E         </td>
         <td>YES         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>-         </td>
         <td>YES         </td>
      </tr>
      <tr>
         <td>Ack By Monitor         </td>
         <td>E         </td>
         <td>YES         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>-         </td>
         <td>YES         </td>
      </tr>
      <tr>
         <td>Ack By User         </td>
         <td>E         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>W then A         </td>
         <td>-         </td>
         <td>YES         </td>
      </tr>
   </tbody>
</table>

**Legend**

YES = corresponding state is routed

Transfer states:

-   E = Ended
-   W = Ended\_to\_ack
-   A = Acked

<span id="duplicates"></span>

## State transitions for duplicate transfers

State transitions for duplicate transfers depend on the global parameter <span class="code">accept\_possible\_duplicate</span>. If this parameter is set to YES, then the Possible Duplicate indication is ignored and the transfer behaves as any normal transfer. If however this parameter is set to NO, then the state transitions behave as explained below.

### FileAct / Real Time when <span class="code">accept\_possible\_duplicate=NO</span>

#### Outgoing

Outgoing duplicate transfers that do *not* require acknowledgement remain in the CANCELLED state.

Outgoing duplicate transfers that do require acknowledgement stay in the CANCELLED state until the acknowledgement has been received. They then go to ACKNOWLEDGED.

#### Incoming

Incoming duplicate transfers are saved in the Mailbox. They behave as any normal FileAct / Real Time incoming transfer.

### FileAct / Store-and-Forward when <span class="code">accept\_possible\_duplicate=NO</span>

#### Outgoing

Outgoing duplicate transfers that do *not* require delivery notification remain in the ENDED state.

Outgoing duplicate transfers that do require delivery notification stay in the ENDED-TO-ACK state until the delivery notification arrives. They then go to NACK.

#### Incoming

Incoming duplicate transfers are simply rejected by Gateway if the original file exists. They do not appear as Mailbox entries.

Related topics

[SWIFTNet connector](../../swiftnet_connector)

[Configuration: Gateway parameters](../../../../configuration_start_here/config_gateway_paras)

[Possible Duplicate management for SWIFTNet](../swiftnet_possible_duplicate)

[Transfer states in Gateway](../../../../transfers_start_here/submitting_transfer_requests_start_here/transfer_states)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
