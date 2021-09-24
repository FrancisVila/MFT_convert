{
    "title": "CFTI messages",
    "linkTitle": "CFTI messages",
    "weight": "340"
}# Transfer CFT messages: CFTI

This topic lists the CFTIxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTI00I"></a>CFTI00I Snumb of spawned procedure is &amp;str1:&amp;str2 </p>
            <p>CFTI00I Snumb of spawned procedure is &amp;str1:&amp;str2</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p><i>z/OS only</i>
</p>
            <p>Information concerning the submission 
 of a procedure that has its job identifier specified in &amp;str1 and the &amp;str2 (which represent the JOBID and JOBNAME).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Fatal </p>
         </td>
         <td>
            <p><a name="CFTI01F"></a>CFTI01F &amp;str  </p>
            <p>CFTI01F &amp;str  </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Internal <span>Transfer CFT</span> execution error.</p>
            <p>The field "&amp;str" can have the following values:</p>
            <ul>
               <li>CFT 
 error &amp;scs:<span>Transfer CFT</span> inter-task communication system problem (waiting for 
 the CFTMAIN scheduler task queue)               </li>
            </ul>
            <ul>
               <li>CFT 
 error _ usage expired:The <span>Transfer CFT</span> user key (CFTPARM KEY) does not authorize 
 <span>Transfer CFT</span> execution beyond the expired period               </li>
            </ul>
            <ul>
               <li>CFT 
 error _ CFT usage not authorized:The <span>Transfer CFT</span> user key (CFTPARM KEY) does not authorize 
 <span>Transfer CFT</span> execution on this operating system or computer               </li>
            </ul>
            <ul>
               <li>CFT error _ file 
 keys not available:  The <span>Transfer CFT</span> user keys are stored in an indirection file 
 (CFTPARM KEY parameter); this file cannot be accessed by <span>Transfer CFT</span>               </li>
            </ul>
            <ul>
               <li>CFT error &amp;scs 
 _ Common_area allocation failed:Definition of the memory area common to the <span>Transfer CFT</span> tasks 
 has failed. This can be caused by insufficient memory               </li>
            </ul>
            <ul>
               <li>CFT error &amp;scs 
 _ Mailbox definition failed: <span>Transfer CFT</span> is unable to link to a mailbox defined by the 
 *CFTOM command               </li>
            </ul>
            <ul>
               <li>CFT error &amp;scs 
 _ CFT semaphore definition failed:<span>Transfer CFT</span> is unable to define an inter-task communications 
 queue               </li>
            </ul>
            <ul>
               <li>CFT error _ CFTEXIT 
 ID=&amp;id missing: A <span>Transfer CFT</span> task dedicated to file EXITs could not be activated 
 (the CFTEXIT command relating to the identifier mentioned (ID) was not 
 found)               </li>
            </ul>
            <ul>
               <li>CFT error _ Maximum 
 process CFTEXIT running reached: A <span>Transfer CFT</span> task dedicated to file EXITs could not be activated 
 (the maximum number of EXIT processes that can be activated has already 
 been reached)               </li>
            </ul>
            <ul>
               <li>CFT error &amp;cs 
 _ Initializing process CFTEXIT: A <span>Transfer CFT</span> task dedicated to file EXITs could not be activated 
 (the maximum number of EXIT processes that can be activated has already 
 been reached)               </li>
            </ul>
            <ul>
               <li>CFT error _ &amp;Net Network Access Method Option not authorized by license key:The <span>Transfer CFT</span> is NOT authorized to use the optional network access method designated by &amp;Net (TCP/IP).               </li>
            </ul>
            <ul>
               <li>CFT error _ SSL Protocol Option not authorized by license key:A protocol defined in the CFTPARM object uses the SSL option, but the SSL option is not available with this license key.               </li>
            </ul>
            <ul>
               <li>CFT error _ FIPS Compliance Option not authorized by license key:The uconf:cft.fips.enable_compliance parameter is set to Yes, but the FIPS option is not available with this license key.               </li>
            </ul>
            <ul>
               <li>CFT error _ File Transfer Acceleration  Option not authorized by license key:The uconf:acceleration.enable parameter is set to Yes, but the acceleration option is not available with this license key.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 concerned by the incident is interrupted, which is the K 
 status.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check parameter settings, analyze the &amp;cs code value to 
 determine, if necessary, the origin of the error:</p>
            <ul>
               <li>CFT error &amp;scs 
 _ LOG stop failed: The message logging task cannot be stopped               </li>
            </ul>
            <ul>
               <li>CFT error &amp;scs 
 _ mailbox delete failed: A mailbox defined by a CFTCOM command cannot be deleted               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Analyze the &amp;scs. code to determine the exact origin of 
 the error.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>
         </td>
         <td>
            <p><a name="CFTI01W"></a>CFTI01W &amp;str </p>
            <p>CFTI01W &amp;str  </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>CFT error &amp;scs 
 _ Initializing process CFTTFIL: A <span>Transfer CFT</span> task dedicated to transfer file access could 
 not be activated.</p>
         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td><span>Transfer CFT</span> is not stopped, and transfers are not interrupted.         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>No action necessary.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Fatal </p>
         </td>
         <td>
            <p><a name="CFTI02F"></a>CFTI02F Init Error code &amp;scs _ Allocating param. 
 file &amp;fname </p>
            <p>CFTI02F Init Error code &amp;scs _ Allocating param. 
 file &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when allocating the <span>Transfer CFT</span> parameter file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check that 
 the file is not already allocated; if it exists, correct the error and 
 then restart <span>Transfer CFT</span>.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI03F"></a>CFTI03F Init Error code &amp;scs _ Opening param. file 
 &amp;fname </p>
            <p>CFTI03F Init Error code &amp;scs _ Opening param. file 
 &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when opening the <span>Transfer CFT</span> parameter file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct 
 the error and then restart <span>Transfer CFT</span>.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI04F"></a>CFTI04F Init Error code &amp;scs _ Allocating partners 
 file &amp;fname </p>
            <p>CFTI04F Init Error code &amp;scs _ Allocating partners 
 file &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when allocating the <span>Transfer CFT</span> partner file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check that 
 the file is not already allocated, correct the error and then restart 
 <span>Transfer CFT</span>.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI05F"></a>CFTI05F Init Error code &amp;scs _ Opening partners 
 file &amp;fname </p>
            <p>CFTI05F Init Error code &amp;scs _ Opening partners 
 file &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when opening the <span>Transfer CFT</span> partner file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct 
 the error and then restart <span>Transfer CFT</span>.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI06F"></a>CFTI06F Init Error code &amp;scs _ Allocating catalog 
 file &amp;fname </p>
            <p>CFTI06F Init Error code &amp;scs _ Allocating catalog 
 file &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when allocating the <span>Transfer CFT</span> catalog file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check that 
 the file is not already allocated, correct the error and then restart 
 <span>Transfer CFT</span>.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI08F"></a>CFTI08F Init error _ Protocol process </p>
            <p>CFTI08F Init error _ Protocol process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when activating the <span>Transfer CFT</span> protocol process.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Inform Transfer 
 CFT Support.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI09F"></a>CFTI09F Init error _ Communication process </p>
            <p>CFTI09F Init error _ Communication process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when activating the <span>Transfer CFT</span> communication process.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Inform Transfer 
 CFT Support.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI10F"></a>CFTI10F Init error _ Logger process </p>
            <p>CFTI10F Init error _ Logger process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During <span>Transfer CFT</span> initialization an error was detected 
 when activating the <span>Transfer CFT</span> message logging process.</p>
            <p>It may be a memory allocation or queue definition type 
 system error (or a problem when submitting a message to the queue).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Inform Product Support.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td>
            <p><a name="CFTI11I"></a>CFTI11I Init complete _ Logger process </p>
            <p>CFTI11I Init complete _ Logger process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Normal end 
 of <span>Transfer CFT</span> logging process initialization.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td>
            <p><a name="CFTI12I"></a>CFTI12I Init complete _ Protocol process </p>
            <p>CFTI12I Init complete _ Protocol process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Normal end 
 of <span>Transfer CFT</span> protocol process initialization.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td>
            <p><a name="CFTI13I"></a>CFTI13I Init complete _ Communication process </p>
            <p>CFTI13I Init complete _ Communication process</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Normal end of <span>Transfer CFT</span> communication task initialization.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTI14I"></a>CFTI14I CFT Init complete </p>
            <p>CFTI14I CFT Init complete</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Normal end 
 of <span>Transfer CFT</span> initialization.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI15F"></a>CFTI15F Error code &amp;ncs _ Trying to define resource 
 &amp;id </p>
            <p>CFTI15F Error code &amp;ncs _ Trying to define resource 
 &amp;id</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Rejection of the define 
 resource request specified by the network interface. The &amp;ncs 
 return code explains the cause of the rejection.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Review Transfer 
 CFT parameter settings (CFTNET commands).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI16F"></a>CFTI16F Error code &amp;ncs _ Register request </p>
            <p>CFTI16F Error code &amp;ncs _ Register request</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Rejection of the register 
 request specified by the network interface. The &amp;ncs 
 return code explains the cause of the rejection.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Review Transfer 
 CFT parameter settings (CFTPROT commands).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI17F"></a>CFTI17F Init error _ Account file &amp;fname </p>
            <p>CFTI17F Init error _ Account file &amp;fname</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During the <span>Transfer CFT</span> initialization phase an error was 
 detected when processing the accounting 
 file (CFTACCNT command).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase has stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the existence and integrity of the &amp;fname file.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTI18I"></a>CFTI18I _ &amp;str </p>
            <p>CFTI18I _ &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>This is a <span>Transfer CFT</span> welcome message describing the computer environment 
 and the main runtime characteristics, according to the options 
 activated by the software key (KEY parameter):</p>
            <ul>
               <li>Usage of this 
 product is strictly limited to &amp;cpu_id machine: The <span>Transfer CFT</span> can only be executed on the computer with the 
 designated CPU               </li>
            </ul>
            <ul>
               <li>Usage of this 
 product is strictly limited to &amp;label: The <span>Transfer CFT</span> can only be executed within a specific framework, 
 as designated by &amp;label               </li>
            </ul>
            <ul>
               <li>Usage of this 
 product is strictly limited until &amp;date: The <span>Transfer CFT</span> cannot be executed after the date designated by 
 &amp;date               </li>
            </ul>
            <ul>
               <li>&amp;Maxtrans 
 simultaneous transfer(s) is(are) authorized: <span>Transfer CFT</span> cannot process more than &amp;Maxtrans simultaneous 
 transfers. This value overrides the MAXTRANS parameter in the CFTPARM 
 command               </li>
            </ul>
            <ul>
               <li>&amp;Net Network 
 Access Method Option is authorized: The <span>Transfer CFT</span> is authorized to use the optional network access 
 method designated by &amp;Net (TCP/IP)            <ul>               <li>The information in this message is related to the UCONF setting for server.authentication_method.                </li>               <li>For more information on Access Management parameters, see the Password authentication for synchronous communication media section in   <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.               </li>            </ul>               </li>
            </ul>
            <ul>
               <li>&amp;Prot Protocol 
 Option is authorized: <span>Transfer CFT</span> is authorized to use the protocol option designated 
 by &amp;Prot (Secure PeSIT)               </li>
            </ul>
            <p> 
 If an attempt is made to use an unauthorized option, such as a network access method 
 or protocol option, <span>Transfer CFT</span> does not start, and displays a message. <br/>Information messages include:</p>
