{
    "title": "CFTT messages",
    "linkTitle": "CFTT messages",
    "weight": "390"
}This topic lists the CFTTxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

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
            <p>CFTT00E CFT request warning _ &amp;str </p>
            <p>CFTT00E CFT request warning - &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>An error may have occurred during a request sent to the Transfer CFT. The &amp;str message label specifies the possible type 
 of error:</p>
            <ul>
               <li>Unknown protocol 
 request: Internal error of the Transfer CFT, which receives an unexpected 
 protocol event               </li>
            </ul>
            <ul>
               <li>Unknown oper 
 request: The operator command received is unknown               </li>
            </ul>
            <ul>
               <li>Not computable 
 state: The transfer is not possible (status other than "D" 
 (Available)               </li>
            </ul>
            <ul>
               <li>Transfer for 
 myself rejected: The target of the transfer is the local site (CFTPARM PART field) The Transfer CFT therefore refuses 
 to activate a transfer to itself               </li>
            </ul>
            <ul>
               <li>Logger currently 
 unreachable: A SWITCH command, switching 
 log files, was attempted while the LOG task (CFT log) was not (or no longer) 
 active               </li>
            </ul>
            <ul>
               <li>Ignored (Catalog 
 Full): The catalog was 100% full and so the last SEND (or RECV) command 
 could not be processed; if it was submitted via the Transfer CFT communication 
 file, it is stored in the file and the associated communication process 
 stops (for more information, refer to the CFTC01W message)               </li>
            </ul>
            <ul>
               <li>Request syntax 
 error: There is a syntax error in the request; inform Product Support               </li>
            </ul>
            <ul>
               <li>Catalog 
 request unknown :The request is invalid               </li>
            </ul>
            <ul>
               <li>Unknown 
 process request: An internal Transfer CFT error was detected; inform Product Support               </li>
            </ul>
            <ul>
               <li>Unknown 
 file request: An internal Transfer CFT error was detected; inform Product Support               </li>
            </ul>
            <ul>
               <li>Transfer 
 already in progress: An attempt was made to restart a transfer in progress; the 
 transfer was not restarted               </li>
            </ul>
            <ul>
               <li>File already 
 transferred: An attempt was made to restart a terminated transfer; the 
 transfer was not restarted               </li>
            </ul>
            <ul>
               <li>&amp;file: A read error was detected on the authorizations file (&amp;file); 
 inform Product Support               </li>
            </ul>
            <ul>
               <li>Access Exit Task 
 unreachable: &amp;diagp: The directory exit task cannot be accessed (DIAGP specifies 
 the cause); inform Product Support               </li>
            </ul>
            <ul>
               <li>Request Ignored 
 : time-out: The request was not processed by the Transfer CFT (end time limit 
 exceeded)               </li>
            </ul>
            <ul>
               <li>Unable to attach 
 Client mailbox: Attachment to the client application was rejected               </li>
            </ul>
            <ul>
               <li>Unable to send 
 data to Client mailbox: Data cannot be sent to the client application               </li>
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
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTT01E"></a>CFTT01E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open 
 mode not allowed </p>
            <p>CFTT01E IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open mode not allowed</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A transfer request was made in OPEN mode, but this mode is not 
 supported for the partner concerned.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is denied. The corresponding catalog entry is set 
 to the KEEP status.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Transfer the files with this partner in closed mode.</p>
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
            <p><a name="CFTT02E"></a>CFTT02E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Transfer 
 Area Full </p>
            <p>CFTT02E _ Transfer Area Full &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A new transfer request was made but the maximum number of transfers 
 allowed at the same time has been reached.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Wait for 
 a decrease in the number of transfers or increase the maximum number of 
 authorized transfers (this increase can only be made by the technicians 
 responsible for porting and customizing the Transfer CFT product).</p>
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
            <p><a name="CFTT03E"></a>CFTT03E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max 
 retry Reached </p>
            <p>CFTT03E _ Max retry Reached &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The Transfer CFT has performed all retry actions to establish the 
 link with the partner.</p>
            <ul>
               <li>The transfer 
 activation retry counter for this protocol has exceeded the value of the 
 RESTART parameter (CFTPROT command) In this case there have been no other 
 network connection attempts and there are no more protocols in this partner's 
 protocol list In this case the DIAGI code is set to 406               </li>
               <li>The physical 
 connection has resulted in an invalid network address. It is the last 
 address for this protocol; there is no backup partner. The internal diagnostic 
 code (DIAGI) is set to 405. When the catalog is displayed, it overrides 
 the value 301 signifying an invalid address               </li>
               <li>The physical 
 connection has resulted in a fatal network error. In this case the DIAGI 
 code is set to 303; the DIAGP value defines the source of the error               </li>
               <li>The last physical 
 connection attempted according to the values of the RETRYM, RETRYN and 
 RETRYW parameters has failed. It is the last protocol in this partner's 
 protocol list; there is no backup partner               </li>
            </ul>
            <p>Note: the internal diagnostic 
 code (DIAGI) is set to 405. When the catalog is displayed, it overrides 
 the value 302 signifying a non-fatal network error.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is refused. The corresponding catalog entry is 
 set to the KEEP status.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Determine the error according to the DIAGI value. Analyze the 
 DIAGP code.</p>
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
            <p><a name="CFTT05E"></a>CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart 
 Failed </p>
            <p>CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart 
 Failed </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A file transfer restart request is not possible (the restart 
 identifier is unknown, for example).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not restarted.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Try a new transfer.</p>
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
            <p><a name="CFTT06W"></a>CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner 
 switching IPART=&amp;part </p>
            <p>CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner 
 switching IPART=&amp;part</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The partner (&amp;part) cannot be reached within the authorized 
 time slot (OMINTIME, OMAXTIME).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer will be retried via the intermediate partner IPART.</p>
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
            <p><a name="CFTT07W"></a>CFTT07W Ending Transfer Task &amp;n Failed _ A transfer 
 Running </p>
            <p>CFTT07W Ending Transfer Task &amp;n Failed _ A transfer 
 Running</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Attempt 
 to delete a transfer task for which not all transfers have been completed. 
 &amp;n designates an internal Transfer CFT task number incremented each 
 time a transfer task is activated.</p>
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
            <p><a name="CFTT08E"></a>CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No 
 prot available </p>
            <p>CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No 
 prot available</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The maximum 
 number of retries authorized for a transfer using the &amp;prot protocol 
 has been reached (see the Transfer CFT CFTPROT RESTART parameter).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The entry corresponding to the transfer in the catalog is set 
 to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Analyze the causes of the broken communication link.</p>
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
            <p><a name="CFTT09E"></a>CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot 
 _ Maximum cv affected </p>
            <p>CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot 
 _ Maximum cv affected</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>All virtual circuits associated with a partner in server mode 
 have already been allocated </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is refused locally.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Wait for 
 virtual circuits to be freed or increase the maximum number of virtual 
 circuits (see the Transfer CFT Online documentation 
 CNXIN and CNXINOUT parameters).</p>
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
            <p><a name="CFTT10E"></a>CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not 
 authorized </p>
            <p>CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not 
 authorized</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;prot protocol is not authorized for this partner.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check Transfer 
 CFT parameter settings.</p>
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
            <p><a name="CFTT11E"></a>CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ 
 &amp;net not found </p>
            <p>CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ 
 &amp;net not found</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The network 
 characteristics associated with the partner and for the &amp;n class of 
 resources have not been found in the Transfer CFT partner file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the 
 Transfer CFT parameter settings.</p>
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
            <p><a name="CFTT12W"></a>CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out 
 of time to call </p>
            <p>CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out 
 of time to call</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A transfer request was made outside the time slot authorized 
 for this partner.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is not executed (remains in the D 
 state).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Execute a new transfer within the time slot authorized for this 
 partner.</p>
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
            <p><a name="CFTT13I"></a>CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters 
 PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host) </p>
            <p>CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters 
 PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Information message for each dialno (or host) switch and 
 protocol. </p>
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
            <p><a name="CFTT14E"></a>CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not 
 found </p>
            <p>CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not 
 found</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;part 
 partner was not found in the Transfer CFT partner file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
