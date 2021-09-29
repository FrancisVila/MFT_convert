{
    "title": "Forcing heterogeneous mode",
    "linkTitle": "Forcing heterogeneous mode",
    "weight": "350"
}# Force heterogeneous mode for a group of files



In <span>Transfer CFT</span> both homogeneous and heterogeneous mode are enabled by default. However, you may want to ensure that groups of files are transferred using only the heterogeneous mode. The UCONF configuration parameter<span> cft.server.force\_heterogeneous\_mode</span> allows you to do this, effectively disabling homogeneous mode even if the partner is configured for homogeneous exchanges.



For more information on sending groups of files and heterogeneous mode exchanges, see [Sending a group of files](../Transfers/Subm_transfers/Send_group_of_files_CL.htm).



To force heterogeneous mode:



1.  Access the unified configuration utility using either [command line](uconf_w_cftutil.htm) or the [GUI](../GUI/UCONF_interface_actions.htm).

2.  Set the following parameter to enable forced heterogeneous exchanges for group file transfers.



Unix/Windows



<table data-cellspacing="0">
<thead>
<tr>
<th>Parameter</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>cft.server.force_heterogeneous_mode</td>
<td>No</td>
<td><p>Force heterogeneous mode for group file transfers. This parameter replaces the deprecated environment variable: CFTSFMCPY.</p>
<p>Possible values:</p>
<ul>
<li>Yes: Force heterogeneous mode exchanges (override homogeneous mode)</li>
<li>No: Standard heterogeneous and homogeneous functioning</li>
</ul></td>
</tr>
</tbody>
</table>



Related topics



-   [Sending a group of files](../Transfers/Subm_transfers/Send_group_of_files_CL.htm)

-   [Environmental variables](../Windows/Env_variables_and_specific_parms.htm)

-   [File management functions (Windows)](../Windows/System_functions/File_management_functions.htm)

