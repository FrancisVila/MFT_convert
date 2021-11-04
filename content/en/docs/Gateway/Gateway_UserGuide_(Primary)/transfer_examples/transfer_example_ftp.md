{
    "title": "Executing a basic FTP transfer",
    "linkTitle": "Basic FTP transfer",
    "weight": "120"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Transfer Examples

[About this example](#about)

[Prerequisites](#Prerequisites)

[Configuring the client/sender (machine A)](#Configuring_the_client_sender__machine_A_)

[Configuring the server/receiver (machine B)](#Configuring_the_server_receiver)

[Executing the FTP transfer to server](#Executing_the_FTP_transfer_to_server_receiver)

[Transfer results](#Transfer_results)

<span id="about"></span>

## About this example

This topic describes the minimal configuration needed to enable you to execute an FTP Transfer, without certificates or security, between two machines, both hosting Gateways.

To send a file via FTP, both the client and the server need to be configured to recognize one another. In addition, the transfer protocol FTP and its most basic parameters must be defined. The following example uses the minimal number of parameters possible to achieve an FTP transfer. You can use this example as a basis for a more complex transfer.

In this example we use the Gateway GUI to transfer a <span class="code">.txt</span> file from <span style="font-weight: bold;">machine A</span>, the client/sender, to <span style="font-weight: bold;">machine B</span>, the server/receiver.

<span id="Prerequisites"></span>

## Prerequisites

-   Gateway must be correctly installed and running on both <span style="font-weight: bold;">machine A</span> and <span style="font-weight: bold;">machine B</span>.
-   The two machines must be linked by a TCP/IP connection.
-   The FTP protocol must be activated on both machines (refer to [Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ftp)).
-   Open a Windows environment to use the GUI.

<span id="Configuring_the_client_sender__machine_A_"></span>

## Configuring the client/sender (machine A)

On <span style="font-weight: bold;">machine A</span> you must configure a Gateway Remote Site object for this FTP transfer.

### Remote Site

On <span style="font-weight: bold;">machine A</span>, define the <span style="font-weight: bold;">machine B</span> values in the *Remote Site* window as follows:

In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
<span style="font-weight: bold;">Partner Management &gt; Sites</span>  

Right-click <span style="font-weight: bold;">Remote Site</span>, then from the context menu that appears, select <span style="font-weight: bold;">New</span>.  
Gateway displays the <span style="font-style: italic;">New Remote Site</span> window.  

Complete the fields of the <span style="font-style: italic;">New Remote Site</span> window. You do not need to complete fields that are not listed.

In the <span style="font-weight: bold;">[General](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab:

-   <span style="font-weight: bold;">Alias</span>: Enter the Remote Site alias. You can enter up to 31 alphanumeric characters.
-   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">FTP</span>.
-   <span style="font-weight: bold;">Group name</span>: Enter a group name for this Site. Keep in mind that the Site must belong to the same group as the Application used for a given Transfer. By default, this value is set to <span style="font-weight: bold;">GDEFAULT</span>.
-   <span style="font-weight: bold;">Role</span>: Click to select all as enabled.
-   <span style="font-weight: bold;">Initialization mode</span>: Click to select all as enabled.  

In the <span style="font-weight: bold;">[Options](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_options_tab)</span> tab:

-   <span style="font-weight: bold;">Maximum data block size (in bytes)</span>: Enter <span style="font-weight: bold;">4000</span>.
-   <span style="font-weight: bold;">Max. no. of simultaneous connections to this Site</span>: Enter <span style="font-weight: bold;">4</span>.
-   <span style="font-weight: bold;">Max. no. of simultaneous connections from this Site</span>: Enter <span style="font-weight: bold;">4</span>.
-   <span style="font-weight: bold;">Max. no. of connection retries before time limit</span>: Enter <span style="font-weight: bold;">300</span>.
-   <span style="font-weight: bold;">Time before first retry (in seconds)</span>: Enter <span style="font-weight: bold;">100 or higher</span>.
-   <span style="font-weight: bold;">Maximum interval between retries (in seconds)</span>: Enter <span style="font-weight: bold;">1800</span>.  

In the <span style="font-weight: bold;">[Network address](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_network_address_tab)</span> tab:

-   <span style="font-weight: bold;">Communication address</span>: Select <span style="font-weight: bold;">Main address</span>.
-   <span style="font-weight: bold;">Network type</span>: From the drop-down list, select <span style="font-weight: bold;">TCP/IP</span>.
-   In the Right pane, TCP specific main address tab:
    -   <span style="font-weight: bold;">IP address or machine name</span>: Enter the IP address as &lt;my. domain.name>
    -   <span style="font-weight: bold;">Port number</span>: Enter 6370.  

In the <span style="font-weight: bold;">[FTP/HTTP](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_ftp_http_tab)</span> tab:

-   <span style="font-weight: bold;">ID/Password to send</span> (<span style="font-style: italic;">Mandatory):</span> Enter the identifier and password to send during the connection phase. You can enter up to 25 alphanumeric characters in the <span style="font-weight: bold;">ID</span> field and 15 alphanumeric characters in the <span style="font-weight: bold;">password</span> field.  
    In client mode, Gateway uses the values that you set in these fields for the login phase on a remote server.
-   <span style="font-weight: bold;">ID/Password to check</span>: Enter the identifier and password used to check partner identity. The identifier corresponds to the protocol identifier.  

After completing all Remote Site tabs, click <span style="font-weight: bold;">OK</span> to confirm.

<span id="Configuring_the_server_receiver"></span>

## Configuring the server/receiver (machine B)

In our example FTP Transfer, <span style="font-weight: bold;">machine B</span> is the destination and receives a file from <span style="font-weight: bold;">machine A</span>, the source for the transfer.

On **machine B**, configure the following Gateway objects to enable <span style="font-weight: bold;">machine B</span>, the server/receiver, to receive a file via an FTP transfer from <span style="font-weight: bold;">machine A</span>:

-   [VFD](../../transfers_start_here/virtual_file_directory_start_here)
-   [CGateGroup](../../managing_partners_start_here/cgates_start_here)
-   [CGate](../../managing_partners_start_here/cgates_start_here)
-   Network Profile. See the Security Guide > [Managing Network profiles](#) for further information (requires login)

### VFD

Create a new VFD object on <span style="font-weight: bold;">machine B</span> as follows:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">VFD</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Virtual File Directory</span> window.
3.  Complete the fields as follows:
    -   <span style="font-weight: bold;">PathName</span>: Enter <span style="font-weight: bold;">/FTP</span> if this is not already displayed. When you create a new directory, Gateway automatically completes the path name field with the path of the parent directory. The absolute path of the root directory is "/".
    -   Repeat to create another directory called <span style="font-weight: bold;">/MyCustomers</span>. The result is <span style="font-weight: bold;">/FTP/MyCustomers</span>.
    -   <span style="font-weight: bold;">Name</span>: Enter the name of the directory, for example <span style="font-weight: bold;">Customer1</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm.  
    Later in this example, you will transfer the selected file to <span style="font-weight: bold;">/FTP/MyCustomers/Customer1</span>.

### CGateGroup

Create a new root CGateGroup object for the <span style="font-weight: bold;">machine B</span> configuration as follows:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab, complete the fields as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">GROUP FTP</span> as the unique name for the CGateGroup.
    -   <span style="font-weight: bold;">Parent CGateGroup</span>: Enter <span style="font-weight: bold;">GFTP</span>.
    -   <span style="font-weight: bold;">State</span>: From the drop-down list select <span style="font-weight: bold;">Enabled</span>.
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">FTP</span>.
    -   <span style="font-weight: bold;">Called address</span>: Enter <span style="font-weight: bold;">\*</span> as the called TCP/IP address for this CGateGroup.
    -   <span style="font-weight: bold;">Called SAP</span>: Enter <span style="font-weight: bold;">\*</span> as the TCP/IP local connection port.  
        Alternatively, you can enter the local SAP defined in the Gateway configuration menu. By default, this value is 6370.
    -   <span style="font-weight: bold;">Template Site</span>: From the drop-down list, select <span style="font-weight: bold;">TFTP</span> as the Template Site that you want Gateway to use to create a dynamic Site.
4.  In the <span style="font-weight: bold;">Output parameters</span> tab, complete the fields as follows:
    -   <span style="font-weight: bold;">Root directory</span>: Enter <span style="font-weight: bold;">/FTP/MyCustomers</span>.
    -   <span style="font-weight: bold;">Home directory</span>: You do not need to complete this field.

      
    The <span style="font-weight: bold;">Output parameters</span> tab is identical for both CGateGroup and CGate objects. The fields on the <span style="font-weight: bold;">Output parameters</span> tab define parameters for the current connection.
5.  In the <span style="font-weight: bold;">VFD Rights</span> tab, complete the fields as follows:
    -   <span style="font-weight: bold;">Directory path</span>: Enter<span class="code" style="font-weight: bold;"> /</span> as the Directory path. Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree below the root directory.
    -   <span style="font-weight: bold;">File pattern</span>: Enter \* in this field. This field further refines the VFD rights to specific file types.
    -   <span style="font-weight: bold;">Sub-directory inheritance</span>: Click to select this box. This indicates that all sub-directories inherit the parameters that you set here.
    -   Click to select all of the <span style="font-weight: bold;">Directory rights</span> boxes: <span style="font-weight: bold;">List</span>, <span style="font-weight: bold;">Create</span>, and <span style="font-weight: bold;">Remove</span>.
    -   Click to select all of the <span style="font-weight: bold;">File rights</span> boxes: <span style="font-weight: bold;">Read</span>, <span style="font-weight: bold;">Delete</span>, and <span style="font-weight: bold;">Write</span>.
6.  Click <span style="font-weight: bold;">Add</span> to confirm.  
7.  In the <span style="font-weight: bold;">Calling Address</span> tab, complete the fields as follows:
    -   <span style="font-weight: bold;">Calling address</span>: Enter the wildcard character <span style="font-weight: bold;">\*</span>.
    -   <span style="font-weight: bold;">Access allowed</span>: Click to select. This authorizes access from the calling address.
8.  Click <span style="font-weight: bold;">Add</span> to confirm.  
    You have created the new CGateGroup object.

### CGate

The CGate object is an identification filter used internally in server mode. CGates determine whether or not a client has the right to connect to Gateway and exchange files with it. Create a CGate object for this example transfer as follows:

1.  Right-click to select the parent <span style="font-weight: bold;">CGateGroup</span> folder that you have just created.
2.  Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">CGate</span> from the context menu to display the <span style="font-style: italic;">CGate</span> window.
3.  Complete the CGate <span style="font-weight: bold;">General</span> tab as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">CG\_FTP1</span>, as a unique identifier for the new object.
    -   <span style="font-weight: bold;">Parent CGateGroup</span>: If it is not already displayed, enter <span style="font-weight: bold;">GFTP</span>, the name of the parent CGateGroup with which the new object is associated.
    -   Complete the <span style="font-weight: bold;">HTTP / FTP / SFTP / PeSIT pre-connection</span> <span style="font-weight: bold;">Identification/Checking</span> fields as follows:

      
    <span style="font-weight: bold;">Login user name</span>: Enter the user [login name of <span style="font-weight: bold;">machine A</span>](#Configuring_the_client_sender__machine_A_), the client/sender.  
    <span style="font-weight: bold;">Login password</span>: Enter the password associated with the user login field. Remember that the password is case sensitive.
4.  Complete the CGate <span style="font-weight: bold;">Output</span> tab as follows:
    -   <span style="font-weight: bold;">Root directory</span>: The root directory for the connected user should be displayed automatically.
    -   <span style="font-weight: bold;">Home directory</span>: In this example, enter <span style="font-weight: bold;">/FTP/MyCustomers/Customer1</span> as the VFD directory on which the first LIST command is processed following protocol connection.
5.  Click <span style="font-weight: bold;">OK</span> to confirm.

### Network Profile

A Network Profile associates an incoming network connection request with a Security Profile. The connection does not use Security if you have not selected TLS or SSH.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Network Profile</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span style="font-style: italic;">New Network Profile</span> window.
3.  In the <span style="font-style: italic;">New Network Profile</span> window, enter the following values:
    -   <span style="font-weight: bold;">Network profile</span>: Enter <span style="font-weight: bold;">NP\_FTP</span>.
    -   <span style="font-weight: bold;">Origin address/port</span>: Enter <span style="font-weight: bold;">\*.\*.\*.\*</span> as the address or the listening port for <span style="font-weight: bold;">machine A</span>.
    -   <span style="font-weight: bold;">Destination address/port</span>: Enter <span style="font-weight: bold;">\*.\*.\*.\*</span> as the address or the listening port for <span style="font-weight: bold;">machine B</span>.
    -   <span style="font-weight: bold;">Network type</span>: Select <span style="font-weight: bold;">TCP/IP</span>.
    -   <span style="font-weight: bold;">Network security</span>: Select <span style="font-weight: bold;">None</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm.

<span id="Executing_the_FTP_transfer_to_server_receiver"></span>

## Executing the FTP transfer to server

From <span style="font-weight: bold;">machine A</span> initiate the transfer:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Transfers</span> sub-node, and then select <span style="font-weight: bold;">New > Transfer Request</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New Transfer Request</span> window<span style="font-style: italic;">.</span>
3.  Complete the Transfer Request <span style="font-weight: bold;">[General](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab)</span> tab.
    -   <span style="font-weight: bold;">Type</span>: From the drop-down list, select the Transfer type: <span style="font-weight: bold;">TRANS</span>.
    -   <span style="font-weight: bold;">Mode</span>: From the drop-down list, select the Transfer connection mode <span style="font-weight: bold;">Initiator</span>.
    -   <span style="font-weight: bold;">Direction</span>: From the drop-down list, select the Transfer direction <span style="font-weight: bold;">Send</span>.
    -   <span style="font-weight: bold;">Application</span>: Select <span style="font-weight: bold;">FTP\_A</span> as the Application from the drop-down list.
    -   <span style="font-weight: bold;">Permanent</span>: This option allows you to set Transfer availability to permanent. From the drop-down list, select <span style="font-weight: bold;">No</span>.
    -   <span style="font-weight: bold;">Originator alias</span>: Enter the Local Site alias that is the source of the file transfer. In this example the alias for <span style="font-weight: bold;">machine A</span>.
    -   <span style="font-weight: bold;">Destination alias</span>: Enter the Site alias that is the file transfer destination. In this example the alias for <span style="font-weight: bold;">machine B</span>.
4.  Complete the Transfer Request <span style="font-weight: bold;">[Attributes](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab)</span> tab.
    -   <span style="font-weight: bold;">File component</span>: Enter the local file name (without the file path) of the physical file to send.
5.  After completing these tabs, click <span style="font-weight: bold;">OK</span> to confirm.  
    <span style="font-weight: bold;">Machine A</span> contacts <span style="font-weight: bold;">machine B</span> and begins the file transfer procedure.

<span id="Transfer_results"></span>

## Transfer results

After completing the procedure [Executing the FTP transfer to server](#Executing_the_FTP_transfer_to_server_receiver), refresh your screen and check that the transfer was successfully completed. If all of the entered network and application conditions are correct, the transfer is executed and a copy of the file is put on <span style="font-weight: bold;">machine B</span>.

After a transfer, remember to refresh the screen in both the Mailbox and the Log file.

### Using the Mailbox

<span style="font-weight: bold;">Machine A</span> and <span style="font-weight: bold;">machine B</span> create and record a record of each processed Transfer Request in their respective Mailboxes.

To view the record of a Transfer Requests in the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> sub-node.  
    In the right pane, Gateway displays all Transfer Request records currently contained in the Mailbox. Each row represents one Transfer Request.
3.  In the left pane, double-click the line that represents the Transfer Request you want to review.  
    Gateway displays the <span style="font-style: italic;">Transfer Request information</span> window. Use the tabs of this window to view the characteristics of the Transfer Request.

### Using the Log file

By default, Gateway records network activity in a log file. To view the log file, in the left pane of the GUI main window click <span style="font-weight: bold;">Transfer Management &gt; Monitoring &gt; Log</span>. Gateway displays the current log file contents in the right pane.

To display a help file that provides information about a specific log entry, double-click any line of the log file in the right pane. Gateway opens the online help, displaying information relating to the line you selected.

If you need more trace information about CGate processes, you can activate CGate logging. In this example, CGate logging can be useful to monitor the connection with <span style="font-weight: bold;">machine B</span>.

On <span style="font-weight: bold;">machine B</span>, proceed as follows to enable the recording of CGate event information to the log file:

-   In the left pane of the Gateway GUI, right-click the icon that represents your Local Gateway and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Gateway</span>.
-   Click the <span style="font-weight: bold;">Log levels</span> button.
-   In <span style="font-weight: bold;">CGate</span>, select <span style="font-weight: bold;">Full</span>.
-   Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.  
    Gateway immediately takes the new settings into account.

Related topics

[About FTP](../../protocols_about/ftp_about)

[Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ftp)

[Viewing and managing the Mailbox](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