<p data-mc-conditions="governance.CG_out">Check the Transfer
 <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro">CFT parameter 
 settings</a>.</p>
            <p>Check the <span>Transfer CFT</span> parameter settings.</p>
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
            <p><a name="CFTT15E"></a>CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters </p>
            <p>CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The network identifier of the &amp;part partner was not found in the Transfer CFT partner file.</p>
            <p>A protocol limitation may have truncated the partner to 24 characters.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is not executed. The corresponding catalog entry is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>Check the Transfer CFT parameter settings and limit the partner ID to 24 characters.         </td>
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
            <p><a name="CFTT16E"></a>CFTT16E PART=&amp;part IDF=&amp;idf _ No implicit send </p>
            <p>CFTT16E PART=&amp;part IDF=&amp;idf _ No implicit send</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The partner 
 has made a selection request and no file is ready to be sent (SEND 
 on HOLD or implicit SEND).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed (no catalog record is created).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
<p data-mc-conditions="governance.CG_out">Prepare 
 a transfer (SEND state=hold) or 
 declare an implicit send in the Transfer <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro">CFT 
 parameter settings</a>.</p>
            <p>Prepare 
 a transfer (SEND state=hold) or 
 declare an implicit send in the <span>Transfer CFT</span> parameter settings.</p>
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
            <p><a name="CFTT17I"></a>CFTT17I PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ STATE=HOLD </p>
            <p>CFTT17I PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ STATE=HOLD</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A transfer 
 request was voluntarily put on Hold 
 (see Transfer CFT Concepts, Send on Hold).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed and is on hold for a possible 
 reception request.</p>
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
            <p><a name="CFTT18E"></a>CFTT18E PART=&amp;part IDF=&amp;idf CFTAUTH id=&amp;id 
 _ Not found </p>
            <p>CFTT18E PART=&amp;part IDF=&amp;idf CFTAUTH id=&amp;id 
 _ Not found</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The identifier 
 of the list of files authorized for a partner <madcap:conditionaltext data-mc-conditions="governance.CG_out">(see <a href="../../../c_intro_userinterfaces/command_summary">CFTPART</a> )</madcap:conditionaltext> 
 was not found in the Transfer CFT parameter file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
