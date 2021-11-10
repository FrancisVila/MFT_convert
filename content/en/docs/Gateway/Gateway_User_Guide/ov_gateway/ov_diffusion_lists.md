{
    "title": "Diffusion Lists",
    "linkTitle": "Diffusion Lists",
    "weight": "110"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

A file transfer involves the exchange of a single file from an originating computer to one or more destination computers (Sites). Gateway enables you to create lists of computers that you want to use as destinations for a given type of file. When you create a Transfer Request, you can then specify the list as the destination. Gateway attempts to deliver the file to each computer on the list.

### Diffusion List object

The <span style="font-style: italic;">Diffusion List object</span> enables you to create a list of destination Sites.

A Diffusion List object comprises:

-   One or more Sites and/or one or more Diffusion Lists, <span style="font-weight: bold;">or</span>
-   A protocol-level destination, if the Diffusion List is associated with a Template Site (only useful if you are using Gateway in Responder mode).

When you submit a Transfer Request with a Diffusion List name as the destination alias, Gateway:

-   Creates a parent Request (Diffusion List Request)
-   Creates one Transfer Request for each Site referenced in the Diffusion List

### Example

Create a Diffusion List BRLIST and use the list as the destination alias in a Transfer Request.

Gateway transfers the file to each Site of BRLIST (SITE1) as well as to each Site contained in each list of BRLIST (SITE2 and SITE3).

<img src="/Images/Gateway/Diffusion_List_756x493.png" class="mediumWidth" />

[Next topic](../ov_vfd)

Related topics

[About Diffusion Lists](../../managing_partners_start_here/diffusion_lists_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
