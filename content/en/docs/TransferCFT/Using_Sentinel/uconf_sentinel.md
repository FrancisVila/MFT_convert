{
    "title": "UCONF: Sentinel options",
    "linkTitle": "UCONF: Sentinel options",
    "weight": "250"
}This section describes how to configure the Sentinel monitoring agent, which is part of Transfer CFT, using the following groups of UCONF parameters:

-   sentinel.trkxxxxx: These parameters correspond to the trkxxxxx parameter described in the [Sentinel Universal Agent User Guide](sentineluniversalagent_2.3.3_usersguide_allos_en.pdf) .
-   sentinel.xfb.xxxx: These parameters indicate how the Sentinel monitoring agent is used in Transfer CFT.
-   Additional uconf values are related to the communication between the Sentinel monitoring agent and Sentinel
    -   ssl.ciphersuites
    -   ssl.version\_min
    -   ssl.extension.enable\_sni
    -   cft.ipv6.disable\_connect
    -   See [UCONF parameters](../../admin_intro/uconf/uconf_directory) for parameter details.
-   sentinel.trktname: The path to the overflow file, where the maximum number of messages that the overflow file can store is equal to sentinel.xfb.buffer\_size (not sentinel.trktmaxmsg).
-   sentinel.trktmaxmsg: *Obsolete*. The maximum number of messages in the sentinel.trktname overflow file is defined by the sentinel.xfb.buffer\_size.

## Overflow file

You can define an overflow file to store Sentinel events if the Sentinel server is not available, for example due to network issues or because the server is stopped. If Sentinel tracking is enabled but the server is not available, the message "CFTS30I XTRK Information Sentinel Connection failed" displays in the log. When the Sentinel connection is available again, the next event triggers the sending of previously-stored events.

Use the following uconf parameters to configure the name and size of the overflow file:

-   sentinel.trktname: The path to the overflow file.
-   sentinel.xfb.buffer\_size: The maximum number of messages that the overflow file can store. Once the maximum value is reached, messages are no longer sent to Sentinel and:
    -   If sentinel.xfb.shut is set to any value other than 0, Transfer CFT stops.
    -   If sentinel.xfb.shut is set to 0, Transfer CFT continues to run.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> The <span>sentinel.trktmaxmsg </span>parameter is <i>obsolete</i>.<span> Sentinel.xfb.buffer_size</span> defines the maximum number of messages in the <span>sentinel.trktname</span> overflow file.         </td>
      </tr>
</table>

## Sentinel configuration parameters

The following table lists the Sentinel parameters in the unified configuration and the corresponding former Sentinel parameter.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Unified configuration parameter</th>
         <th>Default value</th>
         <th>
            <p>Former Sentinel parameter name </p>
            <p>trkapi.cfg</p>