<div>
            <ul>
               <li>FNAME:  CFTLOG name               </li>
               <li>AFNAME: CFTALOG name               </li>
               <li>TYPE: File   FNAME: file communication name               </li>
               <li>TYPE :Mbx  FNAME : mailbox name               </li>
               <li>TYPE :TCPIP HOST: host name PORT: port    if synchronous communication               </li>
            </ul>
</div>
            <p>If PassPort is used for SSL:</p>
            <ul>
               <li>CFTI18I    hostname : addrhost               </li>
               <li>CFTI18I    port    : port number               </li>
               <li>See also <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p><span>Transfer CFT</span> is stopped during the initialization phase.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>
         </td>
         <td>
            <p><a name="CFTI18W"></a>CFTI18W+ Version mismatch between Transfer &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion </p>
            <p>CFTI18W+ Version mismatch between Transfer &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion<a name="CFTI19I"></a></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The UCONF dictionary was created by a different version of Transfer CFT, most likely due to a non-standard installation.</p>
         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td>There is a risk of failure.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Properly reinstall the product.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTI19I"></a>CFTI19I © Copyright AXWAY,.... </p>
            <p>CFTI19I © Copyright AXWAY,....</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p><span>Transfer CFT</span> copyright message.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Fatal </p>
         </td>
         <td>
            <p><a name="CFTI20F"></a>CFTI20F Semaphore 
 definition failure CR=&amp;cr CS= &amp;scs </p>
            <p>CFTI20F Semaphore 
 definition failure CR=&amp;cr CS= &amp;scs</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Cannot define the internal communications queue.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Consequence</p>
         </td>
         <td colspan="1" rowspan="1">
            <p><span>Transfer CFT</span>  is stopped during its initialization phase.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI21F"></a>CFTI21F CFTNET=&amp;id Resource define failure CS=&amp;ncs </p>
            <p>CFTI21F CFTNET=&amp;id Resource define failure CS=&amp;ncs</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Cannot define the resource. The resource identifier for this CFTNET command displays in the message.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p><span>Transfer CFT</span>  is stopped during its initialization phase.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI22F"></a>CFTI22F CFTPROT=&amp;id Register request failure CS=&amp;ncs </p>
            <p>CFTI22F CFTPROT=&amp;id Register request failure CS=&amp;ncs</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Cannot register the protocol defined in this CFTPROT command.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p><span>Transfer CFT</span>  is stopped during its initialization phase.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI23F"></a>CFTI23F MAIN synchronization failure CR=&amp;cr CS=&amp;scs </p>
            <p>CFTI23F MAIN synchronization failure CR=&amp;cr CS=&amp;scs</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Internal synchronization error between the main Transfer 
 CFT task and the protocol task.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p><span>Transfer CFT</span> is stopped during its initialization phase.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTI24I"></a>CFTI24I &amp;str </p>
            <p>CFTI24I &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Message displayed when viewing the command cache or the 
 transfer cache: CFTUTIL or CFTINT MQUERY command. </p>
            <p>The messages depend on the type of cache concerned (command 
 or catalog):</p>
            <p>* TRANSFER CACHE IS EMPTY</p>
            <p>The catalog cache is empty.</p>
            <p>The messages vary according to the context:Or gives details 
 of the cache information (catalog or command cache) according to the type 
 of information displayed</p>
            <p>For a line in the command cache, the information is divided 
 into three parts: </p>
            <ul>
               <li>command 
 execution                </li>
               <li>DATE 
 and TIME               </li>
               <li>type 
 of command (SWITCH ACCNT, SWITCH LOG or PURGE)                </li>
            </ul>
            <p>For a transfer, the information is divided into four parts: 
 </p>
            <ul>
               <li>request activation 
 time               </li>
               <li>identifier of 
 the partner concerned                </li>
               <li>idf identifier 
 and                </li>
               <li>IDT value calculated 
 by <span>Transfer CFT</span>               </li>
            </ul>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI25I"></a>CFTI25I Init complete _ Security  active [&amp;str] </p>
            <p>CFTI25I Init complete _ Security  active [&amp;str]</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The description of the message &amp;str specifies the  activated security options:</p>
            <ul>
               <li value="1">HAB:  Normal end of initialization with activation of the <span>Transfer CFT</span> security  system               </li>
               <li value="2">SSL: Normal end of initialization with activation of the  SSL protocol               </li>
            </ul>
            <p>The information in this message is affected by the UCONF setting for access management.<madcap:conditionaltext data-mc-conditions="governance.CG_out"> For more information, see the am.type parameter and access management options in <a href="../../../internal_a_m_start_here/about_passport_am/unconf_access_management">Access Management and PassPort AM parameters</a>.</madcap:conditionaltext></p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI26I"></a>CFTI26I Init complete _ Security not active </p>
            <p>CFTI26I Init complete _ Security not active</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Normal end 
 of initialization without activating the Security option (<span>Transfer CFT</span> 
 security system and the SSL protocol).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTI27F"></a>CFTI27F Init Error code &amp;scs _ Opening security file 
 &amp;file </p>
            <p>CFTI27F Init Error code &amp;scs _ Opening security file 
 &amp;file</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>When <span>Transfer CFT</span> was initialized, a security system open 
 error was detected.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The Transfer 
 CFT initialization phase is stopped.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Inform Product Support.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI28I"></a>CFTI28I Init complete </p>
            <p>CFTI28I Init complete</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Message on initialization of CFTMAIN. With following Message CFTI18I    FNAME  :catalog name.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI34I"></a>CFTI34I 
 PID=&amp;id &amp;task Task started successfully </p>
            <p>CFTI34I 
 PID=&amp;id &amp;task Task started successfully</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;task Task whose internal identifier is &amp;pid 
 has been started successfully.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI35I"></a>CFTI35I 
 PID=&amp;id &amp;task Task ended </p>
            <p>CFTI35I 
 PID=&amp;id &amp;task Task ended </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;task Task whose internal identifier is &amp;pid 
 has stopped.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI36I"></a>CFTI36I CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname &amp;str</p>
            <p><font>CFTI36I CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname &amp;str</font>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>&amp;Idcron = CFTCRON command identifier</p>
            <p>&amp;Cronname =  id of  the list  in  CRONTABS in CFTPARM</p>
            <p>&amp;Str=</p>
            <ul>
               <li>INSERT OK: NEXT= date time ,TIME=&amp;str - (&amp;str= TIME of CFTCRON command defined by ID)               </li>
            </ul>
            <ul>
               <li>INSERT OK: NOACTIVE- The CFTCRON with a STATE=NOACTIVE in the configuration is not activated.               </li>
            </ul>
            <ul>
               <li>Not enabled - (cronname not defined in the CRONTABS list)               </li>
            </ul>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
  </p>
         </td>
         <td width="80%">
            <p><a name="CFTI38E"></a>CFTI38E CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname INSERT FAILED </p>
            <p>CFTI38E CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname INSERT FAILED</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p><font color="#000000" face="Arial" size="2"><font color="#000000"> Insert failed due to incorrect entry or unexpected character. Check CRONTAB parameters, such as TIME.</font></font>
