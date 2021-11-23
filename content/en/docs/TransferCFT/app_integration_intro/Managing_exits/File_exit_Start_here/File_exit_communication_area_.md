{
    "title": "About  the communication area",
    "linkTitle": "About the communication area",
    "weight": "310"
}This section describes the file exit communication area structure and describes the fields of the communication structure.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>mtype</p>         </td>
         <td><p>Transfer stage<br />
The possible values are:</p>
<ul>
<li>0    
(ALLOC_TYP)   before
the file is allocated</li>
<li>1    
(OPEN_TYP)     before
the file is opened</li>
<li>2    
(TRANS_TYP)    before
the start of the transfer</li>
<li>3    
(DATA_TYP)      before
a record is sent or after it is received</li>
<li>4    
(CHECK_TYP)   after a synchronization point</li>
<li>5    
(RESTART_TYP) before repositioning</li>
<li>6    
(DTEND_TYP)    before the end of the file</li>
<li>7    
(CLOSE_TYP)    before the file is closed</li>
<li>8    
(ENDTR_TYP)    before the end of the transfer</li>
<li>9    
(ABORT_TYP)    after a transfer interruption </li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>masc</strong> </p>         </td>
         <td><p>Mask for selecting stages<br />
This field comprises 16 bytes; each byte can take the value 0 or 1 and
is associated with a stage:</p>
<ul>
<li>Byte
0              =&gt; ALLOC_TYP</li>
<li>Byte
1              =&gt; OPEN_TYP</li>
<li>Byte
2              =&gt; TRANS_TYP</li>
<li>Byte
3              =&gt; DATA_TYP</li>
<li>Byte
4              =&gt; CHECK_TYP</li>
<li>Byte
5              =&gt; RESTART_TYP</li>
<li>Byte
6              =&gt; DTEND_TYP</li>
<li>Byte
7              =&gt; CLOSE_TYP</li>
<li>Byte
8              =&gt; ENDTR_TYP</li>
<li>Byte
9              =&gt; ABORT_TYP</li>
<li>Bytes
10 to 15 =&gt; Reserved</li>
</ul>
<p>Byte 0 always equals 1.</p>
<p>If you set a byte to 1, it means that you want to take
control during the associated stage<br />
The value of the field mtype indicates the rank of the byte associated
with the stage</p>         </td>
      </tr>
      <tr>
         <td><p>access </p>         </td>
         <td><p>File access managements under the control of:</p>
<ul>
<li>Transfer
CFT if set to 0<br />
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> takes charge of all operations; you can, however, change
certain features of the file (name, size, format, etc.) at the allocation
and opening stages</li>
<li>The user
if set to 1<br />
You are responsible for all operations performed on the file: allocation,
opening, read/write, closing, de-allocation</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>retsync</p>         </td>
         <td><p>The return is:</p>
<ul>
<li>0 : synchronous<br />
The user function processes the stage and returns control to the interface.</li>
<li>1: asynchronous<br />
The user function returns control to the interface before processing
the stage (deferred processing). The transfer is suspended and the interface
waits for an end of processing message from the user.</li>
</ul>
<p>As the user does not yet have the information or tools
required to use the possibility of an asynchronous return, the return
will always be synchronous </p>         </td>
      </tr>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>Return code:</p>
<ul>
<li>0 = processing
ok</li>
<li>9 = refusal
and end of transfer</li>
</ul>
<p>Other values are defined depending on the transfer stage.
For more information, refer to the <a href="../using_file_exit_comm_area">Using
the Communication Structure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>ret2</p>         </td>
         <td><p>Error message.<br />
This message appears in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog in the DIAGP field (protocol
diagnosis).</p>         </td>
      </tr>
      <tr>
         <td><p>us_sem</p>         </td>
         <td><p>Reserved</p>         </td>
      </tr>
      <tr>
         <td><p>us_ctx</p>         </td>
         <td><p>Reserved</p>         </td>
      </tr>
      <tr>
         <td><p>idexit </p>         </td>
         <td><p>EXIT identifier</p>         </td>
      </tr>
      <tr>
         <td><p>exname</p>         </td>
         <td><p>User name that must correspond to the value of the exaref
parameter of the <strong>exfini</strong> function.</p>         </td>
      </tr>
      <tr>
         <td><p>parmexit</p>         </td>
         <td><p>User exit parameter</p>         </td>
      </tr>
      <tr>
         <td><p>version</p>         </td>
         <td><p>Exit version either V24 or higher</p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>Language used by the user program:</p>
<ul>
<li>C: C
language</li>
<li>O: COBOL</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>reserv</p>         </td>
         <td><p>Size of the user working area that must correspond to the
