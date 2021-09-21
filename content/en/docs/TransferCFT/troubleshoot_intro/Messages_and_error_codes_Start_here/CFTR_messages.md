{
    "title": "CFTR messages",
    "linkTitle": "CFTR messages",
    "weight": "370"
}This topic lists the CFTRxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

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
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTR02E"></a>CFTR02E &amp;cmd Failed _ Invalid date or time</p>
            <p>CFTR02E &amp;cmd Failed _ Invalid date or time</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;cmd command contains at least one invalid date or time.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax.</p>
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
            <p><a name="CFTR03E"></a>CFTR03E &amp;cmd Failed _ No record found </p>
            <p>CFTR03E &amp;cmd Failed _ No record found for &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;cmd 
 command cannot be associated with any record in the <span>Transfer CFT</span> catalog 
 file (example: deletion of a non-existing record).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax.</p>
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
            <p><a name="CFTR04E"></a>CFTR04E &amp;cmd Failed _ Keyword &amp;keyw too large </p>
            <p>CFTR04E &amp;cmd Failed _ Keyword &amp;keyw too large</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The length of the &amp;keyw keyword is greater than 8.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the 
 description of this parameter in the <span>Transfer CFT</span> Online documentation, 
 correct the error and then resubmit the command.</p>
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
            <p><a name="CFTR05E"></a>CFTR05E &amp;cmd Failed _ Illegal separator for keyword 
 &amp;keyw </p>
            <p>CFTR05E &amp;cmd Failed _ Illegal separator for keyword &amp;keyw</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A parameter separator in the &amp;cmd command is invalid.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax (the separator must be a comma), correct 
 the error and then resubmit the command.</p>
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
            <p><a name="CFTR06E"></a>CFTR06E &amp;cmd Failed _ Keyword &amp;keyw, missing 
 quote </p>
            <p>CFTR06E &amp;cmd Failed _ Keyword &amp;keyw ; missing quote</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A closing quote (') is missing in the value assigned to the 
 &amp;keyw keyword.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the offending parameter, correct the error and then resubmit 
 the command.</p>
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
            <p><a name="CFTR07E"></a>CFTR07E &amp;cmd Failed _ Too many keywords </p>
            <p>CFTR07E &amp;cmd Failed _ Too many keywords</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>There are too many keywords for this command.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax, correct the error and then resubmit 
 the command.</p>
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
            <p><a name="CFTR08E"></a>CFTR08E &amp;cmd Failed _ Keyword &amp;keyw unknown 
 or duplicate </p>
            <p>CFTR08E &amp;cmd Failed _ Keyword &amp;keyw unknown or duplicate</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;keyw keyword is unknown or duplicated in the command.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax, correct the error and then resubmit 
 the command.</p>
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
            <p><a name="CFTR09E"></a>CFTR09E &amp;cmd Failed _ Keyword &amp;keyw missing </p>
            <p>CFTR09E &amp;cmd Failed _ Keyword &amp;keyw missing</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;keyw keyword, which is mandatory for the command, is 
 missing.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the command syntax, correct the error and then resubmit 
 the command.</p>
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
            <p><a name="CFTR10E"></a>CFTR10E &amp;cmd Failed _ Keyword &amp;keyw value out 
 of bounds </p>
            <p>CFTR10E &amp;cmd Failed _ Keyword &amp;keyw value out of bounds</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;keyw keyword of the &amp;cmd command is numeric and 
 its value is outside the authorized limits.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the possible values for this parameter, correct the error 
 and then resubmit the command.</p>
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
            <p><a name="CFTR11E"></a>CFTR11E &amp;cmd Failed _ Invalid value for keyword 
 &amp;keyw </p>
            <p>CFTR11E &amp;cmd Failed _ Invalid value for keyword &amp;keyw</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The value of the &amp;keyw keyword of the &amp;cmd command is 
 not authorized (for example: numeric value for an alphabetic-type parameter).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the possible values for this parameter, correct the error 
 and then resubmit the command.</p>
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
            <p><a name="CFTR12I"></a>CFTR12I &amp;cmd PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt 
 Treated FOR USER=&amp;user &amp;str</p>
            <p>CFTR12I &amp;cmd PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt Treated FOR USER=&amp;user &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The command was executed correctly.</p>
            <p>The partner's name (&amp;part), the IDF (&amp;idf) and 
 the IDT (&amp;idt) are only defined if it is a SEND or RECV command.</p>
            <p>If the jobname is set in the catalog, then the information &lt;JOBNAME=PID&gt; (all platforms except z/OS) or &lt;JOBNAME=jobname jobid&gt; (z/OS platforms) displays in the message in place of (&amp;str). </p>
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
            <p><a name="CFTR13E"></a>CFTR13E &amp;cmd Failed _ IDT=&amp;idt not allowed </p>
            <p>CFTR13E SEND &amp;cmd PART=&amp;part Failed _ IDT=&amp;idt not allowed</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During execution 
 of a command (response to a message or transfer for example) the required 
 transfer identifier (&amp;idt) was not found in the <span>Transfer CFT</span> catalog.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the parameter settings of the command and the transfer 
 identifier value.</p>
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
            <p>Warning </p>
         </td>
         <td>
            <p><a name="CFTR14W"></a>CFTR14W &amp;cmd Failed PART=&amp;part _ No transfer 
 found for this request </p>
            <p>CFTR14W &amp;cmd PART=&amp;part Failed _ No transfer found for this request</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>When processing 
 an ACT or INACT command, no transfer in the 'D' state and with DIAGI=430 
 for ACT or in the 'C' state for INACT was found in the <span>Transfer CFT</span> catalog 
 for the partner(s) designated by &amp;part.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command takes effect for any subsequent transfers concerning 
 the partner(s).</p>
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
            <p>Warning </p>
         </td>
         <td>
            <p><a name="CFTR15W"></a>CFTR15W &amp;cmd not treated for user &amp;user </p>
            <p>CFTR15W &amp;cmd not treated for user &amp;user</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The security system has refused to execute the MQUERY or SHUT 
 command. The CFTX03W message is displayed before this message.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The command is ignored.</p>
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
            <p><a name="CFTR16I"></a>CFTR16I 
 &amp;message </p>
            <p>CFTR16I 
 &amp;message</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Information concerning either the TURN command or the WLOG 
 command. </p>
            <ul>
               <li>TURN 
 command:            <ul>               <li>PART=&amp;part               </li>               <li>MODE=&amp;mode 
 (&amp;str) &amp;mode: create,replace,delete               </li>               <li>&amp;str: 
 “part not found”,”part inact”,”prot DMZ not found” ,”part not in requester 
 mode","commutation not available”,"see omintime,omaxtime”,”already 
 in command cache”,”not into command cache”               </li>            </ul>               </li>
            </ul>
            <ul>
               <li>WLOG 
 command:             <ul>               <li>&amp;message 
 displayed in the <span>Transfer CFT</span> LOG               </li>            </ul>               </li>
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
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTR17I"></a>CFTR17I 
 &amp;cmd In progress for USER &amp;user  &amp;message </p>
            <p>CFTR17I &amp;cmd &amp;message In progress for USER &amp;user</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>This information message displays at the beginning of the processing for the &amp;cmd.</p>
            <ul>
               <li>Cmd =DELETE/END               </li>
            </ul>
            <ul>
               <li>Message where PART=&amp;part IDF=&amp;idf [ IDT=&amp;idt IDTU=&amp;idtu IDA=&amp;ida STATE=&amp;state]                </li>
            </ul>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td colspan="1" rowspan="1">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td colspan="1" rowspan="1">
            <p><a name="CFTR18W"></a>CFTR18W 
 &amp;message </p>
            <p>CFTR18W 
 &amp;message</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Displays warning status in the WLOG command. </p>
            <ul>
               <li>&amp;message 
 displayed in the <span>Transfer CFT</span> LOG               </li>
            </ul>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td colspan="1" rowspan="1">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p><a name="CFTR19E"></a>CFTR19E 
 &amp;message</p>
            <p>CFTR19E 
 &amp;message</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Displays error status in the WLOG command. </p>
            <ul>
               <li>&amp;message 
 displayed in the <span>Transfer CFT</span> LOG               </li>
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
            <p>Information </p>
         </td>
         <td>
            <p><a name="CFTR20I"></a>CFTR20I &amp;message </p>
            <p>CFTR20I &amp;message</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Information concerning the folder monitoring functionality. </p>
            <ul>
               <li>For each configured directory a related message is written to the log.               </li>
               <li>When a file is automatically submitted for emission, a log message is also written to the log.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td colspan="1" rowspan="1">
<p colspan="1" rowspan="1"><a name="CFTR20E"></a>CFTR20E &amp;message</p>
<p colspan="1" rowspan="1">CFTR20E &amp;message</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1">
<p colspan="1" rowspan="1">Error messages originating from the folder monitoring functionality. </p>
<p colspan="1" rowspan="1">Usually triggered by error conditions encountered on file manipulation as renaming, deleting.</p>
         </td>
      </tr>
      <tr>
         <td>Warning         </td>
         <td>CFTR20W &amp;message         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Warning message related to the folder monitoring feature.</p>
            <p>Indicates that  a system error concerning the event subsystem occurred (see <a href="../../../app_integration_intro/intro_folder_monitor/configure_folder_monitoring">USEFSEVENT</a>=YES). </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Fatal </p>
         </td>
         <td colspan="1" rowspan="1">
<p colspan="1" rowspan="1"><a name="CFTR20F"></a>CFTR20F &amp;message </p>
<p colspan="1" rowspan="1">CFTR20F &amp;message</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1">
<p colspan="1" rowspan="1">Fatal messages originating from the folder monitoring functionality.</p>
<p colspan="1" rowspan="1">Indicates that a severe error condition was encountered and is preventing this functionality from proceeding normally.</p>
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
            <p><a name="CFTR21E"></a>CFTR21E &amp;cmd Failed _ No record found &lt;IDTU=&amp;idtu PART=&amp;part IDT=&amp;idt&gt; </p>
            <p>CFTR21E &amp;cmd Failed _ No record found &lt;IDTU=&amp;idtu PART=&amp;part IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During the internal command execution (&amp;cmd) the required unique transfer identifier (&amp;idtu) was not found in the Transfer CFT catalog.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">Consequence         </td>
         <td colspan="1" rowspan="1">The command is ignored.         </td>
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
            <p><a name="CFTR22E"></a>CFTR22E &amp;cmd Failed _ Set FORCE=YES to immediately retry to rename &lt;IDTU=&amp;idtu PART=&amp;part IDT=&amp;idt PHASE=Y PHASESTEP=R&gt; </p>
            <p>CFTR22E &amp;cmd Failed _ Set FORCE=YES to immediately retry to rename &lt;IDTU=&amp;idtu PART=&amp;part IDT=&amp;idt PHASE=Y PHASESTEP=R&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A transfer in the YR phase/phasestep was found for the START command, but it has no effect as FORCE is set to NO.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">Consequence         </td>
         <td colspan="1" rowspan="1">The command is ignored.         </td>
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
            <p>CFTR23I On &amp;time UserId=&amp;userid, JobName=&amp;jobname ran the command &amp;command  </p>
            <p>CFTR23I On &amp;time UserId=&amp;userid, JobName=&amp;jobname ran the command &amp;command</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>This message traces who has cleared what and with which command.</p>
         </td>
      </tr>
</table>
