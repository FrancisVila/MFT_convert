{
    "title": "Routing related EL for AR",
    "linkTitle": "Routing related EL for AR",
    "weight": "320"
}The following table provides the routing related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Routing EL expression</th>
<th colspan="2">Description / example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>routing.routePackageId</p>
         </td>
         <td colspan="2">
            <p>The ID of current Route Package. </p>
            <p><i>Example:</i>
</p>
            <p><code>${routing.routePackageId.matches('&lt;id&gt;')}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>routing.routePackage<br/>SandboxFolder</p>
         </td>
         <td colspan="2">
            <p>The master working directory of current execution of a Route Package; 
 located in <code>${user_home_dir}/.stfs/objects/${routePackageId(0,2)}/${routePackageId(3)}/;</code>
. The directory is same during route recovery and it is persisted with the event.</p>
            <p><i>Example:</i>
</p>
            <p><code>${!routing.routePackageSandboxFolder}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>routing.executeRoute<br/>SandboxFolder</p>
         </td>
         <td colspan="2">
            <p>The working directory of current Execute Route (it is a subdirectory of <code>${routing.routePackageSandboxFolder}</code>).</p>
            <p><i>Example:</i>
</p>
            <p><code>${parentFolder(routing.executeRouteSandboxFolder) eq routing.routePackageSandboxFolder}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>${routing.originalFiles}</p>
         </td>
         <td colspan="2">List of file paths being selected for processing from the Subscription folder.         </td>
      </tr>
      <tr>
         <td>
            <p>${routing.targetFiles}</p>
         </td>
         <td colspan="2">
            <p>List of file paths to process in current Execute Route sandbox (these are copies of <code>${routing.originalFiles};</code> 
 located in <code><code>${routing.executeRouteSandboxFolder}</code>).</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <p>routing.triggeredWithoutPayload</p>
         </td>
         <td colspan="2">
            <p>Determines if the Route was triggered without any file(s) available for processing. This is determined by the <em>Submit the transferred file(s) to the route for processing.</em> checkboxes on the Advanced Routing subscription page.</p>
            <p>Values:</p>
            <ul>
               <li><code>true</code>
               </li>
               <li><code>false</code>
               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [Account related EL for AR](../r_st_account_related)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