</th>
      </tr>
   </thead>
      <tr>
         <td>sentinel.xfb.enable         </td>
         <td>NO         </td>
         <td>XFB.Sentinel (trkapi.cfg)         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.xfb.transfer                            </p>
         </td>
         <td width="20px">
            <p>ALL</p>
         </td>
         <td width="181.2pt">
            <p>XFB.Transfer (trkapi.cfg)
                            </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.xfb.shut                            </p>
         </td>
         <td width="20px">
            <p>0
                            </p>
         </td>
         <td width="181.2pt">
            <p>XFB.Shut (trkapi.cfg)
                            </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.xfb.log                            </p>
         </td>
         <td width="20px">
            <p>IEWF</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
         <td width="181.2pt">
            <p>XFB.Log (trkapi.cfg)
                            </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktname</p>
         </td>
         <td width="20px">
            <p>$(cft.runtime_dir)/data/trkapi.buf  </p>
         </td>
         <td width="181.2pt">
            <p>TRKTNAME (trkapi.cfg)  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trksharedfile </p>
         </td>
         <td width="20px">
            <p>No  </p>
         </td>
         <td width="181.2pt">
            <p>TRKSHAREDFILE  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trklenmsg </p>
         </td>
         <td width="20px">
            <p> </p>
         </td>
         <td width="181.2pt">
            <p>TRKLENMSG  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trklocmaxtime </p>
         </td>
         <td width="20px">
            <p>300  </p>
         </td>
         <td width="181.2pt">
            <p>TRKLOCMAXTIME  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktmode (*<a href="#*sentinel.trktmode">see below</a>)</p>
         </td>
         <td width="20px">
            <p>RETRY</p>
         </td>
         <td width="181.2pt">
            <p>TRKTMODE  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktconnretry </p>
         </td>
         <td width="20px">
            <p>60 </p>
         </td>
         <td width="181.2pt">
            <p>TRKTCONNRETRY  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkretrydelay </p>
         </td>
         <td width="20px">
            <p>10 </p>
         </td>
         <td width="181.2pt">
            <p>TRKRETRYDELAY  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkretrynb </p>
         </td>
         <td width="20px">
            <p>6 </p>
         </td>
         <td width="181.2pt">
            <p>TRKRETRYNB  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkdelay </p>
         </td>
         <td width="20px">
            <p>10 </p>
         </td>
         <td width="181.2pt">
            <p>TRKDELAY  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktimeout </p>
         </td>
         <td width="20px">
            <p>60 </p>
         </td>
         <td width="181.2pt">
            <p>TRKTIMEOUT  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkproductname </p>
         </td>
         <td width="20px">
            <p>CFT  </p>
         </td>
         <td width="181.2pt">
            <p>TRKPRODUCTNAME  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkipaddr </p>
         </td>
         <td width="20px">
            <p>sentinel-server-hostname  </p>
         </td>
         <td width="181.2pt">
            <p>TRKIPADDR  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkipport </p>
         </td>
         <td width="20px">
            <p>1761  </p>
         </td>
         <td width="181.2pt">
            <p>TRKIPPORT  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trk_min_port </p>
         </td>
         <td width="20px">
            <p>5000  </p>
         </td>
         <td width="181.2pt">
            <p>TRK_MIN_PORT  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trk_max_port </p>
         </td>
         <td width="20px">
            <p>32000 </p>
         </td>
         <td width="181.2pt">
            <p>TRK_MAX_PORT  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkipaddr_bkup</p>
         </td>
         <td width="20px">
            <p> </p>
         </td>
         <td width="181.2pt">
            <p>TRKIPADDR_BKUP  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkipport_bkup </p>
         </td>
         <td width="20px">
            <p>1761  </p>
         </td>
         <td width="181.2pt">
            <p>TRKIPPORT_BKUP  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trk_min_port_bkup </p>
         </td>
         <td width="20px">
            <p>5000  </p>
         </td>
         <td width="181.2pt">
            <p>TRK_MIN_PORT_BKUP  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trk_max_port_bkup </p>
         </td>
         <td width="20px">
            <p>32000  </p>
         </td>
         <td width="181.2pt">
            <p>TRK_MAX_PORT_BKUP  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktype </p>
         </td>
         <td width="20px">
            <p>TCP  </p>
         </td>
         <td width="181.2pt">
            <p>TRKTYPE  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trkgmtdiff </p>
         </td>
         <td width="20px">
            <p>60  </p>
         </td>
         <td width="181.2pt">
            <p>TRKGMTDIFF  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktrcfile </p>
         </td>
         <td width="20px">
            <p>$(cft.runtime_dir)/run/sentinel.trc  </p>
         </td>
         <td width="181.2pt">
            <p>TRKTRCFILE  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>
            <p>sentinel.trktrace </p>
         </td>
         <td width="20px">
            <p>0  </p>
         </td>
         <td width="181.2pt">
            <p>TRKTRACE  </p>
         </td>
      </tr>
      <tr valign="middle">
         <td>sentinel.trktmaxmsg          </td>
         <td width="20px">100000 (0 indicates no limit)         </td>
         <td width="181.2pt">TRKTMAXMSG         </td>
      </tr>
