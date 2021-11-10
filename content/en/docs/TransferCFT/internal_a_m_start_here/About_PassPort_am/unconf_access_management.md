{
    "title": "PassPort AM persistent cache ",
    "linkTitle": "PassPort AM persistent cache ",
    "weight": "210"
}This section describes how to configure access management when not using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

When enabled, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> retrieves all permissions from the PassPort AM server and stores this information in the cache. This allows <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to continue to operate using the stored information if the PassPort AM server is non-operational.

> **Note:**
>
> The user/password login are not stored in the cache. This means that if the PassPort server is down, you cannot connect to Copilot, Transfer CFT REST APIs, or the Transfer CFT UI.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameters         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Default         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>am.passport.persistency.enable         </td>
         <td>Yes         </td>
         <td><p>Enables persistent support for PassPort AM.</p>         </td>
      </tr>
      <tr>
         <td>am.passport.persistency.fname         </td>
         <td>$(cft.runtime_dir)/data/CFTAM         </td>
         <td>Persistent cache file name for PassPort AM.         </td>
      </tr>
      <tr>
         <td>am.passport.persistency.check_interval         </td>
         <td>600         </td>
         <td><p>Interval in seconds between two checks of access management updates.</p>
<p>See also the information concerning CFTSXPAM or copsxpam below.</p>         </td>
      </tr>
      <tr>
         <td>am.passport.persistency.cftsxpam.enable         </td>
         <td>Yes         </td>
         <td>Enable the CFTSXPAM process, which updates the PassPort AM cache.         </td>
      </tr>
   </tbody>
</table>

## Updating the cache

When Transfer CFT or Copilot is configured to use PassPort AM , it periodically scans for changes in user rights. The changes are then saved in the file defined in <span class="code">am.passport.persistency.fname</span>. These scans occur at regular intervals as defined by the <span class="code">am.passport.persistency.check\_interval</span> parameter.

-   To force an immediate cache update, you can manually run CFTSXPAM (as described below).
-   If a user (a non-superuser) is not listed in the cache and tries to start Transfer CFT, Transfer CFT cannot start and displays the [CFTX03W](../../../troubleshoot_intro/messages_and_error_codes_start_here/cftx_messages) error in the log. To fix, you can manually execute CFTSXPAM and restart Transfer CFT.

### Manually run CFTSXPAM

1.  Log on as a Transfer CFT superuser, meaning a user that is defined in `am.passport.superuser`.
2.  Load the Transfer CFT profile.
3.  Check that CFTSXPAM is enabled, <span class="code">am.passport.persistency.cftsxpam.enable = yes</span>.
4.  Execute the command: <span class="code">CFTSXPAM</span>

> **Note:**
>
> On z/OS platforms the offline version of the CFTSXPAM process is called CFTUXPAM.

#### Recommendation

When using LDAP in PassPort or <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> for access management, it is highly recommended that you run the CFTSXPAM process offline prior to starting Transfer CFT, or the Transfer CFT Copilot server, if the persistent cache does not exist. Neglecting to do so could result in a significant delay in the first login.

> **Note:**
>
> If you need to troubleshoot the cache, you can see the information in Extract the Access Management Cache.
