{
    "title": "Define the source",
    "linkTitle": "Define the source",
    "weight": "270"
}The following tables describe the parameters available for the source side of a flow definition.

## Transfer properties

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>CG parameter</th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Transfer priority         </td>
         <td>LOW, <br/>MEDIUM: default, <br/>HIGH, <br/>CUSTOM         </td>
         <td>CFTSEND, pri<br/><br/>LOW -&gt;0 <br/>MEDIUM-&gt;128 <br/>HIGH-&gt; 255 <br/>CUSTOM-&gt; integer between 0...255         </td>
         <td>Transfer priorities are equivalent to integer values ranging from 0 (low) to 255 (high).<br/>When <span>Transfer CFT</span> reaches the maximum number of transfers allowed, it queues transfers. When an ongoing transfer is finished and a slot is available for a new transfer, the system selects the one with the highest priority.<br/>The same priority is used for the transfer in target side         </td>
      </tr>
      <tr>
         <td>Bandwidth allocation         </td>
         <td>LOW , <br/>MEDIUM : default, HIGH         </td>
         <td>CFTSEND, cos<br/>LOW -&gt;0 <br/>MEDIUM-&gt;1 <br/>HIGH-&gt; 2         </td>
         <td>The amount of bandwidth allocated to this flow. The value you select determines the data transfer rate for this flow.<br/>The same Bandwidth allocation is used for the transfer in target side         </td>
      </tr>
      <tr>
         <td>Transfer state         </td>
         <td>Ready: default , <br/>On hold,<br/> Kept         </td>
         <td>CFTSEND, state<br/><br/>Ready (D) -&gt; DISP <br/>On hold (H) -&gt;HOLD <br/>Kept (K) -&gt;KEEP         </td>
         <td>Indicates the state of the transfer request.: Ready, On Hold, Kept.<br/>Field is available in UI only if the Initiator is the source.<br/>If Target is the initiator, in source side the transfer state is ready and the field cannot be configured in CG UI.<br/>         </td>
      </tr>
      <tr>
         <td>User id         </td>
         <td>string, max 32, empty by default         </td>
         <td>
            <p>CFTSEND, userid</p>
         </td>
         <td>Identifier of the transfer owner. If this parameter is not defined, its default value is the system "userid" of the <span>Transfer CFT</span>.         </td>
      </tr>
      <tr>
         <td>Detect duplicate transfers         </td>
         <td>string max 512, empty by default         </td>
         <td>CFTSEND, duplicat         </td>
         <td>This field is used in detecting duplicate transfers and may contain a list of symbolic variables separated by a period ".".         </td>
      </tr>
      <tr>
         <td>Compress file         </td>
         <td>Yes: default, <br/>No          </td>
         <td>CFTSEND, comp<br/><br/>Yes → 15<br/>No → 0         </td>
         <td>Indicates whether files are compressed before they are transferred. <br/>Same value will be used for the compression on target side         </td>
      </tr>
      <tr>
         <td>On file modification         </td>
         <td>Continue transfer: default,  <br/>Stop transfer         </td>
         <td>CFTSEND , fdisp<br/>Continue transfer -&gt; SHR<br/> Stop transfer-&gt; CHECK         </td>
         <td>Available only in source side.<br/>Specify what happens if files are modified during the transfer.         </td>
      </tr>
      <tr>
         <td>Action after transfer         </td>
         <td>Delete file ,<br/>Delete file content, <br/>None: default         </td>
         <td>CFTSEND, faction<br/><br/>Delete file -&gt; Delete <br/>Delete file content -&gt; Erase <br/>None-&gt; None: default         </td>
         <td>Specifies what happens to the file in source side when the transfer is complete.<br/>Delete file – Deletes the file.<br/>Delete file content – Removes the contents of the file but leaves the "end of file" mark at the beginning of the file.<br/>None – No action is performed on the file.         </td>
      </tr>
      <tr>
         <td>Delete file on purge         </td>
         <td>Ready (D) ,<br/>Transferring (C), On Hold (H), <br/>Kept (K), Transferred (T), Executed (X) default: no selection         </td>
         <td>CFTSEND, fdelete<br/><br/>Ready (D) -&gt;D <br/>Transferring (C) -&gt; C <br/>On Hold (H) -&gt; H <br/>Kept (K) -&gt; K <br/>Transferred (T) -&gt; T <br/>Executed (X) -&gt; X         </td>
         <td>Indicates the transfer states of files that will be deleted when you remove the associated transfers from the transfer list or when you purge the transfer list. You can select any combination of statuses. If you do not select anything, files are not deleted even when the associated transfers are removed from the transfer list.<br/>Ready – The transfer is available and can start immediately. <br/>Transferring – The transfer is being executed.<br/>On hold – The transfer was interrupted due to an error, such as a network failure, or by a user.<br/>Kept – The transfer was suspended by <span>Transfer CFT</span> or by a user.<br/>Transferred – The transfer was successfully completed.<br/>Executed – The transfer was ended by an application or user.         </td>
      </tr>
      <tr>
         <td>Additional information         </td>
         <td>string max 512, empty by default         </td>
         <td>CFTSEND, parm         </td>
         <td>Use this field for any information you want to provide.         </td>
      </tr>
   </tbody>
