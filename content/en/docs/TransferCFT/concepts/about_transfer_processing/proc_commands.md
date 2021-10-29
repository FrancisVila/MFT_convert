{
    "title": "Use processing scripts",
    "linkTitle": "Standard use of processing commands",
    "weight": "190"
}There are 4 stages where you can configure processing - preprocessing, post-processing, ack processing, and for a transfer error. For these, Transfer CFT provides global definitions in the static configuration that are used by default. However, you can override the default scripts, in the CFTSEND, SEND, CFTRECV and RECV commands, using the following parameters:

-   `Preexec`: for preprocessing
-   `Exec`: for post-processing
-   `Ackexec`: for acknowledge processing
-   `Exece`: for transfer errors

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The exceptions to these rules are described in the following sections.         </td>
      </tr>
   </tbody>
</table>

## Methods for executing processing scripts

There are two ways to execute a processing script, either by referencing a template processing script, or by directly executing a program or a processing script. In either method, you can use symbolic variables, though they are processed differently as described below.

### Executing a template processing script

Using this method, Transfer CFT creates a temporary file based on the template processing script, and replaces all symbolic variables with the corresponding values as they relate to the transfer. For example, if &IDTU is in the script, it is replaced by the actual transfer value. Transfer CFT then executes this temporary file.

For example, to run the myscript.sh script using this method:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftsend id=flow01, exec='exec/myscript.sh'         </td>
      </tr>
   </tbody>
</table>

Example of a template processing script

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL WLOG MSG="execute processing script for the &amp;IDTU transfer "</p>
            <p>CFTUTIL END PART=&amp;PART, IDTU=&amp;IDTU</p>         </td>
      </tr>
   </tbody>
</table>

Example of the corresponding temporary file to execute

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL WLOG MSG="execute processing script for the A0000001 transfer "</p>
            <p>CFTUTIL END PART=PART01, IDTU=A0000001</p>         </td>
      </tr>
   </tbody>
</table>

Operating system differences

Depending on the operating system, the temporary file is treated as follows:

-   Windows: The temporary file is automatically deleted.

-   z/OS: The temporary file is automatically deleted.

-   IBM i: The temporary file is automatically deleted.

-   UNIX: You must add the following lines at the end of the template processing script:

    rm $0

    rm $0.err

-   HP NonStop native environment: You must perform the following steps to remove the temporary file:
    -   #PURGE \[#IN\]
    -   The same BTPURGE procedure as in the previous version is delivered and can be executed

-   HP NonStop OSS environment: You must add the following lines at the end of the template processing script:

    rm $0

    rm $0.err

### <span id="Directly"></span>Directly executing a program or a processing script

Available on Windows and Unix

A second method for executing scripts is to directly run a script. This method allows you to put command arguments directly in the exec parameter itself. However, while you may use symbolic variables in the exec, any symbolic variables contained within the script are not replaced during script execution.

For security reasons, you cannot use this method with the SEND/RECV command's PREEXEC, EXEC or ACKEXEC parameters. Doing so generates an error: CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands.

To implement this method, preface the PREEXEC, EXEC or ACKEXEC value with "cmd:". For example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSEND id=flow01, fname=myfile, exec="cmd:myscript.sh &amp;PART &amp;IDT &amp;IDTU"         </td>
      </tr>
   </tbody>
</table>

To call a program, for example CFTUTIL, you can use a similar syntax as shown here:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSEND id=flow01, fname=myfile, exec="cmd:<strong>CFTUTIL</strong> end part=&amp;PART, idt=&amp;IDT, direct=SEND"         </td>
      </tr>
   </tbody>
</table>

Limitations Unix only

If a command is incorrect and cannot be executed, the transfer remains in the phasestep C. Possible reasons for this include:

-   The command file name is too long
-   The command file name does not point to a regular file
-   The search permission is denied on a component of the command's path prefix
-   The execute permission is denied
-   The system does not support executing this type of file
-   A loop exists in symbolic links encountered during resolution of the path or file argument

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Tip  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" data-valign="top">Refer to <span>man execve</span> for an exhaustive list, since after a fork in the processes Transfer CFT does not retrieve the EXEC failure.         </td>
      </tr>
   </tbody>
