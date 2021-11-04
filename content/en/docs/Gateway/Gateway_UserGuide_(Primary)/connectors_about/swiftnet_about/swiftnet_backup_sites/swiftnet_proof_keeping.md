{
    "title": "SWIFTNet Proof keeping",
    "linkTitle": "Proof keeping",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About SWIFTNet Proof keeping](#about)

[Enabling SWIFTNet Proof keeping](#enabling)

[Proof files](#proof_files)

<span id="about"></span>

## About SWIFTNet Proof keeping

The purpose of proof keeping is to permanently store the XML requests and responses that were exchanged for a transfer in order to have an additional proof in case a misunderstanding appears between the partners.

You can activate or deactivate the proof keeping feature and, if the feature is activated, configure the directory where the proof will be kept (a default directory is proposed). By default, this option is deactivated.

When the proof keeping feature is activated, for every InterAct or FileAct transfer, Gateway stores the request and the response as long as there is no error at the SNL layer. This means that for a certain request (client side) you receive a response from your partner and from a received request (server side) you provide a response to the sender.

<span id="enabling"></span>

## Enabling SWIFTNet Proof keeping

Enable SWIFTNet proof keeping in the configuration menu.

1.  In the left pane of the GUI main window, right-click the Gateway server for which you want to enable proof logging and select <span style="font-weight: bold;">Configure</span> from the context menu.  
    The <span style="font-style: italic;">Configuration</span> window is displayed.
2.  In the left pane of the <span style="font-style: italic;">Configuration</span> window, select <span style="font-weight: bold;">Connectivity > Axway Connectivity > SWIFTNet</span>.  
    For full details of the following parameters, refer to [Configuration: Connectors](../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet).
3.  Activate (or deactivate) <span style="font-weight: bold;">Proof keeping</span>.
4.  Specify the destination folder in <span style="font-weight: bold;">Default proof directory</span>. Gateway environment variables can be used here:
    -   %VAR% and "\\" separator for Windows
    -   $VAR   and "/" separator for UNIX

      
    If it is not possible to write to the specified directory, the <span class="code">&lt;Gateway installation directory>/run\_time/tmp</span> directory is used. A corresponding warning message is output to client and server trace files. If other writing or file permission problems occur, an error trace message is generated.
5.  Click <span style="font-weight: bold;">Activate</span> to enable the connector.
6.  Restart Gateway for the change in configuration to be taken into account.

<span id="proof_files"></span>

## Proof files

Each complete transfer (FileAct or InterAct) will have its own proof file (InterAct has two entries in the Mailbox for one transfer but it is stored in one proof file).

The proof file name depends on whether the transfer is FileAct or InterAct.

### Proof files for FileAct

GatewayXferLocalIdent\_Sw:TransferRef

#### Example: FileAct RealTime

Send a file (Sw:PutFileRequest)

Gateway transfer id: 101

Sw:TransferRef: SNL01568XX1192006337083316C

In this case, the proof file name will be: 101\_SNL01568XX1192006337083316

### Proof files for InterAct

GatewayXferLocalIdent\_SwInt:SwiftRef

#### Example: InterAct RealTime

(SwInt:ExchangeRequest)

Gateway transfer id: 221

SwInt:SwiftRef: SNL01568-2007-10-10T08:25:16.4912.000012Z

In this case, the proof file name will be: 221\_SNL01568-2007-10-10T0825164912000012Z

<span id="Acknowle"></span>

### Acknowledgments

For a FileAct transfer, in order to be sure that the transfer was completed correctly, the Sw:HandleFileEventRequest with the Completed status will also be stored.

The acknowledgment for a specific FileAct RealTime transfer is added in the file that already contains the proof for that transfer, if the file exists. For example, for a file transfer where an ACK was requested, the proof file contains information regarding the transfer. If an ACK arrives for this transfer, the ACK information will be added at the end of the same file.

Changed in 6.15.0. For InterAct and FileAct Store-and-Forward transfers, the acknowledgment (delivery notification) is added in the proof file associated with the RECEIPT mailbox entry.

Related topics

[Configuration: Connectors](../../../../configuration_start_here/config_connectors#olh_connectivity_swiftnet)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
