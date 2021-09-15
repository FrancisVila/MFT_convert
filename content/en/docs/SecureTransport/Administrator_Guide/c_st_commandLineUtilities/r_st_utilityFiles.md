{
    "title": "Utility files",
    "linkTitle": "Utility files",
    "weight": "260"
}SecureTransport includes the utility files listed in the following table:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Utility file</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>bounce
                            </p>
         </td>
         <td>Bounces the <span>SecureTransport</span> protocol servers. If run on a primary server of a cluster, it will also bounce all the secondary servers.         </td>
      </tr>
      <tr>
         <td>
            <p>collect_support_information
                            </p>
         </td>
         <td>Collects information for <span>Axway</span> Global Support as specified on the <em>Support Tool Configuration</em> page.         </td>
      </tr>
      <tr>
         <td>
            <p>gencsr
                            </p>
         </td>
         <td>Generates a key pair and the associated certificate request file. Users can submit the CSR file to a CA to get a CA-issued certificate.         </td>
      </tr>
      <tr>
         <td>
            <p>log_export
                            </p>
         </td>
         <td>Export server log or File Tracking (transfer log) entries from the database in CSV or DBF format.         </td>
      </tr>
      <tr>
         <td>
            <p>mkadmin
                            </p>
         </td>
         <td>Adds a new administrator account or changes the password of an existing administrator account. Changes are automatically synchronized across all servers in a Standard Cluster or Enterprise Cluster, unless the <code>-sync=n</code> option is present.         </td>
      </tr>
      <tr>
         <td>
            <p>repconv
                            </p>
         </td>
         <td>
            <p>Updates repository encryption by decrypting files encrypted in a previous version of <span>SecureTransport</span> and encrypting them for the current version. Can also change the cipher algorithm and certificate <span>SecureTransport</span> uses to encrypt files and decrypt files and folders. </p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>show_ports
                            </p>
         </td>
         <td>Displays the ports on which the servers are configured to run.         </td>
      </tr>
      <tr>
         <td colspan="2"><b>Start scripts</b>
         </td>
      </tr>
      <tr>
         <td>
            <p>start_admin
                            </p>
         </td>
         <td>Starts the Administration Tool server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_all
                            </p>
         </td>
         <td>Starts all <span>SecureTransport</span> servers.         </td>
      </tr>
      <tr>
         <td>
            <p>start_as2d
                            </p>
         </td>
         <td>Starts the AS2 server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_db
                            </p>
         </td>
         <td>Starts the embedded database server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_ftpd
                            </p>
         </td>
         <td>Starts the FTP server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_httpd
                            </p>
         </td>
         <td>Starts the HTTP server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_pesitd
                            </p>
         </td>
         <td>Starts the PeSIT server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_sshd
                            </p>
         </td>
         <td>Starts the SSH server.         </td>
      </tr>
      <tr>
         <td>
            <p>start_tm
                            </p>
         </td>
         <td>Starts Transaction Manager.         </td>
      </tr>
      <tr>
         <td colspan="2"><b>Stop scripts</b>
         </td>
      </tr>
      <tr>
         <td>
            <p>stop_admin
                            </p>
         </td>
         <td>Stops the Administration Tool server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_all
                            </p>
         </td>
         <td>Stops all <span>SecureTransport</span> servers.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_as2d
                            </p>
         </td>
         <td>Stops the AS2 server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_db
                            </p>
         </td>
         <td>Stops the embedded database server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_ftpd
                            </p>
         </td>
         <td>Stops the FTP server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_httpd
                            </p>
         </td>
         <td>Stops the HTTP server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_tm
                            </p>
         </td>
         <td>Stops Transaction Manager.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_pesitd
                            </p>
         </td>
         <td>Stops the PeSIT server.         </td>
      </tr>
      <tr>
         <td>
            <p>stop_sshd
                            </p>
         </td>
         <td>Stops the SSH server.         </td>
      </tr>
      <tr>
         <td colspan="2">
<p colspan="2"><b>Status scripts</b>
</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>status_ftpd
                            </p>
         </td>
         <td> Checks the status of the FTP server.         </td>
      </tr>
      <tr>
         <td>
            <p>status_socks
                            </p>
         </td>
         <td>Checks the status of the SOCKS5 proxy. Only available on Edge.
						         </td>
      </tr>
      <tr>
         <td>
            <p>status_httpd
                            </p>
         </td>
         <td>
            <p> Checks the status of the HTTP server.</p>
            <p> </p>
            <p>The following example is applicable to <code>status_ftpd</code>  as well: you can expect the same messages with either in the place of <code>status_httpd</code>.</p>
            <ul>
               <li><code>status_httpd</code> returns <code>'httpd is disabled'</code>, when all http listeners are disabled.               </li>
               <li><code>status_httpd</code> returns <code>'httpd is alive'</code>, when at least one http listener is enabled, and it is functional.               </li>
               <li><code>status_httpd</code> returns <code>'httpd is down'</code>, when at least one http listener is enabled, and it is stopped or it is not functional.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>status_as2d
                            </p>
         </td>
         <td> Checks the status of the AS2 server.         </td>
      </tr>
      <tr>
         <td>
            <p>status_pesitd
                            </p>
         </td>
         <td>Checks the status of the PeSIT server.         </td>
      </tr>
      <tr>
         <td>
            <p>status_sshd
                            </p>
         </td>
         <td>
            <p>Checks the status of the SSH proxy.</p>
            <p> </p>
            <p>The following example is applicable to <code>status_as2d</code> and <code>status_pesitd</code>  as well: you can expect the same messages with either in the place of <code>status_sshd</code>.</p>
            <ul>
               <li><code>status_sshd</code> returns <code>'sshd is disabled'</code>, when all ssh listeners are disabled, and there are no functional listeners.               </li>
               <li><code>status_sshd</code> returns <code>'sshd is alive'</code>, when at least one SSH listener is functional.               </li>
               <li><code>status_sshd</code> returns <code>'sshd is down'</code>, when at least one SSH listener is enabled, and there are no functional SSH listeners.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>status_admin
                            </p>
         </td>
         <td>Checks the status of the Admin server.         </td>
      </tr>
      <tr>
         <td>
            <p>status_tm
                            </p>
         </td>
         <td>Checks the status of the Transactional manager.         </td>
      </tr>
      <tr>
         <td>
            <p>status_db
                            </p>
         </td>
         <td>
            <p>Checks the status of the Database.</p>
            <p> </p>
            <p>The following example is applicable to <code>status_admin</code>, <code>status_socks</code>, and <code>status_tm</code> as well: you can expect the same messages with either in the place of <code>status_db</code>.</p>
            <ul>
               <li><code>status_db</code> returns <code>'db is alive'</code>, when the service is functional.               </li>
               <li><code>status_db</code> returns <code>'db is down'</code>, when the service is not functional.               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On Windows systems, the repconv tool cannot process files with special characters in their names (such as Japanese, Chinese, or Cyrillic characters).         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In order for the status scripts to work, you need to have the admin server up an running.         </td>
      </tr>
</table>
