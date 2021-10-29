{
    "title": "Transfer CFT messages: CFTS",
    "linkTitle": "CFTS messages",
    "weight": "380"
}This topic lists the CFTSxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS01W"></span>CFTS01W Synch. response time-out _ Waitresp increased to &amp;ns (&amp;str)</p>
            <p>CFTS01W Synch. response time-out _ Waitresp increased to &amp;ns (&amp;str)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The message placed in a synchronous queue has received no response
(time limit has expired).</p>
            <p>Where:</p>
            <ul>
               <li>            <p>&amp;n is the value in seconds of the new WAITRESP</p>               </li>
               <li>            <p>&amp;str is either CFTTCOM or CFTTFIL, the process who wrote the message</p>               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Another attempt will be made.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS02E"></span>CFTS02E PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]
IDT=&amp;idt DIRECT=&amp;direct  &amp;fname not found</p>
            <p>CFTS02E _ &amp;fname not found &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt DIRECT=&amp;direct&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The &amp;fname
procedure was not found for a given transfer (&amp;idt).</p>
            <p>This procedure
was requested after a file or message transfer or subsequent to an error
(see the <span>Transfer CFT</span> Online documentation, EXEC parameters).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS03I"></span>CFTS03I PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt
_ &amp;fname submitted</p>
            <p>CFTS03I _ &amp;fname submitted&lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt; (&amp;n sec)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The procedure
(&amp;fname) was submitted for a given transfer (&amp;idt).</p>
            <p>This procedure
was requested at the end of a file or message transfer, or in the event
of an error (see the
EXECxxx parameters).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS04W"></span>CFTS04W Action file &amp;fname is empty</p>
            <p>CFTS04W Action file &amp;fname is empty</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An action
is envisaged at the end of a transfer or in the event of an error (see
the <span>Transfer CFT</span> Online documentation, EXECxxx
parameters); the file to be submitted is empty.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS05E"></span>CFTS05E Error code &amp;scs _ Trying to
access &amp;str</p>
            <p>CFTS05E Error code &amp;scs _ Trying to access &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An access error was detected on a file.</p>
            <p>This file (&amp;fname) corresponds to an action requested
at the end of a transfer or in the event of an error (see the Transfer
CFT Online
documentation EXECxxx parameters).</p>
            <p>The &amp;str variable can
have the following values:</p>
            <p>&amp;fname</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The procedure will not be executed. If the action was requested
at the end of a transfer, the transfer ends normally.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Check that the characteristics of the file to be submitted are
correct (attributes and length) and inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS06E"></span>CFTS06E Error code &amp;scs _ Trying to access temporary
file</p>
            <p>CFTS06E Error code &amp;scs _ Trying to access temporary file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An action
was requested at the end of a transfer or in the event of an error. This
action is submitted (see the
EXECxxx parameters) through a buffer file (&amp;fname).</p>
            <p>An access
error was detected on this buffer file.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <ul>
               <li>Check
that the characteristics of the buffer file are correct (attributes and
length).               </li>
               <li>Check that it
exists (created or defined logically in the <span>Transfer CFT</span> startup procedure).               </li>
               <li>Contact Product Support.               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS07E"></span>CFTS07E Insufficient space for temporary file</p>
            <p>CFTS07E Insufficient space for temporary file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An action
was requested at the end of a transfer or in the event of an error. This
action is submitted (see the <span>Transfer CFT</span> Online documentation,
EXECxxx parameters) through a buffer file (&amp;fname). The space reserved
for this file proves insufficient.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Increase the file size, inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS08E"></span>CFTS08E Error code &amp;scs _ Executing temporary file</p>
            <p>CFTS08E Error code &amp;scs _ Executing temporary file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The procedure
(&amp;fname) could not be executed for a given transfer (&amp;idt).</p>
            <p>This procedure
was requested at the end of a file or message transfer or in the event
of an error (see the <span>Transfer CFT</span> Online documentation
EXECxxx parameters).</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Analyze the &amp;scs code and inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS10E"></span>CFTS10E File communication task error (&amp;str1) _
&amp;str2</p>
            <p>CFTS10E File communication task error (&amp;str1) _ &amp;str2</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Following a synchronous message queue time-out, the communication