<p data-mc-conditions="governance.CG_out">Check the 
 <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro">Transfer CFT parameter</a> settings.</p>
            <p>Check the <span>Transfer CFT</span> parameter setting.</p>
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
            <p><a name="CFTT19E"></a>CFTT19E PART=&amp;part _ Invalid remote password &amp;str 
 * </p>
            <p>CFTT19E PART=&amp;part _ Invalid remote password &amp;str 
 *</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Transfer 
 request was made and the partner sent an invalid password.</p>
            <p>*where &amp;str = supplied password is incorrect</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The connection is refused.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Execute a new transfer with a valid password.</p>
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
            <p><a name="CFTT20E"></a>CFTT20E PART=&amp;part _ PVC not allowed </p>
            <p>CFTT20E PART=&amp;part _ PVC not allowed</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The call collect connection request received is not authorized 
 for this partner.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The connection is refused. </p>
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
            <p><a name="CFTT21E"></a>CFTT21E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Catalog 
 access failed &amp;scs ,&amp;cr </p>
            <p>CFTT21E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Catalog 
 access failed &amp;scs ,&amp;cr</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During a 
 transfer (or a transfer request) an undetermined Transfer CFT catalog 
 access error was detected (input/output error for example).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is interrupted (or not executed).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Analyze the &amp;scs code and inform Product Support if necessary.</p>
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
            <p><a name="CFTT22E"></a>CFTT22E &amp;str PART=&amp;part  IDF=&amp;idf IDT=&amp;idt_ &amp;str</p>
            <p>CFTT22E _&amp;str &lt;IDTU=&amp;idtu PART=&amp;part  IDF=&amp;idf IDT=&amp;idt&gt; &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Connection refused due to user authentication failure (rpasswd, spasswd error).</p>
            <p>The  &amp;str provides additional information. </p>
            <p> For more information, see  <a href="../../../transport_security_start_here/password_management">Password management</a>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the &amp;str, correct, and retry.</p>
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
            <p><a name="CFTT23E"></a>CFTT23E PART=&amp;part Shutdown in progress _ &amp;str </p>
            <p>CFTT23E PART=&amp;part Shutdown in progress _ &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Information</p>
         </td>
         <td>
            <p>A Transfer CFT shutdown is in progress, the request sent is 
 not processed (the &amp;str message specifies the type of request).</p>
            <p>Connect in being refused: connection request from one of 
 its partners.</p>
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
            <p><a name="CFTT24E"></a>CFTT24E PART=&amp;part PROT=&amp;prot _ Invalid call 
 number &amp;n </p>
            <p>CFTT24E PART=&amp;part PROT=&amp;prot _ Invalid call 
 number &amp;n</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The called number received (server end) is not in the list of 
 numbers defined (and authorized) for this partner (&amp;n represents the 
 unauthorized number).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The connection is refused.</p>
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
            <p><a name="CFTT25E"></a>CFTT25E PART=&amp;part IDF=&amp;idf _ IDF not authorized </p>
            <p>CFTT25E PART=&amp;part IDF=&amp;idf _ IDF not authorized</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>During a transfer request the identifier of the file to be transferred 
 is not authorized for this partner (server or requester end).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is not executed. The corresponding catalog entry is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Request that another file be sent or authorize this identifier.</p>
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
            <p><a name="CFTT26E"></a>CFTT26E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max 
 transfer tasks </p>
            <p>CFTT26E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max 
 transfer tasks</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A new transfer request was made but the maximum number of transfer 
 processes has been reached (as has the maximum number of transfers per 
 process).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is not executed and remains in the D 
 state.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Wait for 
 a decrease in the number of transfers or increase the maximum number of 
 authorized processes or the maximum number of transfers per process. This 
 increase can only be made by the technicians responsible for porting and 
 customizing the Transfer CFT product.</p>
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
            <p><a name="CFTT27E"></a>CFTT27E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Error 
 &amp;scs writing starts </p>
            <p>CFTT27E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Error 
 &amp;scs writing starts</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The statistics relating to the designated transfer could not 
 be written in the accounting file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The accounting file is incomplete.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Analyze the file access system code (&amp;scs) to determine 
 the source of the error.</p>
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
            <p><a name="CFTT28E"></a>CFTT28E No outgoing CV configured on Network </p>
            <p>CFTT28E No outgoing CV configured on Network</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>An outgoing call attempt was made on a network resource configured 
 with the CALL = IN parameter (CFTNET command).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The requester transfer cannot be executed.</p>
            <p>The catalog entry is set to the K 
 state with a protocol diagnostic code (DIAGP): "L 0B 22" - 0B 
 meaning that network access is forbidden.</p>
            <p>If another protocol (CFTPROT) using another network resource 
 (CFTNET) is declared for this partner (PROT parameter of the CFTPART command), 
 Transfer CFT will make another attempt on this resource.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Change the parameter settings so that the protocol designated 
 for the partner points to a network resource available for outgoing calls.</p>
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
            <p><a name="CFTT29E"></a>CFTT29E DEST= &amp;dest -Invalid use _Define for [BOTH/LOCAL/COMMUT] 
 use only </p>
            <p>CFTT29E DEST= &amp;dest -Invalid use _Define for [BOTH/LOCAL/COMMUT] 
 use only</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A broadcast list can be used (FOR = parameter) with the value:</p>
            <ul>
               <li>LOCAL meaning that the partner list 
 can only be used for a direct transfer.               </li>
               <li>COMMUT meaning that the partner list 
 can only be used for store and forward operations.               </li>
               <li>BOTH meaning that the partner list is 
 used locally and for store and forward operations.               </li>
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
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTT30E"></a>CFTT30E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max 
 Exit tasks </p>
            <p>CFTT30E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max 
 Exit tasks</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A new transfer request with an associated EXIT was requested 
 but the maximum number of EXIT processes has been reached.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed (remains set to the D state).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Wait for a decrease in the number of transfers or increase the 
 maximum number of processes allowed.</p>
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
            <p><a name="CFTT31W"></a>CFTT31W Ending Exit Task &amp;n Failed _ A transfer 
 Running </p>
            <p>CFTT31W Ending Exit Task &amp;n Failed _ A transfer 
 Running</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Attempt 
 to delete an EXIT task in which not all transfers have been completed. 
 &amp;n designates an internal Transfer CFT task number incremented each 
 time a transfer task is activated.</p>
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
            <p><a name="CFTT32E"></a>CFTT32E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner not found </p>
            <p>CFTT32E _ Partner not found &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The identifier 
 of the &amp;part partner was not found in the Transfer CFT partner file.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the 
 Transfer CFT parameter settings.</p>
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
            <p><a name="CFTT33E"></a>CFTT33E PART = &amp;dest IDF = &amp;idf IDT = &amp;idt 
 _ Illegal use of CFTDEST </p>
            <p>CFTT33E _ Illegal use of CFTDEST &lt;IDTU=&amp;idtu PART=&amp;part &amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The identifier 
 of a partner mentioned in a list (CFTDEST command) is itself a list identifier. 
 As list embedding is not allowed, the transfer with this partner is interrupted. 
 </p>
            <p>Transfers with the previous partners in the list are nevertheless 
 activated, but only for an explicit list (FNAME parameter of the CFTDEST 
 command).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is interrupted with a DIAGI 401.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Change the partners list to show all the partners on one level.</p>
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
            <p><a name="CFTT34E"></a>CFTT34E PART = &amp;part IDF = &amp;idf _ &amp;cause </p>
            <p>CFTT34E _ &amp;cause&lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Access error on an external file describing a list of items:</p>
            <ul>
               <li>Partners 
 list: CFTDEST FNAME=#filename,               </li>
               <li>File 
 group: SEND FNAME=#filename,               </li>
            </ul>
            <p>Possible values of &amp;cause are:</p>
            <ul>
               <li>Allocating 
 external file &amp;file               </li>
               <li>Opening 
 external file &amp;file               </li>
               <li>Reading 
 external file &amp;file               </li>
            </ul>
            <p>The file processing phase (allocation, opening or reading) 
 is specified in the message.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The external file cannot be read - the corresponding transfers 
 are not activated.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the file access problem.</p>
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
            <p><a name="CFTT35W"></a>CFTT35W PART=&amp;part IDF=&amp;idf IDT=&amp;idt DELETE 
 file &amp;fname Failed _&amp;str </p>
            <p>CFTT35W DELETE 
 file &amp;fname Failed _&amp;str &lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A DELETE command is executed on a catalog request (in receive 
 mode and in a non-terminated H or K state).</p>
            <p>The receive file corresponding to this request could not 
 be deleted.</p>
            <p>“ ” (no label): 
 The file cannot be deleted; inform Product Support</p>
            <ul>
               <li>Allocate file error: File allocation error               </li>
               <li>Open file error File open error               </li>
               <li>Close file error: File closing error               </li>
               <li>Free file error: File release error               </li>
               <li>Allocate memory error: Memory allocation error               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The request is deleted from the catalog but the user is notified 
 that the &amp;wfname file has not been deleted.</p>
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
            <p><a name="CFTT36W"></a>CFTT36W PART=&amp;part IDF=&amp;idf IDT=&amp;idt 
 ERASE file &amp;fname Failed &amp;str</p>
            <p>CFTT36W ERASE file &amp;fname Failed &amp;str &lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf IDT=&amp;idt&gt;<![CDATA[
]]></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A DELETE command is executed on a catalog request (in receive 
 mode and in a non-terminated  state).K or H</p>
            <p>The purge of the received file that corresponds with this 
 request could not be carried out:</p>
            <ul>
               <li>Allocate file 
 error: File allocation error               </li>
               <li>Open file error 
 : File open error               </li>
               <li>Close file error: 
 File clofile close error               </li>
               <li>Free file error: 
 File release error               </li>
               <li>Allocate memory 
 error: Memory allocation error               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The request 
 is deleted from the catalog but the user is notified that the &amp;fname 
 file has not been purged.</p>
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
            <p><a name="CFTT37I"></a>CFTT37I PART=&amp;part _ Not found and ignored for CFTDEST 
 &amp;id </p>
            <p>CFTT37I _ Not found and ignored for CFTDEST 
 &amp;id &lt;IDTU=&amp;idtu PART=&amp;part&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The new parameter NOPART for the CFTDEST command can have 
 on of the following values: ABORT (default value), CONTINUE, or IGNORE.</p>
            <ul>
               <li>ABORT: Transfer CFT continues functioning 
 as it was before the request for change.                </li>
            </ul>
            <p>No transfer is generated if a partner does not exist in the 
 list of partners defined in the PART parameter. If the list of partners 
 is defined in the PART parameter. If the list of partners is defined in 
 a file (FNAME parameter) the transfers carried out for the only for existing 
 partners and the treatment is identical to that for the NOPART=CONTINUE 
 option.</p>
            <ul>
               <li>CONTINUE: If the partner does not exist, 
 Transfer CFT indicates this in a message in the LOG.                </li>
            </ul>
            <p>CFTT32E PART=idpart Not found. Pass the transfer in SFK diagi 
 408 and continue the transfers for the other partners. The generic post 
 remains in the K state and the end of transfer procedure is not executed.</p>
            <ul>
               <li>IGNORE:                </li>
            </ul>
            <ul>
               <li>If 
 a partner does not exist in the list, Transfer CFT ignores the partner 
 (there is no transfer) and moves on to the next partner.                </li>
               <li>A message 
 is displayed in the LOG   CFTT37I 
 PART=idpart _ Not found and ignored for CFTDEST iddest                </li>
               <li>The 
 generic job passes to the T state 
 and is under the end of transfer procedure.               </li>
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
            <p>Information</p>
         </td>
         <td>
            <p><a name="CFTT38I"></a>CFTT38I PART=&amp;part _ Dynamic partner: &amp;npart </p>
            <p>CFTT38I _Dynamic partner: &amp;npart &lt; PART=&amp;part  DIAG=&amp;diag&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Information</p>
         </td>
         <td>
            <p>When receiving an incoming call from an unknown source (no local 
 partner description corresponding to the &amp;part network name received), 
 the &amp;npart dynamic partner creation mechanism is triggered.</p>
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
            <p><a name="CFTT39E"></a>CFTT39E PART=&amp;part DIAG=&amp;diag _ Access Exit 
 Connect Reject </p>
            <p>CFTT39E  _ Access Exit 
 Connect Reject &lt;PART=&amp;part DIAG=&amp;diag&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The connection is refused by the directory EXIT task; &amp;diag 
 contains the field in the communication structure updated by the EXIT.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is aborted with the following diagnostics codes: 
 403, 409, 410, 411, 414, 415, 416, 418, 425, 426.</p>
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
            <p><a name="CFTT40E"></a>CFTT40E PART=&amp;part DIAG=&amp;diag _ Access Exit 
 Error </p>
            <p>CFTT40E  _ Access Exit 
 Error &lt;PART=&amp;part DIAG=&amp;diag&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>An error has been detected in the directory EXIT task.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is aborted with the following possible diagnostics 
 codes: 134, 423.</p>
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
            <p><a name="CFTT42E"></a>CFTT42E part&amp;PART=&lt;Partner switching IPART=PART not available </p>
            <p>CFTT42E _ Partner switching IPART=PART not available &lt;PART=&amp;part&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The IPART value must be different than the PART value.</p>
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
            <p><a name="CFTT44E"></a>CFTT44E PART=&amp;part IDF=&amp;idf _ &amp;str directory &amp;file </p>
            <p>CFTT44E  _ &amp;str directory &amp;file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>The file selection phase is indicated in the message, where &amp;str can be allocating, opening, empty, or reading.             <p>A directory 
 access error has been detected when sending a list of file names or a 
 group of files based on a selection. </p>            <p>SEND FNAME = # FIL* or SEND FNAME 
 = # DIR*. </p>         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>If the directory could not be accessed (allocating, opening 
 or empty), no transfers are triggered.</p>
            <p>If the directory could not be read when selecting the files 
 in the directory, all transfers preceding the error are triggered.</p>
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
            <p>Error </p>
         </td>
         <td>
            <p><a name="CFTT44W"></a>CFTT44W PART=&amp;part IDF=&amp;idf _ &amp;str directory &amp;file (file not found ignored) </p>
            <p>CFTT44W _ &amp;str directory &amp;file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf&gt; (file not found ignored) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file selection phase is indicated in the message, where &amp;str can be allocating, opening, empty, or reading. </p>
            <p>A directory access error has been detected when sending a list of file names or a group of files based on a selection. </p>
            <p>SEND FNAME = # FIL* or SEND FNAME = # DIR*. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>If the directory is empty, Transfer CFT ignores the fact that the file is not found, and passes the transfer to the X phase.</p>
         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Ignore this error.         </td>
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
            <p><a name="CFTT45E"></a>
