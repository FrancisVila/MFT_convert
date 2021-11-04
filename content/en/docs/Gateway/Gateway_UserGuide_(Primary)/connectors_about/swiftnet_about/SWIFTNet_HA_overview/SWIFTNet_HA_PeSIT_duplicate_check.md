{
    "title": "PeSIT Duplicate Checking in the context of SWIFTNet High Availability",
    "linkTitle": "PeSIT Duplicate Checking in the context of SWIFTNet High Availability",
    "weight": "350"
}[About PeSIT High Availability](#About)

[Limitations](#Limitati)

[Prerequisites](#Prerequi)

[Enabling the PeSIT Duplicate Checking](#Enabling)

<span id="About"></span>

## About PeSIT High Availability

The PeSIT Duplicate Checking in the context of SWIFTNet High Availability feature is designed to detect duplicate PeSIT incoming transfers and to reject such transfers.

The duplicate check function is performed using the following PeSIT transfer parameters:

-   PI3 (originator)
-   PI4 (destination)
-   PI12 (logical file name)
-   PI13 (transfer ID)
-   PI51 (file creation date)

The parameters are stored in the High Availability Database when the transfer is completed.

When receiving a new transfer/file CREATE request, Gateway performs a search in the High Availability Database based on the 5 parameters mentioned above. If a match is found, the transfer is considered a duplicate and the transfer is aborted. In such a case, Gateway responds with a 204 “File already exists” message.

If Gateway cannot find a match, the transfer proceeds normally.

> **Note:**
>
> PeSIT duplicate checking is performed only on incoming transfers.

### Duplicate Check for incoming PeSIT transfers

If the Duplicate Check function is active, and a duplicate PeSIT transfer is detected, Gateway responds with a 204 “File already exists“ code and the transfer is aborted.

The client software sending the transfer should not attempt to resend it.

<span id="Limitati"></span>

## Limitations

-   PeSIT E HS

Furthermore, the following functions, though not disabled, may not work as expected in a SWIFTNet High Availability configuration:

Setting of synchronization points

The data sender can initiate sequentially numbered synchronization points during the transfer. The data receiver can acknowledge the synchronization points to confirm that the data transferred up to that point has been correctly received and saved. This mechanism is used to restart a transfer after an incident.

When you establish the logical connection between partner Sites, the two Sites can negotiate the following:

-   Synchronization acknowledgment window
-   Interval between synchronization points
-   Whether resynchronization is allowed

Restarting interrupted transfers

Transfer restart enables you to restart a transfer interrupted before its completion. The interruption closes the file and disables the protocol and network connections. It is always the Initiator who initiates the restart and the Receiver who decides from which synchronization point the transfer is to be restarted.

Dynamic synchronization

Dynamic synchronization allows you to ask the partner to restart the transfer from a previous synchronization point, if an incident was encountered during data transfer. The file remains open during this operation, which can be initiated by either Initiator or Responder.

<span id="Prerequi"></span>

## Prerequisites

The PeSIT Duplicate Checking in the context of the SWIFTNet High Availability feature uses the same configuration parameters as the SWIFTNet High Availability. To activate the PeSIT Duplicate Checking in the context of SWIFTNet High Availability, the SWIFTNet High Availability feature must be configured (See [High Availability User Exit Configuration](../swiftnet_ha_user_exit_config))

> **Note:**
>
> The PeSIT Duplicate Checking in the context of the SWIFTNet High Availability feature needs a valid license key in order to function.

Enabling PeSIT Duplicate Checking in the context of SWIFTNet High Availability without a proper license key will result in Gateway PeSIT processes being unable to start.

The license key is the same as for SWIFTNet High Availability.

<span id="Enabling"></span>

## Enabling the PeSIT Duplicate Checking

The PeSIT Duplicate Checking can be individually enabled for PeSIT D and PeSIT E protocols, using the command line configuration tool, as follows:

1.  Enable the PeSIT Duplicate Checking in the context of SWIFTNet High Availability feature from the command line configuration:

> <span class="code">peluconf set -s ft\_phsd duplicate\_userexit\_option 1</span>
>
> or
>
> <span class="code">peluconf set -s ft\_phse duplicate\_userexit\_option 1</span>

1.  Restart Gateway for the change in configuration to take effect.

Except for the activation parameters, the SWIFTNet High Availability feature configuration is shared between PeSIT and SWIFTNet, and performed in the SWIFTNet module (See [High Availability User Exit Configuration](../swiftnet_ha_user_exit_config)). Ensure all the parameters are properly configured before activating the SWIFTNet High Availability feature.

> **Note:**
>
> While the PeSIT Duplicate Checking in the context of SWIFTNet High Availability was designed to function together with SWIFTNet High Availability as a combined solution, it is not necessary to have SWIFTNet High Availability activated in order to use PeSIT Duplicate Checking in the context of High Availability, but it is necessary to have the parameters for the connectivity with database set in the SWIFTNet configuration section.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
