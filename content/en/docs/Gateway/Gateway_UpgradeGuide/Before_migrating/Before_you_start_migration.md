{
    "title": "Before you start upgrade...",
    "linkTitle": "Before you start migration",
    "weight": "70"
}Before you start the upgrade, export the Gateway objects, Virtual File Directories and security objects as described in the following sections.

## Check pending transfers for routing

The upgrade must be made with no routing scheduled.

It is strongly advised to check the routing queue by using the <span class="code">pmqctl </span>command:

<span class="code">pmqctl info run\_time\\data\\router.pmq</span>

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

If both <span class="code">read\_index </span>and <span class="code">write\_index </span>have the same value, then the queue is empty.

Alternatively use the <span class="code">pmqcheck.sh </span>script. This gives a more readable form of the <span class="code">pmqctl </span>command output:

pmqcheck.sh

Checking file "\[…\]/V6.13/run\_time/data/router.pmq"

R2=66775 W2=66775 E2=4000000 D=0

"\[…\]/V6.13/run\_time/data/router.pmq" is empty

## Export Gateway objects

While the existing version of Gateway is running, use the <span class="code">pelbase </span>command to export the objects (Sites, Applications, Models...) to an editable output file (for example, <span class="code">output\_ file</span>).

Use the <span class="code">-append</span> parameter to concatenate at the end of the file. When using the <span class="code">-append </span>parameter, the order in which you export the objects is important. Export:

-   User Profiles **before** Users
-   Connection Gate Groups **before** Connection Gates
-   Super Connection Gate Groups **before** Super Connection Gates
-   Decision Rules **before** Rule Tables

### Export Users

When exporting Users, you must be logged in as administrator to export user passwords. If not, each character of the password appears as an asterisk in the output file. In this case you need to redefine the user passwords after upgrading to the new version of Gateway.

### Export command examples

-   Export Sites: <span class="code">  
    pelbase export\_site –f output\_file  
    </span>
-   Export Applications: <span class="code">  
    pelbase export\_appli –f output\_file –append</span>
-   Export Models:  
    <span class="code">pelbase export\_model –f output\_file –append</span>
-   Export Diffusion Lists: <span class="code">  
    pelbase export\_list –f output\_file –append</span>
-   Export User Profiles:  
    <span class="code">pelbase export\_profile –f output\_file –append</span>
-   Export Users:  
    <span class="code">pelbase export\_user –f output\_file –append</span>
-   Export Connection Gate Groups: <span class="code">  
    pelbase export\_cgategroup –f output\_file –append</span>
-   Export Connection Gates: <span class="code">  
    pelbase export\_cgate –f output\_file –append</span>
-   Export Decision Rules:  
    <span class="code">pelbase export\_decisionrule –f output\_file –append</span>
-   Export Rule Tables:  
    <span class="code">pelbase export\_ruletable –f output\_file –append</span>
-   Export Proxies:  
    <span class="code">pelbase export\_proxy –f output\_file –append</span>
-   Export Purge Models:  
    <span class="code">pelbase export\_purge\_model –f output\_file –append</span>
-   Export Property Lists:  
    <span class="code">pelbase export\_proplist –f output\_file –append</span>
-   Export Trading Partners:  
    <span class="code">pelbase export\_tradepart –f output\_file –append</span>
-   Export Axway Messaging connectors:  
    <span class="code">pelbase export\_xmsctor –f output\_file –append</span>
-   Export Super Connection Gate Groups:  
    <span class="code">pelbase export\_sgategroup –f output\_file –append</span>
-   Export Super Connection Gates:  
    <span class="code">pelbase export\_sgate –f output\_file –append</span>

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
         <td><p><span class="span_3">Site (</span><span class="code">site</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Application (</span><span class="code">appli</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Model (</span><span class="code">model</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Diffusion List (</span><span class="code">list</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">User (</span><span class="code">user</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">User profile (</span><span class="code">profile</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Connection Gate (</span><span class="code">cgate</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Connection Gate Group<span class="span_3"> (</span><span class="code">cgategroup</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Decision Rule (</span><span class="code">decisionrule</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Rule Table (</span><span class="code">ruletable</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Proxy (</span><span class="code">proxy</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Trading Partner (</span><span class="code">tradepart</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Axway Messaging connector<span class="span_3"> (</span><span class="code">xmsctor</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Property List (</span><span class="code">proplist</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Purge Model (</span><span class="code">purge_model</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p><span class="span_3">Super Connection Gate (</span><span class="code">sgate</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
      <tr>
         <td><p>Super Connection Gate Group <span class="span_3">(</span><span class="code">sgategroup</span><span class="span_3">)</span></p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
         <td><p>√</p>         </td>
      </tr>
   </tbody>
</table>

## Logical sites

It is not recommended to import Logical Sites. Logical Sites are still supported in this version of <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>, but are no longer accessible via the GUI.

## Export Virtual File Directories (VFD)

While the previous version of <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> is running, export Virtual File Directories to an output file that can be edited (for example, v<span class="code">fd\_output\_file</span>):

<span class="code">vfdbase export –f vfd\_output\_file</span>

## Export security objects

While the previous version of <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> is running, export security objects to an output file that can be edited. For example, to export Network Profiles to the file <span class="code">nprof\_output\_file</span>, enter:

secbase export\_netprof –f nprof\_output\_file

You can also export:

-   Security Profiles (sprof), using the <span class="code">secbase export\_sprof </span>command
-   SSH Security Profiles (sshprof), using the <span class="code">secbase export\_sshprof </span>command
-   Certificates, using the <span class="code">secbase export\_cert </span>command
-   Keys, using the <span class="code">secbase export\_key </span>command

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
