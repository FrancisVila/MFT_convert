{
    "title": "Special routing EL variables for AR",
    "linkTitle": "Special routing EL variables for AR",
    "weight": "330"
}The following table provides the special routing variables.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Variable</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>${currentfulltarget}</p>
         </td>
         <td>
            <p>Contains the path to the file in sandbox folder that is currently processed by a transformation or routing step.</p>
            <p>Used in PGP Encryption transformation steps and in Send to Partner and Publish To Account routing steps. Also, used in the Rename output file of Transformation steps.</p>
            <p>The expression is evaluated to the absolute file path of the file being processed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>${transformedfilename}</p>
         </td>
         <td>
            <p>Denotes the name of current transformed file. </p>
            <p>
 Used mainly in PGP and Compression steps (Transformation steps).</p>
            <p>Used in the <em>Rename output file to</em> pane.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>${transferredfilename}</p>
         </td>
         <td>
            <p>Denotes the name of last transferred file.</p>
            <p>It can be the same as ${currentfulltarget} or changed by using "Route file as"/"Publish file as" settings.</p>
            <p>Used in Routing steps (Publish/SendToPartner) in <em>Post Routing Action Rename</em> pane.
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>${transferredfilenames}</p>
         </td>
         <td>Contains the list of names of currently transferred files by the Send To Partner step. Files which were not processed by the Send To Partner step (because of the File Filter criteria) are not on this list. This variable should be used only in the <em>Trigger file content</em> field.         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [Account related EL for AR](../r_st_account_related)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
