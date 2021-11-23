{
    "title": "Monitoring an OFTP transfer",
    "linkTitle": "Monitoring a transfer",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Protocols

[Protocol error reporting](#error_reporting)

[Protocol trace messages](#trace_messages)

<span id="error_reporting"></span>

## Protocol error reporting

Gateway returns an error when a problem is encountered during Transfer Request processing. The error format depends on the Gateway user interface you use:

-   For online commands and the GUI, the error message is displayed directly on output.
-   For API calls, the return value is `-`**1** and an error code is automatically loaded into a global variable named <span style="font-weight: bold;">ErrCod</span>. You can use this code to retrieve the error message with the <span style="font-weight: bold;">[GikErrMsg](../../../customizing_gw_about/c_api_about/c_api_primitives#GikErrMsg)</span> API function.

Protocol errors are reported in end-of-transfer exits and in the log file.

### Errors associated with ESID response messages

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Code</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Action *</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>00</p>         </td>
         <td><p>Normal session termination</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>01</p>         </td>
         <td><p>Command not recognized</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>02</p>         </td>
         <td><p>Protocol violation</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>03</p>         </td>
         <td><p>User code not known</p>         </td>
         <td><p>Stop</p>         </td>
      </tr>
      <tr>
         <td><p>04</p>         </td>
         <td><p>Invalid password</p>         </td>
         <td><p>Stop</p>         </td>
      </tr>
      <tr>
         <td><p>05</p>         </td>
         <td><p>Local Site emergency shutdown</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>06</p>         </td>
         <td><p>Command contained invalid data</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>07</p>         </td>
         <td><p>NSDU size error</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>08</p>         </td>
         <td><p>Resource not available</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>09</p>         </td>
         <td><p>Timeout</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>10</p>         </td>
         <td><p>Incompatible mode or capabilities</p>         </td>
         <td><p>Stop</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>Invalid challenge response</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>12</p>         </td>
         <td><p>Secure requirement incompatible</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
      <tr>
         <td><p>99</p>         </td>
         <td><p>Unspecified abort code</p>         </td>
         <td><p>Retry, backup, stop</p>         </td>
      </tr>
   </tbody>
</table>

#### \* Actions

The possible Gateway actions in response to the ESID codes in the above table are as follows:

-   <span style="font-weight: bold;">None</span> - No action necessary as the session ended normally
-   <span style="font-weight: bold;">Stop</span> - Stop Site by disabling Site Responder mode
-   <span style="font-weight: bold;">Retry, backup, stop</span> - Try to re-establish session, possibly with backup communication path, and finally stop Site by disabling Site Responder mode

### Errors associated with SFNA and EFNA response messages

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Code</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Action *</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>00</p>         </td>
         <td><p>Normal transfer termination</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>01</p>         </td>
         <td><p>Invalid file name</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>02</p>         </td>
         <td><p>Invalid destination</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>03</p>         </td>
         <td><p>Invalid origin</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>04</p>         </td>
         <td><p>Storage record format not supported</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>05</p>         </td>
         <td><p>Maximum record length not supported</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>06</p>         </td>
         <td><p>File size too big</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>10</p>         </td>
         <td><p>Invalid record count</p>         </td>
         <td><p>Restart from the beginning</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>Invalid byte count</p>         </td>
         <td><p>Restart from the beginning</p>         </td>
      </tr>
      <tr>
         <td><p>12</p>         </td>
         <td><p>Access method failure</p>         </td>
         <td><p>Restart</p>         </td>
      </tr>
      <tr>
         <td><p>13</p>         </td>
         <td><p>Duplicate file</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>14</p>         </td>
         <td><p>File direction refused</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>15</p>         </td>
         <td><p>Cipher suite not supported</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>16</p>         </td>
         <td><p>Encrypted file not allowed</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>17</p>         </td>
         <td><p>Unencrypted file not allowed</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>18</p>         </td>
         <td><p>Compression not allowed</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>19</p>         </td>
         <td><p>Signed file not allowed</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>20</p>         </td>
         <td><p>Unsigned file not allowed</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>21</p>         </td>
         <td><p>Invalid file signature</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>22</p>         </td>
         <td><p>File decryption failure</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>23</p>         </td>
         <td><p>File decompression failure</p>         </td>
         <td><p>Cancel</p>         </td>
      </tr>
      <tr>
         <td><p>99</p>         </td>
         <td><p>Unspecified reason</p>         </td>
         <td><p>Restart</p>         </td>
      </tr>
   </tbody>
</table>

#### \* Actions

The possible Gateway actions in response to the SFNA and EFNA codes in the above table are as follows:

-   <span style="font-weight: bold;">None</span> - No action necessary as the transfer ended normally
-   <span style="font-weight: bold;">Cancel</span> - Set transfer state to Canceled: no transfer restart
-   <span style="font-weight: bold;">Restart</span> - Try to resume from the last transfer position
-   <span style="font-weight: bold;">Restart from the beginning</span> - Try to resume transfer from beginning of file

<span id="trace_messages"></span>

## Protocol trace messages

Each protocol command or response corresponds to a protocol trace message that you can record in the log file. The protocol trace is an optional feature that you define for transfer activity for a given Site.

You can enable or disable the protocol trace for a Site, either dynamically during Gateway processing, or when you define or modify the attributes of a Site.

When a protocol trace is enabled or disabled dynamically, it is validated only in memory (the modification is lost when Gateway is stopped).

### Activating protocol trace

1.  In the Gateway GUI, select the Remote Site for which you want to activate the trace.
2.  Right-click the Remote Site to display a context menu.
3.  Select <span style="font-weight: bold;">Trace mode</span>.

Alternatively, enter an online command such as:

<span class="code" style="font-weight: bold;">[pelctl start\_site](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#pelctl_start_site)  -alias remote\_oftp  -trace\_mode</span>

<span style="font-weight: bold;">Note:</span> The FPDUs that the protocol uses to send a diagnostic command (ESID, SFNA and EFNA) are always written to the log file with the previous FPDU, which may be the origin of the error.

Related topics

[OFTP trace example](../oftp_trace_example)

[OFTP protocol log messages (ODT)](../../../log_messages_about/odette_protocol_(odt))

[About OFTP](../)

[Configuring Gateway for OFTP](../oftp_config)

[Submitting an OFTP Transfer Request](../oftp_submitting_transfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