task aborted.</p>
            <p>The str1 and str2 values are:</p>
<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td data-bgcolor="#C0C0C0" width="50%">            <p>str1</p>         </td>
         <td data-bgcolor="#C0C0C0" width="50%">            <p>Associated str2 value</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="50%">            <p>define sem</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="50%">            <p>open</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="50%">            <p>memory</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="50%">            <p>post</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="50%">            <p>invalid sem</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="50%">            <p>catalog full</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="50%">            <p>&lt;cs code&gt;</p>         </td>
         <td width="50%">            <p>terminating</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="50%">            <p>read</p>         </td>
         <td width="50%">            <p>continue</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="50%">            <p>delete shut</p>         </td>
         <td width="50%">            <p>continue</p>         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Contact
Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS11E"></span>CFTS11E Allocation error _ Trying to access temporary
file</p>
            <p>CFTS11E Allocation error _ Trying to access temporary file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An action
was requested at the end of a transfer or in the event of an error.</p>
            <p>This action
is submitted (see the <span>Transfer CFT</span> Online documentation,
EXECxxx parameters) through a buffer file (&amp;fname). An allocation
error was detected on this buffer file.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The procedure will not be executed. If the action was requested
at the end of the transfer, the transfer ends normally.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <ul>
               <li>Check that the
characteristics of the buffer file are correct (attributes and length).               </li>
               <li>Check that it
exists (created or defined logically in the <span>Transfer CFT</span> startup procedure).               </li>
               <li>Contact
Product Support.               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS12W"></span>CFTS12W Error code &amp;scs _ CFT write messages to
output stream</p>
            <p>CFTS12W Error code &amp;scs _ CFT write messages to output stream</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The Transfer
CFT logging process can no longer write messages in the log file(s) (problem
adding to the file, system incident).</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer
CFT messages will be written to the standard output (screen for example).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Analyze the &amp;scs code and inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS13E"></span>CFTS13E Semaphore failure &amp;cs_CFTTPRO aborted</p>
            <p>CFTS13E Semaphore failure &amp;cs_CFTTPRO aborted</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Problem
receiving an internal <span>Transfer CFT</span> message by the PROTOCOL task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>A message has perhaps been lost; the reactions are unpredictable.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Analyze the &amp;scs code and inform Product Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS14E"></span>CFTS14E ID=&amp;id error initializing process</p>
            <p>CFTS14E Unknown synchronization message CLASS=&amp;class TYPE=&amp;type</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot run the end of transfer exit task. This message follows the <span>Transfer CFT</span> message CFTI01.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>No effect on the actual transfer (catalog not updated). The exit
is not executed. If an end of transfer procedure was defined, it is run.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS15I"></span>CFTS15I PART = &amp;part Kill Session Reference &amp;ctx:&amp;ctx</p>
            <p>CFTS15I PART = &amp;part Kill Session Reference &amp;ctx:&amp;ctx</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Internal message to <span>Transfer CFT</span> giving information on the transfer
context killed. The &amp;ctx values specify the context concerned.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS16E"></span>CFTS16E Synch. response time-out_End transfer exit</p>
            <p>CFTS16E Synch. response time-out _ End of transfer exit</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The exit
task is run but does not respond to the <span>Transfer CFT</span>. This corresponds
to the initial phase establishing communications between the <span>Transfer CFT</span> and
the exit task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>None on the actual transfer (catalog not updated). The exit
is not executed. If an end of transfer procedure has been defined, it
is run.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS17E"></span>CFTS17E Error code &amp;scs _ Trying to access End transfer
exit</p>
            <p>CFTS17E Error code &amp;scs _ Trying to access End of transfer exit</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Error posting a <span>Transfer CFT</span> message to the exit task during inter-task
