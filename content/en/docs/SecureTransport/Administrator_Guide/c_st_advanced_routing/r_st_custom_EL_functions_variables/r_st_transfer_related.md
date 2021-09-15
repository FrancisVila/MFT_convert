{
    "title": "Transfer related EL for AR",
    "linkTitle": "Transfer related EL for AR",
    "weight": "350"
}The transfer related EL expressions are derived from the use case where:

-   A LDAP user has an account template (*template-routes*) which is:
    -   Subscribed to an Advanced Routing application - *ba* and assigned:
        -   Subscription folder - (*/ba*)
        -   Business unit - (*bu*)
        -   Account home folder - `/home/vusers/bu/user`
        -   Account email address - `usert@axway.int`
        -   LDAP domain - *ad*

The user logs in over HTTPS and uploads a file `partner_certificate.crt` in the subscription folder under its home folder.

The following table provides the transfer related EL expressions from the use case.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Agent Env Variable </th>
         <th>Routing EL expression</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>DXAGENT_CORE_ID</p>
         </td>
         <td>
            <p>transfer.coreId</p>
         </td>
         <td>
            <p><code>${transfer.coreId eq "390bedec-c82e-45aa-afc2-1b78d846732d"}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TARGETPATH</p>
         </td>
         <td>
            <p>transfer.targetDirFull</p>
         </td>
         <td>
            <p><span>${parentFolder(transfer.targetDirFull) eq account.home}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TRANSFERRED_BYTES </p>
         </td>
         <td>
            <p>transfer.<br/>transferredBytes</p>
         </td>
         <td>
            <p><span>${transfer.transferredBytes ge 20}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TRANSFER_STATUS_START_TIME</p>
         </td>
         <td>
            <p>transfer.startTime</p>
         </td>
         <td>
            <p><span>${transfer.startTime lt transfer.endTime}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TIMESTAMP_INCOMING_END</p>
         </td>
         <td>
            <p>transfer.endTime</p>
         </td>
         <td>
            <p><span>${transfer.endTime gt transfer.startTime}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_XFERTYPE</p>
         </td>
         <td>
            <p>transfer.xferType</p>
         </td>
         <td>
            <p><span>${transfer.xferType eq "A"}</span>
</p>
            <p><span>${transfer.xferType eq "I"}</span>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TARGETDIR</p>
         </td>
         <td>
            <p>transfer.targetDir</p>
         </td>
         <td>
            <p><span>${concat(transfer.targetDir.substring(0,1), leadingFolder(session.workDir)) eq transfer.targetDir}</span> - returns true</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_FULLTARGET</p>
         </td>
         <td>
            <p>transfer.targetFull</p>
         </td>
         <td>
            <p><span>${filename(transfer.targetFull).matches('part.*.crt')}</span> - returns true</p>
            <p><span>${extension(transfer.target) eq extension(filename(transfer.targetFull))}</span> - returns true </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_TARGET</p>
         </td>
         <td>
            <p>transfer.target</p>
         </td>
         <td>
            <p><span>${transfer.target.matches('.*.crt') ? 1 : 0}</span> 
- will return 1</p>
            <p><span>${extract(basename(transfer.target),'_',1) eq 'partner1'}</span> 
- will return true</p>
            <p>${basename(transfer.target).replace('(.*)_(.*)', '$2_$1') eq 'certificate_partner')
                        </p>
         </td>
      </tr>
   </tbody>
</table>

## Additional transfer related expressions

The following table provides additional transfer related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Routing EL expressions</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>transfer.trigger</p>
         </td>
         <td>
            <p>Determines the transfer trigger.</p>
            <p>Values:</p>
            <ul>
               <li><code>server_pull</code> - If the routing was started by a server initiated pull.               </li>
               <li><code>client_download</code> - If the routing was started by a client download.               </li>
               <li><code>client_upload</code> - If the routing was started by a client upload.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>transfer.status</p>
         </td>
         <td>
            <p>Determines the transfer status.</p>
            <p>Values:</p>
            <p><code>success</code> - If the routing was started by a success.</p>
            <p><code>failure</code> - If the routing was started by a failure.</p>
            <p><code>temporary_failure</code> - If the routing was started by a temporary failure.</p>
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
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
