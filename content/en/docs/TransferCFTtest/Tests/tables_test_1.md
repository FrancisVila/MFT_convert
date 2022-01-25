{
    "title": "Test of command parameter formats",
    "linkTitle": "Test of command parameter formats",
    "weight": "50"
}## AAA

## Original from <a href="../original_versions/proc_commands" class="MCXref xref">Use processing scripts</a>

### SEND, CFTSEND

<table>
   <thead>
      <tr>
<th >Command         </th>
<th >Parameter         </th>
<th >Value         </th>
<th >Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td rowspan="14" >SEND, CFTSEND         </td>
         <td >ACKMINDATE         </td>
         <td >integer         </td>
         <td >From this date on, the acknowledgement exec file can be launched.         </td>
      </tr>
      <tr>
         <td >ACKMINTIME         </td>
         <td >integer         </td>
         <td >From this time on, the acknowledgement exec file can be launched.         </td>
      </tr>
      <tr>
         <td >POSTMINDATE         </td>
         <td >integer         </td>
         <td >From this date on, the post processing exec file can be launched.         </td>
      </tr>
      <tr>
         <td >POSTMINTIME         </td>
         <td >integer         </td>
         <td >From this time on, the post processing exec file can be launched.         </td>
      </tr>
      <tr>
         <td >PREMINDATE         </td>
         <td >integer         </td>
         <td >From this date on, the preprocessing exec file can be launched.         </td>
      </tr>
      <tr>
         <td >PREMINTIME         </td>
         <td >integer         </td>
         <td >From this time on, the preprocessing exec file can be launched.         </td>
      </tr>
      <tr>
         <td >ACKEXEC         </td>
         <td >string         </td>
         <td >The acknowledgement exec file that will be launched after receiving an ACK or NACK.         </td>
      </tr>
      <tr>
         <td >ACKSTATE         </td>
         <td >REQUIRE/IGNORE         </td>
         <td >Specify if Transfer CFT{{< TransferCFTtest/axwayvariablesComponentShortName  >}} should wait for an ACK/NACK to enter the X phase.         </td>
      </tr>
      <tr>
         <td >POSTSTATE         </td>
         <td >DISP         </td>
         <td >The transfer phase step as it enters the Y phase.         </td>
      </tr>
      <tr>
         <td >PREEXEC         </td>
         <td >string         </td>
         <td >The preprocessing exec file.         </td>
      </tr>
      <tr>
         <td >PRESTATE         </td>
         <td >DISP/HOLD         </td>
         <td >The transfer phase step as it enters the A phase.         </td>
      </tr>
      <tr>
         <td >EXECSUBPRE         </td>
         <td >LIST/SUBF/FILE         </td>
         <td >Group of files: execution policy for preprocessing phase.         </td>
      </tr>
      <tr>
         <td >EXECSUB         </td>
         <td >LIST/SUBF/FILE         </td>
         <td >Group of files: execution policy for post-processing phase.         </td>
      </tr>
      <tr>
         <td >EXECSUBA         </td>
         <td >LIST/SUBF/FILE         </td>
         <td >Group of files: execution policy for acknowledgement phase.         </td>
      </tr>
   </tbody>
</table>

### END

<table>
   <thead>
      <tr>
<th >Command         </th>
<th >Parameter         </th>
<th >Value         </th>
<th >Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td rowspan="14" >END         </td>
         <td >DIAGC         </td>
         <td >string         </td>
         <td >Specify a comment.         </td>
      </tr>
      <tr>
         <td >FNAME         </td>
         <td >string         </td>
         <td >Modify the FNAME.         </td>
      </tr>
      <tr>
         <td >NFNAME         </td>
         <td >string         </td>
         <td >Modify the NFNAME.         </td>
      </tr>
      <tr>
         <td >SIGFNAME         </td>
         <td >string         </td>
         <td >Modify the SIGFNAME.         </td>
      </tr>
      <tr>
         <td >RAPPL         </td>
         <td >string         </td>
         <td >Modify the RAPPL.         </td>
      </tr>
      <tr>
         <td >SAPPL         </td>
         <td >string         </td>
         <td >Modify the SAPPL.         </td>
      </tr>
      <tr>
         <td >RUSER         </td>
         <td >string         </td>
         <td >Modify the RUSER.         </td>
      </tr>
      <tr>
         <td >SUSER         </td>
         <td >string         </td>
         <td >Modify the SUSER.         </td>
      </tr>
      <tr>
         <td >RPASSWD         </td>
         <td >string         </td>
         <td >Modify the RPASSWD.         </td>
      </tr>
      <tr>
         <td >SPASSWD         </td>
         <td >string         </td>
         <td >Modify the SPASSWD.         </td>
      </tr>
      <tr>
         <td >ISTATE         </td>
         <td >NO/YES         </td>
         <td ><p>Indicates:</p>
<ul>
<li>YES: The END command is only a checkpoint.</li>
<li>NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase.</li>
</ul>         </td>
      </tr>
      <tr>
         <td >PHASE         </td>
         <td >char         </td>
         <td >The transfer phase at which the command is applied.         </td>
      </tr>
      <tr>
         <td >PHASE STEP         </td>
         <td >char         </td>
         <td >The phase step at which the command is applied.         </td>
      </tr>
      <tr>
         <td >APPSTATE         </td>
         <td >string         </td>
         <td >Specify an application state for the processing
