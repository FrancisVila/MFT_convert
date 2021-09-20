{
    "title": "Revision history",
    "linkTitle": "Revision history",
    "weight": "40"
}**Revision history**

The following changes are added to the SecureTransport 5.5 Adminstration Tool online help.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th><span>SecureTransport</span> version</th>
         <th>Topics updated</th>
      </tr>
   </thead>
   <tbody>
      <tr data-mc-conditions="">
         <td>5.5 August 2021 Update         </td>
         <td>
            <ul>
               <li>Use Kerberos configuration file option added to <a href="../c_st_setup/c_st_database/configure-oracle-kerberos">Connect to an Oracle database using Kerberos authentication</a> .                </li>
               <li><a href="../accounts/useraccounts/t_st_create_user_account">Create a user account</a>, <a href="../accounts/useraccounts/t_st_edit_user_account_settings">Edit user account settings</a>, and <a href="../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates">Manage account templates</a>: updated with a new option - Subscription Folder Discovery, allowing administrators to improve the performance of accounts with multiple subscriptions.               </li>
               <li><a href="../accounts/transfersites">Transfer sites</a> are updated with a new checkbox <b>Use Expression Language</b> which replaces checkboxes with input fields to use string values or expressions. Multiple edits relating to this option, throughout the Administration guide.               </li>
               <li>Changed examples in <a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_external_script">External Script</a>               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>5.5 July 2021 Update         </td>
         <td>
            <ul>
               <li>
            <p>New section <i>Change the embedded database connection on MariaDB</i> added to the topic <a href="../c_st_setup/c_st_database/t_st_mysql">Change the embedded database configuration</a></p>
               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>5.5 June 2021 Update         </td>
         <td>
            <ul>
               <li>
            <p>New topic added: <a href="../operations_menu/extended_server_control/ssh-daemon-conf">Modify SSH daemon configuration</a></p>
               </li>
               <li>
            <p>New option to update file permissions using <code>chmod</code> added to <a href="../accounts/transfersites/transfersites-ssh">SSH transfer site settings</a></p>
               </li>
               <li>
            <p><a href="../c_st_standardclustering/c_st_managestandardcluster/t_st_manage_active-passive_cluster">Manage an active/passive cluster</a>  updated
</p>
               </li>
               <li>
            <p><a href="../accounts/transfersites/using_dxagent_transfersapi">Using DXAGENT_TRANSFERSAPI variables  in transfer sites</a> updated                       </p>
               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>5.5 May 2021 Update         </td>
         <td>
            <ul>
               <li><a href="../c_st_advanced_routing/c_st_route_steps/t_st_publish_to_account">Publish To Account</a> updated with a configuration option for better control over Replace of existing file
                                           </li>
               <li><code>SessionTag</code> in <a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes">XFB Tracked Object attributes</a> updated
                                           </li>
               <li>
                                New attribute <code>ServerName</code> added in the following topics:  
                                            <ul>               <li><a href="../operations_menu/c_st_filetransfertracking/t_st_viewfiletransferinfo">View file transfer information</a>               </li>               <li><a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes">XFB Tracked Object attributes</a>               </li>               <li><a href="../c_st_setup/c_st_sentinelintegration/r_st_sentineltrackedobjects">Axway Sentinel tracked objects</a>               </li>            </ul>               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>5.5 April 2021 Update         </td>
         <td>
            <p><a href="../accounts/transfersites/r_st_connectdirecttransfersites">Connect:Direct transfer sites</a> updated with note about select statistics</p>
            <p><a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_compress">Compress</a> and  <a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_decompress">Decompress</a> topics edited for clarity</p>
            <p>Update per additional flow attributes feature in the following topics:</p>
            <ul>
               <li><a href="../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables">Mail template commands and variables</a>                </li>
               <li><a href="../accounts/t_st_transferprofiles">Transfer profiles</a>                </li>
               <li><a href="../accounts/transfersites">Transfer sites</a>                </li>
               <li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates">Manage site templates</a>
               </li>
               <li><a href="t_st_businessunits.htm">Manage business units</a>                </li>
               <li><a href="../c_st_accesscontrol/c_st_loginrestictions/t_st_manloginrestictionpolicies">Create Login Restriction Policy entries</a>                </li>
               <li><a href="../c_st_advanced_routing/c_st_configuration/t_st_manage_route_package_templates"> Manage Route Package Templates</a>                </li>
               <li>all application types under <a href="../applications">Applications</a><![CDATA[
]]>               </li>
            </ul>
            <p>Topics updated with new configuration options to control the usage of expired certificates:</p>
            <ul>
               <li><a href="../accounts/transfersites/transfersites-http">HTTP(S) transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-pesit">PeSIT transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-ftp">FTP(S) transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-ssh">SSH transfer sites</a>
               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>5.5 March 2021 Update         </td>
         <td>
            <ul>
               <li>New topics added:            <ul>               <li><a href="../c_st_setup/usage-tracking">Usage reporting for subscription-based licenses</a>               </li>               <li><a href="../c_st_setup/usage-tracking/st-edge_agent">Set up usage reporting</a>               </li>            </ul>               </li>
               <li><a href="../operations_menu/extended_server_control/ssh-daemon-conf/ext_servercontrol-add-ssh">Manage the SSH server</a> with new settings               </li>
               <li><a href="../accounts/c_st_subscriptions/t_st_subscriptions">Manage subscriptions</a> updated               </li>
               <li><a href="../c_st_advanced_routing/c_st_configuration/t_st_subscribe_advanced_routing_application">Subscribe to Advanced Routing application</a> updated
