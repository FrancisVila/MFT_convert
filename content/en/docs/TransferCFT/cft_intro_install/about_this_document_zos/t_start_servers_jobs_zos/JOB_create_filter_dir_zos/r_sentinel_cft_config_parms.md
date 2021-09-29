{
    "title": "Sentinel communication parameters",
    "linkTitle": "Sentinel communication parameters",
    "weight": "250"
}To define to enable Sentinel to Transfer CFT interoperability, refer to:

-   [](#communication%20with%20the%20event%20router)[Communication with an Event via TCP all platforms](#communication%20with%20an%20event%20via%20tcp) 
-   [UCONF parameters for Sentinel interoperability all platforms](#uconf%20parameters%20for%20sentinel%20interoperability)
-   [Communication with the Event Router](#communication%20with%20the%20event%20router) [for z/OS](#communication%20with%20the%20event%20router)   
-   [Overflow file definition for z/OS](#overflow%20file%20definition) 

## <span id="Communication with an Event via TCP"></span>Communication with an Event via TCP

**All platforms**

This table lists the main parameters that you must define in order to communicate with an Event via TCP, and uses TRKTYPE=TCP as the default value.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th> </th>
<th>Event Router</th>
<th>TRKUTIL</th>
<th>Transfer CFT</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<th>Configuration file</th>
<td>USEPARIN</td>
<td>TRKCONF</td>
<td>UCONF</td>
</tr>
<tr class="even">
<th rowspan="3">TCP definition</th>
<td><p>(AGENT)</p>
<p>queue=”NOQ”</p></td>
<td>TRKTYPE=TCP</td>
<td>UCONFSET ID=sentinel.TRKTYPE,VALUE=TCP</td>
</tr>
<tr class="odd">
<td>(TCPSOURCE) sap=nnnn</td>
<td>TRKIPPORT=nnnn</td>
<td>UCONFSET ID=sentinel.TRKIPPORT,VALUE=nnnn</td>
</tr>
<tr class="even">
<td><p>(TCPSOURCE)</p>
<p>local_address=</p></td>
<td>TRKIPADDR=</td>
<td>UCONFSET ID=sentinel.TRKIPADDR,VALUE=</td>
</tr>
</tbody>
</table>

## <span id="UCONF parameters for Sentinel interoperability"></span>UCONF parameters for Sentinel interoperability

**All platforms**

The table below lists the UCONF values that are used in Transfer CFT to define Sentinel interoperability. You can set these UCONF values using either the Copilot UI or command line.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Unified configuration parameter</th>
<th>Default value</th>
<th><p>Former Sentinel parameter name</p>
<p>trkapi.cfg</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>sentinel.xfb.enable</td>
<td>NO</td>
<td>XFB.Sentinel (trkapi.cfg)</td>
</tr>
<tr class="even">
<td><p>sentinel.xfb.transfer</p></td>
<td><p>ALL</p></td>
<td><p>XFB.Transfer (trkapi.cfg)</p></td>
</tr>
<tr class="odd">
<td><p>sentinel.xfb.shut</p></td>
<td><p>0</p></td>
<td><p>XFB.Shut (trkapi.cfg)</p></td>
</tr>
<tr class="even">
<td><p>sentinel.xfb.log</p></td>
<td><p>IEWF</p></td>
<td><p>XFB.Log (trkapi.cfg)</p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trktname</p></td>
<td><p>$(cft.runtime_dir)/data/trkapi.buf  </p></td>
<td><p>TRKTNAME (trkapi.cfg)  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trksharedfile </p></td>
<td><p>No  </p></td>
<td><p>TRKSHAREDFILE  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trklenmsg </p></td>
<td></td>
<td><p>TRKLENMSG  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trklocmaxtime </p></td>
<td><p>300  </p></td>
<td><p>TRKLOCMAXTIME  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trktmode </p></td>
<td><p>DIFFER</p></td>
<td><p>TRKTMODE  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trktconnretry </p></td>
<td><p>60</p></td>
<td><p>TRKTCONNRETRY  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkretrydelay </p></td>
<td><p>10</p></td>
<td><p>TRKRETRYDELAY  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trkretrynb </p></td>
<td><p>6</p></td>
<td><p>TRKRETRYNB  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkdelay </p></td>
<td><p>10</p></td>
<td><p>TRKDELAY  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trktimeout </p></td>
<td><p>60</p></td>
<td><p>TRKTIMEOUT  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkproductname </p></td>
<td><p>CFT  </p></td>
<td><p>TRKPRODUCTNAME  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trkipaddr </p></td>
<td><p>sentinel-server-hostname  </p></td>
<td><p>TRKIPADDR  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkipport </p></td>
<td><p>1761  </p></td>
<td><p>TRKIPPORT  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trk_min_port </p></td>
<td><p>5000  </p></td>
<td><p>TRK_MIN_PORT  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trk_max_port </p></td>
<td><p>32000</p></td>
<td><p>TRK_MAX_PORT  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trkipaddr_bkup</p></td>
<td></td>
<td><p>TRKIPADDR_BKUP  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkipport_bkup </p></td>
<td><p>1761  </p></td>
<td><p>TRKIPPORT_BKUP  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trk_min_port_bkup </p></td>
<td><p>5000  </p></td>
<td><p>TRK_MIN_PORT_BKUP  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trk_max_port_bkup </p></td>
<td><p>32000  </p></td>
<td><p>TRK_MAX_PORT_BKUP  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trktype </p></td>
<td><p>TCP  </p></td>
<td><p>TRKTYPE  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trkgmtdiff </p></td>
<td><p>60  </p></td>
<td><p>TRKGMTDIFF  </p></td>
</tr>
<tr class="even">
<td><p>sentinel.trktrcfile </p></td>
<td><p>$(cft.runtime_dir)/run/sentinel.trc  </p></td>
<td><p>TRKTRCFILE  </p></td>
</tr>
<tr class="odd">
<td><p>sentinel.trktrace </p></td>
<td><p>0  </p></td>
<td><p>TRKTRACE  </p></td>
</tr>
</tbody>
</table>

##  <span id="Communication with the Event Router"></span>Communication with the Event Router

**Z/OS environment**

The following parameters define communication with the Event Router via XCF. In this setup:

-   The XCF definition (queue=xxxx) is the XCF member name representing the ER server
-   The XCF group is PELISCOP by default. You can modify this default by setting queue = “member group”

<table data-cellspacing="0">
<thead>
<tr class="header">
<th> </th>
<th>ER</th>
<th>TRKUTIL</th>
<th>Transfer CFT</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-mc-conditions="">
<td>Configuration file</td>
<td>USEPARIN</td>
<td>TRKCONF</td>
<td>UCONF</td>
</tr>
<tr class="even" data-mc-conditions="">
<td>SVC</td>
<td><p>(SYSTEM)</p>
<p>svc_nb=nnn</p></td>
<td>TRKSVC=nnn</td>
<td>UCONFSET ID=sentinel.TRKSVC,VALUE=nnn</td>
</tr>
<tr class="odd" data-mc-conditions="">
<td rowspan="2">XCF definition</td>
<td rowspan="2">(AGENT)queue=</td>
<td>TRKQUEUE=</td>
<td>UCONFSET ID=sentinel.TRKQUEUE,VALUE=xxxx</td>
</tr>
<tr class="even" data-mc-conditions="">
<td>TRKTYPE=XCF</td>
<td>UCONFSET ID=sentinel.TRKTYPE,VALUE=XCF</td>
</tr>
</tbody>
</table>

## <span id="Overflow file definition"></span>Overflow file definition

**Z/OS environment**

The following table describes the overflow file definition for the Logger file. In this setup:

-   TRKSHAREDFILE=YES is MANDATORY when the logger file is shared between the Event Router and other applications. Set this to NO if the applications are sending messages directly to the Sentinel server without going through the Event Router
-   The log structure is ONLY used to define a logger file shared between the partitions of the SYSPLEX, and is NOT referenced in any parameters

<table data-cellspacing="0">
<thead>
<tr class="header">
<th> </th>
<th>Event Router</th>
<th>TRKUTIL</th>
<th>Transfer CFT</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-mc-conditions="">
<th>Configuration file</th>
<td>USEPARIN</td>
<td>TRKCONF</td>
<td>UCONF</td>
</tr>
<tr class="even" data-mc-conditions="">
<th rowspan="2">Logger file</th>
<td><p>(AGENT)</p>
<p>api_file=</p></td>
<td>TRKTNAME=</td>
<td>UCONFSET ID=sentinel.TRKTNAME, VALUE=xxxx.xxxx.xxx</td>
</tr>
<tr class="odd" data-mc-conditions="">
<td> </td>
<td>TRKSHAREDFILE=YES</td>
<td>UCONFSET ID=sentinel.TRKSHAREDFILE,VALUE=YES</td>
</tr>
</tbody>
</table>

Related topics

[About Axway Sentinel](../../../../../using_sentinel)

[Using the unified configuration GUI](../../../../../admin_intro/uconf/uconf_interface_actions)

[Using the unified configuration CFTUTIL](../../../../../admin_intro/uconf/uconf_w_cftutil)

[Installing Sentinel for Transfer CFT z/OS](../../../overview_install_zos/manual_installation_steps/t_install_sentinel_zos)
