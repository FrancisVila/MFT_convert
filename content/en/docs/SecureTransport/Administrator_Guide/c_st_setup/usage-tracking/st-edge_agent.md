{
    "title": "Set up usage reporting",
    "linkTitle": "Set up usage reporting",
    "weight": "210"
}This page describes how to configure the Edge Agent for AMPLIFY MFT implementations and configure Axway {{< SecureTransport/securetransportname  >}} for the following use cases:

-   Usage tracking only
-   Usage tracking and Sentinel monitoring

 

Usage tracking only

<img src="/Images/SecureTransport/edge_direct.png" class="maxWidth" />

 

Usage tracking and Sentinel monitoring

<img src="/Images/SecureTransport/edge_indirect.png" class="maxWidth" />

## Configure the Edge Agent

**Prerequisite:** You must have your Edge Agent installed and configured to work with {{< SecureTransport/componentshortname  >}}.

Perform the following steps on the Edge Agent for MFT implementations that use {{< SecureTransport/transfercftname  >}} or {{< SecureTransport/securetransportname  >}}.

1.  Download the `AMPLIFY_Edge_Agent_MFT_<version>_configuration_<BNxxx>.zip` package from the [Axway Support Site](https://support.axway.com/).
2.  Extract the zip locally.
3.  Edit the `MFT.json` file to change the value of the `envId` parameter to the `Environment ID` from the Platform.
4.  Upload the `MFT.json` file from the package to the `<Edge_Agent_install_dir>/conf/agent/report` directory.
5.  Upload the `MFT-usage.json` file from the package to the `<Edge_Agent_install_dir>/conf/agent/aggregation` directory.
6.  Restart the Edge Agent. Refer to the [AMPLIFY Usage Metering and Reporting Guide](https://docs.axway.com/bundle/subusage_en).

> **Note:**
>
> The MFT.json file name is the configurationName that you use when querying the Edge Agent.

## Configure {{< SecureTransport/securetransportname  >}}

There are two methods of configuration depending on the use case you implement.

<span id="UsageTrack"></span>

### Usage tracking with the Edge Agent

In this use case, {{< SecureTransport/componentshortname  >}} sends the usage events to the Edge Agent. Follow this simple procedure to configure usage tracking:

1.  From **Setup > Axway Sentinel/DI**, configure reporting to Edge Agent by following the steps 1-9 as described in <a href="../../c_st_sentinelintegration/t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>. Note that you must use the connection details for Edge Agent and not for Sentinel.
2.  Test and save the configuration.
3.  From **Operations > Server Configuration**:
    1.  Set `StatisticsSummary.AutoReportAdditionalInfo` to `true`. This is needed in order to periodically generate a Sentinel event with usage information on the {{< SecureTransport/componentshortname >}} instance.
    2.  Set `Ssh.AxwayVendorExtensions.enabled` to `true`. This is needed if {{< SecureTransport/componentshortname >}} communicates with Transfer CFT over the SFTP protocol. Note that in order for this change to take effect, you must restart the SSH service on each Server and Edge instance.
4.  Restart the Transaction Manager to apply the configuration.

### Usage tracking with the Edge Agent and monitoring with Sentinel

In this use case, {{< SecureTransport/componentshortname  >}} uses the Event Router to send notifications to both Sentinel and the Edge Agent.

You need an installed Sentinel and Event Router to implement this method. For more information, refer to the latest [Sentinel Event Router User Guide](https://support.axway.com/en/documents/document-details/id/12513).

Note that in this case you must perform the <a href="#UsageTrack" class="MCXref xref">Usage tracking with the Edge Agent</a> , with an important exception: in step 1, you must use the connection details for the Event Router.

#### On the Event Router

You must configure the Event Router to allow sending *usage tracking messages* to the Edge Agent and *monitoring messages* to Sentinel. In the following configuration steps, `XFBTransfer `and `CycleLink `are sent to both the Edge Agent and Sentinel. However, `XFBSTInfo` and `XFBCFTInfo` are only sent to the Edge Agent.

> **Note:**
>
> The default target is called SENTINEL in the instructions that follow.

Edit the Event Router configuration file to route the usage information to Sentinel (`SENTINEL`) and the Edge Agent (`EDGEAGENT`).

1.  Add the Edge Agent as a new target.
2.  Define a route to send the `XFBTransfer` Tracked Object to the Edge Agent.
3.  Define a route to send the `CYCLELINK` to the Edge Agent.
4.  Define a route to send the `XFBSTInfo` only to the Edge Agent.
5.  If you are also implementing Transfer CFT, define a route to send the `XFBCFTInfo` only to the Edge Agent.