value of the RESERV parameter of the CFTEXIT command</p>         </td>
      </tr>
      <tr>
         <td><p>etrace</p>         </td>
         <td><p>Reserved</p>         </td>
      </tr>
      <tr>
         <td><p>waittask</p>         </td>
         <td><p>EXIT task authorized maximum inactivity time (in minutes)<br />
It must correspond to the value of the WAITTASK parameter of the CFTEXIT
command.<br />
If set to 1441, the EXIT task is permanent.</p>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>Partner local identifier </p>         </td>
      </tr>
      <tr>
         <td><p>idf </p>         </td>
         <td><p>File logical identifier</p>         </td>
      </tr>
      <tr>
         <td><p>nidf </p>         </td>
         <td><p>File network identifier</p>         </td>
      </tr>
      <tr>
         <td><p>idt</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>direct</p>         </td>
         <td><p>Transfer direction:</p>
<ul>
<li>S: Send</li>
<li>R: Receive</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>mode </p>         </td>
         <td><p>Mode</p>
<ul>
<li>R: Requester</li>
<li>S: Server</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>relance</p>         </td>
         <td><p>The possible values are:</p>
<ul>
<li>1: Restart</li>
<li>2: Do
not restart</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>prot</p>         </td>
         <td><p>Communication protocol</p>         </td>
      </tr>
      <tr>
         <td><p>prof</p>         </td>
         <td><p>PeSIT only</p>
<p>Profile</p>         </td>
      </tr>
      <tr>
         <td><p>spart</p>         </td>
         <td><p>Partner sending the file </p>         </td>
      </tr>
      <tr>
         <td><p>rpart</p>         </td>
         <td><p>Partner receiving the file</p>         </td>
      </tr>
      <tr>
         <td><p>suser</p>         </td>
         <td><p>User sending the file</p>         </td>
      </tr>
      <tr>
         <td><p>ruser</p>         </td>
         <td><p>User receiving the file</p>         </td>
      </tr>
      <tr>
         <td><p>fpassw</p>         </td>
         <td><p>Password associated with the file</p>         </td>
      </tr>
      <tr>
         <td><p>sappl</p>         </td>
         <td><p>Application sending the file</p>         </td>
      </tr>
      <tr>
         <td><p>rappl</p>         </td>
         <td><p>Application receiving the file </p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td><p>User identifier</p>         </td>
      </tr>
      <tr>
         <td><p>groupid</p>         </td>
         <td><p>Identifier of the group to which the user belongs </p>         </td>
      </tr>
      <tr>
         <td><p>exec</p>         </td>
         <td><p>Name of the end-of-transfer procedure </p>         </td>
      </tr>
      <tr>
         <td><p>fdate</p>         </td>
         <td><p>Date associated with the file </p>         </td>
      </tr>
      <tr>
         <td><p>ftime</p>         </td>
         <td><p>Time associated with the file</p>         </td>
      </tr>
      <tr>
         <td><p>fdisp</p>         </td>
         <td><p>File availability </p>         </td>
      </tr>
      <tr>
         <td><p>faction</p>         </td>
         <td><p>Action on the file </p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>Private parameter </p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>fname</p>         </td>
         <td><p>File name </p>         </td>
      </tr>
      <tr>
         <td><p>fksize</p>         </td>
         <td><p>Key size</p>         </td>
      </tr>
      <tr>
         <td><p>fkloc</p>         </td>
         <td><p>Key position </p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>Record size</p>         </td>
      </tr>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>Block size </p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>Record format </p>         </td>
      </tr>
      <tr>
         <td><p>frecfmx</p>         </td>
         <td><p>z/OS (MVS) only</p>
