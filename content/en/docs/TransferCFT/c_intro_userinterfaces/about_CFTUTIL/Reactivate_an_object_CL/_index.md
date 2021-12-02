{
    "title": "ACT  - Reactivating objects",
    "linkTitle": "Files and configuration",
    "weight": "250"
}This topic describes the ACT command and its parameters. You can use
the ACT command to reactivate:

-   One or more partners (CFTPART)
-   Sentinel notifications
-   CRON object (CFTCRON)
-   Folder object (CFTFOLDER)

Command guide: [ACT](../../command_summary#ACT)


|  Parameter  |  Description  |
| --- | --- |
|  <a href="../../command_summary/parameter_intro/id">ID</a>  |  Identifier for the object to be reactivated. To reactivate several objects with a single command, use wildcard characters or meta characters.  |
|  <a href="../../command_summary/parameter_intro/mode">MODE</a>  |  Mode to be reactivated on partners (only when TYPE=PART object):<br/> • BOTH (default)<br/> • REQUESTER<br/> • SERVER<br/>You can use the shortcuts B, R and S in place of the keywords.  |
|  <a href="../../command_summary/parameter_intro/type">TYPE</a>  |  Object to reactivate:<br/> • PART<br/> • TRK<br/> • CRON<br/> • FOLDER</li>  |


## Using the ACT command

Using CFTUTIL you can perform the following commands.

### Activate a partner

Syntax

Where:

-   is the identifier for the partner to activate. To activate several partners with a single command, use wildcard characters or meta characters
-   is the mode to be activated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"

Example

To activate a partner called PARIS in both modes, enter:

Returning the following output:

You can choose to reactivate in either requester or server mode, or
in both modes. However, note that you cannot use the ACT command on a partner if its definition was
provided or modified by a directory EXIT.

When a partner is reactivated, transfer requests that were suspended
by the INACT command:

-   Are restarted automatically
    in requester mode (diagnostics code 430)
-   Must be restarted
    with the START command in all other cases

### Activate Sentinel notifications

Syntax

All notifications to Sentinel are reactivated. However, the UCONF` sentinel.xfb.enable` parameter must be set to `Yes `to use.

### Activate a CRON object

Syntax

Where `CFTCRON_ID` is the identifier of the CRON object to activate. To activate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To activate a CRON referenced by CRON1, enter:

Returning the following output:

### Activate a folder object

Syntax

Where `CFTFOLDER_ID` is the identifier to the folder object to activate. To activate several folder objects with a single command, use wildcard characters or meta characters.

Example

To activate the folder referenced by USER1, enter:

Returning the following output:

The UCONF` folder_monitoring.enable` parameter must be set to `Yes`, otherwise the folder is not activated even if the state is active.