communications.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>None on the actual transfer (catalog not updated). The exit
is does not receive any directives from the <span>Transfer CFT</span>.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS18W"></span><span id="CFTS18E"></span>CFTS18E PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt _ Catalog record Update Error: &amp;scs</p>
            <p>CFTS18E _ Catalog Update Error: &amp;scs &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">Transfer CFT catalog update issue with error code = &amp;scs.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">The transfer record is not updated.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS18W"></span>CFTS18W PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]
IDT=&amp;idt _ Catalog record label</p>
            <p>CFTS18W _ Catalog record &amp;label &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Label
equals "State not updated x -&gt; y" (x = current state,
y = requested state) or "not deleted".</p>
            <p>Transfer
CFT catalog update issue.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The catalog entry corresponding to the transfer is not updated.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Inform Product Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS19I"></span>CFTS19I PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt
_ Catalog record label</p>
            <p>CFTS19I _ Catalog record &amp;str &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Information
message label equals "updated x to y"  (x = current
state, y = requested state) or "deleted". The Transfer
CFT catalog is updated.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS20I"></span>CFTS20I Communication file row number deleted: nnnnnnnn (&amp;str)</p>
            <p>CFTS20I &amp;str", &amp;str = Communication file row number deleted: nnnnnnnn</p>
            <p>or File communication task INIT (&amp;n,WSCAN=&amp;wscan,RET=&amp;ret)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Communication file related message where the 8 digits (n) represent the record number.</p>
            <p>If the jobname is set in the catalog, then the information &lt;JOBNAME=PID&gt; (all platforms except z/OS) or &lt;JOBNAME=jobname jobid&gt; (z/OS platforms) displays in the message in place of (&amp;str).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS21I"></span>CFTS21I PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt
Exit request ID=&amp;id</p>
            <p>CFTS21I Exit request ID=&amp;id &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Information message prior to sending information to the end
of transfer exit.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>None.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS22I"></span>CFTS22I Task time out End of transfer exit</p>
            <p>CFTS22I Task time out End of transfer exit</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Exit task re-entry time-out. The task is stopped automatically.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The exit task will be rerun by the next call.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>If necessary, increase the value of the WAITTASK parameter in
the CFTEXIT card.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS23E"></span>CFTS23E Bad user return code &lt;details&gt;</p>
            <p>CFTS23E &amp;str PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt ", &amp;str = Bad End transfer exit version : &amp;ver / &amp;ver</p>
            <p>or</p>
            <p>CFTS23E &amp;str &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt &gt;") Invalid state transit '&amp;state'-&gt;'&amp;state' or Unknown state &amp;state</p>
            <p>or</p>
            <p>Unknown action &amp;action or Bad User return code : &amp;scs</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p>Error message specific to the end-of-transfer user exit. The details that display in the message depend on the CFTLOG format (v23 or v24).</p>
            <p><strong>Example</strong></p>
            <p>V24 format:</p>
            <p><span>CFTS23E Bad User return code: 4 &lt;IDTU=idtu PART=part1 IDF=idf1 IDT=idt &gt;</span></p>
            <p>V23 format:</p>
            <p>CFTS23E Bad User return code : 4 PART=part1 IDF=idf1 IDT=idt</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p>Consequence</p>         </td>
         <td width="80%">            <p>None.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS26E"></span>CFTS26E XTRK task error &amp;str </p>
            <p>CFTS26E XTRK task error &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Error initializing the Sentinel monitoring task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Take note of the complete text of the message (&amp;str) and
contact Axway Product Support. </p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS27E"></span>CFTS27E Synchronous communication task error CR=&amp;cr
&amp;str</p>
            <p>CFTS27E Synchronous communication task error CR= &amp;cr &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Synchronous communication task error.</p>
            <p>CR=&amp;cr &amp;str CFT</p>
            <ul>
               <li>Internal synchronization error.               </li>
               <li>Password authentication error due to invalid user or password.               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Depending on the severity of the problem, the
synchronous communication task can be stopped or continued (and either Terminating or Continue is displayed in the accompanying message
&amp;str).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Notify Technical Support, if necessary. Furnish the complete
message as well as the synchronous
communication media parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS29I"></span>CFTS29I Cannot acces XTRK task _ &amp;str</p>
            <p>CFTS29I Cannot acces XTRK task _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Problem in communication with the Sentinel monitoring task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Action</p>         </td>
         <td width="80%">            <p>Take note of the complete text of the message and contact Axway
