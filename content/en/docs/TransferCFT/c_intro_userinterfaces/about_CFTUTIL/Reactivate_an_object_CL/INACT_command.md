{
    "title": "           INACT  - Deactivate an object",
    "linkTitle": "INACT - Deactivating objects",
    "weight": "270"
}<span id="kanchor63"></span>

This page describes the INACT command and its parameters. You can use the INACT command to deactivate:

-   One or more partners (CFTPART)
-   Sentinel notifications
-   CRON object (CFTCRON)
-   Folder object (CFTFOLDER)

> **Note:**
>
> This command cannot be applied to partners whose definition was provided
> or modified by a directory EXIT.

Command guide: [INACT](../../../command_summary#INACT)


| Parameter  | Description  |
| --- | --- |
|  <a href="../../../command_summary/parameter_intro/id">ID</a>  |  Identifier for the object to be deactivated. To deactivate several objects with a single command, use wildcard characters or meta characters.  |
|  <a href="../../../command_summary/parameter_intro/type">TYPE</a>  |  Object to be deactivated:<br/> • PART<br/> • TRK<br/> • CRON<br/> • FOLDER</li>  |
|  <a href="../../../command_summary/parameter_intro/mode">MODE</a>  |  Mode to be deactivated on partners (only when TYPE=PART object):<br/> • BOTH (default)<br/> • REQUESTER<br/> • SERVER<br/>You can use the shortcuts B, R and S in place of the keywords.  |
|  <a href="../../../command_summary/parameter_intro/force">FORCE</a>  |  <li>YES: Stops any transfers in progress involving the deactivated partners.<br/> • NO: Default value, transfers progress normally.</li>  |


## Using the INACT command

Using CFTUTIL you can perform the following commands.

### Deactivate a partner

Syntax

Where:

-   `CFTPART_ID` is the identifier of the partner to deactivate. To deactivate several partners with a single command, use wildcard characters or meta characters.
-   is the mode to be deactivated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"
-   When `FORCE `is set to `YES`, stops any transfers in progress involving the deactivated partners.

Example

to deactivate the partner called PARIS in requester mode, enter:

Returning the following output:

When a partner is deactivated, transfers awaiting processing are:

-   Suspended in requester mode
-   Refused in server mode

The state of a transfer request awaiting execution in requester mode
for a deactivated partner remains **D**,
with a diagnostic code 430 and a protocol diagnostic INACT.

The state of a transfer request awaiting execution in server mode for
a deactivated partner remains <span style="font-weight: bold;">D</span>,
with a diagnostic code 930 and a protocol diagnostic RCO 312, or ABO 312
if the session is already open.

The state of transfers that are interrupted by an INACT command when
FORCE=YES is <span style="font-weight: bold;">H</span>, with a diagnostic
code 121 and a protocol diagnostic OPER.

### Deactivate Sentinel notifications

Syntax

All notifications to Sentinel are suspended.

### Deactivate cron object

Syntax

Where `CFTCRON_ID` is the identifier of the CRON object to deactivate. To deactivate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the CRON referenced by CRON1, enter:

Returning the following output:

### Deactivate folder object

Syntax

Where `CFTFOLDER_ID` is the identifier of the folder object to deactivate. To deactivate several folder objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the folder referenced by USER1, enter:

Returning the following output:
