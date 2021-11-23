{
    "title": "Executing an SFTP transfer",
    "linkTitle": "SFTP transfer",
    "weight": "140"
}{{< Gateway/componentlongname  >}}: Transfer Examples

[About this example](#about)

[Prerequisites](#Prerequisites)

[Configuring the SFTP client/sender (machine A)](#Configuring_the_SFTP_client_sender__machine_A_)

[Configuring the SFTP server/receiver (machine B)](#Configuring_the_SFTP_server)

[Executing the SFTP transfer](#Executing_SFTP_transfer)

[Transfer results](#Transfer_results)

[Validating keys](#validating_keys)

<span id="about"></span>

## About this example

This topic describes the minimal configuration needed to enable you to execute an SFTP transfer, that means using security, between two machines, both hosting Gateways.

To send a file via SFTP, both the client and the server need to be configured to recognize one another. In addition, the transfer protocol SFTP and its most basic parameters must be defined. The following example uses the minimal number of parameters possible to achieve an SFTP transfer. You can use this example as a basis for a more complex transfer.

In this example we use the Gateway GUI to transfer a` .txt` file from **machine A**, the client/sender, to <span style="font-weight: bold;">machine B</span>, the server/receiver.

<img src="/Images/Gateway/SFTP.gif" width="591" height="394" />

<img src="/Images/Gateway/SFTP.png" class="mediumWidth" />

<span id="Prerequisites"></span>

## Prerequisites

-   Gateway must be correctly installed and running on both <span style="font-weight: bold;">machine A</span> and <span style="font-weight: bold;">machine B</span>.
-   The two machines must also be linked by a TCP/IP connection.
-   The sending <span style="font-weight: bold;">machine A</span> and receiving <span style="font-weight: bold;">machine B</span> must both support the SFTP protocol for the transfer. Additionally, the TCP option must be activated for SFTP.
    -   In the configuration menu of both machines, activate the SFTP protocol over TCP. Refer to [Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_sftp).
    -   After modifying the configuration, remember to stop and restart Gateway so that the modifications are taken into account.
-   Both machines must have the appropriate keys, client or server, for the security portion of the SFTP transfer to be realized. If you have not already done so, import both a Public key and a Private key for the server, and a Private key for the client before setting the SSH parameters.
-   This example is executed via a GUI supported by a Windows environment.

<span id="Configuring_the_SFTP_client_sender__machine_A_"></span>

## Configuring the SFTP client/sender (machine A)

For this SFTP transfer, you need to configure the following objects on <span style="font-weight: bold;">machine A</span>.

-   Keys. See *Security Guide* > [Certificates and keys](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/certificates_and_keys_start_here.htm) for further information (requires login)
-   SSH. See *Security Guide >* [SSH](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/ssh_protocol_about.htm) for further information.
-   [Remote Site](../../managing_partners_start_here/sites_start_here/managing_remote_sites)

### Importing keys

On installation, Gateway A provides a set of keys and certificates. You can import additional keys using the GUI.

To import a user key:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Key</span> sub-node.  
    Gateway displays a context menu.
3.  Select <span style="font-weight: bold;">Import...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Key import</span> window.
4.  Complete the <span style="font-style: italic;">Key import</span> window as follows.
    -   **Name**: Enter <span style="font-weight: bold;">SSH\_PRV</span> as the name for the key.
    -   **File containing the key**: Enter the name of the file containing the key, or use the Browse button to select the key file.
    -   **File format**: Select **PEM**.
    -   **Key Type**: Select **PRIVATE**.
    -   **Algorithm**: Select **RSA**.
5.  Click **OK** to confirm and close the <span style="font-style: italic;">Key import</span> window.

### SSH Profile window

Use the <span style="font-weight: bold;">SSH Profile</span> tab to define the SSH profile for <span style="font-weight: bold;">machine A</span>.

If you are performing this procedure for the first time, you must import a key before completing the SSH Profile window. Validate the key before the starting the SFTP transfer portion of this example.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management > Security Profile**
2.  Right-click <span style="font-weight: bold;">SSH Profile</span> and select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> New SSH Profile</span> window.
3.  In the<span style="font-style: italic;"> New SSH Profile</span> window, complete the fields in the <span style="font-weight: bold;">General</span> tab as follows.
    -   **Name**: Enter a unique name for the SSH Profile. In this example use **SSH\_CLIENT**.
    -   **Profile Type**: From the drop down list, select **CLIENT**.
    -   **Key exchange algorithms**: Select **DH\_GROUP1\_SHA1**.
    -   **Encryption algorithms**: Select **AES128\_CBC** and **3DES\_CBC**.
    -   **Mac Algorithm**: Select **HMAC\_SHA1**.
    -   **Public key**: Select **SSH\_RSA**
    -   **Client Authentication**: Select **Password or Public Key**.

      
    A pop-up window lets you know that key authentication parameters are added when you modify the algorithms described above. Click <span style="font-weight: bold;">OK</span> to confirm and close the window.  
    <span style="font-weight: bold;">Hint:</span> The four algorithm buttons must have a value defined to operate in SFTP. Typically the strongest algorithm is listed first. Be sure that for each button there is at least one algorithm in common for both the server and the client.
4.  In the<span style="font-style: italic;"> New SSH Profile</span> window, complete the fields in the <span style="font-weight: bold;">Authentication</span> tab as recommended below.
    -   <span style="font-weight: bold;">Private key alias</span>: Select <span style="font-weight: bold;">CLIENT\_PRV</span>.
    -   <span style="font-weight: bold;">Trust hosted public key</span>: Select to activate.
    -   <span style="font-weight: bold;">Automatic import of partner keys</span>: Select to activate.
5.  Click <span style="font-weight: bold;">OK</span> to save the new SSH profile and close the window.

### Remote Site

On <span style="font-weight: bold;">machine A</span>, define the <span style="font-weight: bold;">machine B</span> values in the Remote Site window. Complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Partner Management > Sites**
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node. From the context menu that appears, select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span style="font-style: italic;">New Remote Site</span> window.
3.  Complete the tabs of the <span style="font-style: italic;">New Remote Site</span> window as follows. You do not need to complete fields that are not listed.
4.  In the <span style="font-weight: bold;">[General](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab:
    -   <span style="font-weight: bold;">Alias</span>: Enter the Remote Site alias. You can enter up to 31 alphanumeric characters.
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">SFTP</span>.
    -   <span style="font-weight: bold;">Role</span>: Click to select all <span style="font-weight: bold;">Role</span> and <span style="font-weight: bold;">Initialization modes</span>.
5.  In the <span style="font-weight: bold;">[Network address](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_network_address_tab)</span> tab:
    -   <span style="font-weight: bold;">Communication address</span>: Select <span style="font-weight: bold;">Main address</span>.
    -   <span style="font-weight: bold;">Network type</span>: From the drop-down list, select <span style="font-weight: bold;">TCP/IP</span>.
    -   In the right pane:

      
    **IP address or machine name**: Enter the IP address as &lt;my.domain.name>  
    **Port number:** For this example enter a port number that is greater than 6320, usually 6321 for SFTP.
6.  In the <span style="font-weight: bold;">[SFTP](../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_sftp_tab)</span> tab:
    -   <span style="font-weight: bold;">User name</span>: Enter <span style="font-weight: bold;">CLIENT\_SFTP</span>.
    -   <span style="font-weight: bold;">SSH Profile</span>: Select <span style="font-weight: bold;">SSH\_CLIENT</span> which was defined earlier in the <span style="font-style: italic;">SSH profile</span> window.
    -   <span style="font-weight: bold;">Newline convention</span>: Select <span style="font-weight: bold;">Windows</span>.

      
    In client mode, Gateway uses the values that you set in these fields for the login phase on a remote server.
7.  Click <span style="font-weight: bold;">OK</span> to confirm and close the window.

<span style="font-weight: bold;">Note:</span> If you are performing this procedure for the first time, you must import a User certificate before beginning the server <span style="font-weight: bold;">Machine B</span> set-up.
See the *Security Guide &gt;* [Importing a Certificate](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Certificate_management_(GUI).htm) for further information (requires login).

<span id="Configuring_the_SFTP_server"></span>

## Configuring the SFTP server/receiver (machine B)

In this example, <span style="font-weight: bold;">machine B</span> is the destination and receives a file from <span style="font-weight: bold;">machine A</span>, the source for the transfer. You need to configure the following objects on <span style="font-weight: bold;">machine B</span> (the server/receiver) to enable it to receive a file via an SFTP transfer from <span style="font-weight: bold;">machine A</span>.

-   Keys. See the *Security Guide > [Managing keys](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/Key_Management_(GUI).htm)* for further information (requires login)
-   [VFD](../../transfers_start_here/virtual_file_directory_start_here/working_with_virtual_file_directories_(gui))
-   SSH Profile. See *Security Guide *&gt; [SSH Protocol](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/ssh_protocol_about.htm)** for further information (requires login)
-   Network Profile. See *Security Guide > [Network profiles](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Network_Profiles/Network_Profiles_Start_here.htm)* for further information.
-   [CGateGroup](../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui))
-   [CGate](../../managing_partners_start_here/cgates_start_here/working_with_cgates_and_cgategroups_(gui))

### Importing keys

A set of keys and certificates is delivered with Gateway.

Import both a public and private key for the server, using the following procedure:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Key</span> sub-node.  
    Gateway displays a context menu.
3.  Select <span style="font-weight: bold;">Import...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Key import</span> window.
4.  To import a public key for the server, complete the <span style="font-style: italic;">Key Import window a</span>s follows:
    -   <span style="font-weight: bold;">Name:</span> Enter <span style="font-weight: bold;">SVR\_PUB</span> as the name for the key.
    -   <span style="font-weight: bold;">File containing the key:</span> Enter the name of the file containing the key, or use the Browse button to select the key file.
    -   File format:<span style="font-weight: normal;"> Select</span> PEM<span style="font-weight: normal;">.</span>
    -   Key Type:<span style="font-weight: normal;"> Select</span> PUBLIC<span style="font-weight: normal;">.</span>
    -   Algorithm:<span style="font-weight: normal;"> Select</span> RSA<span style="font-weight: normal;">.</span>
5.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">Import key</span> window.
6.  Repeat the <span style="font-style: italic;">Key Import</span> process to import a private key as follows. Access the <span style="font-style: italic;">Import key</span> window.
    -   <span style="font-weight: bold;">Name:</span> Enter <span style="font-weight: bold;">SVR\_PRV</span> as the name for the key.
    -   <span style="font-weight: bold;">File containing the key:</span> Enter the name of the file containing the key, or use the Browse button to select the key file.
    -   File format: <span style="font-weight: normal;">Select</span> PEM<span style="font-weight: normal;">.</span>
    -   Key Type:<span style="font-weight: normal;"> Select</span> PRV<span style="font-weight: normal;">.</span>
    -   Algorithm:<span style="font-weight: normal;"> Select</span> RSA<span style="font-weight: normal;">.</span>
7.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">Import key</span> window.

### VFD

On <span style="font-weight: bold;">machine B,</span> create a new VFD object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">VFD</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Virtual File Directory</span> window.
3.  Complete the following field:
    -   <span style="font-weight: bold;">PathName</span>: Enter <span style="font-weight: bold;">/SFTP</span>. When you create a new directory, Gateway automatically completes the path name field with the path of the parent directory. The absolute path of the root directory is "/".
4.  Select the newly created VFD folder SFTP and right-click <span style="font-weight: bold;">New</span>
5.  The window path name displays <span style="font-weight: bold;">/SFTP</span>. Enter the directory name, for example <span style="font-weight: bold;">ClientSFTP</span>.
6.  Click <span style="font-weight: bold;">OK</span> to confirm and close the window. The new SFTP folder appears under the VFD node, and the ClientSFTP sub-folder is displayed below.

### SSH Profile

On<span style="font-weight: bold;"> machine B,</span> define the SSH profile for the server.

If you are performing this procedure for the first time, check that you have imported the server keys before completing the SSH Profile window.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management > Security Profile**
2.  Right-click <span style="font-weight: bold;">SSH Profile</span> and select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New SSH Profile</span> window.
3.  Complete the fields in the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New SSH Profile</span> window as indicated below.
    -   <span style="font-weight: bold;">Name</span>: Enter a unique name for the SSH Profile, the same name that you used in the previous Network tab. In this example use <span style="font-weight: bold;">SSH\_SRV</span>.
    -   <span style="font-weight: bold;">Profile Type</span>: From the drop down list, select the <span style="font-weight: bold;">SERVER</span>.
    -   Key exchange algorithms<span style="font-weight: normal;">: Select</span> DH\_GROUP1\_SHA1<span style="font-weight: normal;">.</span>
    -   Encryption algorithms<span style="font-weight: normal;">: Select</span> AES128\_CBC<span style="font-weight: normal;"> and</span> 3DES\_CBC<span style="font-weight: normal;">.</span>
    -   <span style="font-weight: bold;">Mac Algorithm</span>: Select <span style="font-weight: bold;">HMAC\_SHA1</span>.
    -   <span style="font-weight: bold;">Public key</span>: Select <span style="font-weight: bold;">SSH\_RSA</span>.
    -   <span style="font-weight: bold;">Client Authentication</span>: Select <span style="font-weight: bold;">Password or Public Key</span>.

      
    <span style="font-weight: bold;">Hint:</span> For each of the 4 algorithm buttons at least one value must be defined for to operate in SFTP. Typically the strongest algorithm is listed first. Be sure for each button there is at least one algorithm in common for both the server and the client.
4.  Complete the fields in the <span style="font-weight: bold;">Authentication</span> tab as indicated below.
    -   <span style="font-weight: bold;">Private key alias</span>: Select <span style="font-weight: bold;">SRV\_PRV</span>.
5.  Click <span style="font-weight: bold;">OK</span> to confirm your selections and close the <span style="font-style: italic;">New SSH Profile</span> window.
6.  Gateway displays the new SSH Profile in the right pane work area.

### Network Profile

A Network Profile associates an incoming network connection request with a Security Profile. The connection does not use Security if you have not selected TLS or SSH in the configuration menu.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Right-click the <span style="font-weight: bold;">Network Profile</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span style="font-style: italic;">New Network Profile</span> window.
3.  In the <span style="font-style: italic;">New Network Profile</span> window, enter the following values:
    -   <span style="font-weight: bold;">Network profile:</span> Enter a name for the profile.
    -   <span style="font-weight: bold;">Origin address/port:</span> Enter <span style="font-weight: bold;">\*.\*.\*.\*/\*</span>
    -   <span style="font-weight: bold;">Destination address/port:</span> Enter <span style="font-weight: bold;">\*.\*.\*.\*/\*</span> as the listening port for the <span style="font-weight: bold;">machine B</span>.
    -   <span style="font-weight: bold;">Network type:</span> Select <span style="font-weight: bold;">TCP/IP</span>.
    -   <span style="font-weight: bold;">Network security:</span> Select <span style="font-weight: bold;">SSH</span>.
    -   <span style="font-weight: bold;">Security profile:</span> Select <span style="font-weight: bold;">SSH\_SRV</span>, as defined in the SSH profile.
4.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">New Network Profile</span> window.

### CGateGroup

Create a new root CGateGroup object as follows for the <span style="font-weight: bold;">machine B</span> configuration.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup...</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window.
3.  In the <span style="font-style: italic;">New CGateGroup</span> window, complete the <span style="font-weight: bold;">General</span> tab as follows.
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">GROUP\_SFTP</span> as the unique name for the CGateGroup.
    -   <span style="font-weight: bold;">State</span>: From the drop-down list select the state <span style="font-weight: bold;">Enabled</span>.
    -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">SFTP</span>.
    -   <span style="font-weight: bold;">Called address</span>: Enter <span style="font-weight: bold;">\*</span> as the called TCP/IP address for this CGateGroup.
    -   <span style="font-weight: bold;">Called SAP</span>: Enter <span style="font-weight: bold;">\*</span> as the TCP/IP local connection port.  
        Alternatively, you can enter the default port, 6710.
    -   <span style="font-weight: bold;">Template Site</span>: From the drop-down list, select <span style="font-weight: bold;">TSFTP</span> as the Template Site that you want Gateway to use to create a dynamic Site.
4.  Click the <span style="font-weight: bold;">Output Parameters</span> tab and enter the following values.
    -   <span style="font-weight: bold;">Root directory</span>: Enter <span style="font-weight: bold;">/SFTP/</span>
    -   <span style="font-weight: bold;">Home directory</span>: Leave blank.

      
    The <span style="font-weight: bold;">Output Parameters</span> tab is identical for both CGateGroup and CGate objects. The fields on this tab define parameters for the current connection.
5.  Click the <span style="font-weight: bold;">VFD Rights</span> tab and enter the following values.
    -   <span style="font-weight: bold;">Directory path</span>: Enter<span style="font-weight: bold;"> /</span> as the Directory path. Regardless of the VFD rights defined for the current CGate, the connected user only has access to the VFD directory tree below the root directory.
    -   <span style="font-weight: bold;">File pattern</span>: Enter \* in this field. This field further refines the VFD rights to specific file types.
    -   <span style="font-weight: bold;">Sub-directory inheritance</span>: Click to select this box. This indicates that all sub-directories inherit the parameters that you set here.
    -   Click to select all of the<span style="font-weight: bold;"> Directory rights</span> boxes: List, Create, and Remove.
    -   Click to select all of the <span style="font-weight: bold;">File rights</span> boxes: <span style="font-weight: bold;">Read</span>, <span style="font-weight: bold;">Delete</span>, and <span style="font-weight: bold;">Write</span>.
6.  Click <span style="font-weight: bold;">Add</span> to confirm.
7.  Click the <span style="font-weight: bold;">Calling Address</span> tab and enter the following values.
    -   <span style="font-weight: bold;">Calling address</span>: Enter the wildcard character <span style="font-weight: bold;">\*</span>.
    -   <span style="font-weight: bold;">Access allowed</span>: Click to select. This authorizes access from the calling address.
8.  Click <span style="font-weight: bold;">Add</span>, then click<span style="font-weight: bold;"> OK</span> to confirm. You have created a new CGateGroup object.

### CGate

The CGate object is an identification filter used internally in server mode. CGates determine whether a client has the right to connect to Gateway and exchange files with it or not. Create a CGate object for this example transfer as follows.

1.  Right-click to select the parent <span style="font-weight: bold;">CGateGroup</span> folder that you just created.
2.  Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">CGate</span> from the context menu to display the <span style="font-style: italic;">CGate</span> window.
3.  Complete the <span style="font-weight: bold;">General</span> tab as follows.
    -   <span style="font-weight: bold;">Name</span>: Enter <span style="font-weight: bold;">CG\_SFTP</span>, as a unique identifier for the new object.
    -   Complete the <span style="font-weight: bold;">HTTP / FTP / SFTP / PeSIT pre-connection Identification/Checking</span> fields as follows:
        -   <span style="font-weight: bold;">Login user name</span>: Enter the user login name of the <span style="font-weight: bold;">machine A</span> (<span style="font-weight: bold;">Client1</span> in this example) the client/sender.
        -   <span style="font-weight: bold;">Login password</span>: Enter the password associated with the user login field. Remember that the password is case sensitive.
    -   In the <span style="font-weight: bold;">PHSE</span> pane enter <span style="font-weight: bold;">\*</span> in all fields.
4.  Complete the <span style="font-weight: bold;">Output</span> tab as follows.
    -   <span style="font-weight: bold;">Root directory</span>: In this example use <span style="font-weight: bold;">/SFTP</span>, the VFD root directory for the connected user, is automatically displayed. Alternatively, use the <span style="font-weight: bold;">Browse</span> button to make your selection.
    -   <span style="font-weight: bold;">Home directory</span>: In this example enter <span style="font-weight: bold;">/SFTP/ClientSFTP</span> as the VFD directory.
5.  Complete the <span style="font-weight: bold;">VFD Rights</span> tab as follows.
    -   <span style="font-weight: bold;">File pattern</span>: Enter <span style="font-weight: bold;">\*</span> for the file pattern.
    -   <span style="font-weight: bold;">General information</span>: Click to select <span style="font-weight: bold;">Sub directory inheritance</span>.
    -   <span style="font-weight: bold;">Directory rights</span>: Click to select all.
    -   Click <span style="font-weight: bold;">Add</span> to confirm the selections in the <span style="font-weight: bold;">VFD</span> tab.
6.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">CGate</span> window. The server, machine B, is configured and ready to execute an SFTP transfer.

<span id="Executing_SFTP_transfer"></span>

## Executing the SFTP transfer

From <span style="font-weight: bold;">machine A</span> initiate the transfer:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Transfers</span> sub-node, and then select <span style="font-weight: bold;">New > Transfer Request</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New Transfer Request</span> window.
3.  In the <span style="font-style: italic;">New Transfer Request</span> window, complete the Transfer Request [General tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab):
    -   Type: <span style="font-weight: normal;">Select the Transfer type</span> TRANS<span style="font-weight: normal;">.</span>
    -   Mode: <span style="font-weight: normal;">Select the Transfer connection mode</span> Initiator<span style="font-weight: normal;">.</span>
    -   <span style="font-weight: bold;">Direction</span>: Select the Transfer direction <span style="font-weight: bold;">Send</span>.
    -   Application<span style="font-weight: normal;">: Select</span> DEFAULT\_B<span style="font-weight: normal;">.</span>
    -   Destination alias<span style="font-weight: normal;">: Enter the Site alias that is the file transfer destination. In this example the alias for</span> machine B (SSH server)<span style="font-weight: normal;">.</span>
4.  Complete the Transfer Request [Attributes tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab).
    -   <span style="font-weight: bold;">File component</span>: Enter the local file name (without the file path) of the physical file to send.
5.  Click <span style="font-weight: bold;">OK</span> to confirm. <span style="font-weight: bold;">Machine A</span> contacts <span style="font-weight: bold;">machine B</span> and begins the file transfer procedure.

<span style="font-weight: bold;">Note:</span> If you are using certificates that are not already validated by both machine A and machine B, the SFTP transfer cannot execute until keys are exchanged between the two machines, and then validated, as described in the topic Certificate validation.

<span id="Transfer_results"></span>

## Transfer results

After completing the <span style="font-style: italic;">Executing an SFTP transfer</span> procedure, refresh your screen and check that the transfer was successfully completed. If all of the entered network and application conditions are correct, the transfer is executed and a copy of the file is put on <span style="font-weight: bold;">machine B</span>.

After a transfer, remember to refresh the screen in both the Mailbox and the Log file.

### Using the Mailbox

<span style="font-weight: bold;">Machine A</span> and <span style="font-weight: bold;">machine B</span> create and record a record of each processed Transfer Request in their respective Mailboxes.

To view the record of a Transfer Requests in the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> sub-node.  
    In the right pane, Gateway displays all Transfer Request records currently contained in the Mailbox. Each row represents one Transfer Request.
3.  In the left pane, double-click the line that represents the Transfer Request you want to review.  
    Gateway displays the <span style="font-style: italic;">Transfer Request information</span> window. Use the tabs of this window to view the characteristics of the Transfer Request.

Refer to [Viewing and managing Mailbox contents](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui)).

### Using the Log file

By default, Gateway generates traces of network activities that it records to your log file. To view the log file, in the left pane of the GUI main window click <span style="font-weight: bold;">Transfer Management &gt; Monitoring &gt; Log</span>. Gateway displays the current log file contents in the right pane.

To display a help file that provides information about a specific log entry, double-click any line of the log file in the right pane. Gateway opens the online help, displaying information relating to the line you selected.

For more advanced debugging you can activate [SFTP specific traces](../../configuration_start_here/config_gateway_paras#trace_level_examples).

If you need more trace information about CGate processes, you can activate CGate logging. In this example, CGate logging can be useful to monitor the connection with <span style="font-weight: bold;">machine B</span>.

On <span style="font-weight: bold;">machine B</span>, proceed as follows to enable the recording of CGate event information to the log file:

-   In the left pane of the Gateway GUI, right-click the icon that represents your Local Gateway and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Gateway</span>.
-   Click the <span style="font-weight: bold;">Log levels...</span> button.
-   In <span style="font-weight: bold;">CGate</span>, select <span style="font-weight: bold;">Full</span>.
-   Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.  
    Gateway immediately takes the new settings into account.

Refer to [Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui)).

<span id="validating_keys"></span>

## Validating keys

Before a transfer can occur, you must manually verify any keys that are exchanged by either machine involved in the transfer. After verifying the keys, repeat the SFTP transfer procedure.

For a given machine, either the machine A or B in the example, keys are displayed in the right pane window of the GUI. A yellow dot next to the key name identifies a key that has not been validated.

To validate a key:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management**
2.  Click the **Key** sub-node to select it.  
    Gateway displays a list of all available keys in the display (right) pane.
3.  Click the key name to select the key that you want to validate.
4.  Right-click and select **Enable**. The yellow certificate tag becomes green. We recommend that you rename the key at this time.
5.  When you have validated keys for both machines A and B, repeat the [SFTP transfer procedure](#Executing_SFTP_transfer).

Related topics

[About SFTP](../../protocols_about/sftp_about)

[Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_sftp)

[Viewing and managing the Mailbox](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