with new trigger file options                </li>
               <li><a href="../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs">Manage local certificates and certificate signing requests</a> updated with details about overwriting existing service certificates                </li>
               <li><a href="../c_st_expressionlanguage/r_st_expressionlanguagepesitvariables">PeSIT variables</a> updated with details on PeSIT variables available for Push and Pull                </li>
               <li><a href="../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationfiles">Update configuration files</a> updated with clarification about applying server configuration changes                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 February 2021 Update         </td>
         <td>
            <ul>
               <li><a href="../c_st_firewallsettings/r_st_firewallrules/r_st_large_enterprise_clustering_rules">Enterprise Cluster rules</a> updated                </li>
               <li><a href="../c_st_setup/c_st_database/migrate_oracle_to_postgre">Migrate  from Oracle to PostgreSQL</a> and <a href="../c_st_setup/c_st_database/t_st_oracle">Change the Oracle database configuration</a> updated  to reflect the added support for Oracle Proxy Authentication               </li>
               <li><a href="../operations_menu/c_st_standardbrowserclient">Standard browser client</a> updated with details on setting <code>Http.FdxAuthReply</code>               </li>
               <li><a href="../c_st_setup/c_st_certificates/t_st_trustedcas">Manage trusted CAs</a> updated with further details on importing trusted CAs               </li>
               <li><a href="../c_st_commandlineutilities/file-listing-commands">Command line directory or file listing</a> updated with new configuration option to specify the file size for encrypted files in directory listing               </li>
               <li><a href="../c_st_setup/c_st_sentinelintegration/t_st_sentinel">Configure SecureTransport to send events to Axway Sentinel</a> updated with information on setting up connection timeout when  Sentinel is unavailable               </li>
               <li><a href="../overview5/r_st_axway_and_third-party_software_support">Axway and third-party software support</a> topic updated with a note regarding EoL of CentOS 8.x               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 January 2021 Update         </td>
         <td>
            <ul>
               <li>New topic added: <a href="../c_st_commandlineutilities/file-listing-commands">Command line directory or file listing</a>               </li>
               <li><a href="../accounts/useraccounts/t_st_lock_unlock_user_account">Lock or unlock a user account</a> updated               </li>
               <li><a href="../accounts/useraccounts/t_st_create_user_account">Create a user account</a> updated                </li>
               <li>
                                    Upload Permissions in <a href="../accounts/transfersites/transfersites-ssh">SSH transfer sites</a> updated                </li>
               <li><a href="../c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_setup_cluster">Set up a cluster</a> updated
               </li>
               <li><a href="../c_st_accesscontrol/c_st_userclasses/c_st_custom_expressions">Custom expressions</a> updated with new user attributes               </li>
               <li><a href="../operations_menu/c_st_filetransfertracking">Track file transfer activity</a> updated                </li>
               <li><a href="../operations_menu/t_st_serverlog">Server log</a> updated
                                                   </li>
               <li>New database role requirement for exporting log records from a PostgreSQL database with the <a href="../applications/applicationslogentrymaintenance">Export from PostgreSQL database</a> and <a href="../applications/applicationstransferlogmaintenance">Export from PostgreSQL database</a> application                </li>
               <li><code>tm_agent_error.log</code>
                                   in   <a href="../c_st_serverlogs/r_st_logfilelist">Log file list</a> updated               </li>
               <li>"Configure security policies and HTTP response headers" topic moved to <span>SecureTransport</span> 5.5 Security Guide               </li>
               <li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_redirect_log4j_output_from_database">Redirect log4j output from the database</a> topic
