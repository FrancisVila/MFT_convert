{
    "title": "Routing related EL for AR",
    "linkTitle": "Routing related EL for AR",
    "weight": "310"
}The following table provides the routing related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadE-Column1-Header1">Description / example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>routing.routePackageId</p>         </td>
         <td><p>The ID of current Route Package.</p>
<p><em>Example:</em></p>
<p><code>${routing.routePackageId.matches('&lt;id&gt;')}</code></p>         </td>
      </tr>
      <tr>
         <td><p>routing.routePackage<br />
SandboxFolder</p>         </td>
         <td><p>The master working directory of current execution of a Route Package;
located in <code>${user_home_dir}/.stfs/objects/${routePackageId(0,2)}/${routePackageId(3)}/;</code>
. The directory is same during route recovery and it is persisted with the event.</p>
<p><em>Example:</em></p>
<p><code>${!routing.routePackageSandboxFolder}</code></p>         </td>
      </tr>
      <tr>
         <td><p>routing.executeRoute<br />
SandboxFolder</p>         </td>
         <td><p>The working directory of current Execute Route (it is a subdirectory of <code>${routing.routePackageSandboxFolder}</code>).</p>
<p><em>Example:</em></p>
<p><code>${parentFolder(routing.executeRouteSandboxFolder) eq routing.routePackageSandboxFolder}</code></p>         </td>
      </tr>
      <tr>
         <td><p>${routing.originalFiles}</p>         </td>
         <td>List of file paths being selected for processing from the Subscription folder.         </td>
      </tr>
      <tr>
         <td><p>${routing.targetFiles}</p>         </td>
         <td><p>List of file paths to process in current Execute Route sandbox (these are copies of <code>${routing.originalFiles};</code>
located in <code>${routing.executeRouteSandboxFolder}</code>).</p>         </td>
      </tr>
      <tr>
         <td><p>routing.triggeredWithoutPayload</p>         </td>
         <td><p>Determines if the Route was triggered without any file(s) available for processing. This is determined by the <em>Submit the transferred file(s) to the route for processing.</em> checkboxes on the Advanced Routing subscription page.</p>
<p>Values:</p>
<ul>
<li><code>true</code></li>
<li><code>false</code></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