</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI39I"></a>CFTI39I &amp;str</p>
            <p>CFTI39I
&amp;str </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Displays information about the <span>Transfer CFT</span> Heartbeat. Possible states:</p>
            <ul>
               <li>Enable               </li>
               <li>Update  UCONF parameters               </li>
               <li>Disable               </li>
            </ul>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
  </p>
         </td>
         <td>
            <p><a name="CFTI40E"></a>CFTI40E
 OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
            <p>CFTI40E
 OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>z/OS only</p>
            <p>If the OMVS segment is not defined for Transfer CFT and/or the Transfer CFT Copilot server owner, then Transfer CFT, the Transfer CFT Copilot server, or CFTUTIL (synchronous communication) stops and displays this message.</p>
            <p>To disable the display and check option, modify the environment variable in the ..UPARM(CNFENV)target file as follows:</p>
            <p>omvs_check_disable=1.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information 
  </p>
         </td>
         <td>
            <p><a name="CFTI41I"></a>CFTI41I OMVS information for user=xxxxxx,uid=n,gid=n,home=(/xxxxx) </p>
            <p>CFTI41I OMVS information for user=xxxxxx,uid=n,gid=n,home=(/xxxxx)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>z/OS only</p>
            <p>If the OMVS segment is defined for Transfer CFT and/or the Transfer CFT Copilot server owner, this information message displays.</p>
            <p>To disable the display and check option, modify the environment variable in the ..UPARM(CNFENV)target file as follows:</p>
            <p>omvs_check_disable=1.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
  </p>
         </td>
         <td>
            <p><a name="CFTI42E"></a>CFTI42E PID=&amp;pid &amp;task Task startup error failed to lock resource '&amp;pid_file_name': resource already locked </p>
            <p>CFTI42E PID=&amp;pid &amp;task Task startup error failed to lock resource '&amp;pid_file_name': resource already locked</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The pid_file_name that is used  to ensure process uniqueness could not be locked, causing the task to fail.</p>
            <p>Locate and stop the locked process. If this does not resolve the issue, restart the server using the "force-stop" mode.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information  </p>
         </td>
         <td>
            <p><a name="CFTI42E"></a><a name="CFTI43I"></a>CFTI43I  Attention: The Transfer CFT license expires in n days </p>
            <p>CFTI43I  Attention: The Transfer CFT license expires in n days</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>There are 7 days remaining on the license key for Transfer CFT.</p>
         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>
            <p>To obtain a new key:</p>