updated with file rotation handling notes               </li>
               <li><a href="../overview5/r_st_axway_and_third-party_software_support">Axway and third-party software support</a> topic updated with supported AS2 versions                                              </li>
               <li><a href="../c_st_setup/c_st_database">Configure your database</a> topic updated with clarification about collation with different databases                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 December 2020 Update         </td>
         <td>
            <ul>
               <li>New notification type variables added to <a href="../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables">Mail template commands and variables</a>               </li>
               <li><a href="../accounts/c_st_subscriptions/t_st_subscriptions">Manage subscriptions</a> updated                </li>
               <li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_change_log4j_files">Modify the log4j files</a> updated with file rotation instructions and new examples               </li>
               <li><a href="../c_st_serverlogs/r_st_logfiledetails/c_st_general_log_files">General log files</a> topic updated with generic http transfer site messages and new examples               </li>
               <li><a href="../c_st_serverlogs/r_st_logfiledetails/t_st_redirect_log4j_output_from_database">Redirect log4j output from the database</a> topic updated                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 November 2020 Update         </td>
         <td>
            <ul>
               <li><code>ProtocolFileName</code> and <code>ProtocolFileLabel</code> in <a href="../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes">XFB Tracked Object attributes</a> updated               </li>
               <li><a href="../c_st_advancedaccountadministration/c_st_clientinitiatedandserverinitiatedtransfers">Client-initiated and server-initiated transfers</a> updated with note details on server-initiated transfers and remote server certificate               </li>
               <li><a href="../c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_setup_cluster">Set up a cluster</a> updated with note on SSL encryption across Server nodes               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 October 2020 Update         </td>
         <td>
            <ul>
               <li>New metrics added to the SecureTransport <a href="../c_st_setup/usage-tracking/generate_usage_report">Usage and Deployment information</a>               </li>
               <li>Topics updated with new  protocol server settings  that allow modifying the list of allowed cipher suites, ciphers, and algorithms in FIPS mode:<br/>
                                                <ul>
               <li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-ftp">Manage the FTP server</a>
               </li>
               <li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-http">Manage the HTTP server</a>
               </li>
               <li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-as2">Manage the AS2 server</a>
               </li>
               <li><a href="../operations_menu/extended_server_control/ext_servercontrol-add-pesit">Manage the PeSIT server</a>
               </li>
               <li><a href="../operations_menu/extended_server_control/ssh-daemon-conf/ext_servercontrol-add-ssh">Manage the SSH server</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-ftp">FTP(S) transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-http">HTTP(S) transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/r_st_as2transfersites">AS2 transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-pesit">PeSIT transfer sites</a>
               </li>
               <li><a href="../accounts/transfersites/transfersites-ssh">SSH transfer sites</a>
               </li>
            </ul>
               </li>
               <li>Topics updated to reflect the added support of SecureTransport to connect to Oracle databases using Kerberos authentication:               </li>
            <ul>
               <li>New subtopic added: <a href="../c_st_setup/c_st_database/configure-oracle-kerberos">Connect to an Oracle database using Kerberos authentication</a>, part of <a href="../c_st_setup">Setup</a>                </li>
               <li><a href="../c_st_setup/c_st_database/t_st_oracle">Change the Oracle database configuration</a> updated with settings for configuring Kerberos authentication               </li>
               <li><a href="../overview5/r_st_axway_and_third-party_software_support">Axway and third-party software support</a> updated               </li>
            </ul>
               <li><a href="../c_st_authentication/c_st_active_directory">Configure  Kerberos as an Identity Provider in SecureTransport</a> updated               </li>
               <li>Description of <code>repconv</code> in <a href="../c_st_commandlineutilities/r_st_utilityfiles">Utility files</a> updated               </li>
               <li>New subtopic added: <a href="../c_st_troubleshootcommonproblems/sit-dsa-certificate">SIT transfers fail when using DSA certificates</a>, part of <a href="../c_st_troubleshootcommonproblems">Troubleshoot common problems</a>               </li>
               <li><a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_pgp_encryption">PGP Encryption</a> topic updated                </li>
               <li><a href="../c_st_advanced_routing/c_st_route_step_transformations/t_st_pgp_decryption">PGP Decryption</a> topic updated               </li>
               <li>Topics updated to reflect the newly added support for certificate-based authentication in the Connect:Direct transfer sites<br/>
                                                <ul>
               <li><a href="../accounts/transfersites/r_st_connectdirecttransfersites">Connect:Direct transfer sites</a>
               </li>
               <li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates">Manage site templates</a>
               </li>
               <li><a href="../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_usesitetemplate">Use a site template to define a transfer site</a>
               </li>
            </ul>
               </li>
               <li><a href="../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a> updated
with configuration for usage of specific cipher suites							               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>5.5 June 2020 Update         </td>
         <td><a href="../c_st_setup/t_st_icap_settings">ICAP settings</a> updated with options to include the name of the scanned file in the request URL and set the number of retries and time to wait between retries in case of timeout          </td>
      </tr>
   </tbody>
</table>
