{
    "title": "Creating an Axway Server to represent Gateway",
    "linkTitle": "Creating an Axway Server to represent Gateway",
    "weight": "70"
}[About the Gateway Axway Server](#about_gtw_synch_serv)

[Prerequisites](#prereq_gtw_sync_serv)

[Procedure](#procedure_gtw_synch_serv)

<span id="about_gtw_synch_serv"></span>

## About the Gateway Axway Server

This Axway Server object specifies the machine, protocols and access mechanisms that enable a Gateway Server to communicate with an Integrator Server on the network.

<span id="prereq_gtw_sync_serv"></span>

## Prerequisites

Before you create the Axway Server object, you must create:

-   CommNetwork object that defines the network protocol you use to communicate with the Gateway Server instance  
    [View dedicated topic](../t_cmpsr_createcmntwk)
-   Host object that defines the machine that the Gateway Server instance will run on  
    [View dedicated
    topic](../t_cmpsr_createhost)
-   Optionally, a HostGroup object that defines where the Gateway Server instance is logically situated in your network  
    [View dedicated topic](../t_cmpsr_createhostgroup)

<span id="procedure_gtw_synch_serv"></span>

## Procedure

1.  In the Composer Topography
    workbench, select **New > Configure
    new Axway Server...** from the **File**
    menu.  
    Composer opens the *Axway Server* properties window.
2.  Complete the **General** tab.  
    <a href="" class="MCToggler MCTogglerHead MCTogglerHotSpot MCToggler_Open toggler MCTogglerHotSpot_ MCHotSpotImage"><img src="/Images/Gateway/transparent.gif" class="MCToggler_Image_Icon" width="16" height="11" alt="Closed" />View fields</a>
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadD-Column1-Header1">Contents         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>Name</p>         </td>
             <td><p>Enter a name for this Axway Server.</p>
    <p>The name you enter in this field is used
    to reference a given Axway Server throughout the software.</p>         </td>
          </tr>
          <tr>
             <td><p>Label</p>         </td>
             <td><p>Optionally, enter a free-text description
    for this Axway Server. This text appears in the hint bar when you
    position the cursor over the Axway Server name in the left pane.</p>         </td>
          </tr>
          <tr>
             <td><p>Status</p>         </td>
             <td><p>This field displays the current status of
    the Axway Server. The default status is <strong>ToBeChecked</strong>.
    You cannot directly change the status in this field.</p>         </td>
          </tr>
          <tr>
             <td><p><strong>Host</strong></p>         </td>
             <td><p>From the drop-down list, select a Host object.
    Alternatively, drag-and-drop a Host from the left pane. Once set, you cannot
    modify this value.</p>
    <p>An Axway Server can belong to a single
    Host. The Host that you select in this field determines which CommNetworks
    are available for this Axway Server.</p>         </td>
          </tr>
          <tr>
             <td><p>Type</p>         </td>
             <td><p>From the drop-down list, select the software
    type: <strong>Gateway</strong></p>
    <p>When you select Gateway, the software automatically
    adds the Communication tab to the <em>Properties</em> window.</p>         </td>
          </tr>
          <tr>
             <td><p><span id="Template"></span>Template</p>         </td>
             <td><p>From the drop-down list, select an Axway
    Server Template. The Axway Server inherits all the properties defined
    for the selected Axway Server Template.</p>
    <p>For more information about templates, refer
    to the <em>Working with Templates</em> topic in the Axway Composer documentation.</p>         </td>
          </tr>
          <tr>
             <td><p><strong>Broadcast parameters</strong></p>
    <p>The following parameters identify the address and port
    number of the Broadcast Agent. This agent communicates with the Composer
    Server and sends your configuration to the execution server (the Integrator
    Server).</p>
    <p>These parameters are required for <em>Send
    to Server</em> operations.</p>
    <p>For more information about the <em>Send
    to Server</em> command, refer to the <em>Sending objects to Production</em> topic in the Axway Composer documentation.</p>         </td>
          </tr>
          <tr>
             <td><p>Agent host</p>         </td>
             <td><p>Enter the IP address or host name of the Broadcast
    Agent. This value must be identical to the host name specified for the
    CommNetwork for the Host.</p>
    <p>You can enter
    up to 128 alphanumeric characters.</p>         </td>
          </tr>
          <tr>
             <td><p>Agent port</p>         </td>
             <td><p>Enter the port number of the Broadcast Agent.
    This value must be a numeric value.</p>
    <p>The Broadcast Agent port was specified during
    the Integrator Server installation procedure. For information about Broadcast
    Agent port selection, refer to the documentation of <em>Axway <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span></em>.</p>         </td>
          </tr>
       </tbody>
    </table>
3.  On the **Communication** tab, select the TCP CommNetwork created previously.
4.  Check, save and close the Axway Server object.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
