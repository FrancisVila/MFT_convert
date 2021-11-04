{
    "title": "Decision Rule usage example: Scheduling",
    "linkTitle": "Scheduling",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[Task overview](#Task_overview)

[Example production environment](#Example_production_environment)

[Configuring the function](#Configuring_the_function)

[Results](#Results)

<span id="Task_overview"></span>

## Task overview

This topic provides an example of how to configure Gateway to trigger a specific processing task at a pre-scheduled time each week.

To configure Gateway to retrieve a file from a remote machine at pre-scheduled dates and times, perform the following tasks:

-   [Create an execution Model for retrieving a specified file from a specified remote machine](#Creating_execution_model)
-   [Create a Scheduling-type Decision Rule](#Creating_Scheduling_Decision_Rule)
-   [Create a Scheduling-type Rule Table, and link the Decision Rule to the Rule Table](#Creating_Scheduling_Rule_Table)

<span id="Example_production_environment"></span>

## Example production environment

### Operation

A company uses an accounting application that requires an expense report that is stored on a remote machine. The expense report is available every Monday at 3 p.m., except during the month of December.

### Architecture

In this example:

-   The accounting software and Gateway reside on the same UNIX host.
-   The expense report directory resides on a machine with hostname <span style="font-style: italic;">SiteA</span>. SiteA also hosts an Axway Transfer product.

The following figure illustrates the architecture of the example.

<img src="/Images/Gateway/SchedulingExample.png" class="mediumWidth" />

<span id="Configuring_the_function"></span>

## Configuring the function

### Prerequisites

-   Gateway must be correctly installed and running on the same platform as the accounting application.
-   Axway Transfer must be correctly installed and running on the Remote SiteA machine.
-   You must have created the local and remote Sites necessary for Transfer Request from Gateway to Axway Transfer. This example uses the following site aliases:
    -   Gateway local site alias = GW\_1
    -   Remote machine alias = Remote\_SiteA
-   The machines must be linked by a TCP/IP connection.
-   You require a Windows environment to support the Gateway GUI.

<span id="Creating_execution_model"></span>

### Creating the execution Model

In this example, we will create a Decision Rule that specifies a [Model](../../../transfers_start_here/parameters_start_here/models_start_here) as the execution type when a stored file is detected.

#### To create a new General Model to retrieve a file from a remote server:

In the Directory tree structure, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
**Transfer Management &gt; Parameters &gt; Model**

Right-click the <span style="font-weight: bold;">Transfer Model</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New Transfer Model</span> window.

Complete the following fields of the <span style="font-style: italic;">New Transfer Model</span> window:

-   In the <span style="font-weight: bold;">Name</span> field, enter <span style="font-style: italic;">M\_Retrieve\_Report.</span>
-   In the <span style="font-weight: bold;">Protocol</span> field, select <span style="font-style: italic;">General.</span>
-   Use the <span style="font-weight: bold;">Argument</span> and <span style="font-weight: bold;">Value</span> fields to assign the following values:

Click <span style="font-weight: bold;">OK</span> to validate the values.  
Gateway closes the <span style="font-style: italic;">New General Model</span> window and adds an entry representing the new Model to the General Models list in the General Model display pane.

<span id="Creating_Scheduling_Decision_Rule"></span>

### Creating the Scheduling-type Decision Rule

To create a Decision Rule for a scheduled task:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following four sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS
2.  Right-click the <span style="font-weight: bold;">Scheduling</span> sub-node. A context menu appears. Select <span style="font-weight: bold;">New > Decision Rule</span>  
    Gateway displays a <span style="font-style: italic;">New Decision Rule</span> window.
3.  In the <span style="font-style: italic;">New Decision Rule</span> window, enter the following data:
4.  After entering the values, click <span style="font-weight: bold;">OK</span>.

<span id="Creating_Scheduling_Rule_Table"></span>

### Creating the Scheduling-type Rule Table

For this example we create a Scheduling-type Rule Table, linking the Decision Rule that we created in the previous section.

To create a Scheduling-type Rule Table, follow these steps:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following four sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS
2.  Right-click the <span style="font-weight: bold;">Scheduling</span> sub-node. A context menu appears. Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">Rule Table...</span>.  
    Gateway displays a <span style="font-style: italic;">New Rule Table</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, enter the following data:
4.  In the <span style="font-weight: bold;">Scheduling</span> tab of the <span style="font-style: italic;">New Rule Table</span> window click <span style="font-weight: bold;">New</span>.  
    Gateway opens the <span style="font-style: italic;">Scheduling calendar</span> window.
    -   Use the fields in the Selected Date and Selected Hour sections to set a time and date for repeated triggering of a task. We want to trigger at 3 p.m. on all Mondays, excluding Mondays during the month of December.
    -   In the <span style="font-style: italic;">Selected Date</span> section, click the lower radio button, then click the lower text box and select <span style="font-weight: bold;">add</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the first box. Click the newly displayed text box and select <span style="font-weight: bold;">all</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the second box. Click the newly displayed text box and select <span style="font-weight: bold;">monday</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the third box. Click the newly displayed text box and select the period (<span style="font-weight: bold;">.</span>) from the drop-down list. Reading the boxes from left to right, the boxes should now display: <span style="font-weight: bold;font-style: italic;">add all monday</span>.
        -   Click <span style="font-weight: bold;">Add</span>. Gateway adds the <span style="font-style: italic;">add all monday</span> date set to the list of triggering dates in the Date frame.
    -   In the text box of the <span style="font-style: italic;">Selected Hour</span> section, enter <span style="font-style: italic;">15H00</span>. Then click <span style="font-weight: bold;">Add</span>. Gateway adds the <span style="font-style: italic;">15:00 (3 p.m.)</span> time to the list of triggering times in the Date frame.
    -   In the <span style="font-style: italic;">Selected Date</span> section, click the lower radio button, then click the lower text box and select <span style="font-weight: bold;">remove</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the first box. Click the newly displayed text box and select <span style="font-weight: bold;">all</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the second box. Click the newly displayed text box and select <span style="font-weight: bold;">monday</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the third box. Click the newly displayed text box and select <span style="font-weight: bold;">of december</span> from the drop-down list.
        -   Gateway displays a new text box to the right of the forth box. Click the newly displayed text box and select the period (<span style="font-weight: bold;">.</span>) from the drop-down list. Reading the boxes from left to right, the boxes should now display: <span style="font-weight: bold;font-style: italic;">remove all monday of december</span>.
        -   Click <span style="font-weight: bold;">Add</span>. Gateway adds the<span style="font-style: italic;"> remove all monday of december</span> date set to the list of triggering dates in the Date frame.
        -   Click <span style="font-weight: bold;">OK</span> at the bottom of the calendar window to accept the schedule and return to the <span style="font-weight: bold;">Scheduling</span> tab. This tab now displays your scheduled dates and time, labeled as <span style="font-style: italic;">Calendar #1</span>.
5.  In the <span style="font-weight: bold;">Linked Rules</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, in the Available Rules list click <span style="font-style: italic;">Retrieve\_Report</span> to select it. Then click the <span style="font-weight: bold;">Link</span> button.  
    Gateway links the <span style="font-style: italic;">Retrieve Report</span> Decision Rule to the <span style="font-style: italic;">Retrieve\_file\_test</span> Rule Table.
6.  Click <span style="font-weight: bold;">OK</span> to validate the new Rule Table.  
    Gateway closes the New Rule Table window and adds the <span style="font-style: italic;">Retrieve\_file\_test</span> entry to the display of Rule Tables and Decision Rules for the Scheduling category.

<span id="Results"></span>

## Results

When you have created and activated the <span style="font-style: italic;">Retrieve\_file\_test</span> Decision Rule and linked it to the <span style="font-style: italic;">Retrieve\_file\_test</span> Rule Table as described above, Gateway triggers the retrieval of the <span class="code">report.txt</span> file from Remote SiteA at 3 p.m. on the scheduled dates.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
