{
    "title": "Executing a basic PeSIT transfer",
    "linkTitle": "Basic PeSIT transfer",
    "weight": "120"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Transfer Examples

[About this example](#about)

[Prerequisites](#Prerequisites_Transfer_Request_PeSIT)

[Executing the Transfer Request](#Executing_PeSIT_Transfer_Request)

[Transfer results](#Transfer_Results)

<span id="about"></span>

## About this example

This topic describes a basic configuration that enables you to execute a Transfer Request between two computers, both hosting Gateways. The purpose of this topic is to provide you with the minimum set of parameters you need to accomplish a transfer. In the context of your daily operations you can add functions, and adjust this example configuration to adapt it to your specific requirements.

In this exercise, we use the Gateway GUI to transfer a <span class="code">.txt</span> formatted file from <span style="font-weight: bold;">machine A</span> (the Initiator/Sender), to <span style="font-weight: bold;">machine B</span> (the Responder/Receiver) via the PeSIT E protocol over TCP/IP.

We use a minimal set of configuration values. This enables us to demonstrate basic transfer requirements and to facilitate problem solving in the event of transfer failure.

<span id="Prerequisites_Transfer_Request_PeSIT"></span>

## Prerequisites

### Installation prerequisites

-   Gateway must be correctly installed and running on <span style="font-weight: bold;">machine A</span> and <span style="font-weight: bold;">machine B</span>.
-   The two machines must be linked by a TCP/IP connection.
-   You require a Windows environment to support the Navigator (GUI).

<span style="font-weight: bold;">Hint:</span> For Gateways hosted on Windows platforms, to confirm that Gateway is operating correctly, go to the Windows <span style="font-weight: bold;">Start</span> menu and select <span style="font-weight: bold;">Programs &gt; Axway Software &gt; Axway \[ProjectName\]&gt; Gateway &gt; Process List</span>  
The application displays the <span style="font-style: italic;">Process List</span> window containing a list of all of the currently running Gateway processes.

Example Process List display:

![](/Images/Gateway/processList_473x333.gif)

The list of processes running on your machine may vary depending on your protocol configuration.

### Configuration prerequisites

-   The sending <span style="font-weight: bold;">machine A</span> and receiving <span style="font-weight: bold;">machine B</span> must both support the PeSIT E protocol for the transfer.
-   [Activate the PeSIT E protocol](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_legacy_pesite_tcp) on both machines.

### CGateGroup and CGate prerequisites

A CGate provides security control for incoming connections. During the connection phase of a transfer, the CGate object provides the information that determines whether or not Gateway allows a given remote machine to connect.

In our transfer example, only the Responder/Receiver <span style="font-weight: bold;">machine B</span> requires a CGate object for access negotiation. The Initiator/Sender <span style="font-weight: bold;">machine A</span> is not concerned with an incoming connection attempt.

On <span style="font-weight: bold;">machine B</span>, first create a CGateGroup:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>.  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window.
3.  Enter values in <span style="font-style: italic;">only</span> the following fields of the window:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">PESITTEST</span>
    -   <span style="font-weight: bold;">State</span>: Select <span style="font-weight: bold;">Enabled</span> from the drop-down list
    -   <span style="font-weight: bold;">Protocol</span>: Enter <span style="font-weight: bold;">PESIT E</span>
    -   <span style="font-weight: bold;">Called SAP</span>: Enter<span style="font-weight: bold;"> \*</span> (star character)  
        (If you know the port that is locally configured for the PeSIT protocol, you can enter it in this field. The default port is <span style="font-weight: bold;">6330</span>.)
4.  Click <span style="font-weight: bold;">OK.</span> For this exercise is not necessary to enter any other CGateGroup information.  
    Gateway creates the group and adds it to the directory tree as a subdirectory of the CGate folder.

On <span style="font-weight: bold;">machine B</span> in the CGateGroup you just created, create a CGate object for the <span style="font-weight: bold;">machine A</span> -> <span style="font-weight: bold;">machine B</span> transfer connection:

1.  Right-click the <span style="font-weight: bold;">PESITTEST</span> CGateGroup, and select <span style="font-weight: bold;">New > CGate</span> from the context menu to display the <span style="font-style: italic;">New CGate</span> window.
2.  Enter values in <span style="font-style: italic;">only</span> the following fields of the window:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">PESITALL</span>
    -   <span style="font-weight: bold;">State</span>: Select <span style="font-weight: bold;">Enabled</span> from the drop-down list

      
    To keep the connection negotiation simple, do not enter any values in the <span style="font-weight: bold;">ID</span> or <span style="font-weight: bold;">Password</span> fields of this tab for this exercise.
3.  Click <span style="font-weight: bold;">OK</span>.  
    Gateway creates the CGate and adds it to the directory tree as a subdirectory of the PESITTEST folder.

### Site prerequisites

File transfers occur between two machines. In a transfer using Axway MFT, each participating machine is referred to as a <span style="font-style: italic;">Site</span>. Each of the two Sites in our transfer must recognize the other partner Site to ensure that they can agree on the parameters of the exchange. Gateway uses Site objects to identify Sites. A Site object contains the definitions that enable one site to communicate with another.

#### Machine A: Defining the Remote Site

In our Transfer Request, machine A will send a file to another machine (Remote Site).

We identify the characteristics of the remote machine (<span style="font-weight: bold;">machine B</span>) to Gateway on <span style="font-weight: bold;">machine A</span> by creating a <span style="font-style: italic;">Remote Site object</span>.

On <span style="font-weight: bold;">machine A</span>:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Partner Management > Sites</span>
2.  Right-click <span style="font-weight: bold;">Remote Site</span>, then from the context menu that appears, select <span style="font-weight: bold;">New</span>.  
    Gateway displays the <span style="font-style: italic;">New Remote Site</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New Remote Site</span> window, enter values in the following fields:
    -   <span style="font-weight: bold;">Alias</span>: Enter the HostName of <span style="font-weight: bold;">machine B</span>. If, for example, <span style="font-weight: bold;">machine B</span> has HostName machineB, enter <span style="font-weight: bold;">machineB</span>
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list select <span style="font-weight: bold;">PeSITE E</span>.  
        When you select this protocol, Gateway displays two additional tabs in the <span style="font-style: italic;">New Remote Site</span> window.
    -   **Protocol identifier**: Use the same protocol identifier as you use in the default Local Site definition on <span style="font-weight: bold;">machine B</span>. In our example our Protocol identifier is <span style="font-weight: bold;font-style: italic;">machineB</span> (in this case it is identical to the HostName).
    -   To confirm the protocol identifier of <span style="font-weight: bold;">machine B</span>:
        -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Partner Management > Sites > Local Site</span>
        -   Right-click <span style="font-weight: bold;">Local Site</span>.
        -   In the display pane (right pane), right-click the name of the Local Site. Select <span style="font-weight: bold;">View...</span> from the context menu that appears. Gateway opens the <span style="font-style: italic;">Local Site view</span> window.
        -   Note the name in the **Protocol Identifier** field.
    -   **Group name**: Gateway enters the default group name <span style="font-weight: bold;">GDEFAULT</span>. Do not change this value.
    -   **Role frame**: In this frame, click to select <span style="font-weight: bold;">Responder/Receiver</span> role for <span style="font-weight: bold;">machine B</span>.
    -   **Initialization mode**: In this frame, click to select <span style="font-weight: bold;">Responding Site</span> and <span style="font-weight: bold;">Trace</span>.
4.  In the <span style="font-weight: bold;">Options</span> tab of the <span style="font-style: italic;">New Remote Site</span> window, accept all default values.
5.  In the <span style="font-weight: bold;">Network address</span> tab of the <span style="font-style: italic;">New Remote Site</span> window:
    -   Select the <span style="font-weight: bold;">Main address</span> radio button.
    -   Right-click the <span style="font-weight: bold;">Network type</span> field, and select <span style="font-weight: bold;">TCP</span> from the drop-down list.
    -   When you select **TCP**, Gateway displays IP address, port number and Proxy fields in the tab.
    -   Enter the IP address of the Remote Site machine.
    -   Enter the TCP port for transfer access. For PeSIT transfers, the default port is <span style="font-weight: bold;">6330</span>.
6.  In the <span style="font-weight: bold;">PeSIT</span> tab of the *New Remote Site* window, accept all default values. <span style="font-style: italic;">Do not</span> enter any ID or passwords in provided fields.
7.  In the <span style="font-weight: bold;">Net security</span> tab of the *New Remote Site* window, accept the default value, <span style="font-weight: bold;">None</span>.
8.  Click <span style="font-weight: bold;">OK</span> to accept the parameter values.  
    Gateway creates the machine B Remote Site object.

#### Machine B: Defining the Remote Site

In our Transfer Request, machine B will receive a file from another machine (Remote Site).

We identify the characteristics of the remote machine (<span style="font-weight: bold;">machine A</span>) to Gateway on <span style="font-weight: bold;">machine B</span> by creating a Remote Site object.

On <span style="font-weight: bold;">machine B</span>:

In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: **Partner Management &gt; Sites**

Right-click <span style="font-weight: bold;">Remote Site</span>. From the context menu that appears, select <span style="font-weight: bold;">New</span>  
Gateway displays the <span style="font-style: italic;">New Remote Site</span> window.

In the <span style="font-weight: bold;">General</span> tab of the *New Remote Site* window, enter values in the following fields:

-   <span style="font-weight: bold;">Alias</span>: Enter the HostName of <span style="font-weight: bold;">machine A</span>. For example, if <span style="font-weight: bold;">machine A</span> has as HostName <span style="font-style: italic;">machineA</span>, enter <span style="font-weight: bold;">machineA</span>
-   <span style="font-weight: bold;">Protocol</span>: Select <span style="font-weight: bold;">PeSITE E</span> from the drop-down list.  
    When you select this protocol, Gateway displays two additional tabs in the <span style="font-style: italic;">New Remote Site</span> window.
-   **Protocol identifier**: Use the same protocol identifier as you use in the default Local Site definition on <span style="font-weight: bold;">machine A</span>. In our example our Protocol identifier is <span style="font-weight: bold;font-style: italic;">machineA</span> (in this case it is identical to the HostName).
-   To confirm the protocol identifier of <span style="font-weight: bold;">machine A</span>:
    -   On **machine A**, in the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Partner Management > Sites > Local Site</span>
    -   Right-click <span style="font-weight: bold;">Local Site</span>.
    -   In the display pane (right pane), right-click the name of the Local Site. Select <span style="font-weight: bold;">View...</span> from the context menu that appears. Gateway opens the <span style="font-style: italic;">Local Site view</span> window.
    -   Note the name in the **Protocol Identifier** field.
-   **Group name**: Gateway enters the default group name <span style="font-weight: bold;">GDEFAULT</span>. Do not change this value.
-   **Role frame**: In this frame, click to select **Initiator/Sender** role for <span style="font-weight: bold;">machine A</span>.
-   **Initialization mode**: In this frame, click to select <span style="font-weight: bold;">Initiating Site</span> and <span style="font-weight: bold;">Trace</span>.

In the <span style="font-weight: bold;">Options</span> tab of the *New Remote Site* window, accept all default values.

In the <span style="font-weight: bold;">Network address</span> tab of the *New Remote Site* window:

Select the <span style="font-weight: bold;">Main address</span> radio button.

Right-click the <span style="font-weight: bold;">Network type</span> field, and select <span style="font-weight: bold;">TCP</span> from the drop-down list.

When you select TCP, Gateway displays IP address, port number and Proxy fields in the tab.

-   Enter the IP address of the Remote Site machine.
-   Enter the TCP port for transfer access. For PeSIT transfers, the default port is <span style="font-weight: bold;">6330</span>.

In the <span style="font-weight: bold;">PeSIT</span> tab of the <span style="font-style: italic;">New Remote Site</span> window, accept all default values. <span style="font-style: italic;">Do not</span> enter any ID or passwords in provided fields.

In the <span style="font-weight: bold;">Net security</span> tab of the <span style="font-style: italic;">New Remote Site</span> window, accept the default value, <span style="font-weight: bold;">None</span>.

Click <span style="font-weight: bold;">OK</span> to accept the parameter values.  
Gateway creates the <span style="font-weight: bold;">machine A</span> Remote Site object.

<span id="Executing_PeSIT_Transfer_Request"></span>

## Executing the Transfer Request

We want to transfer the file <span class="code">Test.txt</span> from <span style="font-weight: bold;">machine A</span> to <span style="font-weight: bold;">machine B</span>. For this example we assume that the file <span class="code">Test.txt</span> is located in <span class="code">C:\\temp</span>.

To transfer the file:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click <span style="font-weight: bold;">Transfers</span>, and then select <span style="font-weight: bold;">New > Transfer Request</span> in the context menu.  
    Gateway displays the <span style="font-style: italic;">New Transfer Request</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New Transfer Request</span> window, enter values in the following fields:
    -   **Type**: From the drop-down list, select the request type <span style="font-weight: bold;">Trans</span> (Transfer Request).
    -   **Mode**: From the drop-down list, select the mode in which the local site operates, <span style="font-weight: bold;">Initiator</span>. You are initiating the transfer with your Local Site in the client (initiator) role.
    -   **Direction**: From the drop-down list, select the direction of your transfer, <span style="font-weight: bold;">Send</span>.
    -   **Application**: From the drop-down list, select an application to define file system attributes for your file transfer. Gateway provides the default application <span style="font-style: italic;">DEFAULT\_A</span> for PeSIT transfers of files in ASCII format. Select <span style="font-weight: bold;">DEFAULT\_A</span> from the drop-down list.
    -   **Sites/Destination Alias**: In the Destination Alias field enter the alias of the destination machine, <span style="font-weight: bold;">machineA</span>, exactly as you entered it when you created your Remote Site object.
4.  In the <span style="font-weight: bold;">Attributes</span> tab of the <span style="font-style: italic;">New Transfer Request</span> window, enter the name of the file you want to transfer and the path to that file. For this example, enter: <span class="code" style="font-weight: bold;">C:\\temp\\Test.txt</span>  
    Leave the remaining fields of this tab empty for this example.
5.  For the remaining tabs, accept all default values. The default values of the remaining fields are either empty (no value) or <span style="font-style: italic;">undefined</span>.
6.  Click <span style="font-weight: bold;">OK</span> to validate the values and initiate the Transfer Request.  
    Gateway begins processing of the transfer, and attributes a number to the transfer which it displays in a pop-up window.  
    <img src="/Images/Gateway/TransRequestResult.gif" width="191" height="121" />

<span id="Transfer_Results"></span>

## Transfer results

When you submit the Transfer Request, Gateway analyzes the information you have provided for the transfer in the Transfer Request and in the associated Site and Application objects. If the network and application conditions are correct, the transfer is executed and a copy of the file is deposited on <span style="font-weight: bold;">machine B</span>.

### Using the Mailbox

<span style="font-weight: bold;">Machine A</span> and <span style="font-weight: bold;">machine B</span> create and record a record of each processed Transfer Request in their respective Mailboxes.

To view the record of a Transfer Requests contained in the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> sub-node.  
    In the right pane, Gateway displays all Transfer Request records currently contained in the Mailbox. Each row represents one Transfer Request.
3.  In the left pane, double-click the line that represents the Transfer Request you want to review.  
    Gateway displays the <span style="font-style: italic;">Transfer Request information</span> window. Use the tabs of this window to view the characteristics of the Transfer Request.

### Using the Log file

By default, Gateway generates traces of network activities that it records to your log file. To view the contents of the log file, in the left pane of the GUI main window, select <span style="font-weight: bold;">Transfer Management &gt; Monitoring &gt; Log</span>. Gateway displays the current log file contents in the right pane.

To display a help file that provides information about a specific log entry, double-click any line of the log file in the right pane. Gateway opens the online help, displaying information relating to the line you selected.

If you require supplementary trace information concerning CGate processes, you can activate CGate logging. In this example, CGate logging can be useful to monitor the handling of connection access to <span style="font-weight: bold;">machine B</span>.

On <span style="font-weight: bold;">machine B</span>, proceed as follows to enable the recording of CGate event information to the log file:

-   In the left pane of the Gateway GUI, right-click the icon that represents your Local <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Gateway</span>.
-   Click the <span style="font-weight: bold;">Log levels...</span> button.
-   In <span style="font-weight: bold;">CGate</span>, select <span style="font-weight: bold;">Full</span>.
-   Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.  
    Gateway immediately takes the new settings into account.

Related topics

[About PeSIT Hors SIT](../../protocols_about/pesit_about)

[Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_legacy_pesite_tcp)

[Viewing and managing Mailbox contents](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