Product Support. </p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS30I"></span>CFTS30I XTRK Information &amp;str</p>
            <p>CFTS30I XTRK Information &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Elements of information concerning the Sentinel monitoring task.</p>
            <p>The field "&amp;str" is an explicit string:</p>
            <p>“Buffer File Info : Current = nn , Max=mm”</p>
            <p>where:</p>
            <ul>
               <li>number
of current records = nn               </li>
               <li>maximum
number of records = mm               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS31W"></span>CFTS31W XTRK Warning &amp;str Error Code = &amp;cr</p>
            <p>CFTS31W XTRK Warning &amp;str Error Code = &amp;cr</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The user is warned of a problem in communication with the Sentinel
Server or the Sentinel Agent. The message is stored in the overflow
file for the Sentinel monitoring task.</p>
            <p>The text of the &amp;str message specifies the possible
type of warning:</p>
            <p>sendMessage : send of a message to Sentinel</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>         </td>
         <td width="80%">            <p><span id="CFTS32W"></span>CFTS32W TCOMS Connection
refused (address=nnn.nnn.nnn.nnn, name=userid)</p>
            <p>CFTS32W TCOMS Connection
refused</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An incoming connection from name=userid and address=nnn.nnn.nnn.nnn
was rejected because this address is not authorized for Synchronous Communication.</p>
            <p>See the CFTCOM object  ADDRLIST
parameter.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS33I"></span>CFTS33I CFTLOG current
file before switch</p>
            <p>CFTS33I CFTLOG current file before switch :&amp;fname</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>For SWITCH LOG or SWITCH ACCNT:</p>
            <ul>
               <li>Transfer
CFT start-up               </li>
               <li>SWITCH
operator               </li>
               <li>SWITCH
cache command               </li>
               <li>SWITCH
if file is full during a write               </li>
               <li>If no
switch procedure is defined               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS34I"></span>CFTS34I CFTLOG executed
switch proc</p>
            <p>CFTS34I CFTLOG execute switch procedure : &amp;fname</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>For SWITCH LOG or SWITCH ACCNT:</p>
            <ul>
               <li>Transfer
CFT start-up               </li>
               <li>SWITCH
operator               </li>
               <li>SWITCH
cache command               </li>
               <li>SWITCH
if file is full during a write               </li>
               <li>If no
switch procedure is defined               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS35I"></span>CFTS35I CFTLOG current
file after switch</p>
            <p>CFTS35I CFTLOG current file after switch :&amp;fname</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>For SWITCH LOG or SWITCH ACCNT:</p>
            <ul>
               <li>Transfer
CFT start-up               </li>
               <li>SWITCH
operator               </li>
               <li>SWITCH
cache command               </li>
               <li>SWITCH
if file is full during a write               </li>
               <li>If no
switch procedure is defined               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS36I"></span>CFTS36I CFTACCNT current
file (no switch executed)</p>
            <p>CFTS36I CFTACCNT current file (no switch executed): &amp;fname</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>For SWITCH LOG or SWITCH ACCNT:</p>
            <ul>
               <li>Transfer
CFT start-up               </li>
               <li>SWITCH
operator               </li>
               <li>SWITCH
cache command               </li>
               <li>SWITCH
if file is full during a write               </li>
            </ul>
            <ul>
               <li>If the two CFTLOG
files are full and are not performing the switch:               </li>
            </ul>
            <ul>
               <li>CFTS36I CFTLOG
current file (no switch executed): CFTOUT               </li>
               <li>If the two CFTACCNT
files are full and are not performing the switch:               </li>
               <li>CFTS36I CFTACCNT
