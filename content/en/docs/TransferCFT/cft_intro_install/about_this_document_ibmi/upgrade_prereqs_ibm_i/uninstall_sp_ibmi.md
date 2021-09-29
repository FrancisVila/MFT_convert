{
    "title": "Uninstall a service pack or patch",
    "linkTitle": "Uninstall a service pack or patch",
    "weight": "220"
}## Uninstall a service pack

When you apply a service pack, a backup of your previous version is saved in a SAVF object (named, for example, SPXSAV). This SAVF is located in your production library. You can use the UNINSTALL command, delivered in the program library, to uninstall a service pack and roll back to the previous version.

Follow these steps to uninstall a service pack:

1.  Stop Transfer CFT and Copilot.
2.  Call the UNINSTALL command, press F4, and complete the following fields:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFT Uninstall (UNINSTALL)</p>
<p> </p>
<p>Type choices, press Enter.</p>
<p>Silent installation . . . . . . '<strong>2</strong>'         1:Yes/2:No</p>
<p>CFT Program library . . . . . . CFTPGM Name</p>
<p>CFT Production library . . . . . CFTPROD Name</p>
<p>SAVF name of previous version . SPXSAV Name</p></td>
</tr>
</tbody>
</table>

-   Where:
    -   Parameter 1: Name of your program library
    -   Parameter 2: Name of your production library
    -   Parameter 3: Name of the SAVF where you saved your previous library when you updated Transfer CFT

1.  Press Enter. The patch or service pack is removed, and you are returned to the previous version.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">As with other Transfer CFT commands, ensure that your program library (CFTPGM) and production library are present in your EDTLIBL before calling the UNINSTALL command.</td>
</tr>
</tbody>
</table>

## Uninstall a patch

When you apply a patch, a backup of your previous version is saved in a SAVF object (for example, PATCHSAV). This SAVF file is located in your program library.

If you need to uninstall a patch, please restore the previous SAVF to your CFT program library (PATCHSAV by default).

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>RSTOBJ OBJ(*ALL) SAVLIB(CFTPGM) DEV(*SAVF) OBJTYPE(*ALL) SAVF(CFTPGM/PATCHSAV) OPTION(*ALL) RSTLIB(CFTPGM)</td>
</tr>
</tbody>
</table>
