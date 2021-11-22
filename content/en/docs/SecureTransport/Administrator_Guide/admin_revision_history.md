{
    "title": "Revision history",
    "linkTitle": "Revision history",
    "weight": "30"
}**Revision history**

The following changes are added to the {{< SecureTransport/securetransportname  >}} {{< SecureTransport/componentversion  >}} {{< SecureTransport/documenttype  >}}.

<table>
   <thead>
      <tr>
<th style="text-align: center;" class="HeadE-Column1-Header1">{{< SecureTransport/securetransportname  >}} version         </th>
<th class="HeadD-Column1-Header1">Topics updated         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>5.5 November 2021 Update         </td>
         <td><ul>
<li><p>New topic added: <a href="../c_st_troubleshootcommonproblems/stfs-retries" class="MCXref xref">Troubleshooting I/O problems</a></p></li>
<li><p><a href="../accounts/c_st_subscriptions/t_st_subscriptions" class="MCXref xref">Manage subscriptions</a> updated with new option</p></li>
<li><p>The example expression to access a subscription attribute in the following topics is corrected:</p>
<ul>
<li><p><a href="../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a></p></li>
<li><p><a href="../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates" class="MCXref xref">Manage account templates</a></p></li>
<li><p><a href="../accounts/c_st_subscriptions/t_st_subscriptions" class="MCXref xref">Manage subscriptions</a></p></li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 October 2021 Update         </td>
         <td><ul>
<li><p><a href="../applications/applicationsarchivemaintenance" class="MCXref xref">Archive Maintenance application</a> updated with options to enable multithreading and set a runtime limit</p></li>
<li><p><a href="../c_st_setup/c_st_database/t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a> and <a href="../c_st_setup/c_st_database/configure-oracle-kerberos" class="MCXref xref">Connect to an Oracle database using Kerberos authentication</a> updated to reflect the SecureTransport's ability to auto reload the Kerberos configuration on change in the Kerberos configuration file</p></li>
<li><p><a href="../accounts/transfersites/transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a> updated</p></li>
<li><p><a href="../accounts/transfersites" class="MCXref xref">Transfer sites</a> updated</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 September 2021 Update         </td>
         <td><ul>
<li><p><a href="../overview/r_st_axway_and_third-party_software_support" class="MCXref xref">Axway and third-party software support</a> updated</p></li>
<li><p><a href="../accounts/transfersites/transfersites-ssh" class="MCXref xref">SSH transfer sites</a> updated with options to list remote folders</p></li>
<li><p>Various updates across the guide to reflect the added support for TLSv1.3</p></li>
<li><p><a href="../c_st_setup/c_st_database/t_st_mysql" class="MCXref xref">Change the embedded database configuration</a> updated to reflect the SecureTransport's ability to generate the required certificates for secure connection to MariaDB database</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 August 2021 Update         </td>
         <td><ul>
<li>Use Kerberos configuration file option added to <a href="../c_st_setup/c_st_database/configure-oracle-kerberos" class="MCXref xref">Connect to an Oracle database using Kerberos authentication</a></li>
<li><a href="../accounts/useraccounts/t_st_create_user_account" class="MCXref xref">Create a user account</a>, <a href="../accounts/useraccounts/t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>, and <a href="../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates" class="MCXref xref">Manage account templates</a>: updated with a new option - Subscription Folder Discovery, allowing administrators to improve the performance of accounts with multiple subscriptions</li>
<li><a href="../accounts/transfersites" class="MCXref xref">Transfer sites</a> are updated with a new checkbox <strong>Use Expression Language</strong> which replaces checkboxes with input fields to use string values or expressions. Multiple edits related to this option throughout the guide.</li>
<li>Changed examples in <a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_external_script" class="MCXref xref">External Script</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 July 2021 Update         </td>
         <td><ul>
<li><p>New section <em>Change the embedded database connection on MariaDB</em> added to the topic <a href="../c_st_setup/c_st_database/t_st_mysql" class="MCXref xref">Change the embedded database configuration</a></p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 June 2021 Update         </td>
         <td><ul>