<p>Record extended format</p>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>File allocation size</p>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>Data code</p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>File organization</p>         </td>
      </tr>
      <tr>
         <td><p>facc</p>         </td>
         <td><p>Access method</p>         </td>
      </tr>
      <tr>
         <td><p>fsyst</p>         </td>
         <td><p>Operating system </p>         </td>
      </tr>
      <tr>
         <td><p>nfname</p>         </td>
         <td><p>File network name</p>         </td>
      </tr>
      <tr>
         <td><p>nfver</p>         </td>
         <td><p>Version </p>         </td>
      </tr>
      <tr>
         <td><p>nlrecl</p>         </td>
         <td><p>Record size </p>         </td>
      </tr>
      <tr>
         <td><p>nblksize</p>         </td>
         <td><p>Block size</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfm</p>         </td>
         <td><p>Record format</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfmx</p>         </td>
         <td><p>Extended record format (z/OS / MVS) </p>         </td>
      </tr>
      <tr>
         <td><p>nspace</p>         </td>
         <td><p>File allocation size</p>         </td>
      </tr>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>File type </p>         </td>
      </tr>
      <tr>
         <td><p>ncode</p>         </td>
         <td><p>Data code </p>         </td>
      </tr>
      <tr>
         <td><p>norg</p>         </td>
         <td><p>File organization </p>         </td>
      </tr>
      <tr>
         <td><p>nsyst</p>         </td>
         <td><p>Operating system </p>         </td>
      </tr>
      <tr>
         <td><p>ncomp</p>         </td>
         <td><p>Data compression</p>         </td>
      </tr>
      <tr>
         <td><p>fcars</p>         </td>
         <td><p>Number of bytes written </p>         </td>
      </tr>
      <tr>
         <td><p>frecs</p>         </td>
         <td><p>Number of records written </p>         </td>
      </tr>
      <tr>
         <td><p>ecars</p>         </td>
         <td><p>Number of bytes before compression and after decompression </p>         </td>
      </tr>
      <tr>
         <td><p>nrecs</p>         </td>
         <td><p>Number of records sent </p>         </td>
      </tr>
      <tr>
         <td><p>rpos</p>         </td>
         <td><p>Value of last synchronization point </p>         </td>
      </tr>
      <tr>
         <td><p>notify</p>         </td>
         <td><p>Notification </p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>User message</p>         </td>
      </tr>
      <tr>
         <td><p>ldata</p>         </td>
         <td><p>Length of data sent </p>         </td>
      </tr>
      <tr>
         <td><p>idtu</p>         </td>
         <td><p>Local transfer counter identifier</p>         </td>
      </tr>
      <tr>
         <td><p>cMode</p>         </td>
         <td><p>SSL mode Client/Server</p>         </td>
      </tr>
      <tr>
         <td><p>cAuthPolicy</p>         </td>
         <td><p>SSL auth Anonymous/Simple/Double</p>         </td>
      </tr>
      <tr>
         <td><p>bCipher</p>         </td>
         <td><p>SSL cipher suite</p>         </td>
      </tr>
      <tr>
         <td><p>sParm</p>         </td>
         <td><p>SSL command free parameters</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteUserDn</p>         </td>
         <td><p>Remote User certificate Dn</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteIssuerDn</p>         </td>
         <td><p>Remote Issuer Dn</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteCaId</p>         </td>
         <td><p>Remote CA Alias</p>         </td>
      </tr>
      <tr>
         <td><p>sUserCId</p>         </td>
         <td><p>User Certificate Alias</p>         </td>
      </tr>
      <tr>
         <td><p>sCertFname</p>         </td>
         <td><p>File including Remote certificate</p>         </td>
      </tr>
      <tr>
         <td><p>sProf</p>         </td>
         <td><p>SSL profil Id.</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteSerial</p>         </td>
         <td><p>Serial Number</p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>Free Area between all EXITs</p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>Network first sender partner name</p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>Network last receiver partner name</p>         </td>
      </tr>
      <tr>
         <td><p>XferCycleId</p>         </td>
         <td><p>CycleId of trace occurences</p>         </td>
      </tr>
      <tr>
         <td><p>XferObjectcId</p>         </td>
         <td><p>Name of the XFB transfer trace class</p>         </td>
      </tr>
   </tbody>
</table>

<span id="C_Language_structure"></span>

### C Language structure

If you want to keep an exit that was created in a version of Transfer
CFT <span style="font-weight: bold;">prior</span> to V2.4, you can continue
to use the format displayed below. The <span style="font-weight: bold;">exitdT</span>
communication structure between the interface and the user program is
defined as follows:


    typedef struct {
    union {
    struct {
    /* Structure for the C language */
    /* ... */
    } exC;
    struct {
    /* Structure for the COBOL language */
    /* ... */
    } exnC;
    } exU;
    } exitdT, *exitdTp;

If you want to create an exit using the V2.4 format <span style="font-weight: bold;">exitdnT</span>
communication structure between the interface and the user program is
defined below:


    typedef struct {
    union {
    struct {
    /* Structure for the C language */
    /* ... */
    } exC;
    struct {
    /* Structure for the COBOL language */
    /* ... */
    } exnC;
    } exU;
    } exitdnT, *exitdnTp;

The structures for the C and COBOL languages are described in <span style="font-family: 'Courier New', monospace;font-weight: bold;">exfus.h</span>
that is delivered with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> .

### COBOL language structure

If the user program is written in COBOL, you must comply with C-COBOL
interfacing rules.

The communication structure between the interface and the user program
is defined in the <span style="font-weight: bold;font-family: 'Courier New', monospace;">exfus.cop</span>
file that is delivered with the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> product.