</table>

## Schedule processing

You can use the Premindate/Premintime, Postmindate/Postmintime, and Ackmindate/Ackmintime parameters to schedule script processing activity. Additionally you can use prestate=Hold to wait for a START to start pre-processing.

## Throttle processing

In some cases you may want to limit the number of scripts launched in parallel by Transfer CFT to reduce processing bottlenecks. To do so, set the UCONF cft.server.max\_processing\_scripts parameter to a positive integer to enable and control the number of executed processes.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Caution  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">When using this parameter, every end-of-transfer procedure must notify Transfer CFT once the processing is complete. This can be done either via an END or KEEP command (in the case of an error). Failure to signal that processing is complete means that new procedures cannot start once the<code> cft.server.max_processing_scripts</code> value is reached.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>uconfset id=<span>cft.server.max_processing_scripts</span>, value=64         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">This parameter does not apply to the execution of transfer error scripts.         </td>
      </tr>
   </tbody>
</table>

## Commands in scripts

### End command

The end command monitors the script completion. Depending on the parameter used (appstate, istate, and diagc) you can, for example, check the progression of the script. The end of processing is marked by a CFTUTIL END with istate=no (default).

#### Define istate and appstate

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=no,appstate="completed"         </td>
      </tr>
   </tbody>
</table>

The command CFTUTIL END can be use to set checkpoints in the script execution using the istate=yes (istate is an intermediate state) and APPSTATE value. Doing so allows you to see the step running the script in Transfer CFT.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=yes,appstate="step_1"
            <p>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=yes,appstate="step_2"</p>         </td>
      </tr>
   </tbody>
</table>

#### Define DIAGC

To create a more specific comment you can modify the DIAGC. The DIAGC used in preprocessing phase is reset when a transfer begins.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL END part=&amp;PART,idtu=&amp;IDTU,DIAGC="intermediate checkpoint number 1 “         </td>
      </tr>
   </tbody>
</table>

#### Replace variable

In your script you can also update values, for example the FNAME. However, the initial FNAME is lost in the catalog and replaced by the new one, and is only available in the log file as shown below.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,FNAME=NEW_FNAME</p>
            <p>...</p>
            <p>.....</p>
            <p>CFTR12I END Treated for USER MY_CFT : FNAME value was "pub/FTEST" and is now "NEW_FNAME"</p>         </td>
      </tr>
   </tbody>
</table>

### Stop

When you execute a CFTUTIL HALT or CFTUTIL KEEP, you can set the DIAGP and DIAGC so that when you restart the script it executes specific actions depending on the DIAGP and DIAGC that you defined.

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTUTIL HALT part=&amp;PART,idtu=&amp;IDTU,DIAGP=”Error 1”,DIAGC=”Connection lost”</p>
            <p>CFTUTIL KEEP part=&amp;PART,idtu=&amp;IDTU,DIAGP=”Error 404”,DIAGC=”File not found”</p>         </td>
      </tr>
   </tbody>
</table>

### Restart

In your script, you can handle restart from intermediate steps checking the &APPSTATE value. So if the script fails for any reason, you can run a CFTUTIL HALT or CFTUTIL keep then using a CFTUTIL SUBMIT you can restart your script, which runs from the checkpoint that you set.

Example  

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>Go to &amp;APPSTATE</p>
            <p>Step 1:</p>
            <p>if OK END part=&amp;part, idtu=&amp;idtu, appstate="step 1", istate=yes</p>
            <p>if not OK KEEP part=&amp;part, idtu=&amp;idtu, appstate="step 1", istate=yes &amp;go to error</p>
            <p>Step 2:</p>
            <p>if OK END part=&amp;part, idtu=&amp;idtu, appstate="step 2", istate=yes</p>
            <p>if not OK KEEP part=&amp;part, idtu=&amp;idtu, appstate="step 2", istate=yes &amp;go to error</p>
            <p>END:</p>
            <p>END part=&amp;part, idtu=&amp;idtu, istate=no &amp; go to eof</p>
            <p>Error:</p>
            <p>WLOG MSG="script error at step &amp;appstate"</p>         </td>
      </tr>
   </tbody>
