{
    "title": "Transfer CFT messages:  CFTI",
    "linkTitle": "CFTI messages",
    "weight": "320"
}This topic lists the CFTIxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

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
<p>Information</p>         </td>
         <td><p><span id="CFTI00I"></span>CFTI00I Snumb of spawned procedure is &amp;str1:&amp;str2</p>
<p>CFTI00I Snumb of spawned procedure is &amp;str1:&amp;str2</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p><em>z/OS only</em></p>
<p>Information concerning the submission
of a procedure that has its job identifier specified in &amp;str1 and the &amp;str2 (which represent the JOBID and JOBNAME).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Fatal</p>         </td>
         <td><p><span id="CFTI01F"></span>CFTI01F &amp;str  </p>
<p>CFTI01F &amp;str  </p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Internal <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> execution error.</p>
<p>The field "&amp;str" can have the following values:</p>
<ul>
<li>CFT
error &amp;scs:<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> inter-task communication system problem (waiting for
the CFTMAIN scheduler task queue)</li>
</ul>
<ul>
<li>CFT
error _ usage expired:The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> user key (CFTPARM KEY) does not authorize
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> execution beyond the expired period</li>
</ul>
<ul>
<li>CFT
error _ CFT usage not authorized:The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> user key (CFTPARM KEY) does not authorize
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> execution on this operating system or computer</li>
</ul>
<ul>
<li>CFT error _ file
keys not available:  The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> user keys are stored in an indirection file
(CFTPARM KEY parameter); this file cannot be accessed by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></li>
</ul>
<ul>
<li>CFT error &amp;scs
_ Common_area allocation failed:Definition of the memory area common to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> tasks
has failed. This can be caused by insufficient memory</li>
</ul>
<ul>
<li>CFT error &amp;scs
_ Mailbox definition failed: <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is unable to link to a mailbox defined by the
*CFTOM command</li>
</ul>
<ul>
<li>CFT error &amp;scs
_ CFT semaphore definition failed:<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is unable to define an inter-task communications
queue</li>
</ul>
<ul>
<li>CFT error _ CFTEXIT
ID=&amp;id missing: A <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> task dedicated to file EXITs could not be activated
(the CFTEXIT command relating to the identifier mentioned (ID) was not
found)</li>
</ul>
<ul>
<li>CFT error _ Maximum
process CFTEXIT running reached: A <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> task dedicated to file EXITs could not be activated
(the maximum number of EXIT processes that can be activated has already
been reached)</li>
</ul>
<ul>
<li>CFT error &amp;cs
_ Initializing process CFTEXIT: A <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> task dedicated to file EXITs could not be activated
(the maximum number of EXIT processes that can be activated has already
been reached)</li>
</ul>
<ul>
<li>CFT error _ &amp;Net Network Access Method Option not authorized by license key:The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is NOT authorized to use the optional network access method designated by &amp;Net (TCP/IP).</li>
</ul>
<ul>
<li>CFT error _ SSL Protocol Option not authorized by license key:A protocol defined in the CFTPARM object uses the SSL option, but the SSL option is not available with this license key.</li>
</ul>
<ul>
<li>CFT error _ FIPS Compliance Option not authorized by license key:The uconf:cft.fips.enable_compliance parameter is set to Yes, but the FIPS option is not available with this license key.</li>
</ul>
<ul>
<li>CFT error _ File Transfer Acceleration Option not authorized by license key:The uconf:acceleration.enable parameter is set to Yes, but the acceleration option is not available with this license key.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The transfer
concerned by the incident is interrupted, which is the K
status.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check parameter settings, analyze the &amp;cs code value to
determine, if necessary, the origin of the error:</p>
<ul>
<li>CFT error &amp;scs
_ LOG stop failed: The message logging task cannot be stopped</li>
</ul>
<ul>
<li>CFT error &amp;scs
_ mailbox delete failed: A mailbox defined by a CFTCOM command cannot be deleted</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the &amp;scs. code to determine the exact origin of
the error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTI01W"></span>CFTI01W &amp;str</p>
<p>CFTI01W &amp;str  </p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>CFT error &amp;scs
_ Initializing process CFTTFIL: A <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> task dedicated to transfer file access could
not be activated.</p>         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is not stopped, and transfers are not interrupted.         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No action necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Fatal</p>         </td>
         <td><p><span id="CFTI02F"></span>CFTI02F Init Error code &amp;scs _ Allocating param.
