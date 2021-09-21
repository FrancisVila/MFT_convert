{
    "title": "SUBMIT - Submitting an end-of-transfer",
    "linkTitle": "SUBMIT - Submitting an end-of-transfer",
    "weight": "380"
}# <span id="kanchor9"></span><span id="Title"></span>SUBMIT - Submit a processing procedure

This topic describes the SUBMIT command, which is used to submit a processing procedure for a selected
transfer.

The procedure inherits the transfer context symbolic variables.

You can start, or restart, this procedure when the file or message transfer
is in the T phasestep.

This command has no effect on the transfers belonging to a broadcasting
list even if these transfers are in the T phasestep. Alternatively, it can
be applied to a generic transfer, whose PART parameter equals the broadcasting
list identifier, when it is in the T phasestep.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td><a href="appstate.htm">APPSTATE</a><![CDATA[ ]]>         </td>
         <td width="59.777%">State of the [end] phase for the processing script to restart         </td>
      </tr>
      <tr valign="top">
         <td>
            <p><a href="../../../command_summary/parameter_intro/blknum">BLKNUM</a> </p>
         </td>
         <td width="59.777%">
            <p>Catalog block number. If the values '*' or ' ' are used 
 then all transfers are selected regardless of the block that they belong 
 to.</p>
         </td>
      </tr>
      <tr valign="top">
         <td rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a>
</p>
         </td>
         <td width="59.777%">
            <p>Transfer direction for the requests in question.</p>
            <p>Possible values are:</p>
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
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/exec">EXEC</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Name of the file containing the procedure to be executed.</p>
            <p>By default, this name is the one defined by the parameters:</p>
            <ul>
               <li>EXEC 
 of the SEND/RECV command (according to the transfer direction),               </li>
               <li>or (if 
 this parameter is not defined) EXECSF or EXECRF of CFTPARM (according 
 to the transfer direction).               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ida">IDA</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Local identifier of the transfer assigned by the user or 
 user application.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Model file identifier.</p>
            <p>Several catalog entries may be associated with a given 
 IDF. There is no default value.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idu">IDT</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Transfer identifier.</p>
            <p>This identifies a transfer for a given partner. The value 
 ‘<b>*</b>’ means that no selection is required using the IDT parameter 
 (default value).</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Transfer local counter identifier. </p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>
            <p>(Mandatory)</p>
         </td>
         <td colspan="1" rowspan="1" width="59.777%">
            <p>Partner identifier.</p>
            <p>The value of this parameter can be:</p>
            <ul>
               <li><i>Identifier</i>: 
 the command only concerns the transfers with this partner               </li>
               <li><i>Mask</i>: 
 the command concerns the transfers with the partners, whose identifiers 
 correspond to this mask               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td><a href="phase.htm">PHASE</a>
         </td>
         <td width="59.777%"> Phase of a catalog entry.         </td>
      </tr>
      <tr valign="top">
         <td><a href="phasestep.htm">PHASTESTEP</a>
         </td>
         <td width="59.777%">Phase step of a catalog entry.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/scope">SCOPE</a>
         </td>
         <td width="59.777%">Scope &lt;PARENT&gt;  ('PARENT','ALL','CHILDREN').         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/state">STATE</a>
         </td>
         <td width="59.777%">Transfer request state.         </td>
      </tr>
   </tbody>
</table>

#### Example 1 - Single Transfer

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SUBMIT </p>
            <p> IDT = A1020301,</p>
            <p> IDF = file1,</p>
            <p> IDA = appli1,</p>
            <p> DIRECT = SEND,</p>
            <p> EXEC = myprog</p>
         </td>
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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTDEST</p>
            <p> IDT = list,</p>
            <p> PART = (part1, part2, part3)</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPART </p>
            <p> ID = part1, ....</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPART</p>
            <p> ID = part2, ....</p>
         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTPART </p>
            <p> ID = part3, ....</p>
         </td>
      </tr>
   </tbody>
</table>

 

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTSEND</p>
            <p> PART = list,</p>
            <p> IDF = myfile,</p>
            <p> EXEC = myprog</p>
         </td>
      </tr>
   </tbody>
</table>

The procedure myprog is executed ONCE when all the transfers
are completed.

Before the post-processing procedure is executed, the catalog
looks like this.

<table border="1" bordercolordark="#c0c0c0" bordercolorlight="#c0c0c0" cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>STATE </p>
</th>
         <th>
            <p>PART </p>
</th>
         <th>
            <p>IDF </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>SFT </p>
         </td>
         <td>
            <p>LIST </p>
         </td>
         <td>
            <p>MYFILE (generic transfer) </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SFT </p>
         </td>
         <td>
            <p>PART1 </p>
         </td>
         <td>
            <p>MYFILE </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SFT </p>
         </td>
         <td>
            <p>PART2 </p>
         </td>
         <td>
            <p>MYFILE </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>SFT </p>
         </td>
         <td>
            <p>PART3 </p>
         </td>
         <td>
            <p>MYFILE </p>
         </td>
      </tr>
   </tbody>
</table>

The post-processing procedure can be submitted again as
follows:

<table cellspacing="0" width="90%">
      <tr>
         <td colspan="3" width="12%">
            <p>SUBMIT</p>
            <p> PART = list,</p>
            <p> IDF = myfile,</p>
         </td>
      </tr>
</table>

This relates to the generic transfer. A SUBMIT command
applied to a transfer in the list (SUBMIT PART = PART1 for example) has no effect.