<ol>
               <li value="1">For an existing installation, use the  command <span>cftutil about</span> to retrieve your system information. The <b>ABOUT</b> command displays 
 the Transfer CFT product, host, and key information, and characteristics of the platform
 on which Transfer CFT is installed.               </li>
               <li value="2">Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.            <ul>               <li>For a US key, contact:  <span>fulfillment@us.axway.com</span>                </li>               <li>For an EMEA or APAC key, contact: <span>product.key@axway.com</span>                </li>            </ul>               </li>
               <li value="3">Provide the hostname and system information for the installed or updated Transfer CFT.               </li>
</ol>
            <p>To apply the key:</p>
            <p>To apply the license key from the Axway Fulfillment team, either:</p>
            <ul>
               <li> Enter the key directly.               </li>
               <li>Enter the key(s) in the indirection file.                </li>
            </ul>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">When working in multi-node you must have one key per node and host.         </td>
      </tr>
</table></p>
            <p>See the  <i>Apply a license key</i> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning  </p>
         </td>
         <td>
            <p><a name="CFTI42E"></a><a name="CFTI43W"></a>CFTI43W  Attention: The Transfer CFT license expires in n days</p>
            <p>CFTI43W  Attention: The Transfer CFT license expires in n days</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>There are fewer than 7 days remaining on the license key for Transfer CFT.</p>
         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>
            <p>To obtain a new key:</p>