file &amp;fname</p>
<p>CFTI02F Init Error code &amp;scs _ Allocating param.
file &amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when allocating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter file.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that
the file is not already allocated; if it exists, correct the error and
then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI03F"></span>CFTI03F Init Error code &amp;scs _ Opening param. file
&amp;fname</p>
<p>CFTI03F Init Error code &amp;scs _ Opening param. file
&amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when opening the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter file.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct
the error and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI04F"></span>CFTI04F Init Error code &amp;scs _ Allocating partners
file &amp;fname</p>
<p>CFTI04F Init Error code &amp;scs _ Allocating partners
file &amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when allocating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner file.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that
the file is not already allocated, correct the error and then restart
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI05F"></span>CFTI05F Init Error code &amp;scs _ Opening partners
file &amp;fname</p>
<p>CFTI05F Init Error code &amp;scs _ Opening partners
file &amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when opening the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner file.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct
the error and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI06F"></span>CFTI06F Init Error code &amp;scs _ Allocating catalog
file &amp;fname</p>
<p>CFTI06F Init Error code &amp;scs _ Allocating catalog
file &amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when allocating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog file.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that
the file is not already allocated, correct the error and then restart
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI08F"></span>CFTI08F Init error _ Protocol process</p>
<p>CFTI08F Init error _ Protocol process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when activating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> protocol process.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Inform Transfer
CFT Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI09F"></span>CFTI09F Init error _ Communication process</p>
<p>CFTI09F Init error _ Communication process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when activating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication process.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Inform Transfer
CFT Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI10F"></span>CFTI10F Init error _ Logger process</p>
<p>CFTI10F Init error _ Logger process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization an error was detected
when activating the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> message logging process.</p>
<p>It may be a memory allocation or queue definition type
system error (or a problem when submitting a message to the queue).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTI11I"></span>CFTI11I Init complete _ Logger process</p>
<p>CFTI11I Init complete _ Logger process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Normal end
of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> logging process initialization.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTI12I"></span>CFTI12I Init complete _ Protocol process</p>
<p>CFTI12I Init complete _ Protocol process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Normal end
of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> protocol process initialization.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTI13I"></span>CFTI13I Init complete _ Communication process</p>
<p>CFTI13I Init complete _ Communication process</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Normal end of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication task initialization.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information </p>         </td>
         <td><p><span id="CFTI14I"></span>CFTI14I CFT Init complete</p>
<p>CFTI14I CFT Init complete</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Normal end
of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI15F"></span>CFTI15F Error code &amp;ncs _ Trying to define resource
&amp;id</p>
<p>CFTI15F Error code &amp;ncs _ Trying to define resource
&amp;id</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Rejection of the define
resource request specified by the network interface. The &amp;ncs
return code explains the cause of the rejection.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Review Transfer
CFT parameter settings (CFTNET commands).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI16F"></span>CFTI16F Error code &amp;ncs _ Register request</p>
<p>CFTI16F Error code &amp;ncs _ Register request</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Rejection of the register
request specified by the network interface. The &amp;ncs
return code explains the cause of the rejection.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Review Transfer
CFT parameter settings (CFTPROT commands).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI17F"></span>CFTI17F Init error _ Account file &amp;fname</p>
<p>CFTI17F Init error _ Account file &amp;fname</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>During the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> initialization phase an error was
detected when processing the accounting
file (CFTACCNT command).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase has stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the existence and integrity of the &amp;fname file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information </p>         </td>
         <td><p><span id="CFTI18I"></span>CFTI18I _ &amp;str</p>