</table>

### Define wait time for a restart

You can change the maxduration for a transfer restart using the maxduration parameter in the START command.

## Command parameters

### SEND, CFTSEND

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
         <td rowspan="14">SEND, CFTSEND         </td>
         <td>ACKMINDATE         </td>
         <td>integer         </td>
         <td>From this date on, the acknowledgement exec file can be launched.         </td>
      </tr>
      <tr class="even">
         <td>ACKMINTIME         </td>
         <td>integer         </td>
         <td>From this time on, the acknowledgement exec file can be launched.         </td>
      </tr>
      <tr class="odd">
         <td>POSTMINDATE         </td>
         <td>integer         </td>
         <td>From this date on, the post processing exec file can be launched.         </td>
      </tr>
      <tr class="even">
         <td>POSTMINTIME         </td>
         <td>integer         </td>
         <td>From this time on, the post processing exec file can be launched.         </td>
      </tr>
      <tr class="odd">
         <td>PREMINDATE         </td>
         <td>integer         </td>
         <td>From this date on, the preprocessing exec file can be launched.         </td>
      </tr>
      <tr class="even">
         <td>PREMINTIME         </td>
         <td>integer         </td>
         <td>From this time on, the preprocessing exec file can be launched.         </td>
      </tr>
      <tr class="odd">
         <td>ACKEXEC         </td>
         <td>string         </td>
         <td>The acknowledgement exec file that will be launched after receiving an ACK or NACK.         </td>
      </tr>
      <tr class="even">
         <td>ACKSTATE         </td>
         <td>REQUIRE/IGNORE         </td>
         <td>Specify if <span>Transfer CFT</span> should wait for an ACK/NACK to enter the X phase.         </td>
      </tr>
      <tr class="odd">
         <td>POSTSTATE         </td>
         <td>DISP         </td>
         <td>The transfer phase step as it enters the Y phase.         </td>
      </tr>
      <tr class="even">
         <td>PREEXEC         </td>
         <td>string         </td>
         <td>The preprocessing exec file.         </td>
      </tr>
      <tr class="odd">
         <td>PRESTATE         </td>
         <td>DISP/HOLD         </td>
         <td>The transfer phase step as it enters the A phase.         </td>
      </tr>
      <tr class="even">
         <td>EXECSUBPRE         </td>
         <td>LIST/SUBF/FILE         </td>
         <td>Group of files: execution policy for preprocessing phase.         </td>
      </tr>
      <tr class="odd">
         <td>EXECSUB         </td>
         <td>LIST/SUBF/FILE         </td>
         <td>Group of files: execution policy for post-processing phase.         </td>
      </tr>
      <tr class="even">
         <td>EXECSUBA         </td>
         <td>LIST/SUBF/FILE         </td>
         <td>Group of files: execution policy for acknowledgement phase.         </td>
      </tr>
   </tbody>
</table>

