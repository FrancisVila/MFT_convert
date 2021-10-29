{
    "title": "About  the communication area",
    "linkTitle": "About the communication area",
    "weight": "340"
}This section describes the file exit communication area structure and describes the fields of the communication structure.

<table data-bgcolor="#FFFFFF" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Field</p></th>
         <th>            <p>Explanation</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>mtype</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Transfer stage<br />
The possible values are:</p>
            <ul>
               <li>0    
(ALLOC_TYP)   before
the file is allocated               </li>
               <li>1    
(OPEN_TYP)     before
the file is opened               </li>
               <li>2    
(TRANS_TYP)    before
the start of the transfer               </li>
               <li>3    
(DATA_TYP)      before
a record is sent or after it is received               </li>
               <li>4    
(CHECK_TYP)   after a synchronization point               </li>
               <li>5    
(RESTART_TYP) before repositioning               </li>
               <li>6    
(DTEND_TYP)    before the end of the file               </li>
               <li>7    
(CLOSE_TYP)    before the file is closed               </li>
               <li>8    
(ENDTR_TYP)    before the end of the transfer               </li>
               <li>9    
(ABORT_TYP)    after a transfer interruption                </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p><span>masc</span> </p>         </td>
         <td data-valign="top" width="83.46%">            <p>Mask for selecting stages<br />
This field comprises 16 bytes; each byte can take the value 0 or 1 and
is associated with a stage:</p>
            <ul>
               <li>Byte
0              =&gt; ALLOC_TYP               </li>
               <li>Byte
1              =&gt; OPEN_TYP               </li>
               <li>Byte
2              =&gt; TRANS_TYP               </li>
               <li>Byte
3              =&gt; DATA_TYP               </li>
               <li>Byte
4              =&gt; CHECK_TYP               </li>
               <li>Byte
5              =&gt; RESTART_TYP               </li>
               <li>Byte
6              =&gt; DTEND_TYP               </li>
               <li>Byte
7              =&gt; CLOSE_TYP               </li>
               <li>Byte
8              =&gt; ENDTR_TYP               </li>
               <li>Byte
9              =&gt; ABORT_TYP               </li>
               <li>Bytes
10 to 15 =&gt; Reserved               </li>
            </ul>
            <p>Byte 0 always equals 1.</p>
            <p>If you set a byte to 1, it means that you want to take
control during the associated stage<br />
The value of the field mtype indicates the rank of the byte associated
with the stage</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>access </p>         </td>
         <td data-valign="top" width="83.46%">            <p>File access managements under the control of:</p>
            <ul>
               <li>Transfer
CFT if set to 0<br />
<span>Transfer CFT</span> takes charge of all operations; you can, however, change
certain features of the file (name, size, format, etc.) at the allocation
and opening stages               </li>
               <li>The user
if set to 1<br />
You are responsible for all operations performed on the file: allocation,
opening, read/write, closing, de-allocation               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>retsync</p>         </td>
         <td data-valign="top" width="83.46%">            <p>The return is:</p>
            <ul>
               <li>0 : synchronous<br />
The user function processes the stage and returns control to the interface.               </li>
               <li>1: asynchronous<br />
The user function returns control to the interface before processing
the stage (deferred processing). The transfer is suspended and the interface
waits for an end of processing message from the user.               </li>
            </ul>
            <p>As the user does not yet have the information or tools
required to use the possibility of an asynchronous return, the return
will always be synchronous </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ret1</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Return code:</p>
            <ul>
               <li>0 = processing
ok               </li>
               <li>9 = refusal
and end of transfer               </li>
            </ul>
            <p>Other values are defined depending on the transfer stage.
For more information, refer to the <a href="using_file_exit_comm_area">Using
the Communication Structure</a>.</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>ret2</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Error message.<br />
This message appears in the <span>Transfer CFT</span> catalog in the DIAGP field (protocol
diagnosis).</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>us_sem</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Reserved</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>us_ctx</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Reserved</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>idexit </p>         </td>
         <td data-valign="top" width="83.46%">            <p>EXIT identifier</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>exname</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User name that must correspond to the value of the exaref
parameter of the <strong>exfini</strong> function.</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>parmexit</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User exit parameter</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>version</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Exit version either V24 or higher</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>language</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Language used by the user program:</p>
            <ul>
               <li>C: C
language               </li>
               <li>O: COBOL               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>reserv</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Size of the user working area that must correspond to the
value of the RESERV parameter of the CFTEXIT command</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>etrace</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Reserved</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>waittask</p>         </td>
         <td data-valign="top" width="83.46%">            <p>EXIT task authorized maximum inactivity time (in minutes)<br />
It must correspond to the value of the WAITTASK parameter of the CFTEXIT
command.<br />
If set to 1441, the EXIT task is permanent.</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>part</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Partner local identifier </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>idf </p>         </td>
         <td data-valign="top" width="83.46%">            <p>File logical identifier</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nidf </p>         </td>
         <td data-valign="top" width="83.46%">            <p>File network identifier</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>idt</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Transfer identifier</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>direct</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Transfer direction:</p>
            <ul>
               <li>S: Send               </li>
               <li>R: Receive               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>mode </p>         </td>
         <td data-valign="top" width="83.46%">            <p>Mode</p>
            <ul>
               <li>R: Requester               </li>
               <li>S: Server               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>relance</p>         </td>
         <td data-valign="top" width="83.46%">            <p>The possible values are:</p>
            <ul>
               <li>1: Restart               </li>
               <li>2: Do
