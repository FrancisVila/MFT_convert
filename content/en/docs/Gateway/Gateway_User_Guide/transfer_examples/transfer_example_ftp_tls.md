{
    "title": "Executing an FTP transfer using TLS and certificates",
    "linkTitle": "FTP transfer using TLS and certificates",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Transfer Examples

[About this example](#about)

[Prerequisites](#Prerequisites)

[Configuring the client/sender (machine A)](#Configuring_the_client_sender__machine_A_)

[Configuring the server/receiver (machine B)](#Configuring_the_server_receiver)

[Executing the FTP transfer](#Executing_the_FTP_transfer)

[Transfer results](#Transfer_results)

[Validating certificates](#validating_certificates)

<span id="about"></span>

## About this example

This topic describes the basic configuration that enables you to execute an FTP transfer between two <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> hosted machines using certificates.

To send a file via FTP, both the client and the server need to be configured to recognize one another. In addition, the transfer protocol FTP and its most basic parameters must be defined in the Gateway configuration menu.

The following example uses the minimal number of parameters possible to achieve an FTP transfer. You can use this example as a basis for a more complex transfer.

In this example we use the Gateway GUI to transfer a <span class="code">.txt</span> file from <span style="font-weight: bold;">machine A</span>, the client/sender, to <span style="font-weight: bold;">machine B</span>, the server/receiver.

<span id="Prerequisites"></span>

## Prerequisites

-   Gateway must be correctly installed and running on both <span style="font-weight: bold;">machine A</span> and <span style="font-weight: bold;">machine B</span>.
-   The two machines must also be linked by a TCP/IP connection.
-   Open a windows environment to support the GUI.
-   Configure Gateway to support FTP and to require a secure transfer that uses certificates. Refer to [Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ftp).

<span id="Configuring_the_client_sender__machine_A_"></span>

## Configuring the client/sender (machine A)

For this FTP transfer, configure the following two objects on <span style="font-weight: bold;">machine A</span>.

-   [Remote Site](../../managing_partners_start_here/sites_start_here/managing_remote_sites)
-   TLS Security Profile. See the [Security Guide](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm) for further information (requires login)

### Remote Site

On <span style="font-weight: bold;">machine A</span>, define values for remote <span style="font-weight: bold;">machine B</span> in the Remote Site window. Complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Partner Management > Sites**
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node. From the context menu that appears, select <span style="font-weight: bold;">New</span>.  
    Gateway displays the <span style="font-style: italic;">New Remote Site</span> window.
3.  In the <span style="font-style: italic;">New Remote Site</span> window, complete the tabs as follows. You do not need to complete fields that are not listed.
4.  In the <span style="font-weight: bold;">[General](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab:
    -   <span style="font-weight: bold;">Alias</span>: Enter the Remote Site alias. You can enter up to 31 alphanumeric characters.
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">FTP</span>.
    -   <span style="font-weight: bold;">Group name</span>: Enter a group name for this Site. Keep in mind that the Site must belong to the same group as the Application used for a given Transfer. By default, this value is set to <span style="font-weight: bold;">GDEFAULT</span>.
    -   <span style="font-weight: bold;">Role</span>: Click to select all as enabled.
    -   <span style="font-weight: bold;">Initialization mode</span>: Click to select all as enabled.
5.  In the <span style="font-weight: bold;">[Options](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_options_tab)</span> tab:
    -   <span style="font-weight: bold;">Max. no. of simultaneous connections to this Site</span>: Enter <span style="font-weight: bold;">100</span>.
    -   <span style="font-weight: bold;">Max. no. of simultaneous connections from this Site</span>: Enter <span style="font-weight: bold;">100</span>.
6.  In the <span style="font-weight: bold;">[Network address](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_network_address_tab)</span> tab:
    -   <span style="font-weight: bold;">Communication address</span>: Select <span style="font-weight: bold;">Main address</span>.
    -   <span style="font-weight: bold;">Network type</span>: From the drop-down list, select <span style="font-weight: bold;">TCP/IP</span>.
    -   In the Right pane, TCP specific main address tab:
        -   <span style="font-weight: bold;">IP address or machine name</span>: Enter the IP address as &lt;my.domain.name>
        -   <span style="font-weight: bold;">Port number:</span> For this example enter 6370.
7.  In the <span style="font-weight: bold;">[FTP/HTTP](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_ftp_http_tab)</span> tab:
    -   <span style="font-weight: bold;">ID/Password to send</span> (<span style="font-style: italic;">mandatory</span>): Enter the identifier and password to send during the connection phase. You can enter up to 25 alphanumeric characters in the ID field and 15 alphanumeric characters in the password field.

      
    In client mode, Gateway uses the values that you set in these fields for the login phase on a remote server.
8.  In the <span style="font-weight: bold;">[Net Security](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_net_security_tab)</span> tab:
    -   <span style="font-weight: bold;">Network security</span>: From the drop-down list, select <span style="font-weight: bold;">TLS</span>. The following <span style="font-weight: bold;">TLS security</span> fields are displayed.
    -   <span style="font-weight: bold;">Security profile for outgoing connection</span>: Enter the name of the outgoing TLS Security Profile such as: <span style="font-weight: bold;">SP\_FTP\_OUT</span>.
9.  When you have completed all required fields, click <span style="font-weight: bold;">OK</span> to confirm.

<span id="TLS_Profile_window"></span>

### TLS Security Profile

Once you have completed the Remote Site set-up, use the <span style="font-weight: bold;">TLS Profile</span> tab to define the TLS Profile for <span style="font-weight: bold;">machine A</span>.

If you are performing this procedure for the first time, you must import a User certificate before completing the TLS Profile window.
See *Security Guide &gt; [Importing a Certificate](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Certificate_management_(GUI).htm)* for further information.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Security Profile**
2.  Right-click the <span style="font-weight: bold;">TLS Profile</span> sub-node and select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> New TLS Profile</span> window.
3.  In the<span style="font-style: italic;"> New TLS Profile</span> window, complete the <span style="font-weight: bold;">General</span> tab fields as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter a unique name for the TLS Profile, the same name that you used in the previous Network tab. In this example use <span style="font-weight: bold;">SP\_FTP\_OUT</span>.
    -   <span style="font-weight: bold;">Profile Type</span>: From the drop-down list, select the <span style="font-weight: bold;">CLIENT</span>.
    -   <span style="font-weight: bold;">Client authentication</span>: Select <span style="font-weight: bold;">TLS\_AUT\_OPTIONAL</span>, the most flexible of the authentications, from the drop-down list.
    -   <span style="font-weight: bold;">Accepted SSL versions</span>: Select <span style="font-weight: bold;">TLSV1</span>.
    -   <span style="font-weight: bold;">Accepted cipher suites</span>: We recommend, for this example, that you select <span style="font-weight: bold;">RSA\_WITH\_AES\_128\_CBC\_SHA</span>.
    -   <span style="font-weight: bold;">Automatic import of partner certificate</span>: Click to select and enable this function.
    -   <span style="font-weight: bold;">User certificates</span>: The Select single certificate box should be active. If not, click to select.
    -   Enter the <span style="font-weight: bold;">certificate name</span>.
        Use the <img src="/Images/Gateway/Certificate.gif" width="16" height="16" /> icon to browse the certificate list if you do not know the name of the certificate.
        See *Security Guide > Managing TLS > [Managing TLS Security Profiles](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/TLS_Security_profiles__GUI_.htm)* for further information (requires login).

      
    <span style="font-weight: bold;">Note:</span> In this example, you have to validate the Root certificate validation before the FTP can successfully occur.
    Refer to [Validating certificates](#validating_certificates).
4.  In the <span style="font-weight: bold;">Detail</span> tab of the TLS Profile window leave all default settings.  
    You have completed the <span style="font-weight: bold;">machine A</span>, client/sender, configuration.
5.  Click <span style="font-weight: bold;">OK</span> to confirm your selections.

<span id="Configuring_the_server_receiver"></span>

## Configuring the server/receiver (machine B)

In our example FTP Transfer, <span style="font-weight: bold;">machine B</span> is the destination and receives a file from <span style="font-weight: bold;">machine A</span>, the source for the transfer. Configure the following objects to enable <span style="font-weight: bold;">machine B</span>, the server/receiver, to receive a file via an FTP transfer from <span style="font-weight: bold;">machine A</span>. Define the following for machine B:

-   [VFD](../../transfers_start_here/virtual_file_directory_start_here)
-   [CGateGroup](../../managing_partners_start_here/cgates_start_here)
-   [CGate](../../managing_partners_start_here/cgates_start_here)
-   Network Profile. See *Security guide >* [Managing Network Profiles](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Network_Profiles/Network_Profiles_(GUI).htm) for further information (requires login).
-   TLS Profile. See *Security guide >* [SSL and TLS protocols](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/ssl_and_tls_protocols_about.htm) for further information.

### VFD

On <span style="font-weight: bold;">machine B</span>, create a new VFD object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">VFD</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Virtual File Directory</span> window.
3.  Complete the fields of the <span style="font-style: italic;">New Virtual File Directory</span> window as follows:
    -   <span style="font-weight: bold;">PathName</span>: Enter <span style="font-weight: bold;">/FTP</span> if this is not already displayed. When you create a new directory, Gateway automatically completes the path name field with the path of the parent directory. The absolute path of the root directory is "/". Repeat and create the directory <span style="font-weight: bold;">/MyNewCustomers</span>.
    -   <span style="font-weight: bold;">Name</span>: Enter the directory name, for example <span style="font-weight: bold;">Customer1</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm.

### CGateGroup

On <span style="font-weight: bold;">machine B</span>, create a new root CGateGroup object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window.
3.  In the <span style="font-style: italic;">New CGateGroup</span> window, complete the <span style="font-weight: bold;">General</span> tab as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">GROUP FTP</span> as the unique name for the CGateGroup.
    -   <span style="font-weight: bold;">State</span>: From the drop-down list, select the state <span style="font-weight: bold;">Enabled</span>.
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">FTP</span>.
    -   <span style="font-weight: bold;">Called address</span>: Enter <span style="font-weight: bold;">\*</span> as the called TCP/IP address for this CGateGroup.
    -   <span style="font-weight: bold;">Called SAP</span>: Enter <span style="font-weight: bold;">\*</span> as the TCP/IP local connection port.  
        (Alternatively, you can enter the default port, 6370)
    -   <span style="font-weight: bold;">Template Site</span>: From the drop-down list, select <span style="font-weight: bold;">TFTP</span> as the Template Site that you want Gateway to use to create a dynamic Site.
4.  Click the <span style="font-weight: bold;">Output Parameters</span> tab and complete the fields as follows:
    -   <span style="font-weight: bold;">Root directory</span>: Enter <span style="font-weight: bold;">/FTP/MyNewCustomers</span>.
    -   <span style="font-weight: bold;">Home directory</span>: Leave blank.

      
    The <span style="font-weight: bold;">Output parameters</span> tab is identical for both CGateGroup and CGate objects. The fields on the <span style="font-weight: bold;">Output parameters</span> tab define parameters for the current connection.
5.  Click the <span style="font-weight: bold;">VFD Rights</span> tab and complete the fields as follows:
    -   <span style="font-weight: bold;">Directory path</span>: Enter / as the Directory path. Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree below the root directory.
    -   <span style="font-weight: bold;">File pattern</span>: Enter \* in this field. This field further refines the VFD rights to specific file types.
    -   <span style="font-weight: bold;">Sub-directory inheritance</span>: Click to select this box. This indicates that all sub-directories inherit the parameters that you set here.
    -   Click to select all of the<span style="font-weight: bold;"> Directory rights</span> boxes: List, Create, and Remove.
    -   Click to select all of the <span style="font-weight: bold;">File rights</span> boxes: <span style="font-weight: bold;">Read</span>, <span style="font-weight: bold;">Delete</span>, and <span style="font-weight: bold;">Write</span>.
6.  Click <span style="font-weight: bold;">Add</span> to confirm.
7.  Click the <span style="font-weight: bold;">Calling Address</span> tab and complete the fields as follows:
    -   <span style="font-weight: bold;">Calling address</span>: Enter the wildcard character <span style="font-weight: bold;">\*</span>.
    -   <span style="font-weight: bold;">Access allowed</span>: Click to select. This authorizes access from the calling address.
8.  Click <span style="font-weight: bold;">Add</span>, then click<span style="font-weight: bold;"> OK</span> to confirm.  
    You have created a new CGateGroup object.

### CGate

The CGate object is an identification filter used internally in server mode. CGates determine whether a client has the right to connect to Gateway and exchange files with it or not. Create a CGate object for this example transfer:

1.  Right-click to select the parent <span style="font-weight: bold;">CGateGroup</span> folder that you have just created.
2.  Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">CGate</span> from the context menu to display the <span style="font-style: italic;">CGate</span> window.
3.  Complete the CGate <span style="font-weight: bold;">General</span> tab as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">CG\_FTP1</span>, as a unique identifier for the new object.
    -   Complete the <span style="font-weight: bold;">HTTP / FTP / SFTP / PeSIT pre-connection</span> <span style="font-weight: bold;">Identification/Checking</span> fields as follows:

      
    <span style="font-weight: bold;">Login user name</span>: Enter the user [login name of the <span style="font-weight: bold;">machine A</span>](#Configuring_the_client_sender__machine_A_) (<span style="font-weight: bold;">Customer1</span> in this example) the client/sender.  
    <span style="font-weight: bold;">Login password</span>: Enter the password associated with the user login field. Remember that the password is case sensitive.
4.  Complete the CGate <span style="font-weight: bold;">Output</span> tab as follows:
    -   <span style="font-weight: bold;">Root directory</span>: In this example use <span style="font-weight: bold;">/FTP/MyCustomers</span>, the VFD root directory for the connected user, is automatically displayed.
    -   <span style="font-weight: bold;">Home directory</span>: In this example enter <span style="font-weight: bold;">/FTP/MyCustomers/Customer1</span> as the VFD directory on which the first LIST command is processed following protocol connection.
5.  Click <span style="font-weight: bold;">OK</span> to confirm.

### Network Profile

A Network Profile associates an incoming network connection request with a Security Profile. The connection does not use Security if you have not selected TLS or SSH. Create a Network Profile:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Network Profile</span> node, and from the context menu that appears, select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span style="font-style: italic;">New Network Profile</span> window.
3.  In the <span style="font-style: italic;">New Network Profile</span> window, enter the following values:
    -   <span style="font-weight: bold;">Network profile</span>: Enter <span style="font-weight: bold;">NP\_FTP</span>.
    -   <span style="font-weight: bold;">Origin address/port</span>: Enter <span style="font-weight: bold;">\*.\*.\*.\*</span> as the address and <span style="font-weight: bold;">\*</span> as the listening port for the <span style="font-weight: bold;">machine A</span>.
    -   <span style="font-weight: bold;">Destination address/port</span>: Enter <span style="font-weight: bold;">\*.\*.\*.\*</span> as the address and <span style="font-weight: bold;">\*</span> as the listening port for the <span style="font-weight: bold;">machine B</span>.  
        Alternatively, enter the default port 6370
    -   <span style="font-weight: bold;">Network type</span>: Select <span style="font-weight: bold;">TCP/IP</span>.
    -   <span style="font-weight: bold;">Network security</span>: Select <span style="font-weight: bold;">TLS</span>.
    -   <span style="font-weight: bold;">Security profile</span>: Select <span style="font-weight: bold;">SP\_FTP\_IN</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm.

### TLS Profile window

Once you have completed the Remote Site set-up, use the <span style="font-weight: bold;">TLS Profile</span> tab to define the TLS Profile for <span style="font-weight: bold;">machine B</span>.

If you are performing this procedure for the first time, you must import a Root certificate before completing the TLS Profile window.
See the *Security Guide &gt; [Importing a Certificate](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Certificate_management_(GUI).htm)* for further information (requires login).

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the  nodes:  
    **Security Management > Security Profile**
2.  Right-click the <span style="font-weight: bold;">TLS Profile</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New TLS Profile</span> window.
3.  Complete the fields in the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New TLS Profile</span> window as follows:
    -   <span style="font-weight: bold;">Name</span>: Enter a unique name for the TLS Profile, the same name that you used in the previous Network tab. In this example use <span style="font-weight: bold;">SP\_FTP\_IN</span>.
    -   <span style="font-weight: bold;">Profile Type</span>: From the drop down list, select the <span style="font-weight: bold;">SERVER</span>.
    -   <span style="font-weight: bold;">Client authentication</span>: Select <span style="font-weight: bold;">TLS\_AUT\_OPTIONAL,</span> the most flexible of the authentications,<span style="font-weight: bold;"> </span>from the drop-down list.
    -   <span style="font-weight: bold;">Accepted SSL versions</span>: Select <span style="font-weight: bold;">TLSV1</span>.
    -   <span style="font-weight: bold;">Accepted cipher suites</span>: For this example, select <span style="font-weight: bold;">RSA\_WITH\_AES\_128\_CBC\_SHA</span>.
    -   <span style="font-weight: bold;">Automatic import</span>: Click to select and enable this function.
    -   <span style="font-weight: bold;">User certificates</span>: The <span style="font-weight: bold;">Select single certificate</span> box should be active. If not, click to select. Note that when you activate the User certificate, you may make certificate validation necessary before the FTP can successfully occur.
4.  Enter the certificate name. Use the <img src="/Images/Gateway/Certificate.gif" width="16" height="16" /> icon to browse the certificate list if you do not know the name of the certificate.
    See the *Security Guide >* [Managing Certificates](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Certificate_management_(GUI).htm) for further information.
5.  In the <span style="font-weight: bold;">Detail</span> tab of the <span style="font-style: italic;">TLS Profile</span> window, leave all default settings.  
    You have completed the <span style="font-weight: bold;">machine B</span>, server/receiver, configuration.
6.  Click <span style="font-weight: bold;">OK</span> to confirm your selections.  
    <span style="font-weight: bold;">Note:</span> In this example, you have to validate the User certificate before the FTP transfer can successfully occur. Refer to [Validating certificates](#validating_certificates).

<span id="Executing_the_FTP_transfer"></span>

## Executing the FTP transfer

From <span style="font-weight: bold;">machine A</span> initiate the transfer:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Transfers</span> sub-node, and then select <span style="font-weight: bold;">New > Transfer Request</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New Transfer Request</span> window.
3.  Complete the Transfer Request [General tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab).
    -   Type<span style="font-weight: normal;">: From the drop-down list, select the Transfer type</span> TRANS<span style="font-weight: normal;">.</span>
    -   Mode<span style="font-weight: normal;">: From the drop-down list, select the Transfer connection mode</span> Initiator<span style="font-weight: normal;">.</span>
    -   <span style="font-weight: bold;">Direction</span>: From the drop-down list, select the Transfer direction <span style="font-weight: bold;">Send</span>.
    -   Application<span style="font-weight: normal;">: Select</span> FTP\_A<span style="font-weight: normal;"> as the Application from the drop-down list.</span>
    -   Destination alias<span style="font-weight: normal;">: Enter the Site alias that is the file transfer destination. In this example the alias for</span> machine B<span style="font-weight: normal;">.</span>
4.  Complete the Transfer Request [Attributes tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab).
    -   <span style="font-weight: bold;">File component</span>: Enter the local file name (without the file path) of the physical file to send.
5.  Click <span style="font-weight: bold;">OK</span> to confirm after completing these tabs.<span style="font-weight: bold;">  
    Machine A</span> contacts <span style="font-weight: bold;">machine B</span> and begins the file transfer procedure.

<span style="font-weight: bold;">Note:</span> If you are using certificates that are not already validated by both machine A and machine B, the FTP transfer cannot execute until certificates are exchanged between the two machines, and then validated, as described in [Validating certificates](#validating_certificates).

<span id="Transfer_results"></span>

## Transfer results

After completing the procedure [Executing the FTP transfer](#Executing_the_FTP_transfer), refresh your screen and check that the transfer was successfully completed. If all of the entered network and application parameters are correct, Gateway executes the transfer and deposits the file on <span style="font-weight: bold;">machine B</span>.

After a transfer, remember to refresh the screen in both the Mailbox and the Log file.

### Using the Mailbox

<span style="font-weight: bold;">Machine A</span> and <span style="font-weight: bold;">machine B</span> create and record a record of each processed Transfer Request in their respective Mailboxes.

To view the record of a Transfer Requests in the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> node.  
    In the right pane, Gateway displays all Transfer Request records currently contained in the Mailbox. Each row represents one Transfer Request.
3.  In the left pane, double-click the line that represents the Transfer Request you want to review.  
    Gateway displays the <span style="font-style: italic;">Transfer Request information</span> window. Use the tabs of this window to view the characteristics of the Transfer Request.

Refer to [Viewing and managing Mailbox contents](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui)).

### Using the Log file

By default, Gateway generates traces of network activities that it records to your log file. To view the log file, in the left pane of the GUI main window click <span style="font-weight: bold;">Log</span>. Gateway displays the current log file contents in the right pane.

To display a help file that provides information about a specific log entry, double-click any line of the log file in the right pane. Gateway opens the online help, displaying information relating to the line you selected.

If you need more trace information about CGate processes, you can activate CGate logging. In this example, CGate logging can be useful to monitor the connection with <span style="font-weight: bold;">machine B</span>.

On <span style="font-weight: bold;">machine B</span>, proceed as follows to enable the recording of CGate event information to the log file:

-   In the left pane of the Gateway GUI, right-click the icon that represents your Local Gateway and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Gateway</span>.
-   Click the <span style="font-weight: bold;">Log levels...</span> button.
-   In <span style="font-weight: bold;">CGate</span>, select <span style="font-weight: bold;">Full</span>.
-   Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.  
    Gateway immediately takes the new settings into account.

Refer to [Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui)).

<span id="validating_certificates"></span>

## Validating certificates

Before a transfer can occur, you must manually verify any certificates that are exchanged by either machine involved in the transfer. After verifying the certificates, repeat the FTP transfer procedure.

For a given machine, either the machine A or B in the example, certificates are displayed in the right pane window of the GUI. A yellow dot identifies new certificates that have not been validated.

Before you can successfully execute the example FTP transfer, you must validate the certificates received by both machine A and B.

See the *Security Guide &gt; [Managing certificates](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Certificate_management_(GUI).htm)* for further information (requires login).

To validate a certificate:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Click the <span style="font-weight: bold;">Certificate</span> sub-node to select it.  
    Gateway displays a list of all available certificates in the display (right) pane.
3.  Click the name of the certificate you want to validate.
4.  Right-click the name of the certificate you want to validate, and then select <span style="font-weight: bold;">Enable</span> from the context menu. The yellow certificate tag becomes green.
5.  When you have validated certificates for both machine A and machine B, repeat the procedure [Executing the FTP transfer](#Executing_the_FTP_transfer).

Related topics

[About FTP](../../protocols_about/ftp_about)

[Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ftp)

[Viewing and managing the Mailbox](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
