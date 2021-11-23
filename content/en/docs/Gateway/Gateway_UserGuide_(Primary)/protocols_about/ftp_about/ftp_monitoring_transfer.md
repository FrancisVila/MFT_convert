{
    "title": "Monitoring an FTP Transfer Request",
    "linkTitle": "Monitoring an FTP Transfer Request",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Protocols

## Protocol trace messages

The protocol trace is an optional feature that you define for transfer activity for a given Site.

Activate the protocol trace for more detailed diagnostics when an unexpected error occurs.

Enable or disable trace printing for a Site object at any of the following stages:

-   When creating a Site
-   When modifying an existing Site
-   While Gateway is processing (dynamically)

Activate (or deactivate) the Remote Site **trace** (**<span class="code">-trace\_mode</span>**) parameter to enable (or disable) trace printing.

Alternatively, to initiate an immediate trace, use the command:

pelctl start\_site  -trace\_mode

Gateway prints the corresponding protocol messages to the log file.

If you enable the <span style="font-weight: bold;">trace</span> option, also set the [log levels](../../../configuration_start_here/config_gateway_paras#Log_levels) in the configuration menu for:

-   <span style="font-weight: bold;">FTP control session</span> - FTP commands and replies (FPDUs)
-   <span style="font-weight: bold;">FTP data session</span> - transferred data

The three possible log levels are:

-   Minimum
-   Short
-   Full

The protocol trace log levels apply to all protocol activity on all Sites. FTP data that is traced in **Short** mode records only the first 16 bytes of each frame (the first line of each command and response). In **Full** mode, all bytes (commands, replies, and transferred data) are logged.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
