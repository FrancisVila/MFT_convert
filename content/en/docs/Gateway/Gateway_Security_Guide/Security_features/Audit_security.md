{
    "title": "Audit",
    "linkTitle": "Audit",
    "weight": "170"
}  

Gateway stores the actions performed by users relating to the Gateway configuration in a dedicated audit file, to provide traceability of changes done to the product's configuration. This concerns changes both to global and to object configuration.

This functionality cannot be disabled, and the audit file can only be written by the audit process inside Gateway.

The content can be exported in a readable text format using the command line or UI. When Gateway is stopped, the audit can still be consulted using a dedicated command line tool.

You can archive the current audit file. Gateway then creates an archive file from the current <span class="code">audit.dat </span>file by adding the archiving timestamp. To automatize the process of audit file archiving, you can create a scheduler to call a script calling the archive command.

The following operations are audited:

-   creating, updating or deleting Gateway objects (Sites, Trading Partners, CGates/SGates, CGateGroups/SGateGroups, Applications, Diffusion Lists, Decision Rules, Rule Tables, Models, Purge Models, Property Lists, Proxy, Users, Profiles).
-   creating or updating Transfers
-   starting/stopping a Site
-   creating, updating or deleting a Gateway Security Object (TLS Security Profiles, SSH Security Profiles, Network Profiles, Certificates, Keys)
-   creating, updating or deleting VFD objects
-   control operations on log, statistics, connection statistics, connections and connected users (for more details, refer to Gateway User Guide / User Interfaces / Online commands / [Catalog of online commands/ pelctl](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/user_interfaces/online_commands_catalog.htm))
-   configuration changes (not in peluconf standalone mode)
-   purge operations

For further information refer to Gateway User Guide &gt; [Managing Audit files](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/Logs_audit/Audit.htm)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