current file (no switch executed): Files full               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information
 </p>         </td>
         <td width="80%">            <p><span id="CFTS37I"></span>CFTS37I CRONJOB ID=&amp;idcron, CRONTAB=&amp;cronname &amp;exec executed, NEXT=&amp;date</p>
            <p>CFTS37I CRONJOB: ID=&amp;idcron, CRONTAB=&amp;cronname ACT DONE</p>
            <p>CFTS37I CRONJOB: RECONFIG type=CRON DONE</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p>Job defined by &amp;exec is executed correctly; the next submit is indicated in NEXT=date time.</p>         </td>
      </tr>
   </tbody>
</table>

[ ](cfti_messages)

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning  </p>         </td>
         <td width="80%">            <p><span id="CFTS39E"></span>CFTS38W CRONJOB NEXT TIME CALCUL FAILED, RETURN &amp;ret</p>
            <p>CFTS38W CRONJOB NEXT TIME CALCUL IS AFTER 2035, ABORTING, RETURN &amp;ret</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cronjob next time calcul failed. No time corresponding to filter was found. Cronjob is not executed.</p>
            <p>or</p>
            <p>Cronjob next time calculated is after 2035. Cronjob is not executed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
 </p>         </td>
         <td width="80%">            <p><span id="CFTS39E"></span></p>
            <p>CFTS39E CRONJOB ID=&amp;id, CRONTAB=&amp;cronname exec &amp;fname failed</p>
            <p>CFTS39E CRONJOB: ID=&amp;id INACT FAILED: CRONJOB Not Found</p>
            <p>CFTS39E CRONJOB: ID=&amp;id ACT FAILED: CRONJOB Not Found</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p> Job failed. Could not file the file to submit. Check file properties.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error
 </p>         </td>
         <td width="80%">            <p><span id="CFTS39E"></span></p>
            <p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>
            <p>CFTI40E OMVS SEGMENT NOT DEFINED for user=xxxxxx</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p>Reserved for z/OS systems.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Fatal</p>         </td>
         <td width="80%">            <p><span id="CFTS40F"></span>CFTS40F CFTACCNT FORMAT=(V23/V24) not available for &amp;fname</p>
            <p>CFTS40F CFTACCNT FORMAT=(V23|V24) not available for &amp;fname</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An error occurred in the FORMAT=V23/V24 (V23 default) parameter of CFTFILE TYPE=ACCNT. When using the V23 format, the saved description (for ACCOUNT files) is the same as in previous versions. However when using the V24 format, the length for saving is 2048, and  the saved description takes into account the new longer field lengths.<br />
</p>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">The FORMAT parameter for the CFTACCNT command must be the same setting as for<br />
CFTFILE TYPE=ACCNT. If not, a message displays in the LOG and <span>Transfer CFT</span> does<br />
not start.         </td>
      </tr>
   </tbody>
</table>
<div>
            <p>The message is either:<br />
   CFTS40F CFTACCNT FORMAT=V24 not available for CFT.ACCNT    </p>
            <p>   CFTS40F CFTACCNT FORMAT=V23 not available for CFT.ACCNT<br />
Followed by the message: CFTI17F Init error _ Account file .CFT.ACCNT</p>
</div>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS41I"></span>CFTS41I Catalog Alert
exec &amp;fname executed</p>
            <p>CFTS41I Catalog Alert exec &amp;fname executed</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The procedure &amp;FNAME for a catalog alert was executed.</p>
            <ul>
               <li>When the critical
fill threshold is reached, a message CFTC29W is recorded in the Transfer
CFT log.               </li>
            </ul>
            <p>A batch, which is defined by the CFTCAT TLVWEXEC parameter,
is submitted.</p>
            <ul>
               <li>When
the alert ceases, a message CFTC30W is recorded in the <span>Transfer CFT</span> log.               </li>
            </ul>
            <p>A batch, which is defined by the CFTCAT TLVCEXEC parameter,
is submitted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS42E"></span>CFTS42E Catalog Alert exec &amp;fname &amp;str" where &amp;str= "not found" or "failed"</p>
            <p>CFTS42E Catalog Alert exec &amp;fname &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The procedure &amp;FNAME for a catalog alert was not found
or failed on access producing this error.</p>
            <ul>
               <li>When
