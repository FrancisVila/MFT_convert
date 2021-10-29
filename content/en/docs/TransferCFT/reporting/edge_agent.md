{
    "title": "Implement the Edge Agent",
    "linkTitle": "Implement the Edge Agent",
    "weight": "210"
}This page describes how to configure the Edge Agent for AMPLIFY MFT implementations and configure Transfer CFT for the following use cases:

-   Usage tracking only
-   Usage tracking and Sentinel monitoring

Usage tracking only

![](/Images/TransferCFT/edge_direct.png)

Usage tracking and Sentinel monitoring

![](/Images/TransferCFT/edge_indirect.png)

Report contents are computed once daily and reflect the completed transfers from the preceding day. Depending on your start and end dates, which must be at the very least the previous day, the report will contain the completed transfers for that time period.

For more information on reporting usage, Edge Agent setup and architecture, and other usage tracking details, please refer to the [AMPLIFY Usage Metering and Reporting Guide](https://docs.axway.com/bundle/subusage_en).

## Configure the Edge Agent

Perform the following steps on the Edge Agent for MFT implementations that use Transfer CFT or SecureTransport.

1.  Download the `AMPLIFY_Edge_Agent_MFT_<version>_configuration_<BNxxx>.zip `package from the [Axway Support Site](https://support.axway.com/).
2.  Extract the zip locally.
3.  Upload the MFT-usage.json file from the package to the &lt;Edge\_Agent\_install\_dir>/aggregator/usage\_tracking/`conf/agent/aggregation` directory.
4.  Upload the `MFT.json` file from the package to the &lt;Edge\_Agent\_install\_dir>/conf/agent/report directory.
5.  Restart the Edge Agent. Refer to the [AMPLIFY Usage Metering and Reporting Guide](https://docs.axway.com/bundle/subusage_en).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The MFT.json file name is the <span>configurationName</span> that you use when querying the Edge Agent.         </td>
      </tr>
   </tbody>
</table>

## Configure Transfer CFT

There are two methods of configuration depending on the use case you implement.

### Usage tracking only

In this use case, Transfer CFT sends the usage report directly to the Edge Agent.

Set the following uconf parameters to the Edge Agent values:

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

1.  On Sentinel, copy the XFBCFTInfo and XFBTransfer Tracked Object files from the` <Transfer_CFT_install_dir>/home/extra/sentinel` to &lt;Sentinel\_install\_dir>/broadcast/commit/trackingobject folder.  
    If the Tracked Objects folder does not exist, you must create it.
2.  Restart Sentinel.

#### On the Event Router

When you are using the Event Router to send both usage tracking to the Edge Agent and monitoring to Sentinel, you must customize the Event Router. In the following configuration steps, XFBTransfer and `CycleLink `are sent to both the Edge Agent and Sentinel. However, XFBCFTInfo and `STXFBINFO `are only sent to the Edge Agent.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The default target is called <span>SENTINEL</span> in the steps below.         </td>
      </tr>
   </tbody>
</table>

1.  Access the &lt;install\_dir>/SentinelEventRouter/conf directory.
2.  Edit the target.xml file to route the usage information to Sentinel and the Edge Agent (EDGEAGENT).
    1.  Add the Edge Agent as a new target.

    2.  <table data-cellspacing="0">
           <tbody>
              <tr class="odd">
                 <td>&lt;Target name="EDGEAGENT" defaultXntf="no" defaultXml="no"&gt;
        &lt;Access mode="QLT" addr="&lt;Edge_Agent_IP_address&gt;" port="8002" /&gt;
        &lt;/Target&gt;         </td>
              </tr>
           </tbody>
        </table>

    3.  Define a route to send the `XFBTransfer `Tracked Object to the Edge Agent.

    4.  <table data-cellspacing="0">
           <tbody>
              <tr class="odd">
                 <td>&lt;Route object="XFBTransfer" default_Notify="NotifyIf"&gt;
        &lt;Condition notify="NotifyIf" target="EDGEAGENT" if="
        [PRODUCTIPADDR] NOT _"/&gt;
        &lt;/Route&gt;         </td>
              </tr>
           </tbody>
        </table>

    5.  Define a route to send the `CYCLELINK `to the Edge Agent.

    6.  <table data-cellspacing="0">
           <tbody>
              <tr class="odd">
                 <td>            <p>&lt;Route object="CYCLELINK" default_Notify="NotifyIf"&gt;</p>
                    <p>&lt;Condition notify="NotifyIf" target="EDGEAGENT" if=" [PRODUCTIPADDR] NOT _"/&gt;</p>
                    <p>&lt;/Route&gt;</p>         </td>
              </tr>
           </tbody>
        </table>

    7.  Define a route to send the `XFBCFTInfo `only to the Edge Agent.

    8.  <table data-cellspacing="0">
           <tbody>
              <tr class="odd">
                 <td>&lt;Route object="XFBCFTInfo" default_Notify="NotifyIf"&gt;
        &lt;Condition notify="NotNotifyIf" target="SENTINEL" if="[PRODUCTIPADDR] NOT _"/&gt;
        &lt;Condition notify="NotifyIf" target="EDGEAGENT" if="[PRODUCTIPADDR] NOT _"/&gt;
        &lt;/Route&gt;         </td>
              </tr>
           </tbody>
        </table>

    9.  If you are also implementing SecureTransport, define a route to send the `STXFBINFO `only to the Edge Agent.

    10. <table data-cellspacing="0">
           <tbody>
              <tr class="odd">
                 <td>&lt;Route object="STXFBINFO" default_Notify="NotifyIf"&gt;
        &lt;Condition notify="NotNotifyIf" target="SENTINEL" if="[PRODUCTIPADDR] NOT _"/&gt;
        &lt;Condition notify="NotifyIf" target="EDGEAGENT" if="[PRODUCTIPADDR] NOT _"/&gt;
        &lt;/Route&gt;         </td>
              </tr>
           </tbody>
        </table>
3.  Save the file.
4.  Restart the Event Router.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><pre><code>&lt;TrkEventRouterCfg&gt;
 &lt;TrkXml version=&quot;x.x&quot; /&gt;
   &lt;EventRouter name=&quot;DEFAULT&quot;&gt;
  &lt;/EventRouter&gt;
    &lt;Target name=&quot;SENTINEL&quot; defaultXntf=&quot;yes&quot; defaultXml=&quot;yes&quot;&gt;
   &lt;/Target&gt;
   &lt;Target name=&quot;EDGEAGENT&quot;  defaultXntf=&quot;no&quot;  defaultXml=&quot;no&quot;&gt;
      &lt;Access mode=&quot;QLT&quot;  addr=&quot;&lt;Edge_Agent_IP_address&gt;&quot;  port=&quot;8002&quot; /&gt;
    &lt;/Target&gt;

   &lt;Route object=&quot;XFBTransfer&quot; default_Notify=&quot;NotifyIf&quot;&gt;         &lt;Condition notify=&quot;NotifyIf&quot;    target=&quot;EDGEAGENT&quot;  if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;
   &lt;/Route&gt;
  &lt;Route object=&quot;CYCLELINK&quot; default_Notify=&quot;NotifyIf&quot;&gt;    &lt;Condition notify=&quot;NotifyIf&quot; target=&quot;EDGEAGENT&quot; if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;   &lt;/Route&gt;
   &lt;Route object=&quot;XFBCFTInfo&quot; default_Notify=&quot;NotifyIf&quot;&gt;        &lt;Condition notify=&quot;NotNotifyIf&quot; target=&quot;SENTINEL&quot; if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;
       &lt;Condition notify=&quot;NotifyIf&quot;    target=&quot;EDGEAGENT&quot;  if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;     &lt;/Route&gt;
   &lt;Route object=&quot;STXFBINFO&quot; default_Notify=&quot;NotifyIf&quot;&gt;        &lt;Condition notify=&quot;NotNotifyIf&quot; target=&quot;SENTINEL&quot; if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;
       &lt;Condition notify=&quot;NotifyIf&quot;    target=&quot;EDGEAGENT&quot;  if=&quot;[PRODUCTIPADDR] NOT _&quot;/&gt;    &lt;/Route&gt;&lt;/TrkEventRouterCfg&gt;</code></pre>         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Do not modify the <span>[PRODUCTIPADDR]</span>.         </td>
      </tr>
   </tbody>
</table>