<li><p>New topic added: <a href="../operations_menu/extended_server_control/ssh-daemon-conf" class="MCXref xref">Modify SSH daemon configuration</a></p></li>
<li><p>New option to update file permissions using <code>chmod</code> added to <a href="../accounts/transfersites/transfersites-ssh">SSH transfer site settings</a></p></li>
<li><p><a href="../c_st_standardclustering/c_st_managestandardcluster/t_st_manage_active-passive_cluster" class="MCXref xref">Manage an active/passive cluster</a> updated</p></li>
<li><p><a href="../accounts/transfersites/using_dxagent_transfersapi" class="MCXref xref">Using DXAGENT_TRANSFERSAPI variables in transfer sites</a> updated</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 May 2021 Update         </td>
         <td><ul>
<li><a href="../c_st_advanced_routing/c_st_route_steps/t_st_publish_to_account" class="MCXref xref">Publish To Account</a> updated with a configuration option for better control over Replace of existing file</li>
<li><code>SessionTag</code> in <a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a> updated</li>
<li>New attribute <code>ServerName</code> added in the following topics:
<ul>
<li><a href="../operations_menu/c_st_filetransfertracking/t_st_viewfiletransferinfo" class="MCXref xref">View file transfer information</a></li>
<li><a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a></li>
<li><a href="../c_st_setup/c_st_sentinelintegration/r_st_sentineltrackedobjects" class="MCXref xref">Axway Sentinel tracked objects</a></li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 April 2021 Update         </td>
         <td><ul>
<li><p><a href="../accounts/transfersites/r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a> updated with note about select statistics</p></li>
<li><p><a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_compress" class="MCXref xref">Compress</a> and <a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_decompress" class="MCXref xref">Decompress</a> topics edited for clarity</p></li>
<li><p>Update per additional flow attributes feature in the following topics:</p>
<ul>
<li><a href="../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables" class="MCXref xref">Mail template commands and variables</a></li>
<li><a href="../accounts/t_st_transferprofiles" class="MCXref xref">Transfer profiles</a></li>
<li><a href="../accounts/transfersites" class="MCXref xref">Transfer sites</a></li>
<li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates" class="MCXref xref">Manage site templates</a></li>
<li><a href="" class="MCXref xref">Manage business units</a></li>
<li><a href="../c_st_accesscontrol/c_st_loginrestictions/t_st_manloginrestictionpolicies" class="MCXref xref">Create Login Restriction Policy entries</a></li>
<li><a href="../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a></li>
<li>all application types under <a href="../applications" class="MCXref xref">Applications</a></li>
</ul></li>
</ul>
<ul>
<li><p>Topics updated with new configuration options to control the usage of expired certificates:</p>
<ul>
<li><a href="../accounts/transfersites/transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-ssh" class="MCXref xref">SSH transfer sites</a></li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 March 2021 Update         </td>
         <td><ul>
<li>New topics added:
<ul>
<li><a href="../c_st_setup/usage-tracking" class="MCXref xref">Usage reporting for subscription-based licenses</a></li>
<li><a href="../c_st_setup/usage-tracking/st-edge_agent" class="MCXref xref">Set up usage reporting</a></li>
</ul></li>
<li><a href="../operations_menu/extended_server_control/ssh-daemon-conf/ext_servercontrol-add-ssh" class="MCXref xref">Manage the SSH server</a> with new settings</li>
<li><a href="../accounts/c_st_subscriptions/t_st_subscriptions" class="MCXref xref">Manage subscriptions</a> updated</li>
<li><a href="../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a> updated
with new trigger file options</li>
<li><a href="../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a> updated with details about overwriting existing service certificates</li>
<li><a href="../c_st_expressionlanguage/r_st_expressionlanguagepesitvariables" class="MCXref xref">PeSIT variables</a> updated with details on PeSIT variables available for Push and Pull</li>
<li><a href="../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationfiles" class="MCXref xref">Update configuration files</a> updated with clarification about applying server configuration changes</li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 February 2021 Update         </td>
         <td><ul>
