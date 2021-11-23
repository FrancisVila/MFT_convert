{
    "title": "Transfer states in Gateway ",
    "linkTitle": "Transfer states",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Transfers

## Introduction

Gateway offers the possibility to enable additional processing based on events that occur during its functioning. One such event, which is an important feature of Gateway, is routing. Routing is triggered by a change in state of a transfer.

This section examines the meaning of each transfer state, the difference between apparently similar states and the state changes which trigger a routing event.

## Transfer states

During its life cycle a transfer can have different processing phases, called states. There are three major phases that are common to all transfers: the beginning phase, the processing phase and the end of transfer phase. Depending on configuration options and on the protocol used, different states can correspond to each of these phases.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Beginning phase         </th>
<th class="HeadE-Column1-Header1">Processing phase         </th>
<th class="HeadD-Column1-Header1">End of transfer phase         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><ul>
<li>To begin</li>
<li>To restart</li>
<li>Frozen</li>
<li>Delayed</li>
<li>Created</li>
<li>To pack</li>
<li>Packing</li>
<li>To sign</li>
</ul>         </td>
         <td><ul>
<li>Processing</li>
<li>Processing (responder)</li>
<li>Suspended</li>
<li>Interrupted</li>
</ul>         </td>
         <td><ul>
<li>Ended</li>
<li>To ack</li>
<li>Acknowledged</li>
<li>Nack by user</li>
<li>Nack by XFB</li>
<li>Ended routing</li>
<li>Cancelled routing</li>
<li>Cancelled</li>
<li>To unpack</li>
<li>Unpacking</li>
<li>Ended third party failed (*)</li>
<li>Ended third party authorized (*)</li>
<li>Acked third party failed (*)</li>
<li>Acked third party authorized (*)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

(\*) These states are specific to SWIFTNet transfers.

### Calculated states

Some of these states are calculated by taking into account the state, route state and trade state. These states offer a global overview of what is actually happening with the transfer (trade decoding/encoding, routing).

#### Examples:

*Cancelled routing* means that the transfer will not be routed.

*Unpacking* means that the transfer is ended and a trade processing is in progress.

This table lists the calculated states:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Calculated state         </th>
<th class="HeadE-Column1-Header1">State         </th>
<th class="HeadE-Column1-Header1">Route state         </th>
<th class="HeadD-Column1-Header1"><p>Trade state</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>To pack         </td>
         <td>To begin         </td>
         <td>          </td>
         <td>To process         </td>
      </tr>
      <tr>
         <td>Packing         </td>
         <td>To begin         </td>
         <td>          </td>
         <td><p>Processing</p>         </td>
      </tr>
      <tr>
         <td>To Unpack         </td>
         <td><p>Ended</p>
<p>Ended to ack</p>
<p>Acknowledged</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td>          </td>
         <td>To process         </td>
      </tr>
      <tr>
         <td>Unpacking         </td>
         <td><p>Ended</p>
<p>Ended to ack</p>
<p>Acknowledged</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td>          </td>
         <td><p>Processing</p>         </td>
      </tr>
      <tr>
         <td>Ended wait receipt         </td>
         <td><p>Ended</p>
<p>Ended to ack</p>
<p>Acknowledged</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td>          </td>
         <td><p>Trade wait receipt</p>         </td>
      </tr>
      <tr>
         <td>Ended third party failed         </td>
         <td><p>Ended</p>
<p>Ended to ack</p>         </td>
         <td>          </td>
         <td><p>Trade third party failed</p>
<p>Trade third party rejected</p>         </td>
      </tr>
      <tr>
         <td>Ended third party authorized         </td>
         <td><p>Acknowledged</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td>          </td>
         <td><p>Trade third party authorized</p>         </td>
      </tr>
      <tr>
         <td>Acked third party failed         </td>
         <td><p>Ended</p>
<p>Ended to ack</p>         </td>
         <td>          </td>
         <td><p>Trade third party failed</p>
<p>Trade third party rejected</p>         </td>
      </tr>
      <tr>
         <td>Acked third party authorized         </td>
         <td><p>Acknowledged</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td>          </td>
         <td><p>Trade third party authorized</p>         </td>
      </tr>
      <tr>
         <td>Ended routing         </td>
         <td><p>Ended</p>
<p>Nack by user</p>
<p>Nack by XFB</p>         </td>
         <td><p>May route</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Cancelled routing         </td>
         <td>Cancelled         </td>
         <td><p>May route</p>         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

The calculated state field is used in internal processing for handling state transitions. For all other cases not listed in this table the State field is used as calculated state.

Note that *Ended routing* means that the transfer is scheduled for routing and *Cancelled routing* means that the transfer will not be routed.

## State transitions

During the life cycle of a transfer, each change of state represents a transition – an event which triggers notif (notification) processes within Gateway. These processes are responsible for:

-   Routing
-   Connection to other software products (such as Sentinel)
-   Calendar event scheduling
-   and so on

#### State transitions for transfers in responder mode

Created &gt;&gt;&gt; Processing (responder) &gt;&gt;&gt; Ended routing &gt;&gt;&gt; Ended

#### State transitions for transfers in initiator mode

Frozen &gt;&gt;&gt; To begin &gt;&gt;&gt; Processing &gt;&gt;&gt; Ended routing &gt;&gt;&gt; Ended

The states are listed in the [Route transfer states configuration menu](../../../configuration_start_here/config_gateway_paras#Route_transfer_states). When a transfer reaches a configured state, router processing is triggered, meaning that the Decision Rule selection is started. Each transition to one of these configured states leads to Rule Table evaluation and Decision Rule triggering.

**Example:** By default the *Ended routing* state is selected. Each time a transfer ends, whether it was routed or not, Rule Table evaluation takes place. In this case, if you configure the *Ended* state to be notified to the routing process, you will see two Rule Table events triggered - one for each state. This happens due to the transition from *Ended routing* to *Ended*, because this whole notification mechanism is based on calculated transfer state changes.

By default, to avoid double notifications and to cover the majority of use cases, only a few states are selected. This setting can be considered the safest and avoids any unexpected behavior. We therefore recommend that you leave this setting unchanged.

### Routing with SWIFTNet

When using SWIFTNet, Gateway does not know immediately if a routed transfer has ended successfully or not. Protocol-specific acknowledgments may be received some time after a transfer ends. Initially Gateway assumes a positive ack and the transfer is considered ended (*Ended to ack*).

It could happen that a negative answer is received from the partner and the transfer has to be cancelled.

In the Route transfer states configuration menu, the *Cancelled routing* state is configured by default. However, the *Nack by XFB* state is not configured by default. This might not be enough to trigger Rule Table evaluation.

Even if the state transition occurs (*Ended to ack* &gt;&gt;&gt; *Nack by XFB*), as the final state is not configured, Rule Table evaluation is not triggered.

#### Ensuring that routing is triggered with SWIFTNet

We recommend that you enable the *Nack by XFB* state in the [Route transfer states configuration menu](../../../configuration_start_here/config_gateway_paras#Route_transfer_states).

## Route State Transitions

The following table shows which results trigger which route state transitions:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Route state         </th>
<th class="HeadE-Column1-Header1">Transitions to         </th>
<th class="HeadD-Column1-Header1">When         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>XFER_TO_ROUTE         </td>
         <td>XFER_ROUTED         </td>
         <td>Successfully route transfer to XIB/another transfer         </td>
      </tr>
      <tr>
         <td>XFER_EN_ROUTE         </td>
         <td>Transfer switched to ended state         </td>
      </tr>
      <tr>
         <td>XFER_ROUTED         </td>
         <td>Not applicable         </td>
      </tr>
      <tr>
         <td>XFER_ROUTE_FAILED         </td>
      </tr>
      <tr>
         <td>XFER_NOT_ROUTED / XFER_NOT_TO_ROUTE         </td>
         <td>XFER_ROUTED         </td>
         <td>Routing is done on ACKED state, incoming transfer         </td>
      </tr>
      <tr>
         <td>XFER_EN_ROUTE         </td>
         <td>XFER_NOT_ROUTED         </td>
         <td>Transfer passed into Ended-to-ACK and direction was incoming         </td>
      </tr>
      <tr>
         <td>XFER_ROUTE_FAILED         </td>
         <td>Not able to perform routing, calling of a script does not count         </td>
      </tr>
      <tr>
         <td>XFER_MAY_ROUTE / XFER_EN_ROUTE         </td>
         <td>XFER_ROUTE_FAILED         </td>
         <td>Not able to perform routing, calling of a script does not count         </td>
      </tr>
      <tr>
         <td>XFER_NOT_ROUTED         </td>
         <td>Transfer is ended and direction is incoming and no routing was done         </td>
      </tr>
      <tr>
         <td>XFER_NOT_TO_ROUTE         </td>
         <td>Transfer is ended and direction is outgoing         </td>
      </tr>
      <tr>
         <td>XFER_ACKED         </td>
         <td>XFER_ACKED         </td>
         <td>It is a final state so there are no transitions from it. The <code>route_state</code> becomes Acknowledged ("A") if the routed transfer is acknowledged         </td>
      </tr>
   </tbody>
</table>

Related topics

[Overview: File Transfers and Transfer Requests](../../../ov_gateway/ov_file_transfers)

[Overview: Routing](../../../ov_gateway/ov_routing)

[SWIFTNet state transitions](../../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_state_transitions)

[Managing Events on Gateway](../../../managing_events_start_here)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
