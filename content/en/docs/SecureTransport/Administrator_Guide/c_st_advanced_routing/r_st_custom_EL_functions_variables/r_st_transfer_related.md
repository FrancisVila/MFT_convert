{
    "title": "Transfer related EL for AR",
    "linkTitle": "Transfer related EL for AR",
    "weight": "340"
}The transfer related EL expressions are derived from the use case where:

-   A LDAP user has an account template (*template-routes*) which is:
    -   Subscribed to an {{< SecureTransport/advancedrouting >}} application - *ba* and assigned:
        -   Subscription folder - (*/ba*)
        -   Business unit - (*bu*)
        -   Account home folder - `/home/vusers/bu/user`
        -   Account email address - `usert@axway.int`
        -   LDAP domain - *ad*

The user logs in over HTTPS and uploads a file `partner_certificate.crt` in the subscription folder under its home folder.

The following table provides the transfer related EL expressions from the use case.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Agent Env Variable         </th>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>DXAGENT_CORE_ID</p>         </td>
         <td><p>transfer.coreId</p>         </td>
         <td><p><code>${transfer.coreId eq "390bedec-c82e-45aa-afc2-1b78d846732d"}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TARGETPATH</p>         </td>
         <td><p>transfer.targetDirFull</p>         </td>
         <td><p><code>${parentFolder(transfer.targetDirFull) eq account.home}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TRANSFERRED_BYTES</p>         </td>
         <td><p>transfer.<br />
transferredBytes</p>         </td>
         <td><p><code>${transfer.transferredBytes ge 20}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TRANSFER_STATUS_START_TIME</p>         </td>
         <td><p>transfer.startTime</p>         </td>
         <td><p><code>${transfer.startTime lt transfer.endTime}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TIMESTAMP_INCOMING_END</p>         </td>
         <td><p>transfer.endTime</p>         </td>
         <td><p><code>${transfer.endTime gt transfer.startTime}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_XFERTYPE</p>         </td>
         <td><p>transfer.xferType</p>         </td>
         <td><p><code>${transfer.xferType eq "A"}</code></p>
<p><code>${transfer.xferType eq "I"}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TARGETDIR</p>         </td>
         <td><p>transfer.targetDir</p>         </td>
         <td><p><code>${concat(transfer.targetDir.substring(0,1), leadingFolder(session.workDir)) eq transfer.targetDir}</code> - returns true</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_FULLTARGET</p>         </td>
         <td><p>transfer.targetFull</p>         </td>
         <td><p><code>${filename(transfer.targetFull).matches('part.*.crt')}</code> - returns true</p>
<p><code>${extension(transfer.target) eq extension(filename(transfer.targetFull))}</code> - returns true</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TARGET</p>         </td>
         <td><p>transfer.target</p>         </td>
         <td><p><code>${transfer.target.matches('.*.crt') ? 1 : 0}</code>
- will return 1</p>
<p><code>${extract(basename(transfer.target),'_',1) eq 'partner1'}</code>
- will return true</p>
<p>${basename(transfer.target).replace('(.*)_(.*)', '$2_$1') eq 'certificate_partner')</p>         </td>
      </tr>
   </tbody>
</table>

## Additional transfer related expressions

The following table provides additional transfer related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Routing EL expressions         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>transfer.trigger</p>         </td>
         <td><p>Determines the transfer trigger.</p>
<p>Values:</p>
<ul>
<li><code>server_pull</code> - If the routing was started by a server initiated pull.</li>
<li><code>client_download</code> - If the routing was started by a client download.</li>
<li><code>client_upload</code> - If the routing was started by a client upload.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>transfer.status</p>         </td>
         <td><p>Determines the transfer status.</p>
<p>Values:</p>
<p><code>success</code> - If the routing was started by a success.</p>
<p><code>failure</code> - If the routing was started by a failure.</p>
<p><code>temporary_failure</code> - If the routing was started by a temporary failure.</p>         </td>
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
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