</table>

For more information on event messages, refer to the Axway Sentinel documentation.

## Sentinel Heartbeat implementation parameters

The following table lists the Heartbeat parameters that you can set in the unified configuration.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To disable, set to ' '.         </td>
      </tr>
</table>

## Sentinel parameters

The following table lists the parameters that you can set in the unified configuration.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Unified configuration parameter</th>
         <th>Default value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.heartbeat.enable          </td>
         <td> NO         </td>
         <td>
            <p>Enables sending Heartbeats to the Sentinel Server.</p>
         </td>
      </tr>
      <tr>
         <td>sentinel.heartbeat.periodicity          </td>
         <td>300         </td>
         <td>The delay in seconds between sending Heartbeats.           </td>
      </tr>
      <tr>
         <td>sentinel.heartbeat.script          </td>
         <td>
            <p>$(cft.install_dir)</p>
            <p>/extras/sentinel/MFTheartbeat.sh </p>
            <p><span>or</span>
</p>
            <p>$(cft.install_dir)</p>
            <p>\extras\sentinel\MFTheartbeat.bat         </p>
         </td>
         <td>Script for executing Heartbeats.         </td>
      </tr>
   </tbody>
</table>

<span id="*sentinel.TRKTMODE"></span>\*sentinel.TRKTMODE

The mode that Transfer CFT uses to send messages to the Sentinel Server. The possible values of this parameter include:

-   Immediat: When a connection to the Sentinel Server is established, Transfer CFT sends the messages that are saved in the overload file; it then sends new messages arriving from the application. If a connection does not exist, it attempts a connection to the Sentinel Server upon reception of each new message from the application.  
    For MVS, the messages in the overflow file are not automatically sent on connection.

<!-- -->

-   Differ: Transfer CFT saves incoming messages in the overflow file.
-   Retry: (default mode) Behaves as in the immediate mode (above), except that if the connection to the Sentinel Server fails, the application repeats connection attempts every `n` minutes. To configure the retry period set the UCONF sentinel.TRKTCONNRETRY parameter.

## Sentinel EventTime

By default, the data sent to Sentinel as the EventTime has the format HH:MM:SS. To add milliseconds to the format, HH:MM:SS.sss, set the Transfer CFT UCONF cft.cftlog.time\_precision parameter, where:

-   1 (default): the time in CFTLOG displays in seconds
-   10: the time in CFTLOG displays in tenths of seconds
-   100: the time in CFTLOG displays in hundredths of seconds

If the cft.cftlog.time\_precision value is greater than 1, the Transfer CFT EventTime message sent to Sentinel has the HH:MM:SS.dh0 format.

**Example**

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Unified configuration parameter</th>
         <th>Default value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.xfb.transfer_progress_period         </td>
         <td>60         </td>
         <td>
            <p>The frequency in seconds in which Transfer CFT notifies Sentinel   (for both SENDING and RECEIVING states) that a transfer is running.</p>
            <p> 0 = no notification</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>sentinel.xfb.transfer.send_relay_site_nidf         </td>
         <td>No         </td>
         <td>Enables an NIDF on the relay site. This uses an NIDF instead of COMMUT when sending an event to Sentinel using the XFBTransfer object.         </td>
      </tr>
   </tbody>
</table>

-   1 (default): the time in CFTLOG displays in seconds
-   10: the time in CFTLOG displays in tenths of seconds
-   100: the time in CFTLOG displays in hundredths of seconds

If the cft.cftlog.time\_precision value is greater than 9, the Transfer CFT EventTime message sent to Sentinel has the HH:MM:SS.dh0 format.

**Example**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>uconfset id=cft.cftlog.time_precision, value=10</p>
         </td>
      </tr>
   </tbody>
</table>
