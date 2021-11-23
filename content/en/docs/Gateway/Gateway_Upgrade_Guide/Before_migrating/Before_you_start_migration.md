{
    "title": "Before you start upgrade...",
    "linkTitle": "Before you start migration",
    "weight": "90"
}Before you start the upgrade, export the Gateway objects, Virtual File Directories and security objects as described in the following sections.

## Check pending transfers for routing

The upgrade must be made with no routing scheduled.

It is strongly advised to check the routing queue by using the `pmqctl `command:

`pmqctl info run_time\data\router.pmq`

Example output:

--

signature : a1b2c3d4

version\_major : 1

version\_minor : 0

status : 0

reader\_pid : 0

sequence : 30

sync\_seqn : 29

read\_index : 66775

write\_index : 66775

end\_index : 4000000

--

0 records total, 0 bytes total

If both `read_index `and `write_index `have the same value, then the queue is empty.

Alternatively use the `pmqcheck.sh `script. This gives a more readable form of the `pmqctl `command output:

pmqcheck.sh

Checking file "\[…\]/V6.13/run\_time/data/router.pmq"

R2=66775 W2=66775 E2=4000000 D=0

"\[…\]/V6.13/run\_time/data/router.pmq" is empty

## Export Gateway objects

While the existing version of Gateway is running, use the `pelbase `command to export the objects (Sites, Applications, Models...) to an editable output file (for example, `output_ file`).

Use the `-append` parameter to concatenate at the end of the file. When using the `-append `parameter, the order in which you export the objects is important. Export:

-   User Profiles **before** Users
-   Connection Gate Groups **before** Connection Gates
-   Super Connection Gate Groups **before** Super Connection Gates
-   Decision Rules **before** Rule Tables

### Export Users

When exporting Users, you must be logged in as administrator to export user passwords. If not, each character of the password appears as an asterisk in the output file. In this case you need to redefine the user passwords after upgrading to the new version of Gateway.

### Export command examples

-   Export Sites: `pelbase export_site –f output_file`
-   Export Applications: `pelbase export_appli –f output_file –append`
-   Export Models:  
    `pelbase export_model –f output_file –append`
-   Export Diffusion Lists: `pelbase export_list –f output_file –append`
-   Export User Profiles:  
    `pelbase export_profile –f output_file –append`
-   Export Users:  
    `pelbase export_user –f output_file –append`
-   Export Connection Gate Groups: `pelbase export_cgategroup –f output_file –append`
-   Export Connection Gates: `pelbase export_cgate –f output_file –append`
-   Export Decision Rules:  
    `pelbase export_decisionrule –f output_file –append`
-   Export Rule Tables:  
    `pelbase export_ruletable –f output_file –append`
-   Export Proxies:  
    `pelbase export_proxy –f output_file –append`
-   Export Purge Models:  
    `pelbase export_purge_model –f output_file –append`
-   Export Property Lists:  
    `pelbase export_proplist –f output_file –append`
-   Export Trading Partners:  
    `pelbase export_tradepart –f output_file –append`
-   Export Axway Messaging connectors:  
    `pelbase export_xmsctor –f output_file –append`
-   Export Super Connection Gate Groups:  
    `pelbase export_sgategroup –f output_file –append`
-   Export Super Connection Gates:  
    `pelbase export_sgate –f output_file –append`

The objects that can be exported or imported depend on the version of Gateway, as shown in the following table:

<table>
   <tbody>
      <tr>
         <td><p>Objects</p>         </td>
         <td><p>V6.17</p>         </td>
         <td><p>V6.16.0</p>         </td>
         <td><p>V6.16.1</p>         </td>
      </tr>
      <tr>
         <td><p><code>site</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>appli</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>model</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>list</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>user</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>profile</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>cgate</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Connection Gate Group<code>cgategroup</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>decisionrule</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>ruletable</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>proxy</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>tradepart</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Axway Messaging connector<code>xmsctor</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>proplist</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>purge_model</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><code>sgate</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Super Connection Gate Group <code>sgategroup</code></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
   </tbody>
</table>

## Logical sites

It is not recommended to import Logical Sites. Logical Sites are still supported in this version of {{< Gateway/gatewayname  >}}, but are no longer accessible via the GUI.

## Export Virtual File Directories (VFD)

While the previous version of {{< Gateway/gatewayname  >}} is running, export Virtual File Directories to an output file that can be edited (for example, v`fd_output_file`):

`vfdbase export –f vfd_output_file`

## Export security objects

While the previous version of {{< Gateway/gatewayname  >}} is running, export security objects to an output file that can be edited. For example, to export Network Profiles to the file `nprof_output_file`, enter:

secbase export\_netprof –f nprof\_output\_file

You can also export:

-   Security Profiles (sprof), using the `secbase export_sprof `command
-   SSH Security Profiles (sshprof), using the `secbase export_sshprof `command
-   Certificates, using the `secbase export_cert `command
-   Keys, using the `secbase export_key `command

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
