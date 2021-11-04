{
    "title": "Transfer CFT messages: CFTC",
    "linkTitle": "CFTC messages",
    "weight": "280"
}This topic lists the CFTC (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: <span class="code">CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started</span>

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC01W"></span>CFTC01W CFT catalog storage is short n record(s) free </p>
<p>CFTC01W CFT catalog storage is short n record(s) free </p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Catalog storage is short n record(s) free.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The catalog is nearly full - there are only n records free. Consider modifications to free up space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTC01E"></span>CFTC01E CFT catalog storage is full  </p>
<p>CFTC01E CFT catalog storage is full</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The catalog storage is full. A command SHUT FAST=KILL is executed.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The stored commands can only be retrieved by restarting <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. First purge the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog (and modify the retention dates, for example).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC03W"></span>CFTC03W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _
Running out of time (HHMMSSCC)</p>
<p>CFTC03W Transfer Running out of time &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt [sgt=HHMMSSCC]</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The transfer start time is outside the interval authorized by
the &amp;part partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The next transfer retry will take place at the specified time
[HHMMSSCC].</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC04W"></span>CFTC04W PART=&amp;part  IDF=&amp;idf IDT=&amp;idt
_ State C delete forbidden</p>
<p>CFTC04W _ State C delete forbidden &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A DELETE command was executed on a catalog request (in the C
state), but this operation is not allowed.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The catalog entry could not be deleted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC05W"></span>CFTC05W PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt _ Delete
failed</p>
<p>CFTC05W _ Delete failed &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A DELETE command was executed on a catalog request (in a state
other than C or D), but it failed as a result of a catalog access error.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The catalog entry could not be deleted.</p>
<p>The
CFTT21E message may be displayed before this message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTC06E"></span>CFTC06E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _
Update failed</p>
<p>CFTC06E _ Update failed &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A Transfer
CFT catalog access error was detected when executing commands, such as
END, START, ACT and INACT.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The catalog entry was not updated and the command was ignored.</p>
<p>The CFTT21E message is displayed prior to this message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC07I"></span>CFTC07I PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt
STATE=&amp;state - Deleted</p>
<p>CFTC07I Transfer Deleted &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt STATE=&amp;state DIRECT=&amp;direct</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A Transfer
CFT catalog entry for partner &amp;part, with identifier &amp;idf, idt
&amp;idt and state &amp;state, has been deleted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
Information         </td>
         <td><p><span id="CFTC08I"></span>CFTC08I &amp;str</p>
<p>CFTC08I &amp;str</p>         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td><p>Possible values for &amp;str are described here. The following messages are displayed when the catalog is purged on <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> startup, or at the time set for the daily purge. For example:</p>
<p>When there are no transfers to delete:</p>
<div class="indentTableNested">
<p>Purge Started<br />
Purge catalog-size=1000 in-use=0 pre-filtered=0(0%)<br />
Purge Treated: catalog empty<br />
Purge deleted= n treated=n(d%) match=d%.<br />
Purge Treated<br />
Purge Treated: no record found to delete</p>
</div>
<p>When there are transfers to delete:</p>
<div class="indentTableNested">
<p>Catalog: Loading...<br />
Catalog: Load Done<br />
Catalog: Size=100, Used=8(8%)<br />
Purge Started.<br />
Purge catalog-size=100 in-use=8 pre-filtered=8(100)<br />
Purge deleted=1 treated=1(12) match=100<br />
Purge deleted=2 treated=2(25) match=100<br />
….<br />
Purge deleted=8 treated=8(100) match=100<br />
Purge Treated.</p>
</div>
<p>When <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> starts:</p>
<div class="indentTableNested">
<p>If there are no transfers to delete:</p>
<div class="indentTableNested">
<p>Catalog: Loading...<br />
Catalog: Load Done<br />
Catalog: Size= &amp;00, Used=0(0%)<br />
</p>
</div>
<p>If there are transfers to delete:</p>
<div class="indentTableNested">
<p>Catalog: Loading...<br />
Catalog: Load Done<br />
Catalog: Size=100, Used=8(8%)</p>
</div>
</div>
<p>If there is a problem with the catalog INIT:</p>
<div class="indentTableNested">
<p>Catalog: Recovering<br />
Catalog: Recovery Done: n errors<br />
Catalog Recovery: n transfers from C to D state</p>
</div>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC09I"></span>CFTC09I PART=&amp;part IDF=&amp;idf IDT=&amp;idt STATE=&amp;state
DIRECT=&amp;direct : &amp;cmd not executed</p>
<p>CFTC09I Command not executed &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt STATE=&amp;state DIRECT=&amp;direct : Cmd=&amp;cmd</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The security system does not allow the user to execute this
command on the catalog.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.</p>
<p>This
message is followed by the CFTX02W and CFTX04W messages.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC10I"></span>CFTC10I PART=&amp;part IDF or IDM=&amp;idf STATE=&amp;state
MODE=&amp;mode : &amp;cmd not executed</p>
<p>CFTC10I PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] STATE=&amp;state MODE=&amp;mode : &amp;cmd not executed</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The security system does not allow this user to execute this
command on the catalog.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored. One of the following messages displays after CFTC10I to provide additional information: CFTX01W , CFTX03W , or CFTX04W.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC11I"></span>CFTC11I PART=&amp;part IDM=&amp;idf IDT=&amp;idt :
SEND REPLY not executed</p>
<p>CFTC11I Command not executed &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt : Cmd=&amp;cmd</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The security system does not allow the user to execute this
command on the catalog.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>This message
is followed by the CFTX01W message.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC12I"></span>CFTC12I PART=&amp;part STATE=&amp;state DIRECT=&amp;direct TYPE=&amp;type SENTINEL_STATE=&amp;trkstate Deleted</p>
<p>CFTC12I IDTU=&amp;idtu PART=&amp;part STATE=&amp;state PHASE=&amp;phase PHASESTEP=&amp;phasestep DIRECT=&amp;direct TYPE=&amp;type SENTINEL_STATE=&amp;trkstate Deleted</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>This <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> message is displayed for each transfer that is deleted when the catalog is purged. Where:</p>
<ul>
<li>&amp;state = transfer status (C/D/H/K/T/X)</li>
<li>&amp;direct = S (send) / R (recv)</li>
<li>&amp;type = F (file) / M (message)</li>
<li>&amp;trkstate = Sentinel state</li>
</ul>
<p>Possible values are:</p>
<ul>
<li>TO_EXECUTE</li>
<li>SUSPENDED</li>
<li>RECEIVING</li>
<li>SENDING</li>
<li>CANCELED</li>
<li>RECEIVED</li>
<li>SENT</li>
<li>CREATED</li>
<li>INTERRUPTED</li>
<li>ACKED</li>
<li>NACKED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.<br />
</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC13I"></span>CFTC13I Catalog resize (xxxx --&gt; yyyy) done</p>
<p>CFTC13I Catalog resize (xxxx --&gt; yyyy) done</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A dynamic command to resize the catalog was executed. The first message displays the new size, and the second message indicates that the resizing (from the original size xxxx to the new size yyyy) is complete.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The catalog automatically expands to the new size (the &lt;yyyy&gt; value) when possible, up to the maximum defined limit.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTC13E"></span>CFTC13E <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog resize (xxxx --&gt; yyyy) reached max before expansion</p>
<p>CFTC13I Catalog resize (xxxx --&gt; yyyy) done</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A dynamic command to automatically expand the catalog failed, as the maximum number of records has already been reached. The catalog size remains unchanged (the &lt;xxxx&gt; value).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Normal functioning with existing catalog size, and no catalog expansion occurs.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTC13E"></span><span id="CFTC15I"></span>CFTC15I Deprecated command not executed BLKNUM=&amp;blknum PART=&amp;part IDT=&amp;idt : Cmd=&amp;cmd&gt;</p>
<p>CFTC15I Deprecated command not executed BLKNUM=&amp;blknum PART=&amp;part IDT=&amp;idt : Cmd=&amp;cmd</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Set the uconf parameter <span class="code">cft.cftcat.enable_deprecated_blknum=Yes</span> to enable BLKNUM.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Regardless of the <code>cft.cftcat.enable_deprecated_blknum</code> parameter setting, BLKNUM is disabled in a multi-node configuration (<code>uconf:cft.multi_node.enable=Yes</code>), and this message is displayed.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The command is ignored.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC29W"></span>CFTC29W
Catalog Alert fill threshold reached: level=&amp;level , id=CAT0</p>
<p>CFTC29W Catalog Alert fill threshold reached: level=&amp;level ID=&amp;id</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>&amp;level of the catalog space has been used. &amp;level is the amount
set by the CFTCAT TLVWARN parameter.</p>
<p>When the critical fill threshold is reached, a message
is recorded in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> log.</p>
<p>A batch in response to the alert, the CFTCAT TLVWEXEC parameter,
is submitted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTC30W"></span>CFTC30W Catalog
Alert cleared: level=&amp;level, id=CAT0</p>
<p>CFTC30W Catalog Alert cleared : level=&amp;level ID=&amp;id</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>This alert stops when the fill level drops below the TLVCLEAR
level.</p>
<p>When the alert stops, the message is recorded in the Transfer
CFT log, and a batch, the CFTCAT TLVCEXEC parameter, is submitted.</p>         </td>
      </tr>
   </tbody>
</table>
