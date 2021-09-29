{
    "title": "PassPort AM persistent cache ",
    "linkTitle": "PassPort AM persistent cache ",
    "weight": "210"
}This section describes how to configure access management when not using Central Governance.

When enabled, Transfer CFT retrieves all permissions from the PassPort AM server and stores this information in the cache. This allows Transfer CFT to continue to operate using the stored information if the PassPort AM server is non-operational.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The user/password login are not stored in the cache. This means that if the PassPort server is down, you cannot connect to Copilot, Transfer CFT REST APIs, or the <span>Transfer CFT</span> UI.</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameters</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>am.passport.persistency.enable</td>
<td>Yes</td>
<td><p>Enables persistent support for PassPort AM.</p></td>
</tr>
<tr class="even">
<td>am.passport.persistency.fname</td>
<td>$(cft.runtime_dir)/data/CFTAM</td>
<td>Persistent cache file name for PassPort AM.</td>
</tr>
<tr class="odd">
<td>am.passport.persistency.check_interval</td>
<td>600</td>
<td><p>Interval in seconds between two checks of access management updates.</p>
<p>See also the information concerning CFTSXPAM or copsxpam below.</p></td>
</tr>
<tr class="even">
<td>am.passport.persistency.cftsxpam.enable</td>
<td>Yes</td>
<td>Enable the CFTSXPAM process, which updates the PassPort AM cache.</td>
</tr>
</tbody>
</table>

## Updating the cache

When Transfer CFT or Copilot is configured to use PassPort AM , it periodically scans for changes in user rights. The changes are then saved in the file defined in am.passport.persistency.fname. These scans occur at regular intervals as defined by the am.passport.persistency.check\_interval parameter.

-   To force an immediate cache update, you can manually run CFTSXPAM (as described below).
-   If a user (a non-superuser) is not listed in the cache and tries to start Transfer CFT, Transfer CFT cannot start and displays the [CFTX03W](../../../troubleshoot_intro/messages_and_error_codes_start_here/cftx_messages) error in the log. To fix, you can manually execute CFTSXPAM and restart Transfer CFT.

### Manually run CFTSXPAM

1.  Log on as a Transfer CFT superuser, meaning a user that is defined in `am.passport.superuser`.
2.  Load the Transfer CFT profile.
3.  Check that CFTSXPAM is enabled, am.passport.persistency.cftsxpam.enable = yes.
4.  Execute the command: CFTSXPAM

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">On z/OS platforms the offline version of the CFTSXPAM process is called CFTUXPAM.</td>
</tr>
</tbody>
</table>

#### Recommendation

When using LDAP in PassPort or Central Governance for access management, it is highly recommended that you run the CFTSXPAM process offline prior to starting Transfer CFT, or the Transfer CFT Copilot server, if the persistent cache does not exist. Neglecting to do so could result in a significant delay in the first login.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you need to troubleshoot the cache, you can see the information in <a href="../../../troubleshoot_intro/admin_troubleshooting_server/admin_troubleshooting_runtime/extract_am_cache">Extract the Access Management Cache</a>.</td>
</tr>
</tbody>
</table>