<p>CFTI18I _ &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>This is a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> welcome message describing the computer environment
and the main runtime characteristics, according to the options
activated by the software key (KEY parameter):</p>
<ul>
<li>Usage of this
product is strictly limited to &amp;cpu_id machine: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can only be executed on the computer with the
designated CPU</li>
</ul>
<ul>
<li>Usage of this
product is strictly limited to &amp;label: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can only be executed within a specific framework,
as designated by &amp;label</li>
</ul>
<ul>
<li>Usage of this
product is strictly limited until &amp;date: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> cannot be executed after the date designated by
&amp;date</li>
</ul>
<ul>
<li>&amp;Maxtrans
simultaneous transfer(s) is(are) authorized: <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> cannot process more than &amp;Maxtrans simultaneous
transfers. This value overrides the MAXTRANS parameter in the CFTPARM
command</li>
</ul>
<ul>
<li>&amp;Net Network
Access Method Option is authorized: The <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is authorized to use the optional network access
method designated by &amp;Net (TCP/IP)
<ul>
<li>The information in this message is related to the UCONF setting for server.authentication_method.</li>
<li>For more information on Access Management parameters, see the Password authentication for synchronous communication media section in <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.</li>
</ul></li>
</ul>
<ul>
<li>&amp;Prot Protocol
Option is authorized: <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is authorized to use the protocol option designated
by &amp;Prot (Secure PeSIT)</li>
</ul>
<p>If an attempt is made to use an unauthorized option, such as a network access method
or protocol option, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> does not start, and displays a message.<br />
Information messages include:</p>
<div class="indentTable">
<ul>
<li>FNAME: CFTLOG name</li>
<li>AFNAME: CFTALOG name</li>
<li>TYPE: File FNAME: file communication name</li>
<li>TYPE :Mbx FNAME : mailbox name</li>
<li>TYPE :TCPIP HOST: host name PORT: port if synchronous communication</li>
</ul>
</div>
<p>If PassPort is used for SSL:</p>
<ul>
<li>CFTI18I hostname : addrhost</li>
<li>CFTI18I port : port number</li>
<li>See also <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped during the initialization phase.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTI18W"></span>CFTI18W+ Version mismatch between Transfer &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion</p>
<p>CFTI18W+ Version mismatch between Transfer &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion<span id="CFTI19I"></span></p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The UCONF dictionary was created by a different version of Transfer CFT, most likely due to a non-standard installation.</p>         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td>There is a risk of failure.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Properly reinstall the product.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTI19I"></span>CFTI19I © Copyright AXWAY,....</p>
<p>CFTI19I © Copyright AXWAY,....</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> copyright message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Fatal</p>         </td>
         <td><p><span id="CFTI20F"></span>CFTI20F Semaphore
definition failure CR=&amp;cr CS= &amp;scs</p>
<p>CFTI20F Semaphore
definition failure CR=&amp;cr CS= &amp;scs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot define the internal communications queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped during its initialization phase.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI21F"></span>CFTI21F CFTNET=&amp;id Resource define failure CS=&amp;ncs</p>
<p>CFTI21F CFTNET=&amp;id Resource define failure CS=&amp;ncs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot define the resource. The resource identifier for this CFTNET command displays in the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped during its initialization phase.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI22F"></span>CFTI22F CFTPROT=&amp;id Register request failure CS=&amp;ncs</p>
<p>CFTI22F CFTPROT=&amp;id Register request failure CS=&amp;ncs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot register the protocol defined in this CFTPROT command.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped during its initialization phase.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI23F"></span>CFTI23F MAIN synchronization failure CR=&amp;cr CS=&amp;scs</p>
<p>CFTI23F MAIN synchronization failure CR=&amp;cr CS=&amp;scs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Internal synchronization error between the main Transfer
CFT task and the protocol task.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is stopped during its initialization phase.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTI24I"></span>CFTI24I &amp;str</p>
<p>CFTI24I &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Message displayed when viewing the command cache or the
transfer cache: CFTUTIL or CFTINT MQUERY command.</p>
<p>The messages depend on the type of cache concerned (command
or catalog):</p>
<p>* TRANSFER CACHE IS EMPTY</p>
<p>The catalog cache is empty.</p>
<p>The messages vary according to the context:Or gives details
of the cache information (catalog or command cache) according to the type
of information displayed</p>
<p>For a line in the command cache, the information is divided
into three parts:</p>
<ul>
<li>command
execution</li>
<li>DATE
and TIME</li>
<li>type
of command (SWITCH ACCNT, SWITCH LOG or PURGE)</li>
</ul>
<p>For a transfer, the information is divided into four parts:</p>
<ul>
<li>request activation
time</li>
<li>identifier of
the partner concerned</li>
<li>idf identifier
and</li>
<li>IDT value calculated
by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI25I"></span>CFTI25I Init complete _ Security active [&amp;str]</p>
<p>CFTI25I Init complete _ Security active [&amp;str]</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The description of the message &amp;str specifies the activated security options:</p>
<ul>
<li>HAB: Normal end of initialization with activation of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> security system</li>
<li>SSL: Normal end of initialization with activation of the SSL protocol</li>
</ul>
<p>The information in this message is affected by the UCONF setting for access management. For more information, see the am.type parameter and access management options in <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI26I"></span>CFTI26I Init complete _ Security not active</p>
<p>CFTI26I Init complete _ Security not active</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Normal end
of initialization without activating the Security option (<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
security system and the SSL protocol).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTI27F"></span>CFTI27F Init Error code &amp;scs _ Opening security file
&amp;file</p>
<p>CFTI27F Init Error code &amp;scs _ Opening security file
&amp;file</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>When <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> was initialized, a security system open
error was detected.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The Transfer
CFT initialization phase is stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI28I"></span>CFTI28I Init complete </p>
<p>CFTI28I Init complete</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Message on initialization of CFTMAIN. With following Message CFTI18I FNAME :catalog name.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI34I"></span>CFTI34I
PID=&amp;id &amp;task Task started successfully</p>
<p>CFTI34I
PID=&amp;id &amp;task Task started successfully</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;task Task whose internal identifier is &amp;pid
has been started successfully.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI35I"></span>CFTI35I
PID=&amp;id &amp;task Task ended</p>
<p>CFTI35I
PID=&amp;id &amp;task Task ended</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;task Task whose internal identifier is &amp;pid
has stopped.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI36I"></span>CFTI36I CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname &amp;str</p>
<p>CFTI36I CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>&amp;Idcron = CFTCRON command identifier</p>
<p>&amp;Cronname = id of the list in CRONTABS in CFTPARM</p>
<p>&amp;Str=</p>
<ul>
<li>INSERT OK: NEXT= date time ,TIME=&amp;str - (&amp;str= TIME of CFTCRON command defined by ID)</li>
</ul>
<ul>
<li>INSERT OK: NOACTIVE- The CFTCRON with a STATE=NOACTIVE in the configuration is not activated.</li>
</ul>
<ul>
<li>Not enabled - (cronname not defined in the CRONTABS list)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error
 </p>         </td>
         <td><p><span id="CFTI38E"></span>CFTI38E CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname INSERT FAILED</p>