the critical fill threshold is reached, a message CFTC29W is recorded
in the <span>Transfer CFT</span> log.
            <ul>
               <li>The batch, which is defined by the CFTCAT TLVWEXEC
parameter, is not executed               </li>
            </ul>               </li>
               <li>When
the alert ceases, a message CFTC30W is recorded in the <span>Transfer CFT</span> log
            <ul>
               <li>The batch, which is defined by the CFTCAT TLVCEXEC
parameter, is not executed.               </li>
            </ul>               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p> </p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTS43I"></span>CFTS43I &amp;str", &amp;str = RECONFIG PARM CACHE CFTMAIN or RECONFIG &amp;task : Keep &amp;key : &amp;value or Parameter &amp;task &amp;value --&gt; &amp;value or RECONFIG &amp;task </p>
            <p>CFTS43I &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Displays information about CFTUTIL RECONFIG TYPE=UCONF.</p>
            <p>Wwhere &amp;str = "RECONFIG PARM CACHE CFTMAIN "</p>
            <ul>
               <li>&amp;str = "RECONFIG &amp;task : Keep &amp;key : &amp;value"               </li>
               <li>&amp;str = "Parameter &amp;task &amp;value --&gt; &amp;value or RECONFIG &amp;task"               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS44W"></span>CFTS44W Unexpected message Class &amp;n &lt;TASK=&amp;str&gt;</p>
            <p>CFTS44W Unexpected Message Class &amp;n &lt;TASK=&amp;task&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An internal message received by the &amp;str task has an unexpected class value (&amp;n).         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The message is ignored.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS45W"></span>CFTS45W Unexpected Message Class &amp;n &lt;TASK=&amp;task&gt;</p>
            <p>CFTS45W Unexpected Message Type &amp;n &lt;TASK=&amp;task CLASS=&amp;n&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An internal message received by the &amp;str task with CLASS=&amp;str has an unexpected type value (&amp;n).         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The message is ignored.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Fatal         </td>
         <td width="80%">            <p><span id="CFTS46F"></span>CFTS46F CFTPRX error _ &amp;str</p>
            <p>CFTS46F CFTPRX error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">A fatal error occurred in the proxy task (CFTPRX). The error details are in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%"><span>Transfer CFT</span> stops.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If necessary, contact Axway support.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS47E"></span>CFTS47E CFTPRX error _ &amp;str</p>
            <p>CFTS47E CFTPRX error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">A significant error occurred in the proxy task (CFTPRX). The error is detailed in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The concerned transfer goes into error.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If necessary, contact Axway support.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS48W"></span>CFTS48W CFTPRX _ &amp;str</p>
            <p>CFTS48W CFTPRX _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An anomaly occurred in the proxy task (CFTPRX). The anomaly details are in &amp;str.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS49I"></span>CFTS49I CFTPRX _ &amp;str</p>
            <p>CFTS49I CFTPRX _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Information message from the Proxy task (CFTPRX). The &amp;str value gives additional details.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Fatal         </td>
         <td width="80%">            <p><span id="CFTS50F"></span>CFTS50F CFTJRE error _ &amp;str</p>
            <p>CFTS50F CFTJRE error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">A fatal error occurred when starting the CFT Java task (CFTJRE). The error is detailed in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%"><span>Transfer CFT</span> is stopping.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If necessary, contact <span>AMPLIFY</span> support.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS51E"></span>CFTS51E CFTJRE error _ &amp;str</p>
            <p>CFTS51E CFTJRE error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">A significant error occurred in the <span>Transfer CFT</span> Java task (CFTJRE). The error is detailed in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The concerned transfer goes in error.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If necessary, contact <span>AMPLIFY</span> support.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS52W"></span>CFTS52W CFTJRE _ &amp;str</p>
            <p>CFTS52W CFTJRE _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An anomaly occurred in the <span>Transfer CFT</span> Java task (CFTJRE). The anomaly is detailed in &amp;str.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS53I"></span>CFTS53I CFTJRE _ &amp;str</p>
            <p>CFTS53I CFTJRE _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Information message from the <span>Transfer CFT</span> Java task (CFTJRE). The &amp;str value gives additional details.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS54F"></span>CFTS54F CFTACC task fatal CR=&amp;cr &amp;str</p>
            <p>CFTS54F CFTACC task fatal CR= &amp;cr &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">A fatal error occurred in the accelerator task (CFTACC). The error is detailed in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%"><span>Transfer CFT</span> is stopping.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">If necessary, contact Axway support.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS55I"></span>CFTS55I Acceleration &amp;str</p>
            <p>CFTS55I Acceleration &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Information message from the Accelerator task (CFTACC). the &amp;str value gives more detail.         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS56E"></span>CFTS56E Central Governance error (&lt;error_code&gt;) &lt;error_msg&gt;</p>
            <p>CFTS56E Central Governance &amp;str", &amp;str = &amp;type error (send): (&amp;code) &amp;message</p>
            <p>CFTS56E Central Governance &amp;str", &amp;str = &amp;type error (recv): (&amp;code) &amp;message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>An error occurred when executing a &lt;request&gt; on Central Governance.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The <span>Transfer CFT</span> instance does not display the correct status.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p> </p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS57W"></span>CFTS57W Synchronous communication _ Authentication ignored - authentication_enable=yes but authentication_method=&amp;auth_method</p>
            <p>CFTS57W Synchronous communication _ Authentication ignored - authentication_enable=yes but authentication_method=&amp;auth_method</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>Possible scenarios include:</p>
            <ul>
               <li>            <p>Authentication_enable=yes but authentication_method=none</p>
            <p>In the unified configuration authentication is enabled, but no mode is defined: uconf: cft.server.cftcoms.authentication_enable=yes</p>
            <p>uconf: cft.server.authentication_method=none</p>               </li>
               <li>            <p>User=user01 Group=group01 provided a password but authentication_enable=no</p>
            <p>In the CONFIG command the PASSWORD parameter is set, but in the unified configuration it is disabled: uconf:cft.server.cftcoms.authentication_enable=no</p>               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS59E"></span>CFTS59E Multi-node error _ &amp;str</p>
            <p>CFTS58F Multi-node error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An important error occurred during the transfer recovery. The error is detailed in &amp;str.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">The transfer in question is not recovered.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">Contact the support team if necessary.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS60W"></span>CFTS60W Multi-node _ &amp;str</p>
            <p>CFTS60W Multi-node _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">An anomaly occurred during the transfer recovery. The anomaly is detailed in &amp;str.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS61I"></span>CFTS61I Multi-node _ &amp;str</p>
            <p>CFTS61I Multi-node _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Displays information about the multi-node transfer recovery phase. The &amp;str value provides additional details.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS62I"></span>CFTS62I &amp;str</p>
            <p>CFTS62I &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>Displays information about UCONF scheduling.</p>
            <p>Where:</p>
            <ul>
               <li>&amp;str = "SCHEDULE : Id &amp;id is not a valid uconf entry", or               </li>
               <li>&amp;str = " SCHEDULE &amp;id : Parameter &amp;parm '&amp;value' --&gt; '&amp;value'", or               </li>
               <li>&amp;str = "RECONFIG AM &amp;task or SCHEDULED CONFIG &amp;task"               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Fatal         </td>
         <td width="80%">            <p><span id="CFTS63F"></span>CFTS63F Secure Relay fatal error _ &amp;str</p>
            <p>CFTS63F Secure Relay fatal error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>Fatal error detected. &amp;str indicates the reason
