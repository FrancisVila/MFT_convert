{
    "title": "Gateway Decision Rules for transfers to Integrator",
    "linkTitle": "Gateway Decision Rules for transfers to Integrator",
    "weight": "120"
}[About Decision Rules](#about_des_rules)

[Decision Rule parameters](#dec_rule_paras)

[Learning more](#learn_more)

<span id="about_des_rules"></span>

## About Decision Rules

In the Gateway GUI, you define a Decision Rule to enable Gateway transfers to be routed
to Integrator.

If Gateway receives a file or message transfer with characteristics that match the criteria of a
Decision Rule, and the Decision Rule has the Integrator execution-type option selected, it sends a
notification (containing all transfer attribute values) to Integrator. This notification
message informs Integrator that a file is available in the received files directory (by
default: &lt;Gateway install directory>/run\_time/tmp).

Each Decision Rule is dedicated to a specific event.

<span id="dec_rule_paras"></span>

## Decision Rule parameters

A Decision Rule that routes a message to Integrator takes the following minimum set of
parameters:

-   Conditions
    -   Direction = I (in)
    -   State = E (transfer ended)
-   Processing
    -   Execution type = XIB (Route to Integrator)

### Example conditions

Typically, you add additional conditions to dedicate the Decision Rule to very specific events. For example, a Decision Rule that routes an incoming message in SWIFT FileAct Real time transfer mode might contain the following set of conditions:

-   Conditions
    -   destination alias = destination\_server\_name
    -   direction = I (In)
    -   mode = R (responder)
    -   originator alias = SWIFT\_Remote\_Site
    -   state = E (incoming transfer ended)
    -   type = TRANS (transfer)

Note that this set of conditions specifies characteristics of both the originator and the destination partner.

<span id="learn_more"></span>

## Learning more

For detailed information on how to create and manage Decision Rules, refer to the Axway Gateway online
documentation.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
