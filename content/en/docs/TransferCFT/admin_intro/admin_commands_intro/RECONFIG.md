{
    "title": "RECONFIG - Modify the configuration",
    "linkTitle": "RECONFIG - Modify the configuration",
    "weight": "340"
}# <span id="RECONFIG___Updating_the_configuration"></span>Manage configuration updates - RECONFIG



Use this command to manage configuration updates for the types listed below.



Syntax



RECONFIG



\[ [TYPE](../Parameter_index/type.htm)

= { <span>CRON</span> | UCONF | CAT | FOLDER  | PARMCACHE | AM

} \]



CRON



When the type is set to CRON, Transfer CFT sends a notification to reload the

enabled CRONJOBs. This command is used when a CFTCRON has been modified by:



-   Inserting a new cronjob (with

    a CRONTAB value that matches the CRONTABS list)

-   Deleting a new cronjob

-   Modifying a cronjob



Messages are then displayed in the log ([CFTI36I](../../Troubleshooting/Messages_and_Codes/CFTI_messages.htm) and [CFTI37I](../../Troubleshooting/Messages_and_Codes/CFTI_messages.htm)).



For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=CRON</td>
</tr>
</tbody>
</table>



UCONF



When TYPE=UCONF, the UCONF reconfigurable variables are reloaded. Messages are then displayed in the log ([CFTS43I](../../Troubleshooting/Messages_and_Codes/CFTS_messages.htm)). Note that only the UCONF parameters flagged with RECONFIG/IRECONFIG are affected.



For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=UCONF</td>
</tr>
</tbody>
</table>



CAT



Use this type parameter to dynamically increase the catalog size. Messages are then displayed in the log ([CFTC13I](../../Troubleshooting/Messages_and_Codes/CFTC_messages.htm) and [CFTC13E](../../Troubleshooting/Messages_and_Codes/CFTC_messages.htm)). An additional parameter when using CAT is RECNB (number of records in the catalog). For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=CAT,RECNB=xxx</td>
</tr>
</tbody>
</table>



FOLDER



Use this command if you need to reload the folder objects after a modification. For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=FOLDER</td>
</tr>
</tbody>
</table>



PARMCACHE



Use this parameter to clear the cache while Transfer CFT is running. After the command execution, all changes applied to dynamic objects are taken into account, without restarting Transfer CFT. If you have set the UCONF <span>cft.server.parm.cache\_size</span> value to something other than zero (0), this command reloads both the CFTPART and CFTPARM objects. For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=PARMCACHE</td>
</tr>
</tbody>
</table>



AM



Reload roles (CFTROLE) and privileges (CFTPRIV). You can manually create these objects or they can be deployed via Flow Manager. For more information on CFTROLEs and CFTPRIVs, please see <a href="../../../internal_a_m_start_here/fm_access_management">Access Management using Flow Manager</a>. For example:



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL RECONFIG TYPE=AM</td>
</tr>
</tbody>
</table>
