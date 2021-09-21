{
    "title": "Define the target",
    "linkTitle": "Define the target",
    "weight": "280"
}The following tables describe the parameters available in flow definition, target side.

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
         <td>Transfer state         </td>
         <td>Ready: default , <br/>On hold,<br/>Kept         </td>
         <td>CFTRECV, state<br/><br/>Ready (D) -&gt; DISP <br/>On hold (H) -&gt;HOLD <br/>Kept (K) -&gt;KEEP         </td>
         <td>Indicates the state of the transfer request.: Ready, On Hold, Kept<br/>Field is available in UI only if the Initiator is the target.<br/>If Source is the initiator, in Target side the transfer state is ready and the field cannot be configured in CG UI.         </td>
      </tr>
      <tr>
         <td>User id         </td>
         <td>string, max 32, empty by default         </td>
         <td>CFTRECV, userid         </td>
         <td>Identifier of the transfer owner. If this parameter is not defined, its default value is the system "userid" of the <span>Transfer CFT</span>.         </td>
      </tr>
      <tr>
         <td>Detect duplicate transfers         </td>
         <td>string max 512, empty by default         </td>
         <td>CFTRECV, duplicat         </td>
         <td>This field is used in detecting duplicate transfers and may contain a list of symbolic variables separated by a period ".".         </td>
      </tr>
      <tr>
         <td>No file exists         </td>
         <td>Create: default,<br/>Cancel         </td>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>Specifies the action taken if the received file does not already exist.<br/>Create – The file is created.<br/>Cancel – The transfer is refused.         </td>
      </tr>
      <tr>
         <td>File exists         </td>
         <td>Delete: default,<br/>Cancel,<br/>Overwrite, Overwrite only if empty         </td>
         <td>
            <p>CFTRECV</p>
         </td>
         <td>Specifies the action taken if the received file exists.<br/>Delete – The existing file is deleted.<br/>Cancel – The transfer is refused.<br/>Overwrite – The existing file is overwritten.<br/>Overwrite only if empty – The existing file is overwritten only if it contains no data.         </td>
      </tr>
      <tr>
         <td>Aborted transfer         </td>
         <td>Keep: Default,<br/>Delete         </td>
         <td>CFTRECV, rkerror         </td>
         <td>Specifies the action taken if a transfer is terminated due to a file creation error on the target.<br/>Keep – The transfer remains in the transfer list.<br/>Delete – The transfer is removed from the transfer list.         </td>
      </tr>
      <tr>
         <td>Delete file on purge         </td>
         <td>Ready (D) ,<br/>Transferring (C), On Hold (H), <br/>Kept (K), Transferred (T), Executed (X) default: no selection         </td>
         <td>CFTRECV, fdelete<br/><br/>Ready (D) -&gt;D <br/>Transferring (C) -&gt; C <br/>On Hold (H) -&gt; H <br/>Kept (K) -&gt; K <br/>Transferred (T) -&gt; T <br/>Executed (X) -&gt; X         </td>
         <td>Indicates the transfer states of files that will be deleted when you remove the associated transfers from the transfer list or when you purge the transfer list. You can select any combination of statuses. If you do not select anything, files are not deleted even when the associated transfers are removed from the transfer list.<br/>Ready – The transfer is available and can start immediately. <br/>Transferring – The transfer is being executed.<br/>On hold – The transfer was interrupted due to an error, such as a network failure, or by a user.<br/>Kept – The transfer was suspended by <span>Transfer CFT</span> or by a user.<br/>Transferred – The transfer was successfully completed.<br/>Executed – The transfer was ended by an application or user.         </td>
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
         <th>CG parameter</th>
         <th>CG values</th>
         <th>CFTUTIL‑parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Filename         </td>
         <td>string max 64,<br/>Default value: pub\&amp;IDF.&amp;IDTU.&amp;FROOT.RCV         </td>
         <td>CFTRECV, fname         </td>
         <td>Specify the file name or full path name for the received file or files. This field is required if the initiator of the flow is the source. Default value: pub\&amp;IDF.&amp;IDTU.&amp;FROOT.RCV         </td>
      </tr>
      <tr>
         <td>Temporary file         </td>
         <td>string max 64         </td>
         <td>CFTRECV, wfname         </td>
         <td>Specify the name of the temporary file used during the transfer. When the transfer is complete, the temporary file is renamed using the name defined in the Filename field. If you do not specify a value, <span>Transfer CFT</span> directly creates the file with the name specified in the Filename field.         </td>
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
         <td>CFTRECV, fcode =B         </td>
         <td>Specify whether the file is a binary file.         </td>
      </tr>
      <tr>
         <td>Text         </td>
         <td>
            <p>CFTRECV, see  configuration for FTYPE=TEXT</p>
         </td>
         <td>Specify whether the file is a text file.         </td>
      </tr>
      <tr>
         <td>Record format         </td>
         <td>
            <p>CFTRECV, see  configuration for record format</p>
         </td>
         <td>Indicate whether the records in the file are fixed or variable length.         </td>
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
         <th>CG parameter</th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTRECV, exec         </td>
         <td>Specify the script to be executed after the file is received.         </td>
      </tr>
      <tr>
         <td>Apply to group of files         </td>
         <td>On main request: Default, <br/>For each file in group,<br/>Both          </td>
         <td>CFTRECV, execsub<br/>On main request -&gt; LIST<br/>For each file in group -&gt; FILE <br/>Both -&gt; SUBF         </td>
         <td>This field is displayed if you enabled a broadcast list in source transfer properties.<br/>Values – On main request | For each target in the list | Both<br/>On main request – Executes the script only on the main request.<br/>For each target in the list – Executes the script only for each target in the list.<br/>Both – Executes the script both for the main request and for each target in the list.         </td>
      </tr>
      <tr>
         <td>Apply to collect list         </td>
         <td>On main request: default,<br/>For each source in the list,<br/>Both         </td>
         <td>CFTDEST, exec<br/><br/>On main request -&gt; DEST For each source in the list -&gt; CHILDREN<br/>Both -&gt; PART         </td>
         <td>This field is displayed if you enabled a collect list in target transfer properties.<br/>On main request – Executes the script only on the main request.<br/>For each source in the list – Executes the script only for each source in the list.<br/>Both – Executes the script both for the main request and for each source in the list.         </td>
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
         <th>CG parameter</th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTRECV, ackexec         </td>
         <td>Specify the script to be executed after the file is received and post-processing is complete.         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>Require,<br/>Ignore: default         </td>
         <td>CFTRECV, ackstate<br/>Require -&gt; REQUIRE <br/>Ignore -&gt; IGNORE          </td>
         <td>Indicate if the transfer must wait for an acknowledgement.<br/>Require – The transfer must wait for an acknowledgement before it can be considered complete.<br/>Ignore – The transfer can be considered complete, even if an acknowledgement is not received.         </td>
      </tr>
      <tr>
         <td>Apply to collect list         </td>
         <td>On main request: default,<br/>For each source in the list,<br/>Both         </td>
         <td>CFTDEST, execa<br/><br/>On main request -&gt; DEST For each source in the list -&gt; CHILDREN<br/>Both -&gt; PART         </td>
         <td>This field is displayed if you enabled a collect list in target transfer properties.<br/>On main request – Executes the script only on the main request.<br/>For each source in the list – Executes the script only for each source in the list.<br/>Both – Executes the script both for the main request and for each source in the list.         </td>
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
         <th>CG parameter</th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Script -&gt; Filename         </td>
         <td>if Custom, Filename field: string of max 512c         </td>
         <td>CFTRECV, exece         </td>
         <td>Specify the script to be executed if an error occurs when a file is received.         </td>
      </tr>
   </tbody>
</table>

 

&lt;&lt; [My first transfer flow](../../)
