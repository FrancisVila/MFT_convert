{
    "title": "Reactivate an object",
    "linkTitle": "Reactivate an object",
    "weight": "320"
}# <span id="ACT___Reactivating_objects"></span>ACT - Reactivating objects

This topic describes the ACT command and its parameters. You can use
the ACT command to reactivate:

-   One or more partners (CFTPART)
-   Sentinel notifications
-   CRON object (CFTCRON)
-   Folder object (CFTFOLDER)

Command guide: [ACT](../../../../c_intro_userinterfaces/command_summary)

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Parameter</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a> </p></td>
<td><p>Identifier for the object to be reactivated. To reactivate several objects with a single command,
use wildcard
characters or meta characters.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode">MODE</a></p></td>
<td><p>Mode to be reactivated on partners (only when TYPE=PART object):</p>
<ul>
<li>BOTH (default)</li>
<li>REQUESTER</li>
<li>SERVER</li>
</ul>
<p>You can use the shortcuts B, R and S in place of the keywords.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> </p></td>
<td><p>Object to reactivate:</p>
<ul>
<li>PART</li>
<li>TRK</li>
<li>CRON</li>
<li>FOLDER</li>
</ul></td>
</tr>
</tbody>
</table>

## Using the ACT command

Using CFTUTIL you can perform the following commands.

### Activate a partner

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=PART,ID=&lt;CFTPART_ID&gt;,MODE=&lt;mode&gt;</p></td>
</tr>
</tbody>
</table>

Where:

-   CFTPART\_ID is the identifier for the partner to activate. To activate several partners with a single command, use wildcard characters or meta characters
-   Mode is the mode to be activated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"

Example

To activate a partner called PARIS in both modes, enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=PART, ID=PARIS, MODE=BOTH</p></td>
</tr>
</tbody>
</table>

Returning the following output:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTU20I Part=PARIS : NOACTIVE -&gt; ACTIVEBOTH</p>
<p>CFTU00I ACT _ Correct (TYPE=PART,ID=PARIS)</p></td>
</tr>
</tbody>
</table>

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

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=TRK</p></td>
</tr>
</tbody>
</table>

All notifications to Sentinel are reactivated. However, the UCONF` sentinel.xfb.enable` parameter must be set to `Yes `to use.

### Activate a CRON object

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=CRON,ID=&lt;CFTCRON_ID&gt;</p></td>
</tr>
</tbody>
</table>

Where `CFTCRON_ID` is the identifier of the CRON object to activate. To activate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To activate a CRON referenced by CRON1, enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=CRON,ID=CRON1</p></td>
</tr>
</tbody>
</table>

Returning the following output:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTU20I Cronjob=CRON1 : NOACTIVE -&gt; ACTIVE</p>
<p>CFTU00I ACT _ Correct (TYPE=CRON,ID=CRON1)</p></td>
</tr>
</tbody>
</table>

### Activate a folder object

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=FOLDER,ID=&lt;CFTFOLDER_ID&gt;</p></td>
</tr>
</tbody>
</table>

Where `CFTFOLDER_ID` is the identifier to the folder object to activate. To activate several folder objects with a single command, use wildcard characters or meta characters.

Example

To activate the folder referenced by USER1, enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ACT TYPE=FOLDER,ID=USER1</p></td>
</tr>
</tbody>
</table>

Returning the following output:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTU20I Folder=USER1 : NOACTIVE -&gt; ACTIVE</p>
<p>CFTU00I ACT _ Correct (type=folder,id=user1)</p></td>
</tr>
</tbody>
</table>

The UCONF` folder_monitoring.enable` parameter must be set to `Yes`, otherwise the folder is not activated even if the state is active.
