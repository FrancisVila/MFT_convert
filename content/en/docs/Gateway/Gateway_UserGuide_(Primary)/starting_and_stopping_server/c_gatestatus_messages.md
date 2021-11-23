{
    "title": "About gatestatus messages ",
    "linkTitle": "About gatestatus messages",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing the Server

[GateController and gatestatus](#gatecontroller)

[Possible gatestatus responses](#poss_resp)

[List of gatestatus messages](#list)

[Resetting the status prompted by the `gatestatus` command to the default value](#resetting)

<span id="gatecontroller"></span>

## GateController and gatestatus

Gateway is designed as a modular system of loosely-coupled processes. The GateController process collects heartbeats and status messages from each of these individual processes. Despite being delivered to the operator through the `gatestatus` command, most of the messages GateController relays have nothing to do with GateController itself.

`gatestatus` is not the best way to monitor Gateway. It is a simple reference tool for a system administrator to check the functioning of Gateway. `gatestatus` messages do not necessarily indicate that there is problem, merely a condition that can only be cleared with user intervention.

<span id="poss_resp"></span>

## Possible gatestatus responses

There are four classes of message that `gatestatus` can return:

-   Gateway stopped
-   Gateway running
-   Gateway restarting
-   Process crashed

These messages display the most recent status change for which GateController received a notification. To obtain more complete status information, including the time and date of the event, you should refer to the Gateway logs.

The best way to monitor Gateway is by tracking it in Sentinel. You can then automatically extract messages of interest and create alerts when something is wrong.

<span id="list"></span>

## List of gatestatus messages

### Process crash messages

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status: Warning. TSD process raised a problem to GateController</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>A dynamic Gateway process monitored by the TSD crashed or does not answer any more. It will be managed by its parent process.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>In this case, one of the child processes of the p_tsd process had to be restarted. The actions were all managed by the TSD module, and simply reported to GateController. Unless this happens frequently, it is harmless. One possible cause is insufficient resources due to system or user limits (ulimit). Gateway should resolve this issue on its own and automatically clear this message.</p>
<p>For more details about the problem, look in <code>&lt;Gateway installation directory&gt;/run_time/tmp/TSD-&lt;timestamp&gt;-&lt;pid&gt;.out</code></p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status: Minor error. TSD process raised a problem to GateController</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>A dynamic Gateway process monitored by the TSD crashed or does not answer any more. It will be managed by its parent process.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>Gateway should resolve this issue on its own and automatically clear this message.</p>
<p>For more details about the problem, look in <code>&lt;Gateway installation directory&gt;/run_time/tmp/TSD-&lt;timestamp&gt;-&lt;pid&gt;.out</code></p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status: Minor error. SUP process raised a problem to GateController</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>A dynamic Gateway process monitored by the SUP crashed or does not answer any more. It will be managed by its parent process.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>Gateway should resolve this issue on its own and automatically clear this message.</p>
<p>For more details about the problem, look in <code>&lt;Gateway installation directory&gt;/run_time/tmp/SUP-&lt;timestamp&gt;-&lt;pid&gt;.out</code></p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status: Minor error. TSD process raised a problem to GateController</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>A dynamic Gateway process monitored by the TSD crashed or does not answer any more. It will be managed by its parent process.</p>
<p>For more information refer to the log.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>Gateway should resolve this issue on its own and automatically clear this message.</p>
<p>For more details about the problem, look in <code>&lt;Gateway installation directory&gt;/run_time/tmp/TSD-&lt;timestamp&gt;-&lt;pid&gt;.out</code></p>         </td>
      </tr>
   </tbody>
</table>

### Unable to retrieve messages

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status</strong></p>
<p>Example:</p>
<p>-- 2009/01/24 15:17:32 - ERROR from apigc_cli_build_cli_socket</p>
<p>2009/01/24 15:17:32 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>-- 2009/01/24 15:17:32 - ERROR from apigc_cli_init</p>
<p>2009/01/24 15:17:32 Client socket creation + connection failed. Retries are coming.</p>
<p>-- 2009/01/24 15:17:35 - ERROR from apigc_cli_build_cli_socket</p>
<p>2009/01/24 15:17:35 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>2009/01/24 15:17:39 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>2009/01/24 15:17:44 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>2009/01/24 15:17:48 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>2009/01/24 15:17:52 apigc_net_connect: SOCKET CONNECTION FAILED</p>
<p>GateController problem.</p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>GateController does not answer any more, but Gateway is still running.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>GateController is not running, but the pid file has not been cleaned up.</p>
<p>Check for files named core in the Gateway and system core directories.</p>
<p>Delete the pid file and attempt to restart Gateway.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Message         </td>
         <td><p><strong>Printing Gateway status: GateController problem</strong></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>GateController does not answer any more, but Gateway is still running.</p>         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td><p>GateController is not running, but Gateway is probably still trading.</p>
<p>Restart Gateway when convenient.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="resetting"></span>

## Resetting the status prompted by the gatestatus command to the default value

The `pelmon reset` command enables you to reset the status prompted by the `gatestatus` command to the default value.

After entering this command, Gateway returns the message: **Printing Gateway status: running**.

Related topics

[Overview: Monitoring Gateway](../../ov_gateway/ov_monitoring_gateway)

[Starting and stopping the server](../)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
