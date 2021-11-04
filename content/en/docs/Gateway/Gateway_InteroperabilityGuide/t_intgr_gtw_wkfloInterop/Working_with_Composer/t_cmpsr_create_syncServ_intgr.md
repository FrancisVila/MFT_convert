{
    "title": "Creating an Axway Server to represent Integrator",
    "linkTitle": "Creating an Axway Server to represent Integrator",
    "weight": "80"
}[About the Integrator Axway Server](#about_intr_synch_serv)

[Prerequisites](#prereq_intr_synch_serv)

[Procedure](#procedure_intr_synch%20serv)

[After you create the Axway Server](#after_create_intr_synch_serv)

<span id="about_intr_synch_serv"></span>

## About the Integrator Axway Server object

This Axway Server object specifies the machine, protocols and access mechanisms that enable an Integrator Server to communicate with other local and remote applications.

<span id="prereq_intr_synch_serv"></span>

## Prerequisites

Before you create the Axway Server object, you must create:

-   CommNetwork object that defines the network protocol you use to communicate with the Integrator Server instance  
    [View dedicated topic](../t_cmpsr_createcmntwk)
-   Host object that defines the machine that the Integrator Server instance will run on  
    [View dedicated
    topic](../t_cmpsr_createhost)
-   Optionally, a HostGroup object that defines where the Integrator Server instance is logically situated in your network  
    [View dedicated topic](../t_cmpsr_createhostgroup)

<span id="procedure_intr_synch serv"></span>

## Procedure

1.  In the Composer Topography
    workbench, select **New > Configure
    new Axway Server...** from the **File**
    menu.  
    Composer opens the *Axway Server* properties window.
2.  Complete the **General**
    tab. Be sure to set the <span style="font-style: italic;">Type</span> field to the value **Integrator**.  
    <a href="#" class="MCToggler MCTogglerHead MCTogglerHotSpot MCToggler_Open toggler MCTogglerHotSpot_ MCHotSpotImage"><img src="/Images/Gateway/transparent.gif" class="MCToggler_Image_Icon" width="16" height="11" alt="Closed" />View fields</a>
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
    <p>An Axway Server can belong to a single Host. The Host that you select in this field determines which CommNetworks
    are available for this Axway Server.</p>         </td>
          </tr>
          <tr>
             <td><p>Type</p>         </td>
             <td><p>From the drop-down list, select the software
    type: <strong>Integrator</strong>.</p>
    <p>When you select Integrator, Composer automatically adds the following tabs to the <span style="font-style: italic;">Properties</span>
    window:</p>
    <ul>
    <li>Communication</li>
    <li>Core
    Tasks</li>
    <li>MFC</li>
    <li>Parameters</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p><span id="Template"></span>Template</p>         </td>
             <td><p>From the drop-down list, select an Axway
    Server Template. The Axway Server inherits all the properties defined
    for the selected Axway Server Template.</p>
    <p>For more information about templates, refer
    to the <span style="font-style: italic;">Working with Templates</span> topic in the Axway Composer documentation<span style="font-style: italic;">.</span></p>         </td>
          </tr>
          <tr>
             <td><p><strong>Broadcast parameters</strong></p>
    <p>The following parameters identify the address and port
    number of the Broadcast Agent. This agent communicates with the Composer
    Server and sends your configuration to the execution server (the Integrator
    Server).</p>
    <p>These parameters are required for <span style="font-style: italic;">Send
    to Server</span> operations.</p>
    <p>For more information about the <span style="font-style: italic;">Send
    to Server</span> command, refer to the <span style="font-style: italic;">Sending
    objects to Production</span> topic in the Axway Composer documentation<span style="font-style: italic;">.</span></p>         </td>
          </tr>
          <tr>
             <td><p>Agent host</p>         </td>
             <td><p>Enter the IP address or host name of the Broadcast
    Agent. This value must be identical to the host name specified for the CommNetwork for the Host.</p>
    <p><span style="color: #000000;">You can enter
    up to 128 alphanumeric characters.</span></p>         </td>
          </tr>
          <tr>
             <td><p>Agent port</p>         </td>
             <td><p>Enter the port number of the Broadcast Agent.
    This value must be a numeric value.</p>
    <p>The Broadcast Agent port was specified during
    the Integrator Server installation procedure. For information about Broadcast
    Agent port selection, refer to the <span style="font-style: italic;">Integrator
    Server Installation manual</span> for Windows or UNIX.</p>         </td>
          </tr>
       </tbody>
    </table>
3.  On the **Communication** tab, select the TCP CommNetwork you created previously.
4.  Check, save and close the Axway Server object.

<span id="after_create_intr_synch_serv"></span>

## After you create an Integrator Axway Server

After you define an Integrator Server object, you need to import the object set from the Axway Server instance that the object represents.

[View dedicated topic](../t_cmpsr_impt_intgrobjset)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
