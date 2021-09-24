{
    "title": "END - Change transfer state",
    "linkTitle": "END - Change transfer state",
    "weight": "320"
}You can use the END command to declare
that the processing script
(pre, post, or acknowledgement) was executed correctly. More specifically, if there is an associated processing procedure, the PREEXEC, EXEC, ACKEXEC parameters of the CFTPARM,CFTSEND/SEND and CFTRECV/RECV commands are executed.

Typically, you submit the END command to Transfer CFT via a processing procedure(s). You can, however, submit it manually. After the END command is executed, once transfers are in the C phasestep the associated
catalog entry changes to the next phase. See [About phase and phasestep](../../../../concepts/phase_and_phasestep) for details on transfer work flows.

## END parameters

There are two categories of parameters that you can use with the END command, those that you can use to select transfers, and those that you use to modify the catalog entry. Parameters that have an affect on the transfer entry in the catalog are listed in the **Modify in catalog** column. All others are parameters are related to the transfers as described in **Select for transfers** only.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Select for transfers </th>
         <th>Modify  in catalog </th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/appcycid">APPCYCID</a>
         </td>
         <td>Modify the processing cycle identifier         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/appobjid">APPOBJID</a>
         </td>
         <td> Modify the tracked object name         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="appstate.htm">APPSTATE</a>
         </td>
         <td>          </td>
         <td>
            <p>State of the end phase for the processing script to restart </p>
            <p>Specify an application state for the processing
 script that will help the script to restart at the right step if the
 script is relaunched.
</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p><a href="../../../command_summary/parameter_intro/blknum">BLKNUM </a>
</p>
         </td>
         <td>
            <p>Catalog block number. If the values '*' or ' ' are used 
 then all transfers are selected regardless of the block that they belong 
 to.</p>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="diagc.htm">DIAGC</a>
         </td>
         <td>          </td>
         <td>Modify the complimentary diagnostic information.         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/direct">DIRECT </a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer direction for the requests in question.</p>
            <p>The possible values are:</p>
            <ul>
               <li>BOTH: 
 (default) takes both send transfers and receive transfers into account,               </li>
               <li>RECV: 
 limits the action to receive transfers,               </li>
               <li>SEND: 
 limits the action to send transfers.               </li>
            </ul>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/fname">FNAME</a>
         </td>
         <td>          </td>
         <td>Modify the FNAME,  name of the local file, directory, indirection file, selection mask 
 or selection directory.          </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ida">IDA </a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of the transfer assigned by the user or 
 user application. </p>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idf">IDF </a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Model file identifier.</p>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="idt.htm">IDT</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer identifier.</p>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog identifier. It is a unique, local reference to 
 a transfer. </p>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="istate.htm">ISTATE</a>
         </td>
         <td>          </td>
         <td>
            <p>Intermediate state indicating if the phase has finished:</p>
            <ul>
               <li>YES: The END command is only a checkpoint, the phase is not finished.               </li>
               <li>NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters  the next phase.               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td><a href="kdate.htm">KDATE</a>
         </td>
         <td> Command deposit date         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="ktime.htm">KTIME</a>
         </td>
         <td> Command deposit time         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/nfname">NFNAME</a>
         </td>
         <td>          </td>
         <td>Modify the NFNAME, the name of the physical file at the receiver partner site.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/parm">PARM</a>
         </td>
         <td>User parameter         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/part">PART</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner identifier.</p>
            <p>The value of this parameter may be:</p>
            <ul>
               <li>an <i>identifier</i>: 
 the command only concerns the transfers with this partner               </li>
               <li>a <i>mask</i>: 
 the command concerns the transfers with the partners, whose identifiers 
 correspond to this masks               </li>
            </ul>
         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/pri">PRI</a>
         </td>
         <td> Priority of scheduled transfers         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="phase.htm">PHASE</a>
         </td>
         <td>The transfer phase of a catalog entry at which the command is applied.         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="phasestep.htm">PHASESTEP</a>
         </td>
         <td>The phase step of a catalog entry at which the command is applied.         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/rappl">RAPPL</a>
         </td>
         <td>          </td>
         <td>Modify the RAPPL, the identifier of the file receiver application.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/rpassw">RPASSWD</a>
         </td>
         <td>          </td>
         <td>Modify the RPASSWD, the password for the user who is receiving the file.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/ruser">RUSER</a>
         </td>
         <td>          </td>
         <td>Modify the RUSER, the identifier for the user who is receiving the file.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/state">STATE</a>
         </td>
         <td> Transfer request state         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/scope">SCOPE</a>
         </td>
         <td>Scope &lt;PARENT&gt;  ('PARENT','ALL','CHILDREN')         </td>
         <td>          </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/sigfname">SIGFNAME</a>
         </td>
         <td>          </td>
         <td>Modify the SIGFNAME, which  contains signatures of the different signatories and the subscriber as defined by SUSER.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/sappl">SAPPL</a>
         </td>
         <td>          </td>
         <td>Modify the SAPPL, the identifier of the file sender application.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/suser">SUSER</a>
         </td>
         <td>          </td>
         <td>Modify the SUSER, the identifier for the user who is sending the file.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/spasswd">SPASSWD</a>
         </td>
         <td>          </td>
         <td>Modify the SPASSWD, the password for the user who is sending the file.         </td>
      </tr>
   </tbody>
</table>

## Using the END command

**Using ISTATE=YES**

Upon file reception the END command selects the transfer for the defined partner, and modifies the `DIAGC `in the catalog (`step1_completed` in the catalog) at which point the transfer does not go to the next phase because you have set `ISTATE=YES`.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>END</p>
            <p> PART = HQ,</p>
            <p> ISTATE=YES,</p>
            <p>  DIAGC=step1_completed,</p>
            <p>  DIRECT=RECV,</p>
            <p>  IDF = TEST,</p>
            <p> IDA = X32451</p>
         </td>
      </tr>
   </tbody>
</table>

Log output:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTR12I END Treated for USER &lt;user&gt; : DIAGC value was "" and is now "step1_completed"         </td>
      </tr>
   </tbody>
</table>

**Using ISTATE=NO**

Upon file reception the END command selects the transfer for the defined partner, and modifies the `DIAGC `in the catalog (end\_completed in the catalog), at which point the transfer goes to the next phase because you have set `ISTATE=NO`.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>END</p>
            <p> PART = HQ,</p>
            <p> ISTATE=NO,</p>
            <p> DIAGC=end_completed,</p>
            <p>   DIRECT=RECV,</p>
            <p> IDF = TEST,</p>
            <p> IDA = X32451</p>
         </td>
      </tr>
   </tbody>
</table>

Log output:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTR12I END Treated for USER &lt;user&gt; : DIAGC value was "step1_completed" and is now "end_completed"         </td>
      </tr>
   </tbody>
</table>