<p>CFTI38E CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname INSERT FAILED</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p> Insert failed due to incorrect entry or unexpected character. Check CRONTAB parameters, such as TIME.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI39I"></span>CFTI39I &amp;str</p>
<p>CFTI39I
&amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Displays information about the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Heartbeat. Possible states:</p>
<ul>
<li>Enable</li>
<li>Update UCONF parameters</li>
<li>Disable</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error
 </p>         </td>
         <td><p><span id="CFTI40E"></span>CFTI40E
OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
<p>CFTI40E
OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>z/OS only</p>
<p>If the OMVS segment is not defined for Transfer CFT and/or the Transfer CFT Copilot server owner, then Transfer CFT, the Transfer CFT Copilot server, or CFTUTIL (synchronous communication) stops and displays this message.</p>
<p>To disable the display and check option, modify the environment variable in the ..UPARM(CNFENV)target file as follows:</p>
<p>omvs_check_disable=1.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information
 </p>         </td>
         <td><p><span id="CFTI41I"></span>CFTI41I OMVS information for user=xxxxxx,uid=n,gid=n,home=(/xxxxx)</p>
<p>CFTI41I OMVS information for user=xxxxxx,uid=n,gid=n,home=(/xxxxx)</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>z/OS only</p>
<p>If the OMVS segment is defined for Transfer CFT and/or the Transfer CFT Copilot server owner, this information message displays.</p>
<p>To disable the display and check option, modify the environment variable in the ..UPARM(CNFENV)target file as follows:</p>
<p>omvs_check_disable=1.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error
 </p>         </td>
         <td><p><span id="CFTI42E"></span>CFTI42E PID=&amp;pid &amp;task Task startup error failed to lock resource '&amp;pid_file_name': resource already locked</p>
<p>CFTI42E PID=&amp;pid &amp;task Task startup error failed to lock resource '&amp;pid_file_name': resource already locked</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The pid_file_name that is used to ensure process uniqueness could not be locked, causing the task to fail.</p>
<p>Locate and stop the locked process. If this does not resolve the issue, restart the server using the "force-stop" mode.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information  </p>         </td>
         <td><p><span id="CFTI42E"></span><span id="CFTI43I"></span>CFTI43I Attention: The Transfer CFT license expires in n days</p>