<li><a href="../c_st_firewallsettings/r_st_firewallrules/r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a> updated</li>
<li><a href="../c_st_setup/c_st_database/migrate_oracle_to_postgre" class="MCXref xref">Migrate from Oracle to PostgreSQL</a> and <a href="../c_st_setup/c_st_database/t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a> updated to reflect the added support for Oracle Proxy Authentication</li>
<li><a href="../operations_menu/c_st_standardbrowserclient" class="MCXref xref">Standard browser client</a> updated with details on setting <code>Http.FdxAuthReply</code></li>
<li><a href="../c_st_setup/c_st_certificates/t_st_trustedcas" class="MCXref xref">Manage trusted CAs</a> updated with further details on importing trusted CAs</li>
<li><a href="../c_st_commandlineutilities/file-listing-commands" class="MCXref xref">Command line directory or file listing</a> updated with new configuration option to specify the file size for encrypted files in directory listing</li>
<li><a href="../c_st_setup/c_st_sentinelintegration/t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a> updated with information on setting up connection timeout when Sentinel is unavailable</li>
<li><a href="../overview/r_st_axway_and_third-party_software_support" class="MCXref xref">Axway and third-party software support</a> topic updated with a note regarding EoL of CentOS 8.x</li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 January 2021 Update         </td>
         <td><ul>
<li>New topic added: <a href="../c_st_commandlineutilities/file-listing-commands" class="MCXref xref">Command line directory or file listing</a></li>
<li><a href="../accounts/useraccounts/t_st_lock_unlock_user_account" class="MCXref xref">Lock or unlock a user account</a> updated</li>
<li><a href="../accounts/useraccounts/t_st_create_user_account" class="MCXref xref">Create a user account</a> updated</li>
<li>Upload Permissions in <a href="../accounts/transfersites/transfersites-ssh" class="MCXref xref">SSH transfer sites</a> updated</li>
<li><a href="../c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_setup_cluster" class="MCXref xref">Set up a cluster</a> updated</li>
<li><a href="../c_st_accesscontrol/c_st_userclasses/c_st_custom_expressions" class="MCXref xref">Custom expressions</a> updated with new user attributes</li>
<li><a href="../operations_menu/c_st_filetransfertracking" class="MCXref xref">Track file transfer activity</a> updated</li>
<li><a href="../operations_menu/t_st_serverlog" class="MCXref xref">Server log</a> updated</li>
<li>New database role requirement for exporting log records from a PostgreSQL database with the <a href="../applications/applicationslogentrymaintenance#Export" class="MCXref xref">Export from PostgreSQL database</a> and <a href="../applications/applicationstransferlogmaintenance#Export" class="MCXref xref">Export from PostgreSQL database</a> application</li>
<li><code>tm_agent_error.log</code>
in <a href="../c_st_serverlogs/r_st_logfilelist" class="MCXref xref">Log file list</a> updated</li>
<li>"Configure security policies and HTTP response headers" topic moved to {{< SecureTransport/componentshortname  >}} 5.5 Security Guide</li>
<li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a> topic
updated with file rotation handling notes</li>
<li><a href="../overview/r_st_axway_and_third-party_software_support" class="MCXref xref">Axway and third-party software support</a> topic updated with supported AS2 versions</li>
<li><a href="../c_st_setup/c_st_database" class="MCXref xref">Configure your database</a> topic updated with clarification about collation with different databases</li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 December 2020 Update         </td>
         <td><ul>
<li>New notification type variables added to <a href="../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables" class="MCXref xref">Mail template commands and variables</a></li>
<li><a href="../accounts/c_st_subscriptions/t_st_subscriptions" class="MCXref xref">Manage subscriptions</a> updated</li>
<li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a> updated with file rotation instructions and new examples</li>
<li><a href="../c_st_serverlogs/r_st_logfiledetails/c_st_general_log_files" class="MCXref xref">General log files</a> topic updated with generic http transfer site messages and new examples</li>
<li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a> topic updated</li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 November 2020 Update         </td>
         <td><ul>
