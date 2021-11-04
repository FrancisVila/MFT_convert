{
    "title": "Implement the Edge Agent",
    "linkTitle": "Implement the Edge Agent",
    "weight": "210"
}This page describes how to configure the Edge Agent for AMPLIFY MFT implementations and configure <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> for the following use cases:

-   Usage tracking only
-   Usage tracking and Sentinel monitoring

<span class="autonumber"></span>Usage tracking only

<img src="/Images/TransferCFT/edge_direct.png" class="maxWidth" />

<span class="autonumber"></span>Usage tracking and Sentinel monitoring

<img src="/Images/TransferCFT/edge_indirect.png" class="maxWidth" />

Report contents are computed once daily and reflect the completed transfers from the preceding day. Depending on your start and end dates, which must be at the very least the previous day, the report will contain the completed transfers for that time period.

For more information on reporting usage, Edge Agent setup and architecture, and other usage tracking details, please refer to the [AMPLIFY Usage Metering and Reporting Guide](https://docs.axway.com/bundle/subusage_en).

## Configure the Edge Agent

Perform the following steps on the Edge Agent for MFT implementations that use <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> or <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span>.

1.  Download the `AMPLIFY_Edge_Agent_MFT_<version>_configuration_<BNxxx>.zip `package from the [Axway Support Site](https://support.axway.com/).
2.  Extract the zip locally.
3.  Upload the <span class="code">MFT-usage.json</span> file from the package to the <span class="code">&lt;Edge\_Agent\_install\_dir>/aggregator/usage\_tracking/</span>`conf/agent/aggregation` directory.
4.  Upload the `MFT.json` file from the package to the <span class="code">&lt;Edge\_Agent\_install\_dir>/conf/agent/report</span> directory.
5.  Restart the Edge Agent. Refer to the [AMPLIFY Usage Metering and Reporting Guide](https://docs.axway.com/bundle/subusage_en).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The MFT.json file name is the <span class="code">configurationName</span> that you use when querying the Edge Agent.         </td>
      </tr>
   </tbody>
</table>

## Configure Transfer CFT

There are two methods of configuration depending on the use case you implement.

### Usage tracking only

In this use case, Transfer CFT sends the usage report directly to the Edge Agent.

Set the following <span class="code">uconf </span>parameters to the Edge Agent values:

-   sentinel.trkipaddr: Edge Agent IP address
-   sentinel.trkipport: 8002 (by default, the non-SSL port for the Edge Agent)
-   sentinel.xfb.use\_ssl: No

### Usage tracking with the Edge Agent and monitoring with Sentinel

In this use case, Transfer CFT uses the Event Router to send notifications to both Sentinel and the Edge Agent.

You require an installed Sentinel and Event Router to implement this method. You may want to also refer to the [Sentinel Installation Guide](https://docs.axway.com/bundle/Sentinel_420_InstallationGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm).

#### On Transfer CFT 

Set the following uconf parameters to the Edge Agent values:

-   sentinel.trkipaddr: Event Router IP address
-   sentinel.trkipport: Event Router listening port

#### On the Sentinel server

1.  On Sentinel, copy the <span class="code">XFBCFTInfo </span>and <span class="code">XFBTransfer</span> Tracked Object files from the` <Transfer_CFT_install_dir>/home/extra/sentinel` to <span class="code">&lt;Sentinel\_install\_dir>/broadcast/commit/trackingobject </span>folder.  
    If the Tracked Objects folder does not exist, you must create it.
2.  Restart Sentinel.

#### On the Event Router

When you are using the Event Router to send both usage tracking to the Edge Agent and monitoring to Sentinel, you must customize the Event Router. In the following configuration steps, <span class="code">XFBTransfer </span>and `CycleLink `are sent to both the Edge Agent and Sentinel. However, <span class="code">XFBCFTInfo </span>and `STXFBINFO `are only sent to the Edge Agent.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The default target is called <span style="font-family: &#39;Courier New&#39;;">SENTINEL</span> in the steps below.         </td>
      </tr>
   </tbody>
</table>

1.  Access the <span class="code">&lt;install\_dir>/SentinelEventRouter/conf </span>directory.
2.  Edit the <span class="code">target.xml</span> file to route the usage information to Sentinel and the Edge Agent (<span class="code">EDGEAGENT</span>).
    1.  Add the Edge Agent as a new target.

    2.  

    3.  Define a route to send the `XFBTransfer `Tracked Object to the Edge Agent.

    4.  

    5.  Define a route to send the `CYCLELINK `to the Edge Agent.

    6.  

    7.  Define a route to send the `XFBCFTInfo `only to the Edge Agent.

    8.  

    9.  If you are also implementing SecureTransport, define a route to send the `STXFBINFO `only to the Edge Agent.

    10. 
3.  Save the file.
4.  Restart the Event Router.

Example


    <TrkEventRouterCfg>
     <TrkXml version="x.x" />
       <EventRouter name="DEFAULT">
      </EventRouter>
        <Target name="SENTINEL" defaultXntf="yes" defaultXml="yes">
       </Target>
       <Target name="EDGEAGENT"  defaultXntf="no"  defaultXml="no">
          <Access mode="QLT"  addr="<Edge_Agent_IP_address>"  port="8002" />
        </Target>

       <Route object="XFBTransfer" default_Notify="NotifyIf">   
          <Condition notify="NotifyIf"    target="EDGEAGENT"  if="[PRODUCTIPADDR] NOT _"/>
       </Route>
      <Route object="CYCLELINK" default_Notify="NotifyIf">
        <Condition notify="NotifyIf" target="EDGEAGENT" if="[PRODUCTIPADDR] NOT _"/>
       </Route>
       <Route object="XFBCFTInfo" default_Notify="NotifyIf"> 
           <Condition notify="NotNotifyIf" target="SENTINEL" if="[PRODUCTIPADDR] NOT _"/>
           <Condition notify="NotifyIf"    target="EDGEAGENT"  if="[PRODUCTIPADDR] NOT _"/> 
        </Route>
       <Route object="STXFBINFO" default_Notify="NotifyIf"> 
           <Condition notify="NotNotifyIf" target="SENTINEL" if="[PRODUCTIPADDR] NOT _"/>
           <Condition notify="NotifyIf"    target="EDGEAGENT"  if="[PRODUCTIPADDR] NOT _"/> 
       </Route>
    </TrkEventRouterCfg>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Do not modify the <span class="code">[PRODUCTIPADDR]</span>.         </td>
      </tr>
   </tbody>
</table>
