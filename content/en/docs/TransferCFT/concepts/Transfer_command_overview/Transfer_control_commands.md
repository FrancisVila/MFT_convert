{
    "title": "Transfer control commands",
    "linkTitle": "Transfer control commands",
    "weight": "190"
}This topic describes the transfer control commands and provides a link
to more information on these commands. The transfer control commands can
be used to:

-   Interrupt a transfer
    in process
-   Activate or reactivate
    a suspended or held transfer
-   Delete a transfer
    request
-   Submit, or resubmit,
    an end-of-transfer procedure where the transfer in the T state
-   Declare that the
    processing following a transfer is completed

The following table describes the commands associated with these actions.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Command</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="23%"><p><a href="../../../admin_intro/admin_commands_intro/delete_command">DELETE</a></p></td>
<td data-valign="top" width="77%"><p>Deletes a catalog entry </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/halt_command">HALT</a></p></td>
<td data-valign="top" width="77%"><p>Stops a transfer and sets it to the HOLD state </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/keep_command">KEEP</a></p></td>
<td data-valign="top" width="77%"><p>Stops a transfer and sets it to the KEEP state </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/start_command">START</a></p></td>
<td data-valign="top" width="77%"><p>Reactivates a transfer </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/submit_command">SUBMIT</a></p></td>
<td data-valign="top" width="77%">Runs a preprocessing, a post-processing or an acknowledgment processing procedure according to the current phase of the transfer request.</td>
</tr>
<tr class="even">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/end_command">END</a></p></td>
<td data-valign="top" width="77%"><p>Declares the processing subsequent to the transfer terminated </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="23%"><p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/resume_command">RESUME</a></p></td>
<td data-valign="top" width="77%"><p>Retrieves, in the server mode, a blocked send request having
the hold status</p></td>
</tr>
</tbody>
</table>

The parameters relative to these commands determine the transfer selection
criteria, catalog entries, these commands relate to.

The transfer control commands modify the state of the transfers in the
Transfer CFT catalog. This state can be queried by the [LISTCAT](../../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command) command,
both before and after the control command is executed. The meaning of
these states is indicated in the next topic, Transfer
states.