</p>
            <p>CFTT45E PART=&amp;part  _ Partner switching IPART=&amp;ipart not found</p>
            <p>CFTT45E _ Partner switching not found &lt;PART=&amp;part IPART=&amp;ipart&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The intermediate partner (IPART) was not found.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer cannot be performed.</p>
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
            <p><a name="CFTT46W"></a>CFTT46W PART=&amp;part ,IDF=&amp;idf ,IDT=&amp;idt _ 
 Part inactive: mode &amp;str </p>
            <p>CFTT46W  _ 
 Part inactive: mode &amp;str  &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer 
 attempt for partner &amp;part cannot succeed as the partner is inactive 
 in &amp;str mode:</p>
            <ul>
               <li>&amp;str= 
 requester or                </li>
               <li>&amp;str = server               </li>
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
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTT47E"></a>CFTT47E PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;id 
 _ Cannot find SSL security profil </p>
            <p>CFTT47E  
 _ Cannot find SSL security profil &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot&gt; </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The attempted transfer the &amp;part partner cannot be performed 
 because the security profile was not found. For more information on SSL definition for CFTPART, see the <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ssl">SSL</a> parameter description.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer can not be carried out.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p><table>
   <col/>
   <tbody>
      <tr>
         <td>
            <p><table>
   <col/>
   <tbody>
      <tr>
         <td>
            <p>V23 format</p>
            <p> </p>
            <p>V24 format</p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
            <p>V23 format</p>
            <p> </p>
            <p>V24 format</p>
         </td>
      </tr>
   </tbody>
