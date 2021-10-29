{
    "title": "SUBMIT  - Submit a processing procedure",
    "linkTitle": "SUBMIT - Submitting an end-of-transfer",
    "weight": "380"
}This topic describes the SUBMIT command, which is used to submit a processing procedure for a selected
transfer.

The procedure inherits the transfer context symbolic variables.

You can start, or restart, this procedure when the file or message transfer
is in the T phasestep.

This command has no effect on the transfers belonging to a broadcasting
list even if these transfers are in the T phasestep. Alternatively, it can
be applied to a generic transfer, whose PART parameter equals the broadcasting
list identifier, when it is in the T phasestep.

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td>APPSTATE         </td>
         <td width="59.777%">State of the [end] phase for the processing script to restart         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/blknum">BLKNUM</a> </p>         </td>
         <td width="59.777%">            <p>Catalog block number. If the values '*' or ' ' are used
then all transfers are selected regardless of the block that they belong
to.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/direct">DIRECT</a></p>         </td>
         <td width="59.777%">            <p>Transfer direction for the requests in question.</p>
            <p>Possible values are:</p>
            <ul>
               <li>BOTH:
(default) takes both send transfers and receive transfers into account               </li>
               <li>RECV:
limits the action to receive transfers               </li>
               <li>SEND:
limits the action to send transfers               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/exec">EXEC</a> </p>         </td>
         <td width="59.777%">            <p>Name of the file containing the procedure to be executed.</p>
            <p>By default, this name is the one defined by the parameters:</p>
            <ul>
               <li>EXEC
of the SEND/RECV command (according to the transfer direction),               </li>
               <li>or (if
this parameter is not defined) EXECSF or EXECRF of CFTPARM (according
to the transfer direction).               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/ida">IDA</a> </p>         </td>
         <td width="59.777%">            <p>Local identifier of the transfer assigned by the user or
user application.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idf">IDF</a> </p>         </td>
         <td width="59.777%">            <p>Model file identifier.</p>
            <p>Several catalog entries may be associated with a given
IDF. There is no default value.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idu">IDT</a> </p>         </td>
         <td width="59.777%">            <p>Transfer identifier.</p>
            <p>This identifies a transfer for a given partner. The value
‘<strong>*</strong>’ means that no selection is required using the IDT parameter
(default value).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idtu">IDTU</a> </p>         </td>
         <td width="59.777%">            <p>Transfer local counter identifier.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/part">PART</a> </p>
            <p>(Mandatory)</p>         </td>
         <td width="59.777%">            <p>Partner identifier.</p>
            <p>The value of this parameter can be:</p>
            <ul>
               <li><em>Identifier</em>:
the command only concerns the transfers with this partner               </li>
               <li><em>Mask</em>:
the command concerns the transfers with the partners, whose identifiers
correspond to this mask               </li>
            </ul>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>PHASE         </td>
         <td width="59.777%">Phase of a catalog entry.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>PHASTESTEP         </td>
         <td width="59.777%">Phase step of a catalog entry.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td><a href="../../command_summary/parameter_intro/scope">SCOPE</a>         </td>
         <td width="59.777%">Scope &lt;PARENT&gt; ('PARENT','ALL','CHILDREN').         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td><a href="../../command_summary/parameter_intro/state">STATE</a>         </td>
         <td width="59.777%">Transfer request state.         </td>
      </tr>
   </tbody>
</table>

#### Example 1 - Single Transfer

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>SUBMIT</p>
            <p> IDT = A1020301,</p>
            <p> IDF = file1,</p>
            <p> IDA = appli1,</p>
            <p> DIRECT = SEND,</p>
            <p> EXEC = myprog</p>         </td>
      </tr>
   </tbody>
</table>

The procedure defined in the file "myprog" is
submitted.

This procedure inherits the values of the parameters of
the transfer selected by the SUBMIT command. This provides the possibility
of substituting the symbolic variables which may have been used in the
procedure submitted.

#### Example 2 - Broadcast list

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTDEST</p>
            <p> IDT = list,</p>
            <p> PART = (part1, part2, part3)</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART</p>
            <p> ID = part1, ....</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART</p>
            <p> ID = part2, ....</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTPART</p>
            <p> ID = part3, ....</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSEND</p>
            <p> PART = list,</p>
            <p> IDF = myfile,</p>
            <p> EXEC = myprog</p>         </td>
      </tr>
   </tbody>
</table>

The procedure myprog is executed ONCE when all the transfers
are completed.

Before the post-processing procedure is executed, the catalog
looks like this.

<table data-border="1" data-bordercolordark="#c0c0c0" data-bordercolorlight="#c0c0c0" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>STATE </p></th>
         <th>            <p>PART </p></th>
         <th>            <p>IDF </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>SFT </p>         </td>
         <td>            <p>LIST </p>         </td>
         <td>            <p>MYFILE (generic transfer) </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SFT </p>         </td>
         <td>            <p>PART1 </p>         </td>
         <td>            <p>MYFILE </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SFT </p>         </td>
         <td>            <p>PART2 </p>         </td>
         <td>            <p>MYFILE </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SFT </p>         </td>
         <td>            <p>PART3 </p>         </td>
         <td>            <p>MYFILE </p>         </td>
      </tr>
   </tbody>
</table>

The post-processing procedure can be submitted again as
follows:

<table data-cellspacing="0" width="90%">
   <colgroup>      
         <col style="width: 33%" />
         <col style="width: 33%" />
         <col style="width: 33%" />
   </colgroup>
   <tbody>
      <tr class="odd">
         <td colspan="3" width="12%">            <p>SUBMIT</p>
            <p>PART = list,</p>
            <p>IDF = myfile,</p>         </td>
      </tr>
   </tbody>
</table>

This relates to the generic transfer. A SUBMIT command
applied to a transfer in the list (SUBMIT PART = PART1 for example) has no effect.