<ol>
               <li value="1">For an existing installation, use the  command <span>cftutil about</span> to retrieve your system information. The <b>ABOUT</b> command displays 
 the Transfer CFT product, host, and key information, and characteristics of the platform
 on which Transfer CFT is installed.               </li>
               <li value="2">Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.            <ul>               <li>For a US key, contact:  <span>fulfillment@us.axway.com</span>                </li>               <li>For an EMEA or APAC key, contact: <span>product.key@axway.com</span>                </li>            </ul>               </li>
               <li value="3">Provide the hostname and system information for the installed or updated Transfer CFT.               </li>
</ol>
            <p>To apply the key:</p>
            <p>To apply the license key from the Axway Fulfillment team, either:</p>
            <ul>
               <li> Enter the key directly.               </li>
               <li>Enter the key(s) in the indirection file.                </li>
            </ul>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">When working in multi-node you must have one key per node and host.         </td>
      </tr>
</table></p>
            <p>See the  <i>Apply a license key</i> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
  </p>
         </td>
         <td>
            <p><a name="CFTI42E"></a><a name="CFTI43E"></a>CFTI43E  Attention: The Transfer CFT license has expired </p>
            <p>CFTI43E  Attention: The Transfer CFT license has expired</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The Transfer CFT license key is no longer valid. </p>
         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>
            <p>To obtain a new key:</p>
