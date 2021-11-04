{
    "title": "SWIFTNet ASP check",
    "linkTitle": "SWIFTNet ASP check",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About ASP check for SWIFTNet](#About)

[Prerequisites](#Prerequi)

[Enabling ASP checking](#Enabling)

[ASP package load or reload](#ASP)

[Scope of ASP checking](#Scope)

[Outgoing and incoming checks](#Initiato)

The following sections provide information about <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> support for checking sent and received transfers via SWIFTNet against Application Service Profiles.

<span id="About"></span>

## About ASP check for SWIFTNet

Starting with SWIFTNet 7.0, information is available related to all services, including InterAct and FileAct (not only for FINCopy services). Each service has an Application Service Profile (ASP). This is an XML file containing all service parameters. Based on the ASP package for all published SWIFT services loaded into <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, checks can be made when sending or receiving traffic to ensure use of correct transfer parameters for a service.

By performing ASP filtering, SWIFT does not reject the initiated flows for incorrect transfer parameter configuration.

Another use for ASP checking is determining which services require Relationship Management Application (RMA) interface authorization filtering.

For more details about ASP, refer to the official SWIFT documentation.

<span id="Prerequi"></span>

## Prerequisites

Before using <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to check sent and received transfers via SWIFTNet against ASPs, you must provide the ASP package content for loading. ASP packages are available at [http://www.swift.com](http://www.swift.com/). Decompress downloaded package archives before loading into <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.

<span id="Enabling"></span>

## Enabling ASP checking

You must configure global parameters before using the SWIFTNet ASP check functionality:

Use the following steps to enable SWIFTNet ASP checking and set the path to ASP profiles.

1.  In the left pane of the main window in the user interface, right-click the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> server to enable for ASP checking and select <span class="bold_in_para">Configure</span>. The Configuration window is displayed.
2.  In the left pane of the Configuration window, select <span class="bold_in_para">Connectivity > Axway Connectivity > SWIFTNet (ASP/RMA tab)</span>.
3.  Enable ASP checking by selecting one of the following:
    -   <span class="bold_in_para">ASP & RMA enabled</span>. Both ASP and RMA checks are performed (see <a href="../swiftnet_rma_check" class="MCXref xref">Gateway RMA check</a>)
    -   <span class="bold_in_para">ASP enabled, RMA disabled</span>. Only ASP check is performed

      
    For details see <a href="../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet" class="MCXref xref">Connectivity &gt; Axway Connectivity &gt; SWIFTNet</a>
4.  Specify the ASP profiles directory in the ASP Profiles Directory. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> environment variables can be used:
    -   %VAR% and \\ separator for Windows
    -   $VAR and / separator for UNIX

      
    The folder path name is a dynamic configuration parameter and can be updated at runtime. To reload and use the ASP files from the new location, see <a href="../#pelctl_reload_asp_profiles" class="MCXref xref">pelctl reload_asp_profiles: Trigger reload of ASPs</a>.
5.  Click <span class="bold_in_para">Activate</span> to enable the connector.
6.  Restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for the change in configuration to take effect.

<span id="ASP"></span>

## ASP package load or reload

Upon startup, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> validates ASP package integrity before service profiles in the ASP directory are loaded to memory when ASP checking is enabled.

In addition to the service profile files, the package must contain:

-   An XML file with the digests of all the other files from the package (service profiles, XML schema files).
-   The XML schema for validating the XML digest file.
-   The XML schema for validating the service profiles.

All files enumerated into the digest file must be in the ASP directory. The digest <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> computes for each file must be identical to the digest specified in the digest file in the ASP package.

You can change the values of the ASP profile schema, profile extension, digest file and digest schema for checking the package integrity and loading the ASPs. However, the best practice is to use the default values unless change is absolutely necessary (for example, SWIFT changes file names).

If errors occur at <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> startup while checking ASP package integrity or loading ASPs, the ASP helpers are restarted and errors logged. For example:

SUP I ST-HPROC Starting 'swasp' helper process number 1

SNET E ASPLDSTS Swift ASP package load failed. Reason: Could not open or parse the digest file : \[D\\swift7\_official\_asp\_package/ApplProf.dig\], ErrNo: 16, Date: 20120319, Start: 150433, Stop: 150433, Previous active load: NONE!

JCT I JOBTERML \[H\_SWASP\_1\] Job \[h\_swasp\_job -v (pid=5660, ph=1532)\] pid 5660 terminated

Unless you correct the error, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> continually tries to load the package, and multiple errors are logged. The following are possible causes of ASP loading failures:

-   One or more of the following parameters are incorrect: ASP profiles directory, profile schema, profile extension, profiles digest file, digest schema.
-   One or more of the ASPs are incorrect.

When you have corrected the ASP configuration and restart the ASP helpers, the ASPs are loaded successfully and the action logged. For example:

SNET072I 06.02.2012 17:43:58 Swift ASP package load done. Files: 34, Date: 20120206, Start: 174358, Stop: 174358.

You can use `pelctl` commands to reload a new or updated ASP package into memory while <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> is running. See <a href="../" class="MCXref xref">SWIFTNet ASP check commands</a>.

<span id="Initiato"></span>

## Outgoing and incoming checks

The next transfer parameters are checked for outgoing and incoming transfer requests when the global configuration option is enabled for ASP checking.

### Outgoing requests

After a transfer is created into mailbox, but before sending the outgoing request to SWIFT, an ASP check is performed to validate the correct usage of the following transfer parameters:

-   <span class="bold_in_para">Request type</span>
-   <span class="bold_in_para">Delivery mode</span>
-   <span class="bold_in_para">Signing</span>
-   <span class="bold_in_para">Signature format</span>  
    Checked only when signing is set.
-   <span class="bold_in_para">Non-repudiation</span>
-   <span class="bold_in_para">Headerinfo feature used</span>
-   <span class="bold_in_para">Copy feature used</span>
-   <span class="bold_in_para">3rd parties DN list</span>  
    Checked only when copy feature is used.
-   <span class="bold_in_para">Authorization notification indication used</span>  
    For store-and-forward mode, this is checked when the copy feature is used.

Possible results for ASP check are:

-   <span class="bold_in_para">Failed</span>
-   <span class="bold_in_para">Success</span> followed by <span class="bold_in_para">RMA check required</span>, <span class="bold_in_para">RMA check required (in trial period)</span> or <span class="bold_in_para">RMA check not required</span> information message when RMA check is enabled from the configuration.
-   <span class="bold_in_para">Success with default profile</span> followed by <span class="bold_in_para">RMA check required</span>, <span class="bold_in_para">RMA check required (in trial period)</span> or <span class="bold_in_para">RMA check not required</span> information message when RMA check is enabled from the configuration.

If the ASP check fails, the transfer cancels. This is reflected in the log.

### Incoming requests

After receiving a transfer request from SWIFT, but before creating an entry in the mailbox for the incoming request, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> performs an ASP check only if the global configuration option enables both ASP and RMA checking. This is because the scope of the check is to determine whether RMA filtering is required for the incoming request. If an error occurs during the ASP check, the error writes to the log and <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> rejects the transfer request.

Possible results for ASP checking are:

-   <span class="bold_in_para">Failed</span>
-   <span class="bold_in_para">Success</span> followed by <span class="bold_in_para">RMA check required</span>, <span class="bold_in_para">RMA check required (in trial period)</span> or <span class="bold_in_para">RMA check not required</span> information message.
-   <span class="bold_in_para">Success with default profile</span> followed by <span class="bold_in_para">RMA check required</span>, <span class="bold_in_para">RMA check required (in trial period)</span> or <span class="bold_in_para">RMA check not required</span> information message.

Before sending the response for the incoming request to SWIFT, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> does another ASP check to validate the correct usage of the non-repudiation parameter value in the response. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> generates a warning if the check fails. The non repudiation parameter in the response is copied from the non repudiation in the incoming request.

If <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> cannot find the profile for a service, it uses the corresponding default profile for the service environment depending on the service name suffix (!p, !x, !xp). This occurs rarely. The default profile contains default parameters, which might not be the correct configuration for the selected service. To avoid this, use an updated ASP package.

There is a `peldsp display_trans` parameter for reporting the result of the ASP check. The parameter is <span class="code">x\_asprma\_check\_result</span>. Use it for displaying the check result for ASP and RMA validation. In the context of ASP checking a value of <span class="bold_in_para">ASP Successful</span> means ASP validation against the corresponding profile succeeded. If this value is missing, the ASP checking failed.

Related topics

[SWIFTNet ASP check commands](../)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
