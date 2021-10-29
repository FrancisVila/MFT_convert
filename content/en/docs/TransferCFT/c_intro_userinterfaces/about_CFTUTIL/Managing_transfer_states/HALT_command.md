{
    "title": "HALT- Interrupt transfers ",
    "linkTitle": "HALT - Halting a transfer",
    "weight": "330"
}This command is used to suspend one or all the send and/or receive transfers,
with the partners selected.

The transfers halted are set to the H phasestep in the catalog. They can
be reactivated:

-   By an operator
    START command
-   On receiving a
    transfer reactivation request from the partner

See also [LISTCAT.](../monitoring_cftutil_intro/listcat_command)

Transfer CFT ensures the integrity of the data in case of interruption
and, depending on the protocol used, authorizes the restarting of the
transfer from the last synchronization point set before the interruption,
or simply from the beginning of the file.

You can use the HALT command to interrupt a transfer on Transfer CFT.
This interruption changes the entry to the H phasestep. Alternatively, the
KEEP command changes the entry to the K phasestep.

An accidental halt due to a network incident, a protocol error or a
software or hardware interrupt, makes the entry change to the H, K, or
D phasestep, with the diagnostic codes specifying the origin. For more information
refer to the Transfer CFT *[Codes,
Diagnostics and Messages](../../../troubleshoot_intro/messages_and_error_codes_start_here)* topics.

*In requester mode*, a transfer in
the D state (phase T and phasestep D) is automatically restarted. A transfer in the K or H phasestep
must be manually restarted by a START command.

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/blknum">BLKNUM</a></p>         </td>
         <td width="59.777%">            <p>Catalog block number. If the values '*' or ' ' are used
then all transfers are selected regardless of the block that they belong
to.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/direct">DIRECT</a> </p>         </td>
         <td width="59.777%">            <p>Transfer direction for the requests in question.</p>
            <p>The possible values are:</p>
            <ul>
               <li>BOTH:
(default) takes both send transfers and receive transfers into account,               </li>
               <li>RECV:
limits the action to receive transfers,               </li>
               <li>SEND:
limits the action to send transfers.               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/ida">IDA</a> </p>         </td>
         <td width="59.777%">            <p>Local identifier of the transfer assigned by the user or
user application. The maximum length is 64 characters.</p>
            <p>Several catalog entries may be associated with a given
IDA. There is no default value.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idf">IDF</a> </p>         </td>
         <td width="59.777%">            <p>Model file identifier.</p>
            <p>Several catalog entries may be associated with a given
IDF. There is no default value.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idu">IDT</a> </p>         </td>
         <td width="59.777%">            <p>Transfer identifier.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/idtu">IDTU</a> </p>         </td>
         <td width="59.777%">            <p>Transfer local counter identifier.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td><a href="../../command_summary/parameter_intro/state">STATE</a>         </td>
         <td width="59.777%">Transfer request state         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>KDATE         </td>
         <td width="59.777%">Command deposit date         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>KTIME         </td>
         <td width="59.777%">Command deposit time         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>PHASE         </td>
         <td width="59.777%">Phase of a catalog entry         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>PHASESTEP         </td>
         <td width="59.777%">Phase step of a catalog entry         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td><a href="../../command_summary/parameter_intro/scope">SCOPE</a>         </td>
         <td width="59.777%">Scope &lt;PARENT&gt; ('PARENT','ALL','CHILDREN')         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>DIAGC         </td>
         <td width="59.777%">Complimentary diagnostic information         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td><a href="../../command_summary/parameter_intro/diagp">DIAGP</a>         </td>
         <td width="59.777%">Protocol diagnostic code         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../command_summary/parameter_intro/part">PART</a> </p>
            <p>(Mandatory)</p>         </td>
         <td width="59.777%">            <p>Partner identifier.</p>
            <p>The associated value of this parameter can be:</p>
            <ul>
               <li><em>identifier</em>:
the command only concerns the transfers with this partner               </li>
               <li><em>mask</em>:
the command concerns the transfers with the partners, whose identifiers
correspond to this mask               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

Halt the send transfer of the ACCNT model file for the
partner HQ.

#### Example 1

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>HALT PART = *         </td>
      </tr>
   </tbody>
</table>

This command halts all transfers (IDT = \* by default) in the send and
receive directions (DIRECT = BOTH by default), for all the partners.

#### Example 2

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>HALT</p>
            <p> PART = HQ,</p>
            <p> DIRECT = SEND,</p>
            <p> IDF = ACCNT</p>         </td>
      </tr>
   </tbody>
</table>

This command Halts the send transfer of the ACCNT model file for the
partner HQ.

## Modify transfer entry parameters

The following tables describes the parameters used to modify a transfer entry in the catalog.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Command</th>
         <th>Parameter</th>
         <th>Value</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td rowspan="2">HALT         </td>
         <td>DIAGC         </td>
         <td>string         </td>
         <td>Specify a comment.         </td>
      </tr>
      <tr class="even">
         <td>DIAGP         </td>
         <td>string         </td>
         <td>Specify a comment.         </td>
      </tr>
   </tbody>
</table>