<p>CFTI43I Attention: The Transfer CFT license expires in n days</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>There are 7 days remaining on the license key for Transfer CFT.</p>         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td><p>To obtain a new key:</p>
<ol>
<li>For an existing installation, use the command <span class="code" style="font-weight: bold;">cftutil about</span> to retrieve your system information. The <strong>ABOUT</strong> command displays
the Transfer CFT product, host, and key information, and characteristics of the platform
on which Transfer CFT is installed.</li>
<li>Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
<ul>
<li>For a US key, contact: <span class="code">fulfillment@us.axway.com</span></li>
<li>For an EMEA or APAC key, contact: <span class="code">product.key@axway.com</span></li>
</ul></li>
<li>Provide the hostname and system information for the installed or updated Transfer CFT.</li>
</ol>
<p>To apply the key:</p>
<p>To apply the license key from the Axway Fulfillment team, either:</p>
<ul>
<li>Enter the key directly.</li>
<li>Enter the key(s) in the indirection file.</li>
</ul>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When working in multi-node you must have one key per node and host.         </td>
      </tr>
   </tbody>
</table>
<p>See the <em>Apply a license key</em> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning  </p>         </td>
         <td><p><span id="CFTI42E"></span><span id="CFTI43W"></span>CFTI43W Attention: The Transfer CFT license expires in n days</p>
<p>CFTI43W Attention: The Transfer CFT license expires in n days</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>There are fewer than 7 days remaining on the license key for Transfer CFT.</p>         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td><p>To obtain a new key:</p>
<ol>
<li>For an existing installation, use the command <span class="code" style="font-weight: bold;">cftutil about</span> to retrieve your system information. The <strong>ABOUT</strong> command displays
the Transfer CFT product, host, and key information, and characteristics of the platform
on which Transfer CFT is installed.</li>
<li>Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
<ul>
<li>For a US key, contact: <span class="code">fulfillment@us.axway.com</span></li>
<li>For an EMEA or APAC key, contact: <span class="code">product.key@axway.com</span></li>
</ul></li>
<li>Provide the hostname and system information for the installed or updated Transfer CFT.</li>
</ol>
<p>To apply the key:</p>
<p>To apply the license key from the Axway Fulfillment team, either:</p>
<ul>
<li>Enter the key directly.</li>
<li>Enter the key(s) in the indirection file.</li>
</ul>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When working in multi-node you must have one key per node and host.         </td>
      </tr>
   </tbody>
</table>
<p>See the <em>Apply a license key</em> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error
 </p>         </td>
         <td><p><span id="CFTI42E"></span><span id="CFTI43E"></span>CFTI43E Attention: The Transfer CFT license has expired</p>
<p>CFTI43E Attention: The Transfer CFT license has expired</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The Transfer CFT license key is no longer valid.</p>         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td><p>To obtain a new key:</p>
<ol>
<li>For an existing installation, use the command <span class="code" style="font-weight: bold;">cftutil about</span> to retrieve your system information. The <strong>ABOUT</strong> command displays
the Transfer CFT product, host, and key information, and characteristics of the platform
on which Transfer CFT is installed.</li>
<li>Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.
<ul>
<li>For a US key, contact: <span class="code">fulfillment@us.axway.com</span></li>
<li>For an EMEA or APAC key, contact: <span class="code">product.key@axway.com</span></li>
</ul></li>
<li>Provide the hostname and system information for the installed or updated Transfer CFT.</li>
</ol>
<p>To apply the key:</p>
<p>To apply the license key from the Axway Fulfillment team, either:</p>
<ul>
<li>Enter the key directly.</li>
<li>Enter the key(s) in the indirection file.</li>
</ul>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When working in multi-node you must have one key per node and host.         </td>
      </tr>
   </tbody>
</table>
<p>See the <em>Apply a license key</em> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning  </p>         </td>
         <td><p>CFTI18W Version mismatch between Transfer CFT &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion</p>
<p>CFTI18W Version mismatch between Transfer CFT &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The UCONF dictionary was created with a different Transfer CFT version than the product, probably due to a non-standard installation.</p>         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td>There is a risk of failure.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Perform a standard installation to reinstall the product.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error
 </p>         </td>
         <td><p><span id="CFTS39E"></span></p>
<p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
<p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Reserved for z/OS systems.</p>         </td>
      </tr>
   </tbody>
</table>

 