</table>

## File properties &gt; files

Indicates whether you are sending a single file or multiple files.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            CG parameter                        </th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Single - &gt; Path         </td>
         <td>string max 64         </td>
         <td>CFTSEND, fname         </td>
         <td>Indicate the single file to be sent.         </td>
      </tr>
      <tr>
         <td>Multiple -&gt; Path         </td>
         <td>string max 64         </td>
         <td>CFTSEND, fname         </td>
         <td>If you selected Multiple, the value you enter can be:<br/>A directory name – All the files in this directory will be transferred.<br/>A generic file name, including wildcard characters – Only files that match are transferred. For example, mydirectory/toto*.         </td>
      </tr>
      <tr>
         <td>Multiple -&gt; File list         </td>
         <td>string max 64         </td>
         <td>CFTSEND, selfname         </td>
         <td>This field is displayed if you selected Multiple in the Files field.<br/>Specify the name of the file that contains the list of files to be transferred. This file is also referred to as an indirection file. It must contain one file name per record, and that name must start in the first column of the file. The file names contained in the file must not contain an asterisk (*).<br/>When specifying a file here, the Path field is also required.         </td>
      </tr>
      <tr>
         <td>Multiple -&gt; Archive name         </td>
         <td>string max 64,<br/>&amp;IDF.&amp;idtu.rcv         </td>
         <td>CFTSEND, wfname         </td>
         <td>Name of the file that contains the set of files to be transmitted. Archive files are sent between systems that have the same operating system (grouped mode). The archive file is created automatically by <span>Transfer CFT</span> at the time of the transfer. The file created will be a zip file on Windows systems and a tar file on Linux/UNIX systems. Because Windows systems do not have default compression utilities, <span>Transfer CFT</span> for Windows includes zip and unzip utilities.         </td>
      </tr>
      <tr>
         <td>File name sent         </td>
         <td>string max 64         </td>
         <td>CFTSEND, nfname         </td>
         <td>Specify the name of the physical file that is to be used during transmission over the network.         </td>
      </tr>
      <tr>
         <td>Signature file         </td>
         <td>string max 64         </td>
         <td>CFTSEND, sigfname         </td>
         <td>Specify a file name that contains multiple signatures. The signatures in this file must conform to the format &lt;signature_path&gt; where path is the file path specified in the Path field.         </td>
      </tr>
   </tbody>
</table>

