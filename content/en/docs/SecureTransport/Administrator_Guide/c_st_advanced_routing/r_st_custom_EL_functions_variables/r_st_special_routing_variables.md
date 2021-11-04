{
    "title": "Special routing EL variables for AR ",
    "linkTitle": "Special routing EL variables for AR",
    "weight": "320"
}The following table provides the special routing variables.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Variable         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>${currentfulltarget}</p>         </td>
         <td><p>Contains the path to the file in sandbox folder that is currently processed by a transformation or routing step.</p>
<p>Used in PGP Encryption transformation steps and in Send to Partner and Publish To Account routing steps. Also, used in the Rename output file of Transformation steps.</p>
<p>The expression is evaluated to the absolute file path of the file being processed.</p>         </td>
      </tr>
      <tr>
         <td><p>${transformedfilename}</p>         </td>
         <td><p>Denotes the name of current transformed file.</p>
<p>Used mainly in PGP and Compression steps (Transformation steps).</p>
<p>Used in the <em>Rename output file to</em> pane.</p>         </td>
      </tr>
      <tr>
         <td><p>${transferredfilename}</p>         </td>
         <td><p>Denotes the name of last transferred file.</p>
<p>It can be the same as ${currentfulltarget} or changed by using "Route file as"/"Publish file as" settings.</p>
<p>Used in Routing steps (Publish/SendToPartner) in <em>Post Routing Action Rename</em> pane.</p>         </td>
      </tr>
      <tr>
         <td><p>${transferredfilenames}</p>         </td>
         <td>Contains the list of names of currently transferred files by the Send To Partner step. Files which were not processed by the Send To Partner step (because of the File Filter criteria) are not on this list. This variable should be used only in the <em>Trigger file content</em> field.         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