</table></p>
         </td>
      </tr>
      <tr>
         <td>
            <p> </p>
            <p>Warning</p>
         </td>
      </tr>
   </tbody>
</table></p>
         </td>
         <td>
            <p><table>
   <col/>
   <tbody>
      <tr>
         <td>
            <p><a name="CFTT47W"></a>
</p>
            <p>CFTT47W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot SSLid=&amp;id DIRECT=CLIENT _ Cannot find SSL security profil</p>
            <p>CFTT47W _ Cannot find SSL security profil &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot SSLID=&amp;id DIRECT=CLIENT&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>CFTT47W PART=&amp;part SSLid=&amp;id DIRECT=SERVER _ No SSL security profile for additional checks</p>
            <p>CFTT47W _ No SSL security profile for additional checks &lt;PART=&amp;part SSLID=&amp;id DIRECT=SERVER&gt;</p>
         </td>
      </tr>
   </tbody>
</table></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer attempt for partner &amp;part uses a non-existent CFTSSL (&amp;sslid).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Check the configuration and add the missing profile. </p>
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
            <p><a name="CFTT48E"></a>CFTT48E PART=&amp;part SSL=&amp;id _ Server 
 Session rejected reason=&amp;reason </p>
            <p>CFTT48E  _ Server 
 Session rejected reason=&amp;reason  &lt;PART=&amp;part SSL=&amp;ssl&gt; </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The attempted transfer the &amp;part partner cannot be performed 
 because the security profile is not valid, with as an internal reason 
 (&amp;reason).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer can not be carried out.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Note the REASON (&amp;reason) value and contact the product 
 support team if necessary.</p>
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
            <p><a name="CFTT49W"></a>CFTT49W Unable to send data to Synchronous task </p>
            <p>CFTT49W Unable to send data to Synchronous task</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Synchronous communication task is inaccessible.</p>
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
            <p><a name="CFTT50E"></a>CFTT50E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Duplicate transfer with IDTU=</p>
            <p>CFTT50E _ Duplicate transfer with IDTU=&amp;idtu &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A duplicate transfer occurred. IDTU=&amp;idtu is the previously performed transfer. </p>
            <p>For more information, see the   <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/duplicat">DUPLICAT</a> field details.</p>
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
            <p><a name="CFTT51I"></a>CFTT51I PART=&amp;part ,&amp;str session opened </p>
            <p>CFTT51I PART=&amp;part ,&amp;str session opened</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The session is open, the connection request has been accepted 
 (requester side (&amp;str= requester if not secured, &amp;str=SSL requester) 
 or server (&amp;str = server if not secured , &amp;str=SSL server if secured)).</p>
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
            <p><a name="CFTT52I"></a>CFTT52I PART=&amp;part ,&amp;str session closed </p>
            <p>CFTT52I PART=&amp;part ,&amp;str session closed</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The session is closed: requester side (&amp;str = requester 
 if not secured, &amp;str = SSL requester if secured) or server (&amp;str 
 = server if not secured , &amp;str = SSL server if secured).</p>
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
            <p><a name="CFTT53I"></a>CFTT53I PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;str file &amp;str1</p>
            <p>CFTT53I &amp;str file &amp;str1 &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file is selected (&amp;str1 = selected) or created (&amp;str1 
 = created) either by the requester (&amp;str = requester) or by the server 
 (&amp;str = server).</p>
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
            <p><a name="CFTT54I"></a>CFTT54I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str 
 file deselected </p>
            <p>CFTT54I &amp;fname file deselected &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file is deselected either by the requester (&amp;str = requester) 
 or by the server (&amp;str = server).</p>
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
            <p><a name="CFTT55I"></a>CFTT55I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str 
 file opened </p>
            <p>CFTT55I &amp;fname file opened &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file is opened either by the requester (&amp;str = requester) 
 or by the server (&amp;str = server).</p>
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
            <p><a name="CFTT56I"></a>CFTT56I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str 
 file closed </p>
            <p>CFTT56I &amp;fname file closed &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file is closed either by the requester (&amp;str = requester) 
 or by the server (&amp;str = server.</p>
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
            <p><a name="CFTT57I"></a>CFTT57I PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids,&amp;str 
 transfer started </p>
            <p>CFTT57I &amp;str transfer started &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer has been started either by the requester (&amp;str 
 = requester) or by the server (&amp;str = server).</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">IDS refers to the session identifier.         </td>
      </tr>
</table></p>
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
            <p><a name="CFTT58I"></a>CFTT58I PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids,&amp;str 
 transfer ended </p>
            <p>CFTT58I &amp;str transfer ended &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer has been completed either by the requester (&amp;str 
 = requester) or by the server (&amp;str = server).</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">IDS refers to the session identifier.         </td>
      </tr>
</table></p>
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
            <p><a name="CFTT59I"></a>CFTT59I PART=&amp;part IDM=&amp;idf IDT=&amp;idt ,&amp;str 
 &lt;message|reply&gt; transferred </p>
            <p>CFTT59I &amp;str &lt;message|reply&gt; transferred &lt;IDTU=&amp;idtu PART=&amp;part IDM=&amp;idm IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The message or the reply has been sent either by the requester 
 (&amp;str = requester) or by the server (&amp;str = server).</p>
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
            <p><a name="CFTT60I"></a>CFTT60I &amp;str </p>
            <p>CFTT60I IDTU=&amp;idtu &amp;str</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The &amp;str message is an information message, 
 sent by the file EXIT associated with the transfer.</p>
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
            <p><a name="CFTT61E"></a>CFTT61E PART=&amp;part IDM=&amp;idf IDT=&amp;idt local 
 message reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT61E local message transfer reject &lt;IDTU=&amp;idtu PART=&amp;part IDM=&amp;idm IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The local partner rejects the message transfer.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The message transfer is not executed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT62E"></a>CFTT62E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi 
 ,&amp;diagp </p>
            <p>CFTT62E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer was interrupted by the operator (&amp;diagp = "OPER") 
 or by the file EXIT (&amp;diagp represents the phase of the EXIT which 
 prompted the interruption = "ALLOC", "OPEN", TRANS 
 or CLOSE).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is aborted. The corresponding catalog entry is set to HOLD 
 (after a HALT command from the 
 operator or an interrupt by the EXIT), KEEP 
 (after a KEEP command from the 
 operator).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>After an 
 interruption by the operator, the transfer can be restarted manually (START command). </p>
            <p>After interruption by a file EXIT, the action is to be defined 
 by the engineers responsible for this file EXIT.</p>
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
            <p><a name="CFTT62E"></a><a name="CFTT63E"></a>CFTT63E IDTU=&amp;idtu MODE=&amp;str Transfer refused due to product key limitation until &amp;date </p>
            <p>CFTT63E _ Transfer refused due to product key limitation until &amp;date &lt;IDTU=&amp;idtu MODE=&amp;mode&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The license key is limiting the number of transfers in this time frame, where:</p>
            <ul>
               <li>&amp;str : REQUESTER or SERVER               </li>
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
            <p>Error</p>
         </td>
         <td>
            <p><a name="CFTT64E"></a>CFTT64E PART=&amp;part IDF=&amp;idf _ Flow does not exist and cft.default_idf.enable is set to 'no'</p>
            <p>CFTT64E _ Flow does not exist and cft.default_idf.enable is set to 'no' &lt;PART=&amp;part IDF=&amp;idf&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The default IDF functionality is disabled for the  command.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed and has the status K. The DIAGP also reflects this status.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>For parameter details, see <a href="../../../admin_intro/uconf/uconf_parameters">UCONF: General unified configuration parameters</a>.</p>
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
            <p><a name="CFTT65E"></a>CFTT65E PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Protocol not available </p>
            <p>CFTT65E _ PROT=&amp;prot not available &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>The &amp;prot protocol is not authorized for this partner.         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>The transfer is not executed, and the corresponding catalog entry is set to KEEP. DIAGI=410 ,DIAGP = NO PROT         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>Check the PROT value in the SEND or RECV transfer.         </td>
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
            <p><a name="CFTT66E"></a>CFTT66E Maximum number of partners authorized by license key reached (using PART=&amp;part) </p>
            <p>CFTT66E Maximum number of partners authorized by license key reached (using PART=&amp;part)</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td><span>Transfer CFT</span> license keys support either a limited or unlimited number of partners. The transfer is treated as if the partner does not exist.          </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>An error occurred because you have reached the maximum number of partners allowed by your license key.          </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>In a command line window, you can enter the command CFTUTIL ABOUT to check the number of partners that your license key authorizes. For additional information on license keys, contact an <span>Axway</span> sales representative.         </td>
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
            <p><a name="CFTT66E"></a>CFTT68E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Unexpected AT phase/phasestep at restart, converting T to K </p>
            <p>CFTT68E _ Unexpected AT phase/phasestep at restart, converting T to K &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>If Transfer CFT was stopped abruptly when creating one or more child transfers for the current generic transfer, when you restart Transfer CFT you cannot manage these transfers (AT phase/phasestep).         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>The corresponding transfer entry in the catalog now switches to the K phasestep instead of the previous T phasestep.         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>You can continue to manage the affected transfer (those in K phasestep).         </td>
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
            <p><a name="CFTT69E"></a>CFTT69E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Unexpected YE phase/phasestep at restart, converting E to H </p>
            <p>CFTT69E _ Unexpected YE phase/phasestep at restart, converting E to H IDTU=&amp;idtu, PART=&amp;part, IDF=&amp;idf, IDT=&amp;idt</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>If Transfer CFT was stopped abruptly during the post-processing phase, when you restart Transfer CFT you cannot manage these transfers (YE phase/phasestep).         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>The corresponding transfer entry in the catalog now switches to the H phasestep instead of the previous E phasestep.         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>You can continue to manage the affected transfer (those in H phasestep).         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>Information         </td>
         <td>
            <p><a name="CFTT70I"></a>CFTT70I The user &amp;user is connecting with method &amp;method </p>
            <p>CFTT70I The user &amp;user is connecting with method &amp;method            </p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>A client is trying to connect to the server.         </td>
      </tr>
</table>

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>Error         </td>
         <td>
            <p><a name="CFTT70E"></a>CFTT70E The user &amp;user is not allowed to connect to the server </p>
            <p>CFTT70E The user &amp;user is not allowed to connect to the server             </p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>The user is not allowed to connect to the server, or the password or the authentication method is incorrect.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Correct the user name or password, or add a public key.         </td>
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
            <p><a name="CFTT71E"></a>CFTT71E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote 
 creation reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT71E remote creation reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file 
 was not created, the internal &amp;diagi code explains the reason for 
 the rejection (see the chapter on internal Transfer CFT codes).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT72E"></a>CFTT72E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote 
 selection reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT72E remote selection reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file 
 was not selected; the internal &amp;diagi code explains the reason for 
 the rejection (see the topic on internal Transfer CFT codes).</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT72W"></a>CFTT72W PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote selection reject (file not found ignored) &amp;diagi ,&amp;diagp,</p>
            <p>CFTT72W remote selection reject (file not found ignored) &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>FILENOTFOUND=IGNORE The file was not selected because the file is not found.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is aborted.</p>
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
            <p><a name="CFTT73E"></a>
</p>
            <p>CFTT72E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote selection reject &amp;diagi ,&amp;diagp</p>
            <p>CFTT72E remote selection reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>FILENOTFOUND=ABORT The message was not sent.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The message transfer is aborted. The corresponding catalog entry 
 is put on HOLD.</p>
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
            <p><a name="CFTT73E"></a>CFTT73E PART=&amp;part IDM=&amp;idf IDT=&amp;idt &amp;diagi 
 ,&amp;diagp </p>
            <p>CFTT73E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The message was not sent.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The message transfer is aborted. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT74E"></a>CFTT74E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi 
 ,&amp;diagp </p>
            <p>CFTT74E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The transfer was interrupted by the remote partner.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is aborted, the corresponding catalog entry is 
 put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT75E"></a>CFTT75E PART=&amp;part IDF=&amp;idf IDT=&amp;idt connect 
 reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT75E connect reject &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The connection request was rejected by the partner.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 failed. If the called number was engaged or a network incident occurred 
 (for example), the transfer will be retried several times (see the RETRYM, 
 RETRYN and RETRYW parameters). </p>
            <p>If all retries fail, the transfer is not executed and the corresponding 
 catalog entry is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Analyze the internal &amp;diagi error code for the transfer 
 and try to correct it.</p>
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
            <p>CFTT75E Incorrect user or password   &lt;IDTU=&amp;idtuPART=&amp;part IDF=&amp;idf IDT=&amp;idf DIAGI=&amp;diagi&gt;
 </p>
            <p>CFTT75E Incorrect user or password   &lt;IDTU=&amp;idtuPART=&amp;part IDF=&amp;idf IDT=&amp;idf DIAGI=&amp;diagi&gt;
                   </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Cannot connect to the SFTP server because the user name or password is incorrect.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the user name or password.</p>
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
            <p><a name="CFTT76E"></a>CFTT76E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi 
 ,&amp;diagp </p>
            <p>CFTT76E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The write transfer request is refused.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT77E"></a>CFTT77E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi 
 ,&amp;diagp </p>
            <p>CFTT77E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The read transfer request is refused.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is not executed. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT78E"></a>CFTT78E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp </p>
            <p>CFTT78E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A problem was detected at the end of the transfer.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 has terminated but is not considered to be valid, the corresponding catalog 
 entry is set to DISP (transfer to be restarted), on HOLD 
 (the transfer may be restarted) or to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Automatically 
 by Transfer CFT or manually by the user (correct the error, restart or 
 try a new transfer).</p>
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
            <p><a name="CFTT79E"></a>CFTT79E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote 
 deselect reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT79E remote deselect reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file could not be deselected.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer is interrupted. The corresponding catalog entry 
 is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT80E"></a>CFTT80E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote 
 open reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT80E remote open reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file could not be opened.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is interrupted. The corresponding catalog entry is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT81E"></a>CFTT81E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote 
 close reject &amp;diagi ,&amp;diagp </p>
            <p>CFTT81E remote close reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The file could not be closed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is interrupted. The corresponding catalog entry is put on HOLD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT82E"></a>CFTT82E PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt transfer aborted &amp;diagi ,&amp;diagp</p>
            <p>CFTT82E transfer aborted &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>A serious error was detected.</p>
            <p>Example</p>
            <p>19/02/19 16:01:37 CFTT82E Transfer aborted &lt;IDTU=A0000008 PART=PARIS_KEY IDF=AS3SR IDT=B1916013 DIAGI=110</p>
            <p>19/02/19 16:01:37 CFTT82E+ DIAGP=00000002 DIAGC=File not found: zohs.bat&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer 
 is interrupted and the corresponding catalog entry is set to KEEP.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Correct the error and try again.</p>
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
            <p><a name="CFTT82W"></a>CFTT82W PART=&amp;part IDF=&amp;idf IDT=&amp;idt transfer aborted (file not found ignored) &amp;diagi ,&amp;diagp </p>
            <p>CFTT82W transfer aborted (file not found ignored) &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>File not found error was detected.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Consequence</p>
         </td>
         <td>
            <p>The transfer ignore the file not found problem and pass to X phase.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Action</p>
         </td>
         <td>
            <p>Ignore the error.</p>
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
            <p><a name="CFTT83I"></a>CFTT83I PART=&amp;part IDF=&amp;idf IDT=&amp;idt change 
 direction(CD) for request </p>
            <p>CFTT83I change direction(CD) for request &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>This message is only displayed for the ODETTE protocol and a 
 RECV command. It indicates that the remote partner has accepted its turn 
 to transmit.</p>
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
            <p><a name="CFTT86I"></a>CFTT86I PART=&amp;part IDS=&amp;ids Change direction(TURN) sent </p>
            <p>CFTT86I Change direction(TURN) sent &lt;PART=&amp;part IDS=&amp;ids&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>For a PeSIT protocol in a DMZ 
 profile, the token (TURN) has been sent to the partner &amp;part.</p>
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
            <p>CFTT86I FNAME=&amp;fname 
 S=ByteCount </p>
            <p>CFTT86I FNAME=&amp;fname 
 S=ByteCount</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Name of the file sent or received and the number of bytes 
 in the file. This new message completes the CFTT54I message. Name of the file sent or received and the number of bytes in 
 the file. This message completes the CFTT54I message.</p>
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
            <p><a name="CFTT87I"></a>CFTT87I PART=&amp;part IDS=&amp;ids Change direction(TURN) received </p>
            <p>CFTT87I Change direction(TURN) received&lt;PART=&amp;part IDS=&amp;ids&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>In the case of PeSIT protocol in a DMZ profile, the token (TURN) 
 has been received by the partner &amp;part, where IDS is the reference for the session context.</p>
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
            <p><a name="CFTT88I"></a>CFTT88I+IDT=&amp;idt WORKINGDIR=&amp;workingdir FNAME=&amp;fname NBC=&amp;n DURATION=&amp;time </p>
            <p>CFTT88I+&lt;IDTU=&amp;idtu WORKINGDIR=&amp;workingdir FNAME=&amp;fname NBC=&amp;n DURATION==&amp;time&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>This message completes the message CFTT54I.</p>
            <p>The following fields indicated:</p>
            <ul>
               <li>WORKINGDIR: if the WORKINGDIR is not defined, this field is empty               </li>
               <li>fname: name of the file sent               </li>
               <li>n: number of bytes in the file               </li>
               <li>time: transfer duration in seconds               </li>
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
            <p>Information</p>
         </td>
         <td>
            <p><a name="CFTT89I"></a>CFTT89I PART=&amp;part IDF=&amp;idf IDT=&amp;idt Faction 
 on FNAME=&amp;fname : &amp;str+"deleted" or "erased" </p>
            <p>CFTT89I Faction on FNAME=&amp;fname : &amp;str+"deleted" or "erased" &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Delete or erase message for a file after using the FACTION parameter  in a transfer command (either SEND or RECV). </p>
            <p>The file is either erased or 
 deleted (FACTION=ERASE or FACTION=DELETE)  at the end of the transfer.</p>
         </td>
      </tr>
      <tr>
         <td>Information          </td>
         <td>	CFTT89I Faction on FNAME=&amp;srcfile as &amp;archivefile &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>
            <p>Archive message for a file after using the FACTION parameter in a transfer command (either SEND or RECV).
</p>
            <p>The file is archived (FACTION=ARCHIVE) at the end of the transfer.</p>
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
            <p><a name="CFTT90W"></a>CFTT90W IDF=&amp;idf IDT=&amp;idt Faction on FNAME=&amp;fname 
 : erase failed cs </p>
            <p>CFTT90W IDF=&amp;idf IDT=&amp;idt Faction on FNAME=&amp;fname : erase failed &amp;scs</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>At the end of a transfer, if the parameter FACTION=ERASE 
 cannot be carried out (for example, if the file is already used by another 
 user) the transfer moves to the T 
 state.  </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Warning 
 </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>CFTT90W 
 IDF=&amp;idf IDT=&amp;idt Faction on FNAME=&amp;fname : delete failed 
 cs</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Explanation</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>At the end of a transfer, if the parameter FACTION=DELETE 
 cannot be carried out (for example, if the file is already used by another 
 user) the transfer moves to the T 
 state.  </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Action</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Delete or erase the file manually.</p>
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
            <p><a name="CFTT91W"></a>CFTT91W PART=&amp;part IDS=&amp;ids Change direction(TURN) not supported by server</p>
            <p>CFTT91W Change direction (TURN) not 
 supported by server PART=DMZ1 IDS=&amp;ids</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>When using the DMZ mode, if the server does not accept the 
 TURN, the session is closed by the requester without message. The IDS is the reference for this session context.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Action</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>This message is edited on LOG file.</p>
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
            <p><a name="CFTT93W"></a> CFTT92I IDTU=&amp;idtu CTX=&amp;ctx IDT=&amp;idt 
</p>
            <p>CFTT92I &lt;IDTU=&amp;idtu CTX=&amp;ctx IDT=&amp;idt&gt;</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>Additional message for message CFTT57I, and is displayed only if ATM traces are activated.</p>
            <p>CTX=&amp;ctx provides the protocol context associated with the transfer.</p>
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
            <p><a name="CFTT93W"></a>CFTT93W PART=&amp;part IDS=&amp;ids Negative ack not supported</p>
            <p>CFTT93W Negative ack not supported PART=&amp;part IDS=&amp;ids  
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Explanation</p>
         </td>
         <td>
            <p>The  final 
 partner signals to the initial file sender  that application errors 
 were detected. This occurs via a negative acknowledgments sent in a PeSIT Hors SIT 
 message, where IDS is the reference for the session context.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>Information          </td>
         <td>
            <p><a name="CFTT94I"></a>CFTT94I PART=&amp;part IDF=&amp;idf IDT=&amp;idt FCHARSET=&amp;str NCHARSET=&amp;str </p>
            <p>CFTT94I &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt FCHARSET=&amp;str NCHARSET=&amp;str&gt;</p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>This information message relates to the extended transcoding used for this transfer.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>Error         </td>
         <td>
            <p><a name="CFTT95E"></a>CFTT95E Incorrect user or password   &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idtf DIAGI=&amp;diagi&gt; </p>
            <p>CFTT95E Incorrect user or password &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt DIAGI=&amp;diagi&gt;                </p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>Cannot connect to the SFTP server because the user name or password is incorrect.
         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>Correct the user name or password.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr>
         <td>
            <p>V23 format</p>
            <p>V24 format</p>Information          </td>
         <td>
            <p><a name="CFTT96I"></a>   CFTT96I &amp;str transfer restarted &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt POS=&amp;pos IDS=&amp;ids&gt; </p>
            <p>CFTT96I &amp;str transfer restarted &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt POS=&amp;pos IDS=&amp;ids&gt;                </p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>The requester (&amp;str = requester) or the server (&amp;str = server) has restarted the transfer.
&amp;pos is the file position during restart.
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
            <p><a name="CFTT97E"></a>CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands",</p>
            <p>CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands</p>
            <p><![CDATA[ ]]></p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td><![CDATA[
]]>         </td>
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
            <p><a name="CFTT98W"></a>CFTT98W PART=%-8.8s IDF=%-8.8s IDT=%.8s Rename ignored because WFNAME equals FNAME,</p>
            <p>CFTT98W Rename ignored because WFNAME equals FNAME &lt;IDTU=%.8s PART=%s IDF=%s IDT=%.8s&gt;</p>
         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>The configuration has the same <a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/wfname">WFNAME</a> as the RECV FNAME and so the renaming is ignored.          </td>
      </tr>
</table>

 
