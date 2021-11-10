{
    "title": "Transfer CFT to Sentinel communication parameters",
    "linkTitle": "Sentinel communication parameters",
    "weight": "240"
}To define to enable Sentinel to Transfer CFT interoperability, refer to:

-   [](#Communication%20with%20the%20Event%20Router)[Communication with an Event via TCP all platforms](#Communication%20with%20an%20Event%20via%20TCP) 
-   [UCONF parameters for Sentinel interoperability all platforms](#UCONF%20parameters%20for%20Sentinel%20interoperability)
-   [Communication with the Event Router](#Communication%20with%20the%20Event%20Router) [for z/OS](#Communication%20with%20the%20Event%20Router)   
-   [Overflow file definition for z/OS](#Overflow%20file%20definition) 

<span id="Communication with an Event via TCP"></span>

## Communication with an Event via TCP

**All platforms**

This table lists the main parameters that you must define in order to communicate with an Event via TCP, and uses TRKTYPE=TCP as the default value.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadE-Column1-Header1">Event Router         </th>
<th class="HeadE-Column1-Header1">TRKUTIL         </th>
<th class="HeadD-Column1-Header1">Transfer CFT         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th class="BodyE-Column1-Body1">Configuration file         </th>
         <td>USEPARIN         </td>
         <td>TRKCONF         </td>
         <td>UCONF         </td>
      </tr>
      <tr>
<th rowspan="3" class="BodyE-Column1-Body2">TCP definition         </th>
         <td><p>(AGENT)</p>
<p>queue=”NOQ”</p>         </td>
         <td>TRKTYPE=TCP         </td>
         <td>UCONFSET ID=sentinel.TRKTYPE,VALUE=TCP         </td>
      </tr>
      <tr>
         <td>(TCPSOURCE) sap=nnnn         </td>
         <td>TRKIPPORT=nnnn         </td>
         <td>UCONFSET ID=sentinel.TRKIPPORT,VALUE=nnnn         </td>
      </tr>
      <tr>
         <td><p>(TCPSOURCE)</p>
<p>local_address=</p>         </td>
         <td>TRKIPADDR=         </td>
         <td>UCONFSET ID=sentinel.TRKIPADDR,VALUE=         </td>
      </tr>
   </tbody>
</table>

<span id="UCONF parameters for Sentinel interoperability"></span>

## UCONF parameters for Sentinel interoperability

**All platforms**

The table below lists the UCONF values that are used in Transfer CFT to define Sentinel interoperability. You can set these UCONF values using either the Copilot UI or command line.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Unified configuration parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default value         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Former Sentinel parameter name</p>
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
         <td><p>IEWF</p>         </td>
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
         <td><p>$(cft.runtime_dir)/run/sentinel.trc  </p>         </td>
         <td><p>TRKTRCFILE  </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrace </p>         </td>
         <td><p>0  </p>         </td>
         <td><p>TRKTRACE  </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Communication with the Event Router"></span>

##  Communication with the Event Router

**Z/OS environment**

The following parameters define communication with the Event Router via XCF. In this setup:

-   The XCF definition (queue=xxxx) is the XCF member name representing the ER server
-   The XCF group is PELISCOP by default. You can modify this default by setting queue = “member group”

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">ER         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">TRKUTIL         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Transfer CFT         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Configuration file         </td>
         <td>USEPARIN         </td>
         <td>TRKCONF         </td>
         <td>UCONF         </td>
      </tr>
      <tr>
         <td>SVC         </td>
         <td><p>(SYSTEM)</p>
<p>svc_nb=nnn</p>         </td>
         <td>TRKSVC=nnn         </td>
         <td>UCONFSET ID=sentinel.TRKSVC,VALUE=nnn         </td>
      </tr>
      <tr>
         <td>XCF definition         </td>
         <td>(AGENT)queue=         </td>
         <td>TRKQUEUE=         </td>
         <td>UCONFSET ID=sentinel.TRKQUEUE,VALUE=xxxx         </td>
      </tr>
      <tr>
         <td>TRKTYPE=XCF         </td>
         <td>UCONFSET ID=sentinel.TRKTYPE,VALUE=XCF         </td>
      </tr>
   </tbody>
</table>

<span id="Overflow file definition"></span>

## Overflow file definition

**Z/OS environment**

The following table describes the overflow file definition for the Logger file. In this setup:

-   TRKSHAREDFILE=YES is MANDATORY when the logger file is shared between the <span class="mc-variable suite_variables.EventRouterName variable">Event Router</span> and other applications. Set this to NO if the applications are sending messages directly to the Sentinel server without going through the <span class="mc-variable suite_variables.EventRouterName variable">Event Router</span>
-   The log structure is ONLY used to define a logger file shared between the partitions of the SYSPLEX, and is NOT referenced in any parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Event Router         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">TRKUTIL         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Transfer CFT         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Configuration file         </th>
         <td>USEPARIN         </td>
         <td>TRKCONF         </td>
         <td>UCONF         </td>
      </tr>
      <tr>
<th rowspan="2" class="TableStyle-SynchTableStyle_interop-BodyE-Column1-Body2">Logger file         </th>
         <td><p>(AGENT)</p>
<p>api_file=</p>         </td>
         <td>TRKTNAME=         </td>
         <td>UCONFSET ID=sentinel.TRKTNAME, VALUE=xxxx.xxxx.xxx         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>TRKSHAREDFILE=YES         </td>
         <td>UCONFSET ID=sentinel.TRKSHAREDFILE,VALUE=YES         </td>
      </tr>
   </tbody>
</table>

Related topics

[About Axway Sentinel](../../../../../using_sentinel)

[Using the unified configuration GUI](../../../../../admin_intro/uconf/uconf_interface_actions)

[Using the unified configuration CFTUTIL](../../../../../admin_intro/uconf/uconf_w_cftutil)

[Installing Sentinel for Transfer CFT z/OS](../../../overview_install_zos/manual_installation_steps/t_install_sentinel_zos)
