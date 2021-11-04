{
    "title": "Gateway RMA check",
    "linkTitle": "SWIFTNET RMA check",
    "weight": "320"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About RMA traffic filtering for SWIFTNet](#About)

[Prerequisites](#Prerequi)

[Enabling RMA authorization checking](#Enabling)

[RMA user exit library load](#RMA)

[Scope of RMA checking](#Scope)

The following sections provide information about <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> support for Relationship Management Application (RMA) authorization checking.

> **Note:**
>
> The Gateway RMA component is delivered with the Gateway kit, and is installed only if the license key contains the Gateway RMA option.

<span id="About"></span>

## About RMA traffic filtering for SWIFTNet

Relationship Management Application (RMA) is a SWIFTNet service that allows customers to control the traffic they are willing to accept from other customers.

By enabling the RMA filtering support in <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, RMA authorization checking is performed at the sender or receiver side using an RMA user exit library. This enables the user to stop unwanted traffic. The exit library is delivered with the Gateway RMA component upon installation, only if the license key contains the RMA option, which is a component that manages RMA authorizations.

Based on the Application Service Profile (ASP) check, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> determines which services require RMA interface authorization. RMA filtering user exit is called before sending a transfer request or after receiving a transfer request using a service requesting RMA filtering. Depending on the RMA authorization check result, the transfer:

-   Continues if valid RMA authorization is found
-   Aborts if no authorization or no valid authorization is found for outgoing requests
-   Rejects if no authorization or no valid authorization is found for incoming requests

For more information, refer to the Gateway RMA section of the documentation

<span id="Prerequi"></span>

## Prerequisites

Do the following before using <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to perform RMA authorization checking:

-   Enable ASP and RMA checking (see <a href="../swiftnet_asp_check" class="MCXref xref">SWIFTNet ASP check</a>).
-   Install Gateway RMA and configure it as described in the Gateway RMA section of the documentation.
-   Set the locations of the RMA user exit library and the RMA user exit configuration file delivered with Gateway RMA.

> **Note:**
>
> The Gateway RMA feature needs a valid license key in order to function.
> Enabling Gateway RMA without a proper license key will result in Gateway SWIFTNet processes being unable to start.

<span id="Enabling"></span>

## Enabling RMA authorization checking

You must configure global parameters before using the Gateway RMA authorization check functionality:

Use the following steps to enable Gateway RMA authorization checking and set the paths to the RMA user exit library and RMA user exit configuration file.

1.  In the left pane of the main window in the user interface, right-click the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> server to enable for RMA checking and select <span class="bold_in_para">Configure</span>. The Configuration window is displayed.
2.  In the left pane of the Configuration window, select <span class="bold_in_para">Connectivity > Axway Connectivity > SWIFTNet (ASP/RMA tab)</span>.
3.  Enable RMA checking by selecting <span class="bold_in_para">ASP & RMA enabled</span>. Both ASP and RMA checks are performed.  
    For details see <a href="../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet" class="MCXref xref">Connectivity &gt; Axway Connectivity &gt; SWIFTNet</a>
4.  Specify the following:
    -   Path to the user exit library in the RMA User Exit Library field
    -   Path to the RMA user exit configuration file in the RMA Configuration field

      
    Gateway RMA provides the user exit library and configuration file.

> **Note:**
>
> Default values for these paths are present in the Gateway configuration. If the Gateway RMA component was installed, they already point to the RMA library and conf file. These values do not usually require editing.

1.  Restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for the change in configuration to take effect.

<span id="RMA"></span>

## RMA user exit library load

When RMA checking is enabled, SWIFTNet client and server processes load the RMA user exit library at <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> startup using the specified RMA user exit configuration file.

If errors occur during RMA user exit library loading or initialization, the SWIFTNet processes performing the operation are terminated. Correct the errors reported in the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> log.

An incorrectly configured RMA can prevent the SWIFTNet module from functioning.

<span id="Scope"></span>

## Scope of RMA checking

RMA user exit checking entails searching for a valid authorization in the Gateway RMA authorizations data store. Transfers are not sent or received when valid authorizations are not found.

RMA user exit checking occurs when sending and receiving data to verify whether traffic is authorized:

-   When sending to a partner, RMA checking verifies whether there is a valid authorization-to-send a document to the partner.
-   When receiving from a partner, RMA checking verifies whether there is a valid authorization-to-receive a document from the partner.

When the service is in RMA Trial Period (as specified in the ASP) and the stop unauthorized transfers in Trial Period global configurations flag is not set, processing continues even if the transfer fails RMA authorization checking.

There is a `peldsp display_trans` parameter for reporting the result of the RMA check. The parameter is <span class="code">x\_asprma\_check\_result</span>. Use it for displaying the check result for ASP and RMA validation. There are the following values in the context of RMA checking:

-   <span class="bold_in_para">RMA Performed</span>. RMA authorization checking was performed. This does not indicate whether authorization is valid.
-   <span class="bold_in_para">RMA Successful</span> . RMA authorization for the message was successful.
-   <span class="bold_in_para">RMA Trial</span>. RMA validation was performed in trial period for the specified service.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