<ol>
               <li value="1">For an existing installation, use the  command <span>cftutil about</span> to retrieve your system information. The <b>ABOUT</b> command displays 
 the Transfer CFT product, host, and key information, and characteristics of the platform
 on which Transfer CFT is installed.               </li>
               <li value="2">Contact the Axway Fulfillment team at the appropriate email address to obtain a valid key.            <ul>               <li>For a US key, contact:  <span>fulfillment@us.axway.com</span>                </li>               <li>For an EMEA or APAC key, contact: <span>product.key@axway.com</span>                </li>            </ul>               </li>
               <li value="3">Provide the hostname and system information for the installed or updated Transfer CFT.               </li>
</ol>
            <p>To apply the key:</p>
            <p>To apply the license key from the Axway Fulfillment team, either:</p>
            <ul>
               <li> Enter the key directly.               </li>
               <li>Enter the key(s) in the indirection file.                </li>
            </ul>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">When working in multi-node you must have one key per node and host.         </td>
      </tr>
</table></p>
            <p>See the  <i>Apply a license key</i> section in the Transfer CFT Installation Guide that corresponds with your OS for details.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning  </p>
         </td>
         <td>
            <p>CFTI18W Version mismatch between Transfer CFT &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion </p>
            <p>CFTI18W Version mismatch between Transfer CFT &amp;CFTVersion and the UCONF dictionary &amp;UCONFVersion</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The UCONF dictionary was created with a different Transfer CFT version than the product, probably due to a non-standard installation.</p>
         </td>
      </tr>
      <tr>
         <td>Consequence	         </td>
         <td>There is a risk of failure.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Perform a standard installation to reinstall the product.          </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
  </p>
         </td>
         <td width="80%">
            <p><a name="CFTS39E"></a>
</p>
            <p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx </p>
            <p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p><font color="#000000" face="Arial" size="2"><font color="#000000">Reserved for z/OS systems.</font></font>
</p>
         </td>
      </tr>
</table>

 