not restart               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>prot</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Communication protocol</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>prof</p>         </td>
         <td data-valign="top" width="83.46%">            <p>PeSIT only</p>
            <p>Profile</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>spart</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Partner sending the file </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>rpart</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Partner receiving the file</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>suser</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User sending the file</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ruser</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User receiving the file</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fpassw</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Password associated with the file</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>sappl</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Application sending the file</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>rappl</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Application receiving the file </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>userid</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User identifier</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>groupid</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Identifier of the group to which the user belongs </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>exec</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Name of the end-of-transfer procedure </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fdate</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Date associated with the file </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ftime</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Time associated with the file</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fdisp</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File availability </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>faction</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Action on the file </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>state</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Transfer state</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>parm</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Private parameter </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>comment</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Comment</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>fname</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File name </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fksize</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Key size</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>fkloc</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Key position </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>flrecl</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Record size</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>fblksize</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Block size </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>frecfm</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Record format </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>frecfmx</p>         </td>
         <td data-valign="top" width="83.46%">            <p>z/OS (MVS) only</p>
            <p>Record extended format</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fspace</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File allocation size</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ftype</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File type</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fcode</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Data code</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>forg</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File organization</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>facc</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Access method</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>fsyst</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Operating system </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nfname</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File network name</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nfver</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Version </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nlrecl</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Record size </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nblksize</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Block size</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nrecfm</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Record format</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nrecfmx</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Extended record format (z/OS / MVS) </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nspace</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File allocation size</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ntype</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File type </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>ncode</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Data code </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>norg</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File organization </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nsyst</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Operating system </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ncomp</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Data compression</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>fcars</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Number of bytes written </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>frecs</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Number of records written </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>ecars</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Number of bytes before compression and after decompression </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nrecs</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Number of records sent </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>rpos</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Value of last synchronization point </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>notify</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Notification </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>msg</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User message</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>ldata</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Length of data sent </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>idtu</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Local transfer counter identifier</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>cMode</p>         </td>
         <td data-valign="top" width="83.46%">            <p>SSL mode Client/Server</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>cAuthPolicy</p>         </td>
         <td data-valign="top" width="83.46%">            <p>SSL auth Anonymous/Simple/Double</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>bCipher</p>         </td>
         <td data-valign="top" width="83.46%">            <p>SSL cipher suite</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>sParm</p>         </td>
         <td data-valign="top" width="83.46%">            <p>SSL command free parameters</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>sRemoteUserDn</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Remote User certificate Dn</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>sRemoteIssuerDn</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Remote Issuer Dn</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>sRemoteCaId</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Remote CA Alias</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>sUserCId</p>         </td>
         <td data-valign="top" width="83.46%">            <p>User Certificate Alias</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>sCertFname</p>         </td>
         <td data-valign="top" width="83.46%">            <p>File including Remote certificate</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>sProf</p>         </td>
         <td data-valign="top" width="83.46%">            <p>SSL profil Id.</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>sRemoteSerial</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Serial Number</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>ExitFree</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Free Area between all EXITs</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>nspart</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Network first sender partner name</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>nrpart</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Network last receiver partner name</p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="16.54%">            <p>XferCycleId</p>         </td>
         <td data-valign="top" width="83.46%">            <p>CycleId of trace occurences</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="16.54%">            <p>XferObjectcId</p>         </td>
         <td data-valign="top" width="83.46%">            <p>Name of the XFB transfer trace class</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="C_Language_structure"></span>C Language structure

If you want to keep an exit that was created in a version of Transfer
CFT prior to V2.4, you can continue
to use the format displayed below. The exitdT
communication structure between the interface and the user program is
defined as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>typedef struct {<br />
union {<br />
struct {<br />
/* Structure for the C language */<br />
/* ... */<br />
} exC;<br />
struct {<br />
/* Structure for the COBOL language */<br />
/* ... */<br />
} exnC;<br />
} exU;<br />
} exitdT, *exitdTp;         </td>
      </tr>
   </tbody>
</table>

If you want to create an exit using the V2.4 format exitdnT
communication structure between the interface and the user program is
defined below:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>typedef struct {<br />
union {<br />
struct {<br />
/* Structure for the C language */<br />
/* ... */<br />
} exC;<br />
struct {<br />
/* Structure for the COBOL language */<br />
/* ... */<br />
} exnC;<br />
} exU;<br />
} exitdnT, *exitdnTp;         </td>
      </tr>
   </tbody>
</table>

The structures for the C and COBOL languages are described in exfus.h
that is delivered with Transfer CFT .

### COBOL language structure

If the user program is written in COBOL, you must comply with C-COBOL
interfacing rules.

The communication structure between the interface and the user program
is defined in the exfus.cop
file that is delivered with the Transfer CFT product.
