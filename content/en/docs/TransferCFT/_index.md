{
    "title": "Transfer CFT 3.9 User Guide ",
    "linkTitle": "Transfer CFT User Guide",
    "weight": "20"
}Welcome to the Axway {{< TransferCFT/platformorsuiteshortname  >}}  Transfer CFT documentation. {{< TransferCFT/componentshortname  >}} is the file transfer component in the Axway   Managed File Transfer platform, and provides  a multi-platform, high-volume, file  transfer service. This documentation explains how to install, configure, and manage {{< TransferCFT/componentshortname  >}}.

You can configure {{< TransferCFT/transfercftname  >}} and manage flows using {{< TransferCFT/centralgovernancename  >}} or Flow Manager. These governance products simplify Transfer CFT usage, and provide services such as identity and access management, certificate management,  monitoring, alerting, and a web dashboard. For more information, visit [www.axway.com](http://www.axway.com/).

Additionally, the Transfer CFT {{< TransferCFT/doctypeuser  >}} explains standalone options for users who have not yet activated or Flow Manager. Axway encourages {{< TransferCFT/componentlongname  >}} users to discover the benefits of centralized management.

> **Note:**
>
> Visit the Changelog for details on new features in this version as well as previous versions.

 

<table>
   <tbody>
      <tr>
         <td><h2 id="for-new-users">For new users</h2>
<p><a href="overview_intro/about_transfer_cft">About {{< TransferCFT/componentshortname  >}}</a></p>
<p><a href="overview_intro/c_cg_concepts" >What are governance services?</a></p>
<p><a href="c_intro_userinterfaces/about_cftutil">Use  command line</a></p>
<p><a href="admin_intro/start_stop_cft">Basic administrative tasks</a></p>
<p><a href="gettingstarted_intro/my_first_transfer_flow_using_cg" >My first transfer flow</a></p>
<p><a href="gettingstarted_intro/my_first_file_transfer" >My first file transfer (CL)</a></p>
<p><a href="gettingstarted_intro/my_first_transfer_flow_using_cg">CFTUTIL basics and help</a></p>
<h2 id="for-existing-users">For existing users</h2>
<p><a href="app_integration_intro/intro_folder_monitor/configure_folder_monitoring">Configure folder monitoring</a></p>
<p><a href="about_multinode">Manage multi-node architecture</a></p>
<p><a href="cft_intro_install/about_this_document_zos/using_apis">Use API services</a></p>
<p>Check platform specifics</p>
<p><a href="admin_intro/uconf/uconf_directory">Set UCONF parameters</a></p>
<h2 id="migration-and-upgrades">Migration and upgrades</h2>
<p><a href="cft_intro_install/mig_impact_considerations">Impact and considerations</a></p>
<h2 id="troubleshooting">Troubleshooting</h2>
<p><a href="troubleshoot_intro">Troubleshooting information</a></p>
<p><a href="troubleshoot_intro/messages_and_error_codes_start_here">Messages and error codes</a></p>
<p><a href="troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes">Diagnostic codes</a></p>         </td>
         <td><h2 id="documentation">Documentation</h2>
<p>Transfer CFT User Guide <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_PDF/resource/Transfer_CFT_UsersGuide_allOS_en.pdf">PDF</a> | <a href="">Webhelp (Download)</a></p>
<p>Release Notes <a href="https://docs.axway.com/bundle/TransferCFT_38_ReleaseNotes_allOS_en_HTML5/page/Content/release_notes/Transfer_CFT_ReleaseNotes_allOS_en.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_ReleaseNotes_allOS_en_PDF/resource/Transfer_CFT_ReleaseNotes_allOS_en.pdf">PDF</a></p>
<p>Install Unix <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/UNIX/unix_install_start_here.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_unix_en_PDF/resource/TransferCFT_InstallationGuide_unix_en.pdf">PDF</a></p>
<p>Install Windows <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Windows/Windows/windows_install_start_here.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_windows_en_PDF/resource/TransferCFT_InstallationGuide_windows_en.pdf">PDF</a></p>
<p>Install z/OS <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/about_this_document_zos.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_mvs_en_PDF/resource/TransferCFT_InstallationGuide_mvs_en.pdf">PDF</a></p>
<p>Install IBM i  <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/about_this_document_ibmi.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_os400_en_PDF/resource/TransferCFT_InstallationGuide_os400_en.pdf">PDF</a></p>
<p>Install HP NonStop <a href="https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/HP_NS/preface.htm">HTML</a> | <a href="https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_hp_nonstop_en_PDF/resource/TransferCFT_InstallationGuide_hp_nonstop_en.pdf">PDF</a></p>
<p>Transfer CFT Security Guide (login required) <a href="https://docs.axway.com/bundle/TransferCFT_38_SecurityGuide_allOS_en_HTML5/page/Content/AxwayStartsecurity.htm">HTML </a>| <a href="https://docs.axway.com/bundle/TransferCFT_38_SecurityGuide_allOS_en_PDF/resource/Transfer_CFT_SecurityGuide_allOS_en.pdf">PDF</a></p>
<p>Swagger Doc <a href="http://apidocs.axway.com/swagger-ui/index.html?productname=transfercft&amp;productversion=3.8&amp;filename=transfercft-swagger-api.json">v1.7</a></p>
<p><a href="https://docs.axway.com/bundle/AccessibilityVPATS_allOS_en_HTML5/page/Content/accessibility.htm">VPAT</a></p>
<p>Third-Party Licenses (login required) <a href="https://support.axway.com/en/documents/document-details/id/1448127">PDF </a></p>
<h2 id="additional-resources">Additional resources</h2>
<p><a href="https://apidocs.axway.com/swagger-ui/index.html?productname=transfercft&amp;productversion=3.8&amp;filename=transfercft-swagger-api.json" >Transfer CFT REST API Swagger</a></p>
<p><a href="https://docs.axway.com/bundle/Axway_Products_SupportedPlatforms_allOS_en/resource/Axway_Products_SupportedPlatforms_allOS_en.pdf" >Axway Supported Platforms</a></p>
<p><a href="https://apidocs.axway.com/swagger-ui/index.html?productname=transfercft&amp;productversion=3.8&amp;filename=transfercft-swagger-api.json" >Axway Flow Manager</a></p>
<p><a href="https://support.axway.com/" >Axway Support</a></p>
<p><a href="https://community.axway.com/s/" >Axway Community</a></p>
<h2 id="search-tips">Search tips</h2>
<ul>
<li>Use filters to narrow searches.</li>
<li>Put words in quotes “like this” for exact matches of phrases.</li>
<li>Log in with your Axway ID to access documents that are not available for public users.</li>
</ul>
<h2 id="other">Other</h2>
<p>Go to Axway <a href="https://support.axway.com/">support</a> to find documentation for Sentinel versions earlier than 4.2.0.</p>         </td>
      </tr>
      <tr>
         <td><h4 id="join-the-discussion-in-axway-community">Join the discussion in <a href="https://community.axway.com">Axway Community</a>!  </h4>         </td>
      </tr>
   </tbody>
</table>

Document version:
