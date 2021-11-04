{
    "title": "Decision Rule usage example: Directory Scanning",
    "linkTitle": "Directory Scanning",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[Task overview](#Task_overview)

[Example production environment](#Example_production_environment)

[Configuring the function](#Configuring_the_function)

[Results](#Results)

<span id="Task_overview"></span>

## Task overview

This topic provides an example of how to configure Gateway to scan a directory for a certain type of file.

You can create a Directory Scanning type Decision Rule so that Gateway monitors a specified folder on the host machine. You can then specify an action for Gateway to execute when it detects a file in this folder.

To configure Gateway to execute a process based on the presence of a file in a specified folder, perform the following tasks:

-   [Select storage and work folders for file monitoring by Gateway](#Selecting_folder)
-   [Create execution Models for transferring the deposited files to remote machines](#Creating_execution_model)
-   [Create Directory Scanning type Decision Rules](#Creating_Directory_Scanning_Decision_Rules)
-   [Create a Directory Scanning type Rule Table, and link the Decision Rules to the Table](#Creating_Directory_Scanning_Rule_Table)

<span id="Example_production_environment"></span>

## Example production environment

### Operation

A company handles billing records from diverse machines on its network. Several billing terminals regularly send billing records to an accounting application on a centralized UNIX machine. The accounting application analyzes each incoming billing record and creates two types of report:

-   <span class="code">IntlReportNxxx.txt</span> - concerning international accounts. These files are to be transferred and stored on SiteA.
-   <span class="code">NtlReportNxxx.txt</span> - concerning national accounts. These files are to be transferred and stored on SiteB.

When the accounting application creates the reports it deposits them in the local folder: <span class="code" style="font-weight: bold;">/usr/local/appli/report</span>. When deposited to this folder, the files are in their final form and their contents are no longer modified.

### Architecture

In this example:

-   The central accounting application and Gateway reside on the same UNIX host
-   Both International handling SiteA and National handling SiteB host Axway Transfer applications (Transfer CFT or Transfer InterPel)
-   Billing terminals communicate with the central accounting application independently of Gateway

The following figure illustrates the architecture of the example.

![](/Images/Gateway/FileStoringExample_756x327.png)

<span id="Configuring_the_function"></span>

## Configuring the function

### Prerequisites

-   Gateway must be correctly installed and running on the same platform as the central accounting application.
-   Axway Transfer applications must be correctly installed and running on SiteA and SiteB machines.
-   You must have created the local and remote Sites necessary to enable transfers from the Gateway to the Axway Transfer sites. This example uses the following site aliases:
    -   Gateway local site alias = GW\_1
    -   International processing server remote alias = SiteA
    -   National processing server remote alias = SiteB
-   The machines must be linked by a TCP/IP connection.
-   You require a Windows environment to support the Gateway GUI.

<span id="Selecting_folder"></span>

### Selecting the storage and work folder for Gateway monitoring

In this example, the folder we want to monitor is the folder that the central accounting application uses for report deposits:  
<span class="code" style="font-weight: bold;">/usr/local/appli/report</span>.

Create the working folder in which Gateway processes files. In this example:  
<span class="code" style="font-weight: bold;">/usr/local/appli/work</span>.

<span class="bold_in_para">Note</span>: The working folder and the watch folder must be on the same file system.

<span id="Creating_execution_model"></span>

### Creating the execution Models

In this example, we create Decision Rules that specify a Model as the execution type when a stored file is detected. We require two General Models: one for Transfers to the international processing server, and another for Transfers to the national processing server.

The [General Model](../../../transfers_start_here/parameters_start_here/models_start_here#gen_and_protocol) is mandatory for Transfers, since you can only define the Transfer destination in the General Model and not in a Protocol Model.

#### To create a new General Model for Transfers to the international processing server:

1.  In the Directory tree structure, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Transfer Management > Parameters > Model
2.  Right-click the <span style="font-weight: bold;">Transfer Model</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New General Model</span> window.
3.  Complete the fields of the <span style="font-style: italic;">New General Model</span> window as follows.
    -   In the <span style="font-weight: bold;">Name</span> field, enter: <span style="font-style: italic;">M\_Trans\_Intl\_Report.</span>
    -   Use the <span style="font-weight: bold;">Argument</span> and <span style="font-weight: bold;">Value</span> fields to assign the following values:
4.  After entering the values, click <span style="font-weight: bold;">OK</span>.  
    Gateway closes the <span style="font-style: italic;">New General Model</span> window and adds an entry representing the new Model to the list in the <span style="font-style: italic;">Transfer Model</span> display pane.

#### To create a new General Model for Transfers to the national processing server:

1.  In the Directory tree structure, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Transfer Management > Parameters > Model
2.  Right-click the <span style="font-weight: bold;">Transfer Model</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New General Model</span> window.
3.  Complete the fields of the <span style="font-style: italic;">New General Model</span> window as follows:
    -   In the <span style="font-weight: bold;">Name</span> field, enter: <span style="font-style: italic;">M\_Trans\_Ntl\_Report.</span>
    -   Use the <span style="font-weight: bold;">Argument</span> and <span style="font-weight: bold;">Value</span> fields to assign the following values:
4.  After entering the values, click <span style="font-weight: bold;">OK</span>.  
    Gateway closes the <span style="font-style: italic;">New General Model</span> window and adds an entry representing the new Model to the list in the <span style="font-style: italic;">Transfer Model</span> display pane.

<span id="Creating_Directory_Scanning_Decision_Rules"></span>

### Creating the Directory Scanning type Decision Rules

We require two Decision Rules: one for Transfers to the international processing server, and another for Transfers to the national processing server.

#### To create a Decision Rule for Transfers to the International processing server:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway displays the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS
2.  Right-click the <span style="font-weight: bold;">Directory Scanning</span> sub-node. A context menu appears. Select<span style="font-weight: bold;"> New > Decision Rule...</span>  
    Gateway displays the <span style="font-style: italic;">New Decision Rule</span> window.
3.  In the <span style="font-style: italic;">New Decision Rule</span> window, enter the following data:
4.  After entering the values, click <span style="font-weight: bold;">OK</span>.  
    Gateway closes the <span style="font-style: italic;">New Decision Rule</span> window and adds an entry representing the new Decision Rule to the list in the Decision Rule display pane.

#### To create a Decision Rule for Transfers to the national processing server:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway displays the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS
2.  Right-click the <span style="font-weight: bold;">Directory Scanning</span> sub-node.  A context menu appears.  Select<span style="font-weight: bold;"> New > Decision Rule...</span>  
    Gateway displays the <span style="font-style: italic;">New Decision Rule</span> window.
3.  In the <span style="font-style: italic;">New Decision Rule</span> window, enter the following data:
4.  After entering the values, click <span style="font-weight: bold;">OK</span>.  
    Gateway closes the <span style="font-style: italic;">New Decision Rule</span> window and adds an entry representing the new Decision Rule to the list in the Decision Rule display pane.

<span id="Creating_Directory_Scanning_Rule_Table"></span>

### Creating the Directory Scanning type Rule Table

For this example we create a Directory Scanning type Rule Table, linking the Decision Rules that we created in the previous section.

To create a Directory Scanning type Rule Table, follow these steps:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway displays the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS
2.  Right-click the <span style="font-weight: bold;">Directory Scanning</span> sub-node. A context menu appears. Select<span style="font-weight: bold;"> New</span> then <span style="font-weight: bold;">Rule Table...</span>.  
    Gateway displays a <span style="font-style: italic;">New Rule Table</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, enter the following data:
4.  In the <span style="font-weight: bold;">File Event</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, enter the following values.
5.  In the <span style="font-weight: bold;">Linked rules</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, in the <span style="font-weight: bold;">Available Rules</span> list:
    -   Click <span style="font-style: italic;">Trans\_International\_Report</span> to select it. Then click the <span style="font-weight: bold;">Link</span> button.
    -   Click <span style="font-style: italic;">Trans\_National\_Report</span> to select it. Then click the <span style="font-weight: bold;">Link</span> button again.  
        Gateway links the two Decision Rules to the <span style="font-style: italic;">Acct\_file\_test</span> Rule Table.
    -   Click <span style="font-weight: bold;">OK</span> to validate the new Rule Table.

      
    Gateway closes the <span style="font-style: italic;">New Rule Table</span> window and adds the <span style="font-style: italic;">Acct\_file\_test</span> entry to the display of Rule Tables and Decision Rules for the Directory Scanning category.

<span id="Results"></span>

## Results

When you have created and activated the Decision Rules and linked them to a Rule Table as described above, Gateway scans the <span class="code" style="font-weight: bold;">/usr/local/appli/report</span> folder every 20 seconds for the presence of a file.

The presence of one or more files triggers the copy of the file(s) to the work folder. Gateway then extracts the information necessary to analyze the Rule Table for Decision Rule criteria matches. If Gateway finds a match, it deposits the appropriate Transfer Model and transfers the file to the specified server.

After execution of the Transfers, the original files are periodically purged from the work folder.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
