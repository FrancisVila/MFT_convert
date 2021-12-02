{
    "title": "Use processing scripts",
    "linkTitle": "Standard use of processing commands",
    "weight": "180"
}There are 4 stages where you can configure processing - preprocessing, post-processing, ack processing, and for a transfer error. For these, Transfer CFT provides global definitions in the static configuration that are used by default. However, you can override the default scripts, in the CFTSEND, SEND, CFTRECV and RECV commands, using the following parameters:

-   `Preexec`: for preprocessing
-   `Exec`: for post-processing
-   `Ackexec`: for acknowledge processing
-   `Exece`: for transfer errors

> **Note:**
>
> The exceptions to these rules are described in the following sections.

## Methods for executing processing scripts

There are two ways to execute a processing script, either by referencing a template processing script, or by directly executing a program or a processing script. In either method, you can use symbolic variables, though they are processed differently as described below.

### Executing a template processing script

Using this method, {{< TransferCFT/componentlongname  >}} creates a temporary file based on the template processing script, and replaces all symbolic variables with the corresponding values as they relate to the transfer. For example, if &IDTU is in the script, it is replaced by the actual transfer value. {{< TransferCFT/componentlongname  >}} then executes this temporary file.

For example, to run the `myscript.sh` script using this method:

Example of a template processing script

Example of the corresponding temporary file to execute

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

<span id="Directly"></span>

### Directly executing a program or a processing script

Available on Windows and Unix

A second method for executing scripts is to directly run a script. This method allows you to put command arguments directly in the exec parameter itself. However, while you may use symbolic variables in the exec, any symbolic variables contained within the script are not replaced during script execution.

For security reasons, you cannot use this method with the SEND/RECV command's PREEXEC, EXEC or ACKEXEC parameters. Doing so generates an error: `CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands`.

To implement this method, preface the PREEXEC, EXEC or ACKEXEC value with "`cmd:`". For example:

To call a program, for example CFTUTIL, you can use a similar syntax as shown here:

Limitations Unix only

If a command is incorrect and cannot be executed, the transfer remains in the phasestep C. Possible reasons for this include:

-   The command file name is too long
-   The command file name does not point to a regular file
-   The search permission is denied on a component of the command's path prefix
-   The execute permission is denied
-   The system does not support executing this type of file
-   A loop exists in symbolic links encountered during resolution of the path or file argument

> **Note:**
>
> Tip  
> Refer to man execve for an exhaustive list, since after a fork in the processes Transfer CFT does not retrieve the EXEC failure.

## Schedule processing

You can use the Premindate/Premintime, Postmindate/Postmintime, and Ackmindate/Ackmintime parameters to schedule script processing activity. Additionally you can use prestate=Hold to wait for a START to start pre-processing.

## Throttle processing

In some cases you may want to limit the number of scripts launched in parallel by {{< TransferCFT/transfercftname  >}} to reduce processing bottlenecks. To do so, set the UCONF `cft.server.max_processing_scripts` parameter to a positive integer to enable and control the number of executed processes.

> **Note:**
>
> Caution  
> When using this parameter, every end-of-transfer procedure must notify Transfer CFT once the processing is complete. This can be done either via an END or KEEP command (in the case of an error). Failure to signal that processing is complete means that new procedures cannot start once the cft.server.max\_processing\_scripts value is reached.

> **Note:**
>
> This parameter does not apply to the execution of transfer error scripts.

## Commands in scripts

### End command

The end command monitors the script completion. Depending on the parameter used (appstate, istate, and diagc) you can, for example, check the progression of the script. The end of processing is marked by a CFTUTIL END with `istate=no` (default).

#### Define istate and appstate

Example

The command CFTUTIL END can be use to set checkpoints in the script execution using the istate=yes (istate is an intermediate state) and APPSTATE value. Doing so allows you to see the step running the script in {{< TransferCFT/componentshortname  >}}.

Example

#### Define DIAGC

To create a more specific comment you can modify the DIAGC. The DIAGC used in preprocessing phase is reset when a transfer begins.

#### Replace variable

In your script you can also update values, for example the FNAME. However, the initial FNAME is lost in the catalog and replaced by the new one, and is only available in the log file as shown below.

Example

### Stop

When you execute a CFTUTIL HALT or CFTUTIL KEEP, you can set the DIAGP and DIAGC so that when you restart the script it executes specific actions depending on the DIAGP and DIAGC that you defined.

Example

### Restart

In your script, you can handle restart from intermediate steps checking the &APPSTATE value. So if the script fails for any reason, you can run a CFTUTIL HALT or CFTUTIL keep then using a CFTUTIL SUBMIT you can restart your script, which runs from the checkpoint that you set.

Exa**m**ple  

### Define wait time for a restart

You can change the maxduration for a transfer restart using the maxduration parameter in the START command.

## Command parameters

### SEND, CFTSEND

### END


| Command  | Parameter  | Value  | Description  |
| --- | --- | --- | --- |
| END  | DIAGC  | string  | Specify a comment.  |
| FNAME  | string  | Modify the FNAME.  |
| NFNAME  | string  | Modify the NFNAME.  |
| SIGFNAME  | string  | Modify the SIGFNAME.  |
| RAPPL  | string  | Modify the RAPPL.  |
| SAPPL  | string  | Modify the SAPPL.  |
| RUSER  | string  | Modify the RUSER.  |
| SUSER  | string  | Modify the SUSER.  |
| RPASSWD  | string  | Modify the RPASSWD.  |
| SPASSWD  | string  | Modify the SPASSWD.  |
| ISTATE  | NO/YES  |  Indicates:<br/> • YES: The END command is only a checkpoint.<br/> • NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase.</li>  |
| PHASE  | char  | The transfer phase at which the command is applied.  |
| PHASE STEP  | char  | The phase step at which the command is applied.  |
| APPSTATE  | string  | Specify an application state for the processing script that will help the script to restart at the right step if the script is relaunched.  |


### KEEP

### HALT

### SUBMIT

### START