### END

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
         <td rowspan="14">END         </td>
         <td>DIAGC         </td>
         <td>string         </td>
         <td>Specify a comment.         </td>
      </tr>
      <tr class="even">
         <td>FNAME         </td>
         <td>string         </td>
         <td>Modify the FNAME.         </td>
      </tr>
      <tr class="odd">
         <td>NFNAME         </td>
         <td>string         </td>
         <td>Modify the NFNAME.         </td>
      </tr>
      <tr class="even">
         <td>SIGFNAME         </td>
         <td>string         </td>
         <td>Modify the SIGFNAME.         </td>
      </tr>
      <tr class="odd">
         <td>RAPPL         </td>
         <td>string         </td>
         <td>Modify the RAPPL.         </td>
      </tr>
      <tr class="even">
         <td>SAPPL         </td>
         <td>string         </td>
         <td>Modify the SAPPL.         </td>
      </tr>
      <tr class="odd">
         <td>RUSER         </td>
         <td>string         </td>
         <td>Modify the RUSER.         </td>
      </tr>
      <tr class="even">
         <td>SUSER         </td>
         <td>string         </td>
         <td>Modify the SUSER.         </td>
      </tr>
      <tr class="odd">
         <td>RPASSWD         </td>
         <td>string         </td>
         <td>Modify the RPASSWD.         </td>
      </tr>
      <tr class="even">
         <td>SPASSWD         </td>
         <td>string         </td>
         <td>Modify the SPASSWD.         </td>
      </tr>
      <tr class="odd">
         <td>ISTATE         </td>
         <td>NO/YES         </td>
         <td>            <p>Indicates:</p>
            <ul>
               <li>YES: The END command is only a checkpoint.               </li>
               <li>NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase.               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>PHASE         </td>
         <td>char         </td>
         <td>The transfer phase at which the command is applied.         </td>
      </tr>
      <tr class="odd">
         <td>PHASE STEP         </td>
         <td>char         </td>
         <td>The phase step at which the command is applied.         </td>
      </tr>
      <tr class="even">
         <td>APPSTATE         </td>
         <td>string         </td>
         <td>Specify an application state for the processing
script that will help the script to restart at the right step if the
script is relaunched.         </td>
      </tr>
   </tbody>
</table>

### KEEP

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
         <td rowspan="4">KEEP         </td>
         <td>DIAGP         </td>
         <td>string         </td>
         <td>Specify a customized error that will be set for DIAGP in the catalog.         </td>
      </tr>
      <tr class="even">
         <td>DIAGC         </td>
         <td>string         </td>
         <td>Specify a customized error that will be set for DIAGC in the catalog.         </td>
      </tr>
      <tr class="odd">
         <td>PHASE         </td>
         <td>char         </td>
         <td>The transfer phase at which the command is applied.         </td>
      </tr>
      <tr class="even">
         <td>PHASE STEP         </td>
         <td>char         </td>
         <td>The phase step at which the command is applied.         </td>
      </tr>
   </tbody>
</table>

### HALT

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
         <td rowspan="4">HALT         </td>
         <td>DIAGP         </td>
         <td>string         </td>
         <td>Specify a customized error that will be set for DIAGP in the catalog.         </td>
      </tr>
      <tr class="even">
         <td>DIAGC         </td>
         <td>string         </td>
         <td>Specify a customized error that will be set for DIAGC in the catalog.         </td>
      </tr>
      <tr class="odd">
         <td>PHASE         </td>
         <td>char         </td>
         <td>The transfer phase at which the command is applied.         </td>
      </tr>
      <tr class="even">
         <td>PHASE STEP         </td>
         <td>char         </td>
         <td>The phase step at which the command is applied.         </td>
      </tr>
   </tbody>
</table>

### SUBMIT

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
         <td rowspan="3">SUBMIT         </td>
         <td>APPSTATE         </td>
         <td>string         </td>
         <td>Specify an application state for the
processing script that will allow a SUBMIT to occur at the correct script step.         </td>
      </tr>
      <tr class="even">
         <td>PHASE         </td>
         <td>char         </td>
         <td>The transfer phase at which the command is applied.         </td>
      </tr>
      <tr class="odd">
         <td>PHASE STEP         </td>
         <td>char         </td>
         <td>The phase step at which the command is applied.         </td>
      </tr>
   </tbody>
</table>

### START

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
         <td rowspan="3">START         </td>
         <td>PHASE         </td>
         <td>char         </td>
         <td>The transfer phase at which the command is applied.         </td>
      </tr>
      <tr class="even">
         <td>MAXDURATION         </td>
         <td>integer         </td>
         <td>Restart a transfer that reached its maxduration, time in minutes {<u>0</u>...32767}.         </td>
      </tr>
      <tr class="odd">
         <td>PHASE STEP         </td>
         <td>char         </td>
         <td>The phase step at which the command is applied.         </td>
      </tr>
   </tbody>
</table>
