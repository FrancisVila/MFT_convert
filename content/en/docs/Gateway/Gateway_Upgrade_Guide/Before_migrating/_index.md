{
    "title": "Before Upgrading",
    "linkTitle": "Before migrating",
    "weight": "50"
}This topic explains what you must do before upgrading from <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> V6.16.x to <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> V6.17.

## Preparation

### Record the characteristics of your Gateway installation

Before upgrading to a new version of Gateway, record the characteristics of your existing installation. Use the tables provided in the <a href="../audit_form" class="MCXref xref">Audit form</a> to note the recorded values.

### Suspend Axway Gateway activity

During the upgrade procedure for the Mailbox, you must stop Gateway. To limit downtime, it is recommended that you analyze Gateway activity.

Stop Gateway when the file transfer activity is at a minimum, that is:

-   After purging the Mailbox
-   Once each transfer has been completed and routed
-   When no transfer deposit is being performed via batches or programs

### List custom procedures and programs

List the set of procedures and programs that are linked to Gateway:

-   Automatic procedures (start, stop, purge, log…)
-   Transfer Request deposits
-   Programs that use the APIs

### Record Gateway Navigator characteristics

Keep in mind that the version of Gateway Navigator (Gateway client) is linked to the version of Gateway. You must install the correct version of Gateway Navigator.

List the workstations where Gateway Navigator is installed.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
