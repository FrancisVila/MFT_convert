{
    "title": "Overview of SECS online commands",
    "linkTitle": "Overview of SECS online commands",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Security

Gateway provides two online commands that enable you to manage all Security server configuration elements (Certificates, Security Profiles and Network Profiles):

-   `secadm`: to manage security elements
-   `secdsp`: to view and select security elements

Before you execute these commands, confirm that you have:

-   Set the global environment variables
-   Started Gateway (the `p_secs` process is running)

<span id="List_of_secadm_and_secdsp_commands"></span>

## List of secadm and secdsp commands

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Object         </th>
<th class="HeadE-Column1-Header1"><code>secadm</code> commands         </th>
<th class="HeadD-Column1-Header1"><code>secdsp</code> commands         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Certificates</p>         </td>
         <td><p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secadm_import_cert">import_cert</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secadm_update_cert">update_cert</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secadm_delete_cert">delete_cert</a></p>         </td>
         <td><p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secdsp_display_cert">display_cert</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secdsp_select_cert">select_cert</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli#secdsp_status_cert">status_cert</a></p>         </td>
      </tr>
      <tr>
         <td><p>Keys</p>         </td>
         <td><p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secadm_import_key">import_key</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secadm_update_key">update_key</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secadm_delete_key">delete_key</a></p>         </td>
         <td><p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secdsp_display_key">display_key</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secdsp_select_key">select_key</a></p>
<p><a href="../../certificates_and_keys_start_here/managing_certificates_cli/managing_keys_cli#secdsp_status_key">status_key</a></p>         </td>
      </tr>
      <tr>
         <td><p>TLS Profiles</p>         </td>
         <td><p><a href="../../ssl_and_tls_protocols_about/managing_tls_security_profiles_cli#secadm_import_sprof">import_sprof</a></p>
<p><a href="../../ssl_and_tls_protocols_about/managing_tls_security_profiles_cli#secadm_delete_sprof">delete_sprof</a></p>         </td>
         <td><p><a href="../../ssl_and_tls_protocols_about/managing_tls_security_profiles_cli#secdsp_display_sprof">display_sprof</a></p>
<p><a href="../../ssl_and_tls_protocols_about/managing_tls_security_profiles_cli#secdsp_select_sprof">select_sprof</a></p>
<p><a href="../../ssl_and_tls_protocols_about/managing_tls_security_profiles_cli#secdsp_status_sprof">status_sprof</a></p>         </td>
      </tr>
      <tr>
         <td><p>SSH Profiles</p>         </td>
         <td><p><a href="../../ssh_protocol_about/managing_ssh_security_profiles_cli#secadm_import_sshprof">import_sshprof</a></p>
<p><a href="../../ssh_protocol_about/managing_ssh_security_profiles_cli#secadm_delete_sshprof">delete_sshprof</a></p>         </td>
         <td><p><a href="../../ssh_protocol_about/managing_ssh_security_profiles_cli#secdsp_display_sshprof">display_sshprof</a></p>
<p><a href="../../ssh_protocol_about/managing_ssh_security_profiles_cli#secdsp_select_sshprof">select_sshprof</a></p>
<p><a href="../../ssh_protocol_about/managing_ssh_security_profiles_cli#secdsp_status_sshprof">status_sshprof</a></p>         </td>
      </tr>
      <tr>
         <td><p>Network Profiles</p>         </td>
         <td><p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secadm_create_netprof">create_netprof</a></p>
<p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secadm_update_netprof">update_netprof</a></p>
<p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secadm_delete_netprof">delete_netprof</a></p>         </td>
         <td><p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secdsp_display_netprof">display_netprof</a></p>
<p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secdsp_select_netprof">select_netprof</a></p>
<p><a href="../../network_profiles_start_here/managing_network_profiles_cli#secdsp_status_netprof">status_netprof</a></p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
