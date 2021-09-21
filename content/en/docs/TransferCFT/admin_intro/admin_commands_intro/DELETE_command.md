{
    "title": "DELETE - Deleting catalog entries",
    "linkTitle": "DELETE - Deleting catalog entries",
    "weight": "310"
}# <span id="kanchor3"></span><span id="Title"></span>DELETE - Delete catalog entries

The DELETE command is used to <span id="delete_command"></span>delete one
or more catalog entries. A transfer in process is interrupted and its
transfer request disappears from the catalog.

This file is automatically deleted for an R, Receive, type request in
non terminated state, a state other than T and X, if the receive file
is a temporary file.

For any selected set of transfers, transfers are processed in batches
of 20 transfers every 5 seconds.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Description</th>
<th colspan="2">Use this command to delete one or more catalog entries.</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="13">
            <p>Parameters</p>
         </td>
         <td>
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/blknum">BLKNUM</a> </p>
         </td>
         <td>
            <p>Block number. If the values '*' or ' ' are used then all 
 transfers are selected regardless of the block that they belong to.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/direct">DIRECT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer direction for the requests in question.</p>
            <p>The possible values are:</p>
            <ul>
               <li>BOTH: 
 (default) takes both send transfers and receive transfers into account               </li>
               <li>RECV: 
 limits the action to receive transfers               </li>
               <li>SEND: 
 limits the action to send transfers               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ida">IDA</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of the transfer assigned by the user or 
 user application. The maximum length is 64 characters.</p>
            <p>Several catalog entries may be associated with a given 
 IDA. There is no default value.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idf">IDF</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Model file identifier.</p>
            <p>Several catalog entries may be associated with a given 
 IDF. There is no default value.</p>
            <p>If a set of transfers is selected, transfers are processed 
 in batches of 20 every 5 seconds.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idu">IDT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer identifier.</p>
            <p>This identifies a transfer for a given partner and direction. 
 The value ‘*’ means that no selection is required using the IDT 
 parameter (default value).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idtu">IDTU</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer local counter identifier. </p>
         </td>
      </tr>
      <tr>
         <td><a href="kdate.htm">KDATE</a>
         </td>
         <td>Command deposit date         </td>
      </tr>
      <tr>
         <td><a href="ktime.htm">KTIME</a>
         </td>
         <td>Command deposit time         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a>
</p>
            <p>(Mandatory)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner identifier.</p>
         </td>
      </tr>
      <tr>
         <td><a href="phase.htm">PHASE</a>
         </td>
         <td>Phase of a catalog entry         </td>
      </tr>
      <tr>
         <td><a href="phasestep.htm">PHASESTEP</a>
         </td>
         <td>Phase step of a catalog entry         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/scope">SCOPE</a>
         </td>
         <td> Scope &lt;PARENT&gt;  ('PARENT','ALL','CHILDREN')         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/state">STATE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer state.</p>
            <p>The default value * means no selection is required 
 to be made on the transfer state. (refer 
 to the Transfer-related successive phases and actions).</p>
         </td>
      </tr>
      <tr>
         <td colspan="3" rowspan="1">
            <p>Example 1</p>
<div>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
</div>
            <p>This command deletes all transfers, IDT = * by default, in the send 
 and receive directions, DIRECT = BOTH by default, for the partners whose 
 identifier begins with "SIE" and contains 5 characters in all.</p>
            <p>Example 2</p>
<div>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
</div>
            <p>This command deletes all transfers, IDT = * by default, in the send 
 direction (DIRECT = SEND) of the model file ACCNT to the partner HQ.</p>
         </td>
      </tr>
   </tbody>
</table>
