{
    "title": "SWIFTNet HA overview",
    "linkTitle": "High Availability",
    "weight": "300"
}Standard Gateway installations cannot be scaled horizontally due to limitations of Gateway itself: when correlating an acknowledgment with a previously sent transfer, Gateway must have the transfer in its mailbox. If the transfer was sent by another Gateway or it has been deleted from its mailbox, the acknowledgment is rejected.

The High Availability solution removes this limitation, storing instead necessary transfer information in a shared correlation database. This way, SWIFTNet MRR can be used to distribute the incoming traffic on several Gateway installations running in parallel.

An incoming acknowledgment or notification system message will be correlated against the shared correlation database, instead of the local Gateway mailbox. Information contained in such acknowledgment or notification messages can be routed to a back-end application like Integrator.

> **Note:**
>
> SWIFTNet MRR” refers to "SWIFTNet Message Reception Registry".
> This is the registry of rules that are set by any SWIFT Customer defining the way he expects SWIFTNet to send messages. These MRRs can define nominal and backup connection points inside the Customer’s Information System, as seen from a SWIFTNet Network point of view. These connection points refer either to “SWIFTNet Link” instances or to “StoreAndForward queues”. By defining nominal and backup SWIFTNet Link instances, the SWIFT Network is able to switch in case of failure of the nominal connection. For more information about MRR, refer to the official SWIFT documentation.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
