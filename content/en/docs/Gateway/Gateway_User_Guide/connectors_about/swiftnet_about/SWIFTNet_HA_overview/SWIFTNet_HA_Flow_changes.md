{
    "title": "SWIFTNet HA flow changes",
    "linkTitle": "Flow changes",
    "weight": "330"
}[RECEIPT transfers routing to Integrator](#RECEIPT)

[Extension of SWIFTNet dump to XML](#Extensio)

[Forced retries on non-correlated Acknowledgments](#Forced)

[Limitations](#Limitati)

The following changes were introduced when implementing Gateway High Availability:

<span id="RECEIPT"></span>

## RECEIPT transfers routing to Integrator

In order for the backend application to centralize and correlate the incoming Acknowledgment messages, it is now possible to define decision rules that route these Acknowledgment messages to Integrator. For more information, see [Axway Integrator connector.](../../../integrator_about/integrator_connector)

<span id="Extensio"></span>

## Extension of SWIFTNet dump to XML

To make Notification-type system messages content available to the back-end application, Gateway dumps the content for Authorization, Refusal, Delivery Notification and Failed Delivery Notification system messages to XML files.

For a complete list of information that will be dumped to XML files see

[SWIFTNet dump to XML.](../../swiftnet_backup_sites/swiftnet_dump_to_xml)

<span id="Forced"></span>

## Forced retries on non-correlated Acknowledgments

If the Gateway High Availability solution cannot correlate an incoming Acknowledgment or Notification system message against the High Availability database, it returns an empty response. In effect, a retry could be triggered. For Store-and-Forward flows, this is done automatically by the SWIFTNet infrastructure (up to 10 retries). For Real Time flows, retries are performed by the remote partner.

<span id="Limitati"></span>

## Limitations

The following limitations apply to a Gateway High Availability solution:

### FileAct RealTime Get flows do not work in a High Availability configuration

Do not use FileAct RealTime Get in a High Availability configuration. You will need to configure a separate, non-High Availability Gateway in order to use them.

A file can be put at disposal by a Gateway node, and the request to get the file might be received by another Gateway node, because in High Availability mode, any Gateway node might be replaced on the fly by any other Gateway node.

### Incomplete end state transitions for Acknowledged transfers

Because in a High Availability configuration an Acknowledgment for a transfer can be received by a different Gateway to the transfer’s sender, the transfer will not be updated to the Acknowledged state - instead remaining in Ended-to-Ack.

However, the Gateway receiving the Acknowledgment still sends Ack notifications to Sentinel (if Sentinel is enabled in the configuration). Note that the Tracking Object used in the context of SWIFTNet High Availability must have the “null management” option set.

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
