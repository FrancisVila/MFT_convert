{
    "title": "Session related EL for AR",
    "linkTitle": "Session related EL for AR",
    "weight": "260"
}The following table provides the session related EL expressions:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Agent Env Variable         </th>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>DXAGENT_PROTOCOL</p>         </td>
         <td><p>session.protocol</p>         </td>
         <td><code>${session.protocol eq 'http'}</code>
- returns <code>true</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PWD=/</p>         </td>
         <td><p>session.workDir</p>         </td>
         <td><code>${concat(transfer.targetDir.substring(0,1), leadingFolder(session.workDir)) eq transfer.targetDir}</code> - returns <code>true</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_PWD_RESOLVED</p>         </td>
         <td><p>session.workDirFull</p>         </td>
         <td><code>${session.workDirFull.substring(13,15) eq account.businessUnit.name}</code> - returns <code>true</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_REMOTEADDR</p>         </td>
         <td><p>session.remoteAddress</p>         </td>
         <td><code>${session.remoteAddress eq session.remoteHost}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_REMOTEHOST</p>         </td>
         <td><p>session.remoteHost</p>         </td>
         <td><p><code>${session.remoteHost.matches('10.*')}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_CLIENT</p>         </td>
         <td><p>session.streamingClient</p>         </td>
         <td><p><code>${session.streamingClient eq 'httpd'}</code></p>
<p><code>${extract(session.streamingClient,'d',1) eq session.protocol} </code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_SECURE_DATA</p>         </td>
         <td><p>session.isSSL</p>         </td>
         <td><p><code>${session.isSSL}</code></p>
<p><code>${!session.isSSL}</code></p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TYPE</p>         </td>
         <td><p>session.transferDirection</p>         </td>
         <td><p>The direction of the transfer configuration.</p>
<p>Values:</p>
<ul>
<li><code>0</code> indicates a transfer from an account to the application.</li>
<li><code>1</code> indicates a transfer from the application to an account.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_TIMESTAMP_OUTGOING_END</p>         </td>
         <td><p>session.timestampOutgoingEnd</p>         </td>
         <td><p><code>${session.timestampOutgoingEnd}</code> - the timestamp for events with outgoing type and trigger end.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_LOGFILENAME</p>         </td>
         <td><p>session.logFileName</p>         </td>
         <td><p><code>${session.logFileName}</code> - the log file name. This will be used by runas utility on Unix to redirect stderr.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_EDGEID</p>         </td>
         <td><p>session.edgeId</p>         </td>
         <td><p><code>${session.edgeId}</code> - the identifier of the current {{< SecureTransport/componentshortname  >}} Edge. The Edge identification string is set in the protocol server's configuration file(s).</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_SUBSCRIPTION_FOLDER</p>         </td>
         <td><p>session.subscriptionFolder</p>         </td>
         <td><p><code>${session.subscriptionFolder}</code> - the subscription folder in the form of a POSIX-style path relative to the user home directory. This value represents the client path.</p>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_APPLICATION_TYPE</p>         </td>
         <td><p>session.applicationType</p>         </td>
         <td><code>${session.applicationType}</code> - a string that identifies application type.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_APPLICATION_NAME</p>         </td>
         <td><p>session.applicationName</p>         </td>
         <td><code>${session.applicationName}</code> - the name of the application instance.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_APPLICATION_NOTES</p>         </td>
         <td><p>session.applicationNotes</p>         </td>
         <td><code>${session.applicationNotes}</code> - notes associated with the application instance.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_SITE_ATTR_UPLOAD_FOLDER</p>         </td>
         <td><p>session.siteUploadFolder</p>         </td>
         <td><code>${session.siteUploadFolder} </code>- the upload folder specifies the directory on the remote server where the uploaded files are placed.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_SITE_ATTR_USERNAME</p>         </td>
         <td><p>session.siteUsername</p>         </td>
         <td><code>${session.siteUsername} </code>- the username presented to the remote server for authentication; optional Site attribute.         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_SITE_ATTR_HOST</p>         </td>
         <td><p>session.siteHost</p>         </td>
         <td><code>${session.siteHost}</code> - the remote host represented by the site. If absent, the site does not establish a connection to the remote host. An example of that is the Folder Monitor site.         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