Secure Relay Master agent is stopped.</p>
            <p>Secure Relay is not available.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">Check the configuration depending on the reason and restart Transfer CFT.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS64I"></span>CFTS64I Secure Relay _ &amp;str</p>
            <p>CFTS64I Secure Relay _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Secure relay information message : &amp;str= Router agent &amp;n is enabled but has no host or ports.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS64I"></span><span id="CFTS65W"></span>CFTS65W Unable to launch another script for 60s due to the cft.server.max_processing_scripts limit</p>
            <p>CFTS65W Unable to launch another script for 60s due to the cft.server.max_processing_scripts limit</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">The total number of transfers in the AC, YC and ZC state has reached the <code>cft.server.max_scripts</code> limit and has not decreased for 60s.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">A script has been waiting to be launched for at least 60s.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">Check that there is an END command in the EXEC scripts.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS64I"></span><span id="CFTS66E"></span>CFTS66E TFIL error _ &amp;str", &amp;str = Regular expression &amp;mask parsing error or List generation error &amp;scs</p>
            <p>CFTS66E TFIL error _ &amp;str</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>The regular expression (REGEX) &amp;mask configured in fname (SEND or CFTSEND) can not be parsed with error &amp;scs
Consequence.</p>
            <p>Where;</p>
            <ul>
               <li>&amp;str = "Regular expression &amp;mask parsing error", or               </li>
               <li>&amp;str = " List generation error &amp;scs"               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">Transfer is not executed.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Action         </td>
         <td width="80%">Check and modify the REGEX &amp;mask value.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS67E"></span>CFTS67E Error replacing variable &amp;var &amp;message</p>
            <p>CFTS67E Error replacing variable &amp;var &amp;message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">The <strong>&lt;var&gt;</strong> variable contains blacklisted characters.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Error         </td>
         <td width="80%">            <p><span id="CFTS68E"></span>CFTS68E PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm]IDT=&amp;idt _ &amp;fname not executed</p>
            <p>CFTS68E _ &amp;fname not executed &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf | IDM=&amp;idm] IDT=&amp;idt DIRECT=&amp;direct&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">The <strong>&amp;fname</strong> script was not executed because a variable contained blacklisted characters. The file was nonetheless created, and may contain some data.         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS71W"></span>CFTS71W Command file Alert fill threshold reached: level=&amp;level ID=&amp;id</p>
            <p>CFTS71W Command file Alert fill threshold reached: level=&amp;level ID=&amp;id</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>&amp;level of the COM file space has been used. &amp;level is the amount set by the CFTCOM TLVWARN parameter.
