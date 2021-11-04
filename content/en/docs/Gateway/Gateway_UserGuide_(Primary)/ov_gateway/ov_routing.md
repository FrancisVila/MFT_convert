{
    "title": "Routing",
    "linkTitle": "Routing",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

As described in the [previous topic](../ov_events), the Event management functions in Gateway enable you to use the occurrence of events to trigger processes. One important application of Event management functions is for routing.

<span style="font-style: italic;">Routing</span> is the process of passing a message from one stage in a predefined processing path to the next stage. In most Gateway routing scenarios, Gateway acts as intermediate machine between an originating machine and the final recipient.

In its role as a gateway, Gateway operates as an intermediary site in a Store-and-Forward process, between the file sender and the file receiver. This means that, for each exchange that transits Gateway, at least two file transfer processes are involved, as illustrated in the following figure. Note that the sender and the receiver are represented in Gateway by Remote Site objects.

<img src="/Images/Gateway/routing.png" class="mediumWidth" />

In Gateway, you automate routing by creating and managing Decision Rule objects. In the Decision Rule, you define a set of conditions to apply to the current transfer. For example:

-   Protocol used for the current transfer = FTP
-   Destination = Site A
-   Destination is not the same as the originating Site
-   ...

When all the Decision Rule conditions match those of the current transfer, Gateway applies the execution type specified for this Decision Rule to the transfer.

<span style="font-weight: bold;">Example:</span> To redirect an incoming transfer to Axway Integrator, create a Decision Rule that applies an XIB-type Model to the incoming transfer type. When Gateway detects an incoming transfer of the specified type, it applies the Model, which in turn submits a new Transfer Request to the desired Axway Integrator Site.

You can restrict routing to a limited set of transfers. For example, you could restrict the routing to a certain Site to transfers with the following characteristics:

-   Transfer type: TRANS
-   Transfer status: ENDED or ACKED

[Next topic](../ov_models)

Related topics

[Managing Events on <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](../../managing_events_start_here)

[Transfer states in Gateway](../../transfers_start_here/submitting_transfer_requests_start_here/transfer_states)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
