{
    "title": "Creating Channels for Integrator / Gateway exchanges",
    "linkTitle": "Creating Channels for Integrator / Gateway exchanges",
    "weight": "90"
}[Overview](#overview)

[Prerequisites](#prereqs)

[Creating the Integrator Receive\_from\_Gateway Channel](#create_integrator_receive)

[Creating the Integrator Send\_to\_Gateway Channel](#create_integrator_send)

<span id="overview"></span>

## Overview

To link Integrator and Gateway for the exchange of messages, you create two Channels in Composer:

-   Integrator Receive from Gateway Channel
-   Integrator Send to Gateway Channel

<span id="prereqs"></span>

## Prerequisites

Before you can create the Channels, you must create:

-   An Axway Server
    object to represent Integrator  
    [View topic](../t_cmpsr_create_syncserv_intgr)
-   An Axway Server
    object to represent Gateway  
    [View topic](../t_cmpsr_create_syncserv_gtw)
-   An Integrator Gateway CommAdapter  
    [View topic](../t_cmpsr_createcmdptr_gtw)

<span id="create_integrator_receive"></span>

## Creating a Channel for Integrator reception from Gateway

1.  In the Composer Integration-Services workbench, **Transport** tab /**Hierarchy** sub-tab, right-click the Axway Server object that represents
    Integrator and then select **Channel** from the context menu.  
    Composer displays the *Channel* properties window.
2.  Complete the **General** tab:
3.   In the **Connection point 1** tab, select the Receiver in the *Receiver or Sender* field.
4.  In the Receive criteria section, select one or more message reception options.
5.  Check, save and close the object.

<span id="create_integrator_send"></span>

## Creating a Channel Integrator sending to Gateway

1.  In the Composer Integration-Services workbench, **Transport** tab /**Hierarchy** sub-tab, right-click the Axway Server object that represents
    Integrator and then select **Channel** from the context menu.
2.  Composer displays the *Channel* properties window.
3.  Complete the **General** tab:
4.   In the **Connection point 1** tab, select **Sender** in the *Receiver or Sender* field. Accept the defaults for Transfer timeout and Retry.
5.  In the Send criteria section, select one or more message sending options.
6.  Check, save and close the object.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
