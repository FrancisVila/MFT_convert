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

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Identifier for the object to be reactivated. To reactivate several objects with a single command,
use wildcard
characters or meta characters.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../command_summary/parameter_intro/mode">MODE</a></p>         </td>
         <td><p>Mode to be reactivated on partners (only when TYPE=PART object):</p>
<ul>
<li>BOTH (default)</li>
<li>REQUESTER</li>
<li>SERVER</li>
</ul>
<p>You can use the shortcuts B, R and S in place of the keywords.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td><p>Object to reactivate:</p>
<ul>
<li>PART</li>
<li>TRK</li>
<li>CRON</li>
<li>FOLDER</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

## Using the ACT command

Using CFTUTIL you can perform the following commands.

### Activate a partner

Syntax



    ACT TYPE=PART,ID=<CFTPART_ID>,MODE=<mode>

Where:

-   is the identifier for the partner to activate. To activate several partners with a single command, use wildcard characters or meta characters
-   is the mode to be activated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"

Example

To activate a partner called PARIS in both modes, enter:



    ACT TYPE=PART, ID=PARIS, MODE=BOTH

Returning the following output:



    CFTU20I Part=PARIS : NOACTIVE -> ACTIVEBOTH
    CFTU00I ACT _ Correct (TYPE=PART,ID=PARIS)

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



    ACT TYPE=TRK

All notifications to Sentinel are reactivated. However, the UCONF` sentinel.xfb.enable` parameter must be set to `Yes `to use.

### Activate a CRON object

Syntax



    ACT TYPE=CRON,ID=<CFTCRON_ID>

Where `CFTCRON_ID` is the identifier of the CRON object to activate. To activate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To activate a CRON referenced by CRON1, enter:



    ACT TYPE=CRON,ID=CRON1

Returning the following output:



    CFTU20I Cronjob=CRON1 : NOACTIVE -> ACTIVE
    CFTU00I ACT _ Correct (TYPE=CRON,ID=CRON1)

### Activate a folder object

Syntax



    ACT TYPE=FOLDER,ID=<CFTFOLDER_ID>

Where `CFTFOLDER_ID` is the identifier to the folder object to activate. To activate several folder objects with a single command, use wildcard characters or meta characters.

Example

To activate the folder referenced by USER1, enter:



    ACT TYPE=FOLDER,ID=USER1

Returning the following output:



    CFTU20I Folder=USER1 : NOACTIVE -> ACTIVE
    CFTU00I ACT _ Correct (type=folder,id=user1)

The UCONF` folder_monitoring.enable` parameter must be set to `Yes`, otherwise the folder is not activated even if the state is active.
