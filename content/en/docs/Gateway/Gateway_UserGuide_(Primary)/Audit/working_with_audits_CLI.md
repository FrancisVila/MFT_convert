{
    "title": "Working with Audits (command line)",
    "linkTitle": "Working with Audits (command line)",
    "weight": "210"
}-   <a href="#pelbase_export_audit" class="MCXref xref">pelbase export_audit</a>
-   <a href="#pelctl_archive_audit" class="MCXref xref">pelctl archive_audit: Archive the audit</a>
-   <a href="#pelauditexport" class="MCXref xref">pelauditexport: export audit file when Gateway is stopped</a>

<span id="pelbase_export_audit"></span>

## pelbase export\_audit

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><code>pelbase export_audit [-audit_file(-af)][-from_date(-fd)][-to_date(-td)][-username(-user)][-resource_type(-rt) ][-resource_name(-rn)][-action_type(-at) ][-action_result(-ar) ][-output(-f) output_filename][-append(-ap)]</code></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Exports the audit file; see <a href="../" class="MCXref xref">Managing Audit files</a></p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><p><code>-audit_file(-af) full_path_to_audit_filename</code></p>         </td>
      </tr>
      <tr>
         <td><p><code>-from_date(-fd)</code> start date of exported data</p>         </td>
      </tr>
      <tr>
         <td><p><code>-to_date(-td)</code> end date of exported data</p>         </td>
      </tr>
      <tr>
         <td><p><code>-resource_type(-rt)</code></p>
<p>The resource can be one of the following: Application | CGate | CGateGroup | SGate | SGateGroup | DecisionRule | RuleTable | DiffusionList | Log | Model | Profile | User | Proxy | Site | LocalSite | Transfer | TradingPart | VFD | Config | Certificate | Key | TlsProfile | NetworkProfile | SshProfile | Statistics | Trace | PurgeModel | PRopertyList | ConnectedUser | Audit | Connection</p>         </td>
      </tr>
      <tr>
         <td><p><code>-resource_name(-rn) </code>specify the name of a resource to export audits for</p>         </td>
      </tr>
      <tr>
         <td><p><code>-action_type(-at) </code></p>
<p>Can be one of the following: Read | Create | Delete | Update | Admin | Login | Logout | Start | Stop | Cancel | Suspend | Resume | Block | Unblock | Archive | Append | Rotate | Truncate | Load | Rebuild | Mount | Unmount | Purge | Disconnect | Reset | AcquireSwQueue | ReleaseSwQueue | CreateSwOutputChannel | DeleteSwOutputChannel | OpenSwOutputChannel | CloseSwOutputChannel | CreateSwInputChannel | DeleteSwInputChannel | OpenSwInputChannel | CloseSwInputChannel | Invalidate<code></code></p>         </td>
      </tr>
      <tr>
         <td><p><code>-action_result(-ar)</code></p>
<p>Can be one of the following: A(ttempt) | S(uccess) | F(ailed) | D(enied)</p>         </td>
      </tr>
      <tr>
         <td><code>-output(-f)</code> specify the filename of the audit output         </td>
      </tr>
      <tr>
         <td><code>-append(-ap)</code>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><br />

<p><code>pelbase export_audit -f my_audit_file.txt</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_archive_audit"></span>

## pelctl archive\_audit: Archive the audit

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>pelctl archive_audit</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command archives the audit file (similarly to <code>archive_log </code>command) in order to limit the size of the audit file. To automatize the process of audit file archiving, you can create a scheduler to call a script in which the archive command it run.</p>
<p><strong>Recommendation:</strong> Archive the audit file regularly to avoid the file becoming too large.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

  
<span id="pelctl_suspend_log"></span><span id="pelauditexport"></span>

## pelauditexport: export audit file when Gateway is stopped

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><span class="code"><strong>pelauditexport</strong> [-audit_file(-af)][-from_date(-fd)][-to_date(-td)][-username(-user)][-resource_type(-rt) ][-resource_name(-rn)][-action_type(-at) ][-action_result(-ar) ][-output(-f) output_filename][-append(-ap)]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Exports the audit file. It is similar to the <span class="code">pelbase export_audit </span>command, except it can also be used when Gateway is stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>
<p>all optional</p>         </td>
         <td><span class="code">-audit_file(-af) </span>audit file name (specify the full path)<span class="code"></span>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-from_date(-fd) </span> specify the start date of exported data</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-to_date(-td)</span> end date of exported data</p>         </td>
      </tr>
      <tr>
         <td><span class="code">username(-user)</span> export only audits for a given user         </td>
      </tr>
      <tr>
         <td><p><span class="code">-resource_type(-rt)</span></p>
<p>The resource can be one of the following: Application | CGate | CGateGroup | SGate | SGateGroup | DecisionRule | RuleTable | DiffusionList | Log | Model | Profile | User | Proxy | Site | LocalSite | Transfer | TradingPart | VFD | Config | Certificate | Key | TlsProfile | NetworkProfile | SshProfile | Statistics | Trace | PurgeModel | PRopertyList | ConnectedUser | Audit | Connection</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-resource_name(-rn) </span>specify the name of a resource to export audits for</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-action_type(-at)</span></p>
<p>Can be one of the following: Read | Create | Delete | Update | Admin | Login | Logout | Start | Stop | Cancel | Suspend | Resume | Block | Unblock | Archive | Append | Rotate | Truncate | Load | Rebuild | Mount | Unmount | Purge | Disconnect | Reset | AcquireSwQueue | ReleaseSwQueue | CreateSwOutputChannel | DeleteSwOutputChannel | OpenSwOutputChannel | CloseSwOutputChannel | CreateSwInputChannel | DeleteSwInputChannel | OpenSwInputChannel | CloseSwInputChannel | Invalidate<span class="code"></span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-action_result(-ar)</span></p>
<p>Can be one of the following: A(ttempt) | S(uccess) | F(ailed) | D(enied)</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-output(-f)</span> specify the filename of the audit output         </td>
      </tr>
      <tr>
         <td><span class="code">-append(-ap) </span>append audit at the end of an existing audit file <span class="code"></span>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_resume_log"></span>

## 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)