When the critical fill threshold is reached, a message is recorded in the Transfer CFT log.</p>
            <p>A batch in response to the alert, the CFTCOM TLVWEXEC parameter, is submitted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Warning         </td>
         <td width="80%">            <p><span id="CFTS72W"></span>CFTS72W Command file Alert cleared : level=&amp;level ID=&amp;id</p>
            <p>CFTS72W Command file Alert cleared : level=&amp;level ID=&amp;id</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>This alert stops when the fill level drops below the TLVCLEAR level.</p>
            <p>When the alert stops, the message is recorded in the Transfer CFT log and a batch, the CFTCOM TLVCEXEC parameter, is submitted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
Information         </td>
         <td width="80%">            <p><span id="CFTS73I"></span>CFTS73I Command file Alert exec &amp;fname executed</p>
            <p>CFTS73I Command file Alert exec &amp;fname executed</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>The &amp;FNAME procedure for a catalog alert was executed.</p>
            <ul>
               <li>If the critical fill threshold is reached, the CFTS71W message is recorded in the Transfer CFT log.               </li>
               <li>If the alert ceases, the CFTS72W message is recorded in the Transfer CFT log.               </li>
            </ul>
            <p>Either way a batch is submitted, as by the CFTCOM TLVCEXEC parameter.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTS74E"></span>CFTS74E Command file Alert exec &amp;fname &amp;str"</p>
            <p>CFTS74E Command file Alert exec &amp;fname &amp;str"</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">            <p>The &amp;FNAME procedure for a command file alert was not found or failed on access, producing this error.</p>
            <ul>
               <li>If the critical fill threshold is reached, the CFTS71W message is recorded in the Transfer CFT log.               </li>
            </ul>
            <ul>
               <li>If the alert ceases, the CFTS72W message is recorded in the Transfer CFT log.               </li>
            </ul>
            <p>In either case, the batch defined by the CFTCOM TLVCEXEC parameter is not executed.</p>
            <p>Where:</p>
            <ul>
               <li>&amp;str = "not found", or               </li>
               <li>&amp;str = "failed"               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>
