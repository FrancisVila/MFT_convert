{
    "title": "CLEARCMD - Delete a command in the COM file",
    "linkTitle": "Delete a command in the COM file",
    "weight": "310"
}This page describes the <span id="CLEARCMD_command"></span>CLEARCMD. Use this
command to delete a transfer request from the communication file. A log message is generated to trace who has cleared which command.

> **Note:**
>
> You must include either the COMMAND or JOBNAME parameter when using this command.


           | Parameters  | Description  |
 --- | --- | --- |
|  COMMAND  |  Request keyword.  |
|  INDEX  |  Request number as displayed by the LISTCOM command.<br/>For example:<br/> • <code>INDEX=*</code> Selects all record numbers.<br/> • <code>INDEX=12345</code> Selects the record number 12345 in the COM file.</li>  |
| JOBNAME  |  Jobname (string 15), which you can combine with wildcard characters.<br/>For example:<br/> • JOBNAME=12345<br/> • JOBNAME=123*<br/> • JOBNAME=12?45</li>  |
|  USERID  |  Identifier of the request owner.  |


### Delete a single command

To use CLEARCMD to delete a single command, the USERID, INDEX, and COMMAND parameters are mandatory.

**Example**

Begin by running the LISTCOM command.

Enter the CLEARCMD command.

Repeat the LISTCOM command, and the example below displays  the results (note the record is now set to CLEARED).

### Delete a group of commands

To delete a group of commands use the following syntax.

To delete all commands=cmd for this userid:

To delete all commands for this jobname and this userid:

To delete all commands=cmd for this jobname and this userid:

**Example**

To delete all RECV commands that have the JOBNAME 9168 for the Axway/Manager account user begin by executing the LISTCOM command.

Enter the CLEARCMD command.

Run LISTCOM; the selected records now display as CLEARED.

### Syntax error

The following is a list of error and information messages that display.

**Error 1**

CFTU26E CLEARCMD \_ Error (Index value not authorized\_ Bad command)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=4\*,command=recv)

 

**Error 2**

CFTU26E CLEARCMD \_ Error (COMMAND Keyword missing)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=4,jobname=1234)

 

**Error 3**

CFTU26E CLEARCMD \_ Error (COMMAND or JOBNAME Keyword missing)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=\*)
