{
    "title": "Restart a SAG",
    "linkTitle": "Restart an SAG",
    "weight": "330"
}This procedure explains the steps to restart a SAG (SWIFT Alliance Gateway):

1.  Before shutting down the SAG/SNL, stop the active SWIFTNet Remote Sites linked to this SAG/SNL.
2.  After the SAG/SNL is restarted and their status is up and running, restart the previously stopped SWIFTNet remote sites.
3.  Once the SWIFTNet remote sites are restarted, check the status of the SnF queue.  
    Use the command `peldsp status_swoutputsession `  
    See <a href="../../swiftnet_input_channels/swiftnet_output_channels" class="MCXref xref">SWIFTNet queues and output channels</a>
4.  If a queue status is not acquired, then either:
    -   restart the related SWIFTNet remote site, or
    -   use the Gateway command to do the reacquisition, such as:  
        `pelctl acquire_swqueue -qn queue_name -si remote_site -f`

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