<li><code>ProtocolFileName</code> and <code>ProtocolFileLabel</code> in <a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a> updated</li>
<li><a href="../c_st_advancedaccountadministration/c_st_clientinitiatedandserverinitiatedtransfers" class="MCXref xref">Client-initiated and server-initiated transfers</a> updated with note details on server-initiated transfers and remote server certificate</li>
<li><a href="../c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_setup_cluster" class="MCXref xref">Set up a cluster</a> updated with note on SSL encryption across Server nodes</li>
</ul>         </td>
      </tr>
      <tr>
         <td>5.5 October 2020 Update         </td>
         <td>New metrics added to the SecureTransport <a href="../c_st_setup/usage-tracking/generate_usage_report" class="MCXref xref">Usage and Deployment information</a>
Topics updated with new protocol server settings that allow modifying the list of allowed cipher suites, ciphers, and algorithms in FIPS mode:<br />

<ul>
<li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-ftp" class="MCXref xref">Manage the FTP server</a></li>
<li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-http" class="MCXref xref">Manage the HTTP server</a></li>
<li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-as2" class="MCXref xref">Manage the AS2 server</a></li>
<li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-pesit" class="MCXref xref">Manage the PeSIT server</a></li>
<li><a href="../operations_menu/extended_server_control/ssh-daemon-conf/ext_servercontrol-add-ssh" class="MCXref xref">Manage the SSH server</a></li>
<li><a href="../accounts/transfersites/transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a></li>
<li><a href="../accounts/transfersites/r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-pesit" class="MCXref xref">PeSIT transfer sites</a></li>
<li><a href="../accounts/transfersites/transfersites-ssh" class="MCXref xref">SSH transfer sites</a></li>
</ul>
Topics updated to reflect the added support of SecureTransport to connect to Oracle databases using Kerberos authentication:
<ul>
<li>New subtopic added: <a href="../c_st_setup/c_st_database/configure-oracle-kerberos" class="MCXref xref">Connect to an Oracle database using Kerberos authentication</a>, part of <a href="../c_st_setup" class="MCXref xref">Setup</a></li>
<li><a href="../c_st_setup/c_st_database/t_st_oracle" class="MCXref xref">Change the Oracle database configuration</a> updated with settings for configuring Kerberos authentication</li>
<li><a href="../overview/r_st_axway_and_third-party_software_support" class="MCXref xref">Axway and third-party software support</a> updated</li>
</ul>
<a href="../c_st_authentication/c_st_active_directory" class="MCXref xref">Configure Kerberos as an Identity Provider in SecureTransport</a> updated
Description of <code>repconv</code> in <a href="../c_st_commandlineutilities/r_st_utilityfiles" class="MCXref xref">Utility files</a> updated
New subtopic added: <a href="../c_st_troubleshootcommonproblems/sit-dsa-certificate" class="MCXref xref">SIT transfers fail when using DSA certificates</a>, part of <a href="../c_st_troubleshootcommonproblems" class="MCXref xref">Troubleshoot common problems</a>
<a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a> topic updated
<a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a> topic updated
Topics updated to reflect the newly added support for certificate-based authentication in the Connect:Direct transfer sites<br />

<ul>
<li><a href="../accounts/transfersites/r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a></li>
<li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates" class="MCXref xref">Manage site templates</a></li>
<li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_usesitetemplate" class="MCXref xref">Use a site template to define a transfer site</a></li>
</ul>
<a href="../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a> updated
with configuration for usage of specific cipher suites         </td>
      </tr>
      <tr>
         <td>5.5 June 2020 Update         </td>
         <td><a href="../c_st_setup/t_st_icap_settings" class="MCXref xref">ICAP settings</a> updated with options to include the name of the scanned file in the request URL and set the number of retries and time to wait between retries in case of timeout         </td>
      </tr>
   </tbody>
</table>
