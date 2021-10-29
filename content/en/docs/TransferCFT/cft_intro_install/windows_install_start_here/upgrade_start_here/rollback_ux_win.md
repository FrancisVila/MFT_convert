{
    "title": "Roll back to a previous version ",
    "linkTitle": "Roll back to a previous version",
    "weight": "210"
}This section describes the procedure to revert to the previous version if, for whatever reason, you need to roll back an upgrade. However, if you executed transfers in the upgraded version that used parameters or metadata that are not available in the earlier version, this metadata is lost when you roll back.

## Prerequisites

-   Download the installation package you want to downgrade to, noting that you can only downgrade to a version from which you have previously upgraded. For example, if you upgraded from version 3.4 directly to 3.8, you can only downgrade to version 3.4 and not to an intermediary version 3.6.
-   You must have already upgraded from Transfer CFT 3.4 or higher to Transfer CFT 3.9

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">On Unix systems, do not set the profile prior to upgrading. If you are in a session and the profile is set, exit the bash session before running the upgrade.         </td>
      </tr>
   </tbody>
</table>

## Procedure

Unix and Windows

Execute the following steps:

1.  Run the installation program that corresponds to the version you want to roll back. When prompted, enter the installation directory of the Transfer CFT instance to roll back.
2.  Start Transfer CFT to verify the procedure and check the version.
