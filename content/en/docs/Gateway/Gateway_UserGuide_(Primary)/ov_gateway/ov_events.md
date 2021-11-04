{
    "title": "Event management",
    "linkTitle": "Event management",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

Gateway includes a set of tools that enable you to program the triggering of tasks by events that occur on the Gateway. You can use this triggering mechanism for such tasks as:

-   Routing
-   Scheduled maintenance
-   Scheduled transfers
-   Directory polling
-   Execution of script-based processes

## Triggering Events

A broad range of events can trigger Gateway processes. Gateway groups possible triggering events into four categories:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Triggering Category         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer Change State</p>         </td>
         <td><p>Enables you to use one or more attribute values of a Transfer to trigger a Gateway process.</p>         </td>
         <td><p>The reception of a Transfer from a specified Axway Transfer product triggers the deposit of a new Transfer Request with a Diffusion List as destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory Scanning</p>         </td>
         <td><p>Enables you to use the detection of a specific file or file type in a directory of the Gateway host machine to trigger a Gateway process.</p>         </td>
         <td><p>The deposit of <span class="code">example.txt</span> in the directory <span class="code">C:\xfb_poll\*</span> triggers the deposit of a Transfer Request that forwards the file to a specified Axway Transfer product.</p>         </td>
      </tr>
      <tr>
         <td><p>Scheduling</p>         </td>
         <td><p>Enables you to set the times when a specified action is triggered.</p>         </td>
         <td><p>Gateway automatically archives a specified log file every day at the same time.</p>         </td>
      </tr>
      <tr>
         <td><p>XMS</p>         </td>
         <td><p>An Axway Messaging message transfer triggers the deposit of a Transfer Request.</p>         </td>
         <td><p>Gateway detects a transfer over the Axway Messaging connector and applies the appropriate Model to the transfer.</p>         </td>
      </tr>
   </tbody>
</table>

## Triggered Processes

When you select a triggering event, you link the event to a task that is executed by Gateway. The following table summarizes the types of task that Gateway can execute.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Triggered Process         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>Gateway applies a routing definition as specified in a Model object.</p>         </td>
      </tr>
      <tr>
         <td><p>AMTrix/XIB</p>         </td>
         <td><p>Gateway redirects a Transfer to AMTrix/ Axway Integrator for processing.</p>         </td>
      </tr>
      <tr>
         <td><p>Perl Script</p>         </td>
         <td><p>Gateway executes a Perl script.</p>         </td>
      </tr>
      <tr>
         <td><p>Batch command</p>         </td>
         <td><p>Gateway executes a specified online command.</p>         </td>
      </tr>
      <tr>
         <td><p>Purge</p>         </td>
         <td><p>Gateway purges a Mailbox or log file.</p>         </td>
      </tr>
      <tr>
         <td><p>No action</p>         </td>
         <td><p>Gateway takes no action.</p>         </td>
      </tr>
   </tbody>
</table>

## Configuring Gateway to trigger processes

To create processing triggers and link them to events, you create <span style="font-style: italic;">Decision Rule</span> objects and <span style="font-style: italic;">Rule Table</span> objects.

-   <span style="font-weight: bold;">Decision Rule</span> objects contain the definitions of the events that you want to trigger a specific action. They also specify the action that is carried out when the event occurs. You can create as many Decision Rules as you require.
-   <span style="font-weight: bold;">Rule Table</span> objects are ordered lists of one or more Decision Rules. For each Decision Rule that it contains, the Rule Table displays the following parameters:
    -   Order
    -   Decision Rule name
    -   Action to be executed
    -   Condition parameters

      
    The order in which a Decision Rule appears in the Rule Table list indicates its priority. Gateway analyzes all events and when an event corresponds to an event type of a Rule Table, it scans the table list in order, top to bottom. If it finds a rule whose criteria completely match the event, it executes the specified process specified by the rule.

[Next topic](../ov_routing)

Related topics

[Managing Events on <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](../../managing_events_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