script that will help the script to restart at the right step if the
script is relaunched.         </td>
      </tr>
   </tbody>
</table>

## Flat form of <a href="../original_versions/proc_commands" class="MCXref xref">Use processing scripts</a>

### SEND, CFTSEND command parameters

**ACKMINDATE**: From this date on, the acknowledgement exec file can be launched.

Value: integer

**ACKMINTIME**: From this time on, the acknowledgement exec file can be launched.

Value: integer

**POSTMINDATE** : From this date on, the post processing exec file can be launched.

Value: integer

**POSTMINTIME** : From this time on, the post processing exec file can be launched.

Value: integer

**PREMINDATE** : From this date on, the preprocessing exec file can be launched.

Value: integer

**PREMINTIME** : From this time on, the preprocessing exec file can be launched.

Value: integer

**ACKEXEC** : The acknowledgement exec file that will be launched after receiving an ACK or NACK.

Value: string

**ACKSTATE** : Specify if Transfer CFT{{< TransferCFTtest/axwayvariablesComponentShortName  >}} should wait for an ACK/NACK to enter the X phase.

Values: REQUIRE/IGNORE

**POSTSTATE** : The transfer phase step as it enters the Y phase.

Value: DISP

**PREEXEC** : The preprocessing exec file.

Value: string

**PRESTATE** : The transfer phase step as it enters the A phase.

Values: DISP/HOLD

**EXECSUBPRE**: Group of files: execution policy for preprocessing phase.

Values: LIST/SUBF/FILE

**EXECSUB**

Values: LIST/SUBF/FILE

Group of files: execution policy for post-processing phase.

**EXECSUBA**: Group of files: execution policy for acknowledgement phase.

Values: LIST/SUBF/FILE

### END Command parameters

**DIAGC**: Specify a comment.

Value: string

**FNAME** : Modify the FNAME.

Value: string

**NFNAME**: Modify the NFNAME.

Value: string

**SIGFNAME**: Modify the SIGFNAME.

Value: string

**RAPPL**: Modify the RAPPL.

Value: string

**SAPPL**: Modify the SAPPL.

Value: string

**RUSER**: Modify the RUSER.

Value: string

**SUSER**: Modify the SUSER.

Value: string

**RPASSWD**: Modify the RPASSWD.

Value: string

**SPASSWD**: Modify the SPASSWD.

Value: string

**ISTATE**: Indicates:

- YES: The END command is only a checkpoint.
- NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase.

Value: NO/YES

**PHASE**: The transfer phase at which the command is applied.

Value: char

**PHASE STEP** : The phase step at which the command is applied.

Value: char

**APPSTATE**: Specify an application state for the processing
script that will help the script to restart at the right step if the
script is relaunched.

Value: string

## Remove 1st col on <a href="../original_versions/proc_commands" class="MCXref xref">Use processing scripts</a>

### SEND, CFTSEND commands


| Parameter  | Value  | Description  |
| --- | --- | --- |
| ACKMINDATE  | integer  | From this date on, the acknowledgement exec file can be launched.  |
| ACKMINTIME  | integer  | From this time on, the acknowledgement exec file can be launched.  |
| POSTMINDATE  | integer  | From this date on, the post processing exec file can be launched.  |
| POSTMINTIME  | integer  | From this time on, the post processing exec file can be launched.  |
| PREMINDATE  | integer  | From this date on, the preprocessing exec file can be launched.  |
| PREMINTIME  | integer  | From this time on, the preprocessing exec file can be launched.  |
| ACKEXEC  | string  | The acknowledgement exec file that will be launched after receiving an ACK or NACK.  |
| ACKSTATE  | REQUIRE/IGNORE  | Specify if Transfer CFT{{< TransferCFTtest/axwayvariablesComponentShortName  >}} should wait for an ACK/NACK to enter the X phase.  |
| POSTSTATE  | DISP  | The transfer phase step as it enters the Y phase.  |
| PREEXEC  | string  | The preprocessing exec file.  |
| PRESTATE  | DISP/HOLD  | The transfer phase step as it enters the A phase.  |
| EXECSUBPRE  | LIST/SUBF/FILE  | Group of files: execution policy for preprocessing phase.  |
| EXECSUB  | LIST/SUBF/FILE  | Group of files: execution policy for post-processing phase.  |
| EXECSUBA  | LIST/SUBF/FILE  | Group of files: execution policy for acknowledgement phase.  |


### END command


| Parameter  | Value  | Description  |
| --- | --- | --- |
| DIAGC  | string  | Specify a comment.  |
| FNAME  | string  | Modify the FNAME.  |
| NFNAME  | string  | Modify the NFNAME.  |
| SIGFNAME  | string  | Modify the SIGFNAME.  |
| RAPPL  | string  | Modify the RAPPL.  |
| SAPPL  | string  | Modify the SAPPL.  |
| RUSER  | string  | Modify the RUSER.  |
| SUSER  | string  | Modify the SUSER.  |
| RPASSWD  | string  | Modify the RPASSWD.  |
| SPASSWD  | string  | Modify the SPASSWD.  |
| ISTATE  | NO/YES  | Indicates:<br/> • YES: The END command is only a checkpoint.<br/> • NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase. |
| PHASE  | char  | The transfer phase at which the command is applied.  |
| PHASE STEP  | char  | The phase step at which the command is applied.  |
| APPSTATE  | string  | Specify an application state for the processing script that will help the script to restart at the right step if the script is relaunched.  |