## File properties &gt; file type

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>CG parameter</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Binary          </td>
         <td>CFTSEND, fcode =B         </td>
         <td>Specify whether the file is a binary file.         </td>
      </tr>
      <tr>
         <td>Text         </td>
         <td>
            <p>CFTSEND, see  configuration for FTYPE=TEXT</p>
         </td>
         <td>Specify whether the file is a text file.         </td>
      </tr>
      <tr>
         <td>Record format         </td>
         <td>
            <p>CFTSEND, see  configuration for record format</p>
         </td>
         <td>Indicate whether the records in the file are fixed or variable length.         </td>
      </tr>
   </tbody>
</table>

## Processing scripts &gt; pre-processing

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            CG parameter                        </th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTSEND, preexec         </td>
         <td>Specify the script to be executed before the file is transferred.         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>Ready: default,<br/>On hold         </td>
         <td>CFTSEND, prestate<br/>Ready -&gt;DISP : default <br/>On hold -&gt; HOLD         </td>
         <td>Indicate the status of the transfer on the source. The script is run only if the transfer is in the specified state.<br/>Ready – Indicates that the transfer is available and can start immediately.<br/>On hold – Indicates that the transfer is deferred until a remote receive request is accepted, or until a local START command changes this transfer to the ready state.         </td>
      </tr>
      <tr>
         <td>Apply to broadcast list         </td>
         <td>On main request: default,<br/>For each target in the list,<br/>Both         </td>
         <td>CFTDEST, execpre<br/><br/>On main request -&gt; DEST For each target in the list -&gt; CHILDREN<br/>Both -&gt; PART         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
   </tbody>
</table>

## Processing scripts &gt; post-processing

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            CG parameter                        </th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTSEND, exec         </td>
         <td>Specify the script to be executed after the file is transferred.         </td>
      </tr>
      <tr>
         <td>Apply to group of files         </td>
         <td>On main request: Default, <br/>For each file in group,<br/>Both          </td>
         <td>CFTSEND, execsub<br/>On main request -&gt; LIST<br/>For each file in group -&gt; FILE <br/>Both -&gt; SUBF         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>Values – On main request | For each target in the list | Both<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
      <tr>
         <td>Apply to broadcast list         </td>
         <td>On main request: default,<br/>For each target in the list,<br/>Both         </td>
         <td>CFTDEST, exec<br/><br/>On main request -&gt; DEST For each target in the list -&gt; CHILDREN<br/>Both -&gt; PART         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
   </tbody>
</table>

## Processing scripts &gt; acknowledgment

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            CG parameter                        </th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTSEND, ackexec         </td>
         <td>Specify the script to be executed after an acknowledgement is received for a sent file.         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>Require,<br/>Ignore: default         </td>
         <td>CFTSEND, ackstate<br/>Require -&gt; REQUIRE <br/>Ignore -&gt; IGNORE          </td>
         <td>Indicate if the transfer must wait for an acknowledgement.<br/>Require – The transfer must wait for an acknowledgement before it can be considered complete.<br/>Ignore – The transfer can be considered complete, even if an acknowledgement is not received.         </td>
      </tr>
      <tr>
         <td>Apply to group of files         </td>
         <td>On main request, <br/>For each file in group,<br/>Both: default          </td>
         <td>CFTSEND, execsub<br/>On main request -&gt; LIST<br/>For each file in group -&gt; FILE <br/>Both -&gt; SUBF         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>Values – On main request | For each target in the list | Both<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
      <tr>
         <td>Apply to broadcast list         </td>
         <td>On main request: default,<br/>For each target in the list,<br/>Both         </td>
         <td>CFTDEST, execa<br/><br/>On main request -&gt; DEST For each target in the list -&gt; CHILDREN<br/>Both -&gt; PART         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
   </tbody>
</table>

## Processing scripts &gt; error

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
                            CG parameter                        </th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTSEND, exece         </td>
         <td>Specify the script to be executed after an error occurs during a transfer.         </td>
      </tr>
   </tbody>
</table>

 

&lt;&lt; [My first transfer flow](../../)
