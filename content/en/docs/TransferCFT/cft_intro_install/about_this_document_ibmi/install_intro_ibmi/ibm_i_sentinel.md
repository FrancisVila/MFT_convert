{
    "title": "Manually enable Sentinel ",
    "linkTitle": "Manually enable Sentinel",
    "weight": "240"
}When using <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, the visibility features are managed by <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>. Do not modify these parameters when running with <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

## Sentinel configuration parameters

The following table lists the Sentinel parameters in the unified configuration and the corresponding former Sentinel parameter.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">UCONF parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Former Sentinel parameter</p>
<p>TRKCNF</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>sentinel.xfb.enable         </td>
         <td>NO         </td>
         <td>XFB.Sentinel (TRKCNF)         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>XFB.Transfer (TRKCNF)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.shut</p>         </td>
         <td><p>0</p>         </td>
         <td><p>XFB.Shut (TRKCNF)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.log</p>         </td>
         <td><p>IEWF</p>         </td>
         <td><p>XFB.Log (TRKCNF)</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktname</p>         </td>
         <td><p>$(cft.runtime_dir)<br />
/data/trkapi.buf  </p>         </td>
         <td><p>TRKTNAME (TRKCNF)  </p>         </td>
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
         <td><p>sentinel.trktmode </p>         </td>
         <td><p>DIFFER</p>         </td>
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
         <td><p>$(cft.runtime_dir)<br />
/run/sentinel.trc  </p>         </td>
         <td><p>TRKTRCFILE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrace </p>         </td>
         <td><p>0  </p>         </td>
         <td><p>TRKTRACE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer_progress_period</p>
<p>The frequency in seconds in which Transfer CFT notifies Sentinel (for both SENDING and RECEIVING states) that a transfer is running.</p>
<p>0 = no notification</p>         </td>
         <td>60         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer.send_relay_site_nidf</p>
<p>Enables an NIDF on the relay site. This uses an NIDF instead of COMMUT when sending an event to Sentinel using the XFBTransfer object.</p>         </td>
         <td>No         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

For more information on event messages, refer to the <span class="italic_in_para">Axway Sentinel</span> documentation.

## About Transfer CFT heartbeat functionality

When the Transfer CFT heartbeat function is activated, it sends the attributes to the Axway Sentinel server via TRKUTIL.

For more information on tracked objects, refer to the Axway Sentinel User's Guide.

### Sentinel Heartbeat implementation parameters

The following table lists the Heartbeat parameters that you can set in the unified configuration.

Each Transfer CFT environment number n (from 1 to 5) has its own corresponding Heartbeat script. You should check the default names (such as in the production library, jobd, and Transfer CFT file) that are used in the script.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Unified configuration parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default value         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
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
         <td><p>CFTPROD/HEARTBEAT</p>         </td>
         <td>Script for executing Heartbeats.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>Example


    uconfset id=sentinel.heartbeat.enable,value=yes
    uconfset id=sentinel.heartbeat.periodicity,value=300
    uconfset id=sentinel.heartbeat.script,value=CFTPROD/HEARTBEAT
    uconfset id=sentinel.trkipaddr,value=serveur.sentinel.address
    uconfset id=sentinel.trkipport,value=11277
    uconfset id=sentinel.trklocaladdr,value=as400.local.address
