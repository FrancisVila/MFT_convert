{
    "title": "SWIFTNet ASP check commands",
    "linkTitle": "ASP & RMA: filtering",
    "weight": "300"
}{{< Gateway/componentlongname  >}}: Connectors

[pelctl reload\_asp\_profiles](#pelctl_reload_asp_profiles)

[pelctl check\_asp\_status](#pelctl_check_asp_status)

<span id="pelctl_reload_asp_profiles"></span>

## pelctl reload\_asp\_profiles: Trigger reload of ASPs

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>pelctl reload_asp_profiles</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command triggers reloading of ASPs. This is useful when you have:</p>
<ul>
<li>Updated the current ASP profiles directory.</li>
<li>Modified the ASP directory path and want to reload the ASPs from the new directory without restarting {{< Gateway/componentshortname  >}}.</li>
</ul>
<p>If the reload operation fails, the last successful loaded ASP package files remains in use. When more ASP helpers are configured, the reload is considered successful only if all helpers loaded the ASP package.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Log output for a successfully reloaded ASP package:</p>
<p>SNET I ASPLDSTS Swift ASP package reload done. Files: 179, Date: 20120319, Start: 145726, Stop: 145726</p>
<p>Log output for a failed ASP package reloading operation:</p>
<p>SNET E ASPLDSTS Swift ASP package reload failed. Reason: Could not open or parse the digest file : [D:\swift7_official_asp_package\ApplProf.dig], ErrNo: 16, Date: 20120319, Start: 150433, Stop: 150433, Previous active load: NONE!</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_check_asp_status"></span>

## pelctl check\_asp\_status: Check result of ASPs reload

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>pelctl check_asp_status</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command checks the result of an operation to reload ASPs.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Log output for a successfully reloaded ASP package:</p>
<p>ASP profiles reloaded status: Ok.</p>
<p>Load started/finished: 03/19/2012 10:42:54 / 03/19/2012 10:42:59.</p>
<p>Last successful load: 03/19/2012 10:42:59, 179 ASP profiles loaded.</p>
<p>ASP directory for loading: D:\swift7_official_asp_package.</p>
<p>Log output for a failed ASP package loading:</p>
<p>ASP profiles loaded status: error encountered during load process.</p>
<p>Last load attempt: 01/26/2012 17:46:38</p>
<p>Last successful load: 01/26/2012 17:44:29, 179 ASP profiles loaded.</p>
<p>Error code: 16, error message: Could not open or parse the digest file : [D:\wrong_asp_package_dir/ApplProf.dig]</p>
<p>ASP directory for loading: D:\swift7_official_asp_package.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[SWIFTNet ASP check](swiftnet_asp_check)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
