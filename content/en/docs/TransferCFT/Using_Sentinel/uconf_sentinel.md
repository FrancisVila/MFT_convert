{
    "title": "UCONF: Sentinel options",
    "linkTitle": "UCONF: Sentinel options",
    "weight": "240"
}This section describes how to configure the Sentinel monitoring agent, which is part of Transfer CFT, using the following groups of UCONF parameters:

-   sentinel.trkxxxxx: These parameters correspond to the trkxxxxx parameter described in the [Sentinel Universal Agent User Guide](#) .
-   sentinel.xfb.xxxx: These parameters indicate how the Sentinel monitoring agent is used in Transfer CFT.
-   Additional uconf values are related to the communication between the Sentinel monitoring agent and Sentinel
    -   ssl.ciphersuites
    -   ssl.version\_min
    -   ssl.extension.enable\_sni
    -   cft.ipv6.disable\_connect
    -   See <a href="../../admin_intro/uconf/uconf_directory" class="MCXref xref">UCONF parameters</a> for parameter details.
-   sentinel.trktname: The path to the overflow file, where the maximum number of messages that the overflow file can store is equal to sentinel.xfb.buffer\_size (not sentinel.trktmaxmsg).
-   <span class="code">sentinel.trktmaxmsg</span>: *Obsolete*. The maximum number of messages in the <span class="code">sentinel.trktname</span> overflow file is defined by the sentinel.xfb.buffer\_size.

## Overflow file

You can define an overflow file to store Sentinel events if the Sentinel server is not available, for example due to network issues or because the server is stopped. If Sentinel tracking is enabled but the server is not available, the message "CFTS30I XTRK Information Sentinel Connection failed" displays in the log. When the Sentinel connection is available again, the next event triggers the sending of previously-stored events.

Use the following uconf parameters to configure the name and size of the overflow file:

-   sentinel.trktname: The path to the overflow file.
-   sentinel.xfb.buffer\_size: The maximum number of messages that the overflow file can store. Once the maximum value is reached, messages are no longer sent to Sentinel and:
    -   If <span class="code">sentinel.xfb.shut</span> is set to any value other than 0, Transfer CFT stops.
    -   If <span class="code">sentinel.xfb.shut</span> is set to 0, Transfer CFT continues to run.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The <span class="code">sentinel.trktmaxmsg </span>parameter is <em>obsolete</em>.<span class="code"> Sentinel.xfb.buffer_size</span> defines the maximum number of messages in the <span class="code">sentinel.trktname</span> overflow file.         </td>
      </tr>
   </tbody>
</table>

## Sentinel configuration parameters

The following table lists the Sentinel parameters in the unified configuration and the corresponding former Sentinel parameter.

<table>
   <th>
      <tr>
<th>Unified configuration parameter         </th>
<th>Default value         </th>
<th><p>Former Sentinel parameter name</p>
<p>trkapi.cfg</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.xfb.enable         </td>
         <td>NO         </td>
         <td>XFB.Sentinel (trkapi.cfg)         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>XFB.Transfer (trkapi.cfg)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.shut</p>         </td>
         <td><p>0</p>         </td>
         <td><p>XFB.Shut (trkapi.cfg)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.log</p>         </td>
         <td><p>IEWF</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To disable, set to ' '.         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p>XFB.Log (trkapi.cfg)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktname</p>         </td>
         <td><p>$(cft.runtime_dir)/data/trkapi.buf  </p>         </td>
         <td><p>TRKTNAME (trkapi.cfg)  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trksharedfile </p>         </td>
         <td><p>No  </p>         </td>
         <td><p>TRKSHAREDFILE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trklenmsg </p>         </td>
         <td>         </td>
         <td><p>TRKLENMSG  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trklocmaxtime </p>         </td>
         <td><p>300  </p>         </td>
         <td><p>TRKLOCMAXTIME  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktmode (*<a href="#*sentinel.TRKTMODE">see below</a>)</p>         </td>
         <td><p>RETRY</p>         </td>
         <td><p>TRKTMODE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktconnretry </p>         </td>
         <td><p>60</p>         </td>
         <td><p>TRKTCONNRETRY  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkretrydelay </p>         </td>
         <td><p>10</p>         </td>
         <td><p>TRKRETRYDELAY  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkretrynb </p>         </td>
         <td><p>6</p>         </td>
         <td><p>TRKRETRYNB  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkdelay </p>         </td>
         <td><p>10</p>         </td>
         <td><p>TRKDELAY  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktimeout </p>         </td>
         <td><p>60</p>         </td>
         <td><p>TRKTIMEOUT  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkproductname </p>         </td>
         <td><p>CFT  </p>         </td>
         <td><p>TRKPRODUCTNAME  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipaddr </p>         </td>
         <td><p>sentinel-server-hostname  </p>         </td>
         <td><p>TRKIPADDR  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipport </p>         </td>
         <td><p>1761  </p>         </td>
         <td><p>TRKIPPORT  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_min_port </p>         </td>
         <td><p>5000  </p>         </td>
         <td><p>TRK_MIN_PORT  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_max_port </p>         </td>
         <td><p>32000</p>         </td>
         <td><p>TRK_MAX_PORT  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipaddr_bkup</p>         </td>
         <td>         </td>
         <td><p>TRKIPADDR_BKUP  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipport_bkup </p>         </td>
         <td><p>1761  </p>         </td>
         <td><p>TRKIPPORT_BKUP  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_min_port_bkup </p>         </td>
         <td><p>5000  </p>         </td>
         <td><p>TRK_MIN_PORT_BKUP  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_max_port_bkup </p>         </td>
         <td><p>32000  </p>         </td>
         <td><p>TRK_MAX_PORT_BKUP  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktype </p>         </td>
         <td><p>TCP  </p>         </td>
         <td><p>TRKTYPE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkgmtdiff </p>         </td>
         <td><p>60  </p>         </td>
         <td><p>TRKGMTDIFF  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrcfile </p>         </td>
         <td><p>$(cft.runtime_dir)/run/sentinel.trc  </p>         </td>
         <td><p>TRKTRCFILE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrace </p>         </td>
         <td><p>0  </p>         </td>
         <td><p>TRKTRACE  </p>         </td>
      </tr>
      <tr>
         <td>sentinel.trktmaxmsg         </td>
         <td>100000 (0 indicates no limit)         </td>
         <td>TRKTMAXMSG         </td>
      </tr>
   </tbody>
</table>

For more information on event messages, refer to the <span class="italic_in_para">Axway Sentinel</span> documentation.

## Sentinel Heartbeat implementation parameters

The following table lists the Heartbeat parameters that you can set in the unified configuration.

<table>
   <th>
      <tr>
<th>Unified configuration parameter         </th>
<th>Default value         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.heartbeat.enable         </td>
         <td>NO         </td>
         <td><p>Enables sending Heartbeats to the Sentinel Server.</p>         </td>
      </tr>
      <tr>
         <td>sentinel.heartbeat.periodicity         </td>
         <td>300         </td>
         <td>The delay in seconds between sending Heartbeats.         </td>
      </tr>
      <tr>
         <td>sentinel.heartbeat.script         </td>
         <td><p>$(cft.install_dir)</p>
<p>/extras/sentinel/MFTheartbeat.sh</p>
<p><span class="italic_in_para">or</span></p>
<p>$(cft.install_dir)</p>
<p>\extras\sentinel\MFTheartbeat.bat</p>         </td>
         <td>Script for executing Heartbeats.         </td>
      </tr>
   </tbody>
</table>

## Sentinel parameters

The following table lists the parameters that you can set in the unified configuration.

<table>
   <th>
      <tr>
<th>Unified configuration parameter         </th>
<th>Default value         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.xfb.transfer_progress_period         </td>
         <td>60         </td>
         <td><p>The frequency in seconds in which Transfer CFT notifies Sentinel (for both SENDING and RECEIVING states) that a transfer is running.</p>
<p>0 = no notification</p>
<p> </p>         </td>
      </tr>
      <tr>
         <td>sentinel.xfb.transfer.send_relay_site_nidf         </td>
         <td>No         </td>
         <td>Enables an NIDF on the relay site. This uses an NIDF instead of COMMUT when sending an event to Sentinel using the XFBTransfer object.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span><span id="sentinel.TRKTMODE"></span>\*sentinel.TRKTMODE

The mode that Transfer CFT uses to send messages to the Sentinel Server. The possible values of this parameter include:

-   Immediat: When a connection to the Sentinel Server is established, Transfer CFT sends the messages that are saved in the overload file; it then sends new messages arriving from the application. If a connection does not exist, it attempts a connection to the Sentinel Server upon reception of each new message from the application.  
    For MVS, the messages in the overflow file are not automatically sent on connection.

<!-- -->

-   Differ: Transfer CFT saves incoming messages in the overflow file.
-   Retry: (default mode) Behaves as in the immediate mode (above), except that if the connection to the Sentinel Server fails, the application repeats connection attempts every `n` minutes. To configure the retry period set the UCONF sentinel.TRKTCONNRETRY parameter.

## Sentinel EventTime

By default, the data sent to Sentinel as the EventTime has the format HH:MM:SS. To add milliseconds to the format, HH:MM:SS.sss, set the Transfer CFT UCONF <span class="code">cft.cftlog.time\_precision</span> parameter, where:

-   1 (default): the time in CFTLOG displays in seconds
-   10: the time in CFTLOG displays in tenths of seconds
-   100: the time in CFTLOG displays in hundredths of seconds

If the<span class="code"> cft.cftlog.time\_precision</span> value is greater than 1, the Transfer CFT EventTime message sent to Sentinel has the HH:MM:SS.dh0 format.

**Example**



    uconfset id=cft.cftlog.time_precision, value=10

-   1 (default): the time in CFTLOG displays in seconds
-   10: the time in CFTLOG displays in tenths of seconds
-   100: the time in CFTLOG displays in hundredths of seconds

If the<span class="code"> cft.cftlog.time\_precision</span> value is greater than 9, the Transfer CFT EventTime message sent to Sentinel has the HH:MM:SS.dh0 format.

**Example**



    uconfset id=cft.cftlog.time_precision, value=10
