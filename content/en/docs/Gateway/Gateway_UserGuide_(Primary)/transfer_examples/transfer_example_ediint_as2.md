{
    "title": "Executing an EDIINT AS2 transfer",
    "linkTitle": "EDIINT AS2 transfer",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Transfer Examples

[About this example](#about)

[Before you execute this example (AS2 transfer prerequisites)](#AS2_Transfer_prerequisites)

[Configuring the EDIINT *distributor* machine](#Configuring_the_originator_machine)

[Submitting an AS2 Transfer Request](#submitting_AS2_trans_req)

[After the transfer](#After_the_transfer)

<span id="about"></span>

## About this example

This topic provides an example for transferring files via the EDIINT AS2 protocol based on an example Trading Partner Agreement. In the context of your daily operations you can adapt this example to your specific transfer requirements.

In this example we use the Gateway GUI to transfer a `.txt` file from the local machine of a commercial *distributor* entity to the remote machine of a *buyer* entity. The receiving remote *buyer* entity responds to the file transfer by returning a receipt.

![](/Images/Gateway/EDIINTex1_756x418.png)

### Transfer overview

To initiate a file transfer towards a business partner using EDIINT AS2:

-   [Establish a Trading Partner Agreement](#Establishing_TP_agreement) with the remote business partner with whom you want to exchange the file
-   Confirm that the EDIINT AS2 processes are activated in the Gateway configuration menu. Refer to [Configuring Protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ediint_as2).
-   [Configure the sender {{< Gateway/componentlongname >}} to recognize the remote receiving partner](#Remote_Site) by creating the appropriate Site object
-   [Create the Trading Partner objects](#Remote_Trading_Partner) that describe both the local and remote partner EDIINT security characteristics
-   [Set the authentication method](#Default_authentication_method)
-   [Create the local file directories](#VFD) for the deposit of files transferred via HTTP
-   [Create the CGateGroup and CGate objects](#CGateGroup_local_obj) to control remote access to your local machine
-   [Submit an AS2-type Transfer Request](#submitting_AS2_trans_req)

The example in this topic uses a set of parameters to achieve an EDIINT AS2 transfer based on an example Trading Partner Agreement. You can use this example as a model for executing a transfer based on a similar type of agreement.

<span id="Establishing_TP_agreement"></span>

### Establishing the Trading Partner Agreement

In any EDIINT exchange, the exchange partners need to have prior agreement on certain exchange parameters. This agreement is formalized in a Trading Partner Agreement.

For this example, the Trading Partner Agreement establishes that the following parameters are to be used between the buyer and distributor partners:

-   **AS version**:
    -   AS2 over HTTP
-   <span style="font-weight: bold;">EDIINT partner names</span>:
    -   Distributor
    -   Buyer
-   <span style="font-weight: bold;">Certificates</span>:
    -   The partners exchange the certificates they will use for signing and encryption. Because they have selected dual certificate use (separate certificates for signing and encryption), each partner will possess four certificates. Each certificate includes the associated public key. Each partner will possess the private keys for two of these certificates.
-   **Security services**:
    -   signature: yes
    -   encryption: yes
    -   compression: yes
-   <span style="font-weight: bold;">Algorithms</span>:
    -   The partners indicate any algorithm restrictions.
-   **Receipts**
    -   required: yes
    -   signed: yes
    -   synchronous: yes
    -   protocol: HTTP

<span id="AS2_Transfer_prerequisites"></span>

## Before you execute this example

-   Install and start Gateway on your local machine
-   Confirm that you are linked to your business partner by a TCP/IP connection
-   Open a Windows environment to support the GUI
-   Configure Gateway to activate support for the EDIINT protocol AS2 format. Refer to [Configuring protocols](../../configuration_start_here/config_protocols_about/config_protocols#olh_connectivity_internet_ediint_as2).
-   Confirm that you and your exchange partner own the necessary security certificates and keys and agree on the processes associated with exchanges

<span id="Configuring_the_originator_machine"></span>

## Configuring the EDIINT <span style="font-style: italic;">distributor</span> machine

For this AS2 transfer example, your local machine is the <span style="font-style: italic;">distributor</span> machine. The <span style="font-style: italic;">distributor</span> machine initiates sending of the file you want to transfer, and accepts the return emission of the EDIINT receipt. To enable these operations you configure the following Gateway objects on the distributor machine:

-   [Remote Site](#Remote_Site)
-   [Remote Trading Partner](#Remote_Trading_Partner)
-   [Local Trading Partner](#Local_Trading_Partner)
-   [VFDs](#VFD)
-   [CGateGroup](#CGateGroup_local_obj)
-   [CGate](#CGateGroup_local_obj)

Additionally you need to [change the default authentication method](#Default_authentication_method) in the configuration menu.

<span id="Remote_Site"></span>

### Remote Site object

In Gateway, on the distributor machine, define values for the machine of the <span style="font-style: italic;">buyer</span> partner that is the target of the file transfer. Use the Remote Site object.

To create a Remote Site object that describes the <span style="font-style: italic;">buyer</span> partner of the EDIINT AS2 transfer, complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Partner Management > Sites**
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node. From the context menu that appears, select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span style="font-style: italic;">New Remote Site window</span>.
3.  Complete the <span style="font-weight: bold;">Remote Site</span> tabs as follows. You do not need to complete fields that are not listed.
    -   In the <span style="font-weight: bold;">General</span> tab:
        -   <span style="font-weight: bold;">Alias:</span> Enter <span style="font-style: italic;">ALIAS\_BUYER</span>
        -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-weight: bold;">AS2</span>
        -   <span style="font-weight: bold;">Protocol identifier</span>: Enter <span style="font-style: italic;">BUYER</span>
        -   <span style="font-weight: bold;">Role</span>: Click all check boxes to select all roles
        -   <span style="font-weight: bold;">Initialization mode</span>: Click all check boxes to select all initialization modes
    -   In the <span style="font-weight: bold;">FTP/HTTP</span> tab:
        -   <span style="font-weight: bold;">acknowledgment option</span>: Select <span style="font-style: italic;">By monitor</span>
    -   In the <span style="font-weight: bold;">Network address</span> tab:
        -   <span style="font-weight: bold;">Communication address</span>: Select <span style="font-weight: bold;">Main address</span>.
        -   <span style="font-weight: bold;">Network type</span>: From the drop-down list, select <span style="font-weight: bold;">TCP/IP</span>.
        -   In the Right pane, TCP specific main address tab:
            -   <span style="font-weight: bold;">IP address or machine name</span>: For this example we use the imaginary address &lt;<span class="code">ADDRESS\_HOST\_CLIENT</span>&gt;
            -   <span style="font-weight: bold;">Port number</span>: For this example we use port <span style="font-weight: bold;">8080</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm and close the window.

<span id="Remote_Trading_Partner"></span>

### Remote Trading Partner object

The Remote Trading Partner object provides Gateway with information about the EDIINT compression, signature, encryption and encapsulation operations to be used for the transfer.

On your local <span style="font-style: italic;">distributor</span> machine, in Gateway, define values for the remote <span style="font-style: italic;">buyer</span> Trading Partner.

To create a Remote Trading Partner object for the EDIINT AS2 transfer, complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node. From the context menu that appears, select <span style="font-weight: bold;">New > AS2 partner</span>.  
    Gateway displays the <span style="font-style: italic;">Trading Partner</span> window.
3.  Complete the following fields of the <span style="font-style: italic;">Trading Partner</span> window.
    -   In the <span style="font-style: italic;">Identification criteria</span> section:
        -   <span style="font-weight: bold;">Local Partner</span>: Confirm that this check box is <span style="font-style: italic;">not</span> selected
        -   <span style="font-weight: bold;">Name</span>: Enter a name for the remote partner, <span style="font-style: italic;">BUYER</span>
        -   <span style="font-weight: bold;">Format</span>: <span style="font-weight: bold;">AS2</span> is displayed
        -   <span style="font-weight: bold;">Alias</span>: Enter an alias for the remote partner, <span style="font-style: italic;">ALIAS\_BUYER</span>
    -   In the <span style="font-style: italic;">Certificate/Key</span> section:
        -   <span style="font-weight: bold;">Use dual certificates:</span> Click to select dual certificate use
        -   <span style="font-weight: bold;">Signing certificate: Type</span>: From the drop-down list, select <span style="font-style: italic;">SEC\_ALIAS</span>
        -   <span style="font-weight: bold;">Signing certificate: Name</span>: Enter the name of the local certificate you are using to check the signature the remote partner: For example <span style="font-style: italic;">Buyer\_cert\_sign</span>
        -   <span style="font-weight: bold;">Encryption certificate: Type</span>: From the drop-down list, select <span style="font-style: italic;">SEC\_ALIAS</span>
        -   <span style="font-weight: bold;">Encryption certificate: Name</span>: Enter the name of the local certificate you are using to encrypt information sent to the remote partner. For this example, enter <span style="font-style: italic;">Buyer\_cert\_encrypt</span>
        -   <span style="font-weight: bold;">Signing algo:</span> From the drop-down list, select <span style="font-style: italic;">SHA1withRSA</span>
    -   For details about the certificates and associated keys necessary for EDIINT transfers, refer to [About EDIINT - Certificates](../../protocols_about/ediint_about#EDIINT_Certificates).  
          

    <!-- -->

    -   In the <span style="font-style: italic;">Requested Services</span> section:
        -   <span style="font-weight: bold;">Encrypt file</span>: Click to select
        -   <span style="font-weight: bold;">Sign file</span>: Click to select
        -   <span style="font-weight: bold;">Compress file</span>: Click to select
        -   <span style="font-weight: bold;">Request receipt</span>: From the drop-down list, select <span style="font-style: italic;">Signed</span>
        -   <span style="font-weight: bold;">Synchronize receipt</span>: Click to select  
            Refer to [About EDIINT - Synchronous and asynchronous receipt processes](../../protocols_about/ediint_about#Receipt_synchronization).
        -   <span style="font-weight: bold;">Receipt URL/email</span>: Enter the address at which you want to receive the return receipt. For example: <span class="code" style="font-style: italic;">http://ADDRESS\_HOST\_DISTRIBUTOR/client/transfer?user=buyer&password=buyer</span>
    -   In the <span style="font-style: italic;">Parameters for file reception</span> section:
        -   <span style="font-weight: bold;">Force signed</span>: Click to select
        -   <span style="font-weight: bold;">Force encrypted</span>: Click to select
        -   <span style="font-weight: bold;">Force receipt requested</span>: From the drop-down list, select <span style="font-style: italic;">Signed</span>
        -   <span style="font-weight: bold;">Force receipt URL/email</span>: Enter the address where you want to receive the return receipt. For example: <span class="code" style="font-style: italic;">http://ADDRESS\_HOST\_DISTRIBUTOR/client/transfer?user=buyer&password=buyer</span>
4.  Click <span style="font-weight: bold;">OK</span> to confirm and close the window.

<span id="Local_Trading_Partner"></span>

### Local Trading Partner object

The Local Trading Partner object contains information about the local EDIINT compression, signature, encryption and encapsulation operations that are used for the transfer. It also enables you to specify how to handle receipts returned by the remote <span style="font-style: italic;">buyer</span> partner.

To create a Local Trading Partner object for the EDIINT AS2 transfer, complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node. From the context menu that appears, select <span style="font-weight: bold;">New > AS2 partner</span>.  
    Gateway displays the <span style="font-style: italic;">Trading Partner</span> window.
3.  Complete the following fields of the <span style="font-style: italic;">Trading Partner</span> window.
    -   In the <span style="font-style: italic;">Identification criteria</span> section:
        -   <span style="font-weight: bold;">Local Partner</span>: Click to select
        -   <span style="font-weight: bold;">Name</span>: Enter a name for the remote partner, <span style="font-style: italic;">DISTRIBUTOR</span>
        -   <span style="font-weight: bold;">Format</span>: <span style="font-weight: bold;">AS2</span> is displayed
        -   <span style="font-weight: bold;">Alias</span>: Enter an alias for the remote partner, <span style="font-style: italic;">ALIAS\_DISTRIBUTOR</span>
    -   In the <span style="font-style: italic;">Certificate/Key</span> section:
        -   <span style="font-weight: bold;">Use dual certificates</span>: Click to select
        -   <span style="font-weight: bold;">Signing certificate: Type</span>: From the drop-down list, select <span style="font-style: italic;">SEC\_ALIAS</span>
        -   <span style="font-weight: bold;">Signing certificate: Name</span>: Enter the certificate name, for this example <span style="font-style: italic;">DistributorSignCert</span>  
            <span style="font-weight: bold;">Note:</span> You must possess the private key for this certificate.  
              
        -   <span style="font-weight: bold;">Signing certificate: Key password</span>: Enter the password for the certificate key, for this example <span style="font-style: italic;">DistribSnCert</span>
        -   <span style="font-weight: bold;">Encryption certificate: Type</span>: From the drop-down list, select <span style="font-style: italic;">SEC\_ALIAS</span>
        -   <span style="font-weight: bold;">Encryption certificate: Name</span>: Enter the certificate name, for this example <span style="font-style: italic;">DistributorEnCert</span>  
            <span style="font-weight: bold;">Note:</span> You must possess the private key for this certificate.  
              
        -   <span style="font-weight: bold;">Encryption certificate: Key password</span>: Enter the password for the certificate key, for this example <span style="font-style: italic;">DistribEnCert</span>
        -   <span style="font-weight: bold;">Signing algo</span>: From the drop-down list, select <span style="font-style: italic;">SHA1withRSA</span>

      
    For details about the certificates and associated keys necessary for EDIINT transfers, refer to [About EDIINT - Certificates](../../protocols_about/ediint_about#EDIINT_Certificates).
4.  Click <span style="font-weight: bold;">OK</span> to confirm and close the window.

<span id="Default_authentication_method"></span>

### Setting the authentication method

The Gateway default authentication method for server identification is unsuitable for this example. In the configuration menu, reset the authentication method to <span style="font-style: italic;">CGI user password</span>:

1.  In the left pane of the GUI main window, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Configuration</span> window in the right pane.
2.  Select <span style="font-weight: bold;">Connectivity > Internet protocols > EDIInt > AS2</span>.
3.  Click <span style="font-weight: bold;">Options...</span>.  
    Gateway displays the <span style="font-style: italic;">HTTP options</span> window.
4.  In the <span style="font-weight: bold;">Server identification / Method</span> field, select <span style="font-style: italic;">CGI user password.</span>
5.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">HTTP options</span> window.
6.  Click <span style="font-weight: bold;">OK</span> to close the <span style="font-style: italic;">Configuration</span> window.

<span id="VFD"></span>

### VFD

To create a new VFD object for the reception of receipts from the <span style="font-style: italic;">buyer</span>.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">VFD</span> sub-node, then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Virtual File Directory</span> window.
3.  Complete the fields as follows:
    -   <span style="font-weight: bold;">PathName</span>: Enter <span style="font-style: italic;">/http\_as2/client/</span>
    -   Repeat to create another directory called <span style="font-style: italic;">/receipts</span>. The result is <span style="font-style: italic;">/http\_as2/client/receipts</span>.
4.  Click <span style="font-weight: bold;">OK</span> to confirm.

<span id="CGateGroup_local_obj"></span>

### CGateGroup object

The CGateGroup object enables you to control protocol characteristics of connection attempts to your local machine. To receive the return EDIINT receipt from the <span style="font-style: italic;">buyer</span> entity, create a CGateGroup entity that enables <span style="font-style: italic;">buyer</span> to connect to your machine.

To create a CGateGroup object for the EDIINT AS2 transfer, complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">CGate</span> sub-node, and from the context menu that appears, select <span style="font-weight: bold;">New CGateGroup</span>  
    Gateway displays the <span style="font-style: italic;">New CGateGroup</span> window.
3.  Complete the following fields of the <span style="font-style: italic;">New CGateGroup</span> window.
    -   In the <span style="font-weight: bold;">General</span> tab:
        -   <span style="font-weight: bold;">Name</span>: Enter the name for the CGateGroup, <span style="font-style: italic;">GR\_AS2</span>
        -   <span style="font-weight: bold;">State</span>: From the drop-down list, select <span style="font-style: italic;">Enabled</span>
        -   <span style="font-weight: bold;">Protocol</span>: From the drop-down list, select <span style="font-style: italic;">AS2</span>
        -   <span style="font-weight: bold;">Called SAP</span>: Enter the universal value "\*"
        -   <span style="font-weight: bold;">Template Site</span>: From the drop-down list, select <span style="font-style: italic;">AS2</span>
4.  Click <span style="font-weight: bold;">OK</span> to validate your values and save the object.

### CGate object

The CGate object enables you to impose password control on connection attempts to your local machine. It also enables you to define VFD access rights.

To receive the return EDIINT receipt from the <span style="font-style: italic;">buyer</span> entity, create a CGate object that enables <span style="font-style: italic;">buyer</span> to connect to your machine via a password, and access restricted local directories.

To create a CGate object for the EDIINT AS2 transfer, complete the fields in the tabs as follows. Do not modify fields that are not listed.

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to the left of CGateGroup to display the list of all existing CGateGroups.
3.  From the list, right-click the CGateGroup name <span style="font-weight: bold;">GR\_AS2</span> that you created in the [previous section](#CGateGroup_local_obj).  
    Gateway displays a context menu.
4.  From the context menu, select <span style="font-weight: bold;">New CGate</span> to display the <span style="font-style: italic;">New CGate</span> window. Complete the following fields of the <span style="font-style: italic;">New CGate</span> window.
    -   In the <span style="font-weight: bold;">General</span> tab:
        -   <span style="font-weight: bold;">Name</span>: enter the name for the CGate, <span style="font-style: italic;">as2\_buyer</span>
        -   <span style="font-weight: bold;">Parent CGateGroup</span>: enter the name of the CGateGroup that you created in the previous procedure, <span style="font-style: italic;">GR\_AS2</span>
        -   <span style="font-weight: bold;">State</span>: From the drop-down list, select <span style="font-style: italic;">Enabled</span>
        -   <span style="font-weight: bold;">Login user name</span>: Enter<span style="font-style: italic;"> buyer</span>
        -   <span style="font-weight: bold;">Login password</span>: Enter the universal value<span style="font-style: italic;"> buyer</span>
    -   In the <span style="font-weight: bold;">Output parameters</span> tab:
        -   <span style="font-weight: bold;">Root directory</span>: Enter <span style="font-style: italic;">/http\_as2</span>
        -   <span style="font-weight: bold;">Home directory</span>: enter <span style="font-style: italic;">/http\_as2/buyer</span>
    -   In the <span style="font-weight: bold;">VFD Rights</span> tab:
        -   <span style="font-weight: bold;">VFD rights - directory path</span>: enter <span style="font-style: italic;">/http\_as2:\*:R:L:Y ; /http\_as2/buyer:\*:DRW:LCR:Y ;/http\_as2/buyer/receipts:\*:DWR:LRC:Y</span>
5.  Click <span style="font-weight: bold;">OK</span> to validate your values and save the object.

<span id="submitting_AS2_trans_req"></span>

## Submitting an AS2 Transfer Request

When you have created your Gateway objects as described in the above sections, you are ready to execute the EDIINT transfer. To execute a transfer, submit a Transfer Request as follows.

From Gateway on your local machine (<span style="font-style: italic;">distributor</span>) initiate the transfer:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Transfers</span> sub-node, and then select <span style="font-weight: bold;">New > Transfer Request</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New Transfer Request</span> window.
3.  In the <span style="font-style: italic;">New Transfer Request</span> window, complete the Transfer Request [General tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab):
    -   <span style="font-weight: bold;">Type</span>: Select the Transfer type <span style="font-weight: bold;">TRANS</span>.
    -   <span style="font-weight: bold;">Mode</span>: Select the Transfer connection mode <span style="font-weight: bold;">Initiator</span>.
    -   <span style="font-weight: bold;">Direction</span>: Select the Transfer direction <span style="font-weight: bold;">Send</span>.
    -   <span style="font-weight: bold;">Destination alias</span>: Enter the Site alias that is the file transfer destination. For this example we enter the alias defined in the [Remote Site object](#Remote_Site) above, <span style="font-style: italic;">ALIAS\_BUYER</span>.
4.  Complete the Transfer Request [Attributes tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab).
    -   <span style="font-weight: bold;">File component</span>: Enter the local file name (without the file path) of the physical file to send.
5.  Complete the Transfer Request [Trading Partner tab](../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_trading_partner_tab).
    -   <span style="font-weight: bold;">Destination partner</span>: Enter <span style="font-style: italic;">Buyer</span>
    -   <span style="font-weight: bold;">Originator partner</span>: Enter <span style="font-style: italic;">Distributor</span>
    -   <span style="font-weight: bold;">Format</span>: <span style="font-style: italic;">AS2</span> is displayed
    -   <span style="font-weight: bold;">Is signing</span>: From the drop-down list, select <span style="font-style: italic;">Yes</span>
    -   <span style="font-weight: bold;">Is compressing</span>: From the drop-down list, select <span style="font-style: italic;">No</span>
    -   <span style="font-weight: bold;">Is encrypting</span>: From the drop-down list, select <span style="font-style: italic;">Yes</span>
    -   <span style="font-weight: bold;">Receipt request</span>: From the drop-down list, select <span style="font-style: italic;">Signed</span>
    -   <span style="font-weight: bold;">Synchronize receipt</span>: From the drop-down list, select <span style="font-style: italic;">Yes</span>
    -   <span style="font-weight: bold;">Receipt URL/email</span>: Enter the address. For example: <span class="code">ADDRESS\_HOST\_DISTRIBUTOR/client/transfer?user=buyer&password=buyer</span>
6.  Click <span style="font-weight: bold;">OK</span> to confirm.  
    The origination machine contacts the target machine and begins the file transfer procedure.  
    The machine that is the target of the transfer processes the transfer, and generates and returns a receipt to the originating machine.

<span class="bold_in_para">Note</span>: A subject can be set in the "email subject" field from the Transfer Request SMTP tab.

<span id="After_the_transfer"></span>

## After the transfer

### Using the Mailbox

For each AS2 transfer that you send, Gateway records two transfer records in the Mailbox:

-   One transfer record containing details of the transfers to the remote partner
-   One transfer record containing details of the reception of the receipt from the remote partner

To view the details contained in transfer records:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> node.  
    Gateway displays all currently stored Mailbox records in a table in the display pane. By default, Gateway displays a set of columns containing information about each transfer. The table columns contain the following information for each recorded Transfer (if the data exists for that transfer).
3.  Right-click the corresponding record in the Mailbox to view details of a transfer.  
    Each record contains eight tabs displaying details of different aspects of the transfer process. The Trading Partners tab contains information pertaining particularly to AS2 transfers.

### Using the Log file

By default, Gateway generates traces of network activities that it records to your log file. To view the log file, in the left pane of the GUI main window click <span style="font-weight: bold;">Transfer Management &gt; Monitoring &gt; Log</span>. Gateway displays the current log file contents in the right pane.

To display a help file that provides information about a specific log entry, double-click any line of the log file in the right pane. Gateway opens the online help, displaying information relating to the line you selected.

If you need more trace information about CGate processes, you can activate CGate logging. In this example, CGate logging can be useful to monitor the connection initiated by the remote machine.

Proceed as follows to enable the recording of CGate event information to the log file:

-   In the left pane of the Gateway GUI, right-click the icon that represents your Local <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Gateway</span>.
-   Click the <span style="font-weight: bold;">Log levels...</span> button.
-   In <span style="font-weight: bold;">CGate</span>, select <span style="font-weight: bold;">Full</span>.
-   Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.  
    Gateway immediately takes the new settings into account.

Related topics

[Overview: Trading Partners](../../ov_gateway/ov_trading_partners)

[About EDIINT](../../protocols_about/ediint_about)

[Working with Logs](../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
