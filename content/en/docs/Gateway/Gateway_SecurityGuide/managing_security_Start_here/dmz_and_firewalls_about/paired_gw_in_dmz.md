{
    "title": "Paired Axway Gateways in a DMZ",
    "linkTitle": "Paired Gateways in a DMZ",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[About paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> DMZs](#About_paired_Gateways_in_DMZ)

[Using paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s in DMZs](#Using_paired_Gateways_in_DMZ)

[Transfer scenarios using paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s in the DMZ](#Paired_Gateways_Transfer_Scenarios)

[Managing DMZ-related transfer failures](#Managing_DMZ_related_transfer_failures)

<span id="About_paired_Gateways_in_DMZ"></span>

## About paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> DMZs

To provide secure links between your corporate network applications and file-exchange partners located on the Internet, you can deploy Gateways in a DMZ protected architecture.

For an overview of Gateway DMZ solutions, refer to [Overview: DMZ deployment](../../../../gateway_userguide_(primary)/ov_gateway/ov_dmz_deployment).

You have the option of deploying paired Gateways in a secure DMZ bridge configuration. Alternatively, you can use the [<span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span>](../secure_relay_about) option for DMZ configurations.

<span id="Using_paired_Gateways_in_DMZ"></span>

## Using paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s in DMZs

### General considerations

To create a secure and manageable DMZ for your network, keep in mind the following default rules for DMZ configuration:

-   Do not enable default polling from either the public or private DMZ. Configure polling mechanisms only when strictly necessary.
-   Do not enable FTP transfers between the intranet and the Private Gateway component of the DMZ.
-   Do not enable NFS mounting. The file systems of applications within the DMZ should be strictly local.
-   Rigorously limit the number of external systems that you permit to exchange transfers with the public Gateway. This enables you to open a limited and manageable number of ports on the firewall.

### Roles of Gateways in the DMZ

When you create a DMZ by deploying paired Gateways, you configure the Gateways to operate together as public and private DMZ partners:

#### Private Gateway

A <span style="font-style: italic;">private</span> Gateway contains definitions that enable the applications situated in your corporate network to act as servers and/or clients for exchanges with Internet partners.

You control the identity of intranet applications that connect to the private Gateway via [Remote Site objects](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here).

You control the protocol-level connections to the private Gateway via [CGate objects](../../../../gateway_userguide_(primary)/managing_partners_start_here/cgates_start_here).

On your private Gateway you decrypt incoming files. You can scan decrypted files for viruses before forwarding files to the target destination on your corporate intranet.

#### Public Gateway

A <span style="font-style: italic;">public</span> Gateway contains definitions of all external Internet partners.

In your public Gateway, to control the identities and possible connection attempts of your external Internet partners, you create:

-   Remote Site object definitions for Internet partners acting as servers
-   CGate object definitions for Internet partners acting as clients

The temporary files that the public Gateway stores and all Gateway internal files (administration and Mailbox files) are encrypted to protect against malicious intrusions.

#### Exchanges between public and private Gateways

The public and private Gateways communicate via the PeSIT protocol (secured by SSL/TLS) or via SFTP.

### Gateway DMZ transfers using the PeSIT protocol

The PeSIT protocol provides two basic methods that you can use to exchange files between the private and the public Gateways and between the private Gateway and Axway Transfer products located in the corporate network:

#### Method 1: The receiving Site is the sender/requester

To enable the public Gateway to initiate transfers towards the private Gateway, or to enable the private Gateway to initiate transfers towards the corporate network:

-   Configure the PeSIT protocol in the configuration menu, specifying the access ports for both the public and private Gateway
-   Configure PeSIT CGates for both the public and private Gateway
-   Open a port for Gateway to Gateway PeSIT exchanges in the DMZ firewall application

#### Method 2: The receiving Site is the sender/server

In this case, using the GUI you set the following attributes of the Remote Site object that defines the receiving Site:

-   Clear all <span style="font-style: italic;">initiator</span> role check boxes in the <span style="font-weight: bold;">General</span> tab
-   Select the <span style="font-style: italic;">Change direction support</span> option of the <span style="font-weight: bold;">PeSIT</span> tab
-   Enter a polling interval in the <span style="font-weight: bold;">PeSIT</span> tab

#### Example exchange scenario:

The private Gateway (acting in client mode) calls the public Gateway (acting in server mode). The private Gateway then either sends files to, or asks to receive files from the server. The server application waits for client connection requests to receive files from the client, or to transmit files to the client upon a selection request.

#### Enhancing error protection

To enhance error detection when using PeSIT (for example, during Store-and-Forward operations) you can select the <span style="font-style: italic;">Negative acknowledgment option</span> in the PeSIT tab of the Remote Site objects between the two Gateways. This option activates PeSIT Hors SIT Negative EERP Support.

### Rerouting (Store-and-Forward) mechanisms

After each change in the transfer state (Ended, Acked, Canceled, ToAck), a Gateway process triggers a Store-and-Forward mechanism.

For Store-and-Forward, the following process events occur in this order:

1.  Gateway executes the <span class="code">ExitXferMonitor</span> C exit, which enables you to set variables and specify routing behavior
2.  Gateway executes the <span class="code">XferMonitor</span> Perl exit, which enables you to set user variables and specify routing behavior
3.  Gateway evaluates Decision Rules in order to apply one of the following actions:
    -   Default routing
    -   Application of a model and deposit of the corresponding routed transfer
    -   Execution of a Perl script
    -   Execution of a batch command
    -   Routing to Axway Integrator or AMTrix
    -   No action

#### Managing user exits

<span style="font-weight: bold;">Note:</span> Although the C-code and Perl user exits provide you with the possibility of customizing processing results, we recommend that you use the customization features of Store-and-Forward mechanisms that are available via Decision Rule management.

The user exits can return a result that blocks the progression to the next processing step. When the three processing events are sequentially dependent, and you customize an exit, it is important be sure that the structures modified by an exit are not overwritten by a subsequent processing step.

As illustrated in the step list above, the user exits <span class="code">ExitXferMonitor</span> (in C) and <span class="code">XferMonitor</span> (in Perl) are executed just before the Decision Rule mechanism.

The Perl exit is the most flexible and easy to implement. It requires no compilation, and does not require a stop/restart of Gateway to take into account any changes.

You can use the Perl exit to set user variables that are then available to define conditions in the Decision Rule objects, or to be used in associated Models. Some of these variables can be seen in the Gateway GUI as <span style="font-style: italic;">integer user param (1 and 2)</span> and <span style="font-style: italic;">string user param (1 and 2)</span>.

This enables you to apply specific processing via Decision Rules, based on the incoming file Transfer attributes.

#### Managing Store-and-Forward via Decision Rules and Models

Gateway provides two specific objects that you can use to reroute incoming files:

-   Decision Rules
-   Models

About Decision Rules

You automate routing by creating and managing Decision Rule objects. In a Decision Rule object, you define a set of conditions to apply to the current transfer. When all the Decision Rule conditions match those of the current transfer, Gateway applies an <span style="font-style: italic;">execution type</span>, also specified in the Decision Rule, to the transfer.

About Models

For file Store-and-Forward (rerouting), you typically select <span style="font-style: italic;">Model</span> as the resulting <span style="font-style: italic;">execution type</span> for a Decision Rule. You can create Models that provide sets of attributes for submitting new Transfer Requests. When, as a result of the analysis of a Decision Rule, Gateway generates and submits a new Transfer Request, it extracts attributes from the specified Model. The main advantage of Models is that they enable you to automatically re-use the parameters values of an incoming transfer as values for an outgoing transfer via the application of symbolic variables.

Applying Decision Rules

In general, you should try to manage the least possible number of Decision Rules for your DMZs. Theoretically, you require only two:

-   A Decision Rule on the private Gateway manages all the transfers coming from the corporate intranet. This Decision Rule applies a Model that reroutes incoming transfers towards the public Gateway.  
    **Note:** You must include the identity of the final destination partner of the transfer in the rerouted transfer to the public Gateway, This enables the public Gateway to complete file routing or, when acting as a server, to indicate the availability of the file to the targeted client.
-   A Decision Rule of the public Gateway manages all the transfers coming from the Internet. This Decision Rule applies another Model, (or alternatively, a script) that reroutes the incoming transfer towards the an application on your corporate intranet.

### Naming conventions for DMZ transfers

#### Overview

When you establish file naming conventions for transfers via a DMZ, it is important that you allow yourself the capability to extend data exchanges for new applications you may add as exchange partners.

Generally it is advised that you replace partner applications names and transferred file names with logical names. From a production point of view, this will enable you to more easily identify which partner deals which kind of exchange.

#### Applying conventions

For physical file names, you can establish naming convention that uses symbolic variables to create names that correspond your production procedures.

For instance, you can establish a naming convention for your file transfer flow that includes sender and receiver partner in the transfer identity. For example, a flow will be identified by the name <span style="font-style: italic;">XYnn</span> in one transfer direction and <span style="font-style: italic;">YXnn</span> in the other.

Where:

-   <span style="font-style: italic;">X</span> (or in the other flow direction, Y) represents the sender application
-   <span style="font-style: italic;">Y</span> (or in the other flow direction X) represents the receiver application
-   <span style="font-style: italic;">nn</span> represents the flow type

### FTP and HTTP file transfer issues

If a file sending partner application situated on the Internet is an FTP or HTTP client, the Gateway <span class="code">application\_name</span> attribute has no meaning. In this case, either:

-   Use the FTP or HTTP <span class="code">quote site</span> command to specify the application name before you upload files
-   Specify the application name in place of the physical file name in the FTP or HTTP <span class="code">put</span> command
-   Configure Gateway to deduce the application name from the transfer

### Temporary and database file storage

#### Protecting data on the public Gateway

To protect the data on your public Gateway from malicious intrusions, you must [activate encryption of the temporary files](../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras#olh_gateway_database_protection) stored on the public Gateway and all Gateway internal files (administration and Mailbox files).

### Virus scanning and file storage

It is important to complete the Store-and-Forward mechanism by scanning received Internet files for virus, before sending them towards your corporate network applications.

Virus scanning is not possible on the encrypted files of the public Gateway. For incoming Internet files, you execute virus scans on the <span style="font-style: italic;">private</span> Gateway, after the decryption process.

To set up virus scanning on the <span style="font-style: italic;">private</span> Gateway, you can do either of the following:

-   <span style="font-weight: bold;">Use a Decision Rule</span>  
    Define a Decision Rule that calls a script (batch/shell or Perl) at the end of the file transfer reception. This script executes a virus scan on the file, and if the file is <span style="font-style: italic;">clean,</span> it then executes the forwarding Transfer Request via the <span class="code">peltrans</span> line command.
-   <span style="font-weight: bold;">Use C-code or Perl exits</span>  
    Customize an exit so that the file will be scanned for viruses. If the file is <span style="font-style: italic;">clean</span>, the exit returns a positive answer, permitting the continuation of Store-and-Forward mechanism. The forwarding Transfer Request is deposited as defined in the Decision Rules (for example, via a Model).

### Gateway file systems

In order to preserve the existing environment with FTP, HTTP or SFTP clients, use RFD (Real File Directory) to store the client files.

#### Example

Define a Virtual File Directory, <span class="code">/ftp/user1</span>, that is mounted on a physical directory, for instance <span class="code">/data/user1</span>.

In this case the name of each file must be unique. You can use a symbolic variables to generate file names. For example you could use <span class="code">x\_local\_ident</span>, which represents the transfer identifier of the Gateway Mailbox record.

### Reliability management

Use the time slot defined by the application for exchanges to trigger retry processes. You can set maximum retry limits and time delays between each retry in the Remote Site object <span style="font-weight: bold;">[PeSIT](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pesit_tab)</span> tab.

You can use synchronization points during the transfers to optimize the flow control on network and minimize the data to re-transfer in case of failure. Set synchronization in the Remote Site object <span style="font-weight: bold;">[PeSIT](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pesit_tab)</span> tab.

In addition to the transfer level control, you can activate an application control level using acknowledgment messages. Set acknowledgment options in the Remote Site object <span style="font-weight: bold;">[PeSIT](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pesit_tab)</span> tab.

When you activate this feature, public Gateway generates a message containing the process status (correct/incorrect), and sends the message back to the transfer originating application.

### Monitoring file transfers

You can use Axway Sentinel to provide end-to-end monitoring of Axway MFT activities. Sentinel enables you to view the status of all network application activities from a single point, in an Internet browser.

All information related to Axway Transfer and Axway Gateway file transfer activity is sent to the Sentinel Server and stored in a database (ORACLE, SQL server).

Sentinel can provide graphic views of transfer Cycle phases. These displays shows links between successive related file transfers. You can configure Sentinel to generate Cycle graph displays in which the color of displayed nodes (transfer events) depends on the last transfer state (Ended, in Alert, Available, Acked…).

<span id="Paired_Gateways_Transfer_Scenarios"></span>

## Transfer scenarios using paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s in the DMZ

This section contains examples of file transfers between Internet and intranet partners in which paired Gateways provide DMZ security for corporate applications.

This section describes the events that constitute a transfer:

-   [From an intranet application to an Internet partner](#Scenario_intranet_to_Internet)
-   [From an Internet partner to an Axway Integrator application on the corporate intranet](#Scenario_Internet_to_intranet)

<span id="Scenario_intranet_to_Internet"></span>

### Scenario 1: Intranet partner to Internet partner

This scenario describes the typical events that occur when transferring a file from an intranet application (such as Axway Transfer) to an Internet partner application.

<img src="/Images/Gateway/2GTWDMZex1_756x489.png" class="maxWidth" />

The transfer illustrated above is composed of the following steps:

1.  Intranet application A (for example, an Axway Transfer product) sends a file in initiator mode to the private Gateway via the PeSIT HS E protocol. The final destination is specified in the Transfer Request.  
    The private Gateway accepts the transfer via the generic CGate for PeSIT partners. The partner parameters match a Remote Site defined on the private Gateway.  
    The file is received correctly on the private Gateway.
2.  The private Gateway analyzes the incoming transfer using a Decision Rule. It applies a Model specified in the Decision Rule to forward the file to the public Gateway via the PeSIT HS E protocol.  
    The file is received correctly on the public Gateway.
3.  The public Gateway analyzes the incoming transfer using a Decision Rule. It applies a Model specified in the Decision Rule. If the destination is a server, the public Gateway sends the file directly to the final destination. Otherwise, the public Gateway makes the file available to the client in the specifies home directory, for example <span class="code">/ftp/Y/download/</span>.  
    The file is sent correctly to the FTP server, or alternatively, the FTP client downloads the available file.
4.  The public Gateway automatically generates and sends back an acknowledgment to the private Gateway. The acknowledgment includes the final destination (the original file sender).
5.  The private Gateway automatically routes the acknowledgment to the final destination. The transfer state then changes to <span style="font-style: italic;">Acknowledged</span>.

<span id="Scenario_Internet_to_intranet"></span>

### Scenario 2: Internet partner to intranet partner

This scenario describes the typical events that occur when receiving a file transfer from an application located on the Internet to an Axway Integrator application situated on the intranet.

<img src="/Images/Gateway/2GTWDMZex2_756x489.png" class="maxWidth" />

The transfer illustrated above is composed of the following steps:

1.  Internet client application A in initiator mode sends a file to the public Gateway. The transfer could, for example be executed using FTP.  
    The public Gateway can accept the transfer only through a CGate specified for this client. The public Gateway dynamically generates a Remote Site object for the transfer connection by using a Template Site.  
    The public Gateway correctly receives the file (encrypted).
2.  The public Gateway analyzes the incoming transfer using a Decision Rule. It applies a Model specified in the Decision Rule to forward the file to the private Gateway via the PeSIT HS E protocol.  
    At the end of the reception on the public Gateway, the handling process calls an exit that executes a virus scan. If the received is infected, the file is deleted and an error procedure is started. In this case, a message can be sent to the destination application specifying that an infected file has been received and deleted.  
    In this example, the file is virus free, and is received correctly on the private Gateway.
3.  The private Gateway analyzes the incoming transfer using a Decision Rule with <span class="code">execution\_type = XIB</span>. It applies a Model specified in the Decision Rule. The private Gateway sends the file directly to the destination Integrator application.  
    The file is sent correctly to Integrator.
4.  The private Gateway automatically generates and sends back an acknowledgment to the public Gateway.
5.  The transfer state of the file transfer issued in step 1 now changes to <span style="font-style: italic;">Acknowledged</span>. If the destination application accepts acknowledgment, the public Gateway applies a Model via a Decision Rule to route the acknowledgment to the final destination.

<span id="Managing_DMZ_related_transfer_failures"></span>

## Managing DMZ-related transfer failures

### Using negative acknowledgment between paired Gateways

An easy way to track Gateway DMZ errors is to implement the negative acknowledgment option between the paired Gateways.

When you have selected this option and a transfer is canceled, a negative acknowledgment is automatically sent from one Gateway to the other one.

The following examples show selected Mailbox records from paired DMZ Gateway partners of a failed file transfer.

#### Example – Public Gateway Mailbox

<table>
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/Mailbox1.gif" />   TEST  GW_PRV  Ils     DEFAULT_A   PeSIT E   TRANS   Responder   Receive   nack by USER (U)?</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Mailbox2.gif" />   TEST  Ils     Ils     DEFAULT_A   FTP       TRANS   Initiator   Send      Cancelled (C) A</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Mailbox3.gif" />   TEST  GW_PRV  MONITOR DEFAULT_A   PeSIT     EERP    Initiator   Send      Ended (E)  5</p>         </td>
      </tr>
   </tbody>
</table>

#### Example – Private Gateway Mailbox

<table>
   <tbody>
      <tr>
         <td><p><img src="/Images/Gateway/Mailbox2.gif" />   TEST  MONITOR  GW_PUB   DEFAULT_A   PeSIT    TRANS    Initiator   8311080   nack by USER (U)?</p>         </td>
      </tr>
      <tr>
         <td><p><img src="/Images/Gateway/Mailbox4.gif" />   TEST  Ils      GW_PUB   DEFAULT_A   PeSIT    EERP     Responder   8311080   Ended (E)  7</p>         </td>
      </tr>
   </tbody>
</table>

#### Mailbox record description

<span style="font-weight: bold;">104</span>: The private Gateway sends a transfer to the public Gateway

<span style="font-weight: bold;">185</span>: The file is received and the transfer state changes to <span style="font-style: italic;">Ended</span> in the Public Gateway

<span style="font-weight: bold;">186</span>: The public Gateway sends the file to an IIS server, but the transfer fails and the transfer state changes to <span style="font-style: italic;">Cancelled</span>

<span style="font-weight: bold;">187</span>: The public Gateway sends a negative acknowledgment back to the private Gateway

<span style="font-weight: bold;">105</span>: The private Gateway receives the negative acknowledgment

<span style="font-weight: bold;">104</span>: The transfer state on the private Gateway changes from <span style="font-style: italic;">Ended</span> to <span style="font-style: italic;">nack by User</span>

### File availability management : date\_to\_end

On the public Gateway, in order to simplify error tracking, you can define a <span class="code">date\_to\_end</span> for each Transfer Request.

Then, if the client does not pick up the file, or if the file is not sent to the server before the specified <span class="code">date\_to\_end</span>, the corresponding transfer state changes to <span style="font-style: italic;">Cancelled</span>.

To specify the <span class="code">date\_to\_end</span>, you define a Model object on the public Gateway.

You can specify a relative <span class="code">date\_to\_end.</span> For example: <span class="code" style="font-weight: bold;">+000010</span> means after 10 minutes the file transfer will be canceled if nothing happens in the meantime.

In this case the following message code is returned to the public Gateway:

<img src="/Images/Gateway/DMZ_date_to_end2.gif" width="432" height="43" />

### Route state value

Gateway automatically sets a route state value for each Transfer Request. The possible values for this route state are:

-   Acked (A)
-   Routed (R)
-   Failed (F)
-   To Route (T)
-   Not Routed (N)

You can use the route state value to check for instances in which a routing fails. For example, if the final destination for a transfer does not exist in the Public Gateway, the detailed Mailbox view of the corresponding incoming transfer request displays a <span style="font-style: italic;">Failed</span> route state value.

### Traces in the Rule Table properties

By default, Gateway generates traces of network activities and records these traces to your log file.

You can activate an additional set of tracing mechanisms by setting the Log Level option in the <span style="font-weight: bold;">General</span> tab of the Decision Rules object creation window.

The following examples compare the results of the two types of tracing, for two different transfer failure cases.

#### Case 1: The Remote Site does not exist on the public Gateway

-   Default tracing results on the public Gateway:  
    Gateway sets the route state to <span style="font-style: italic;">Failed</span> but nothing is logged in the Log file.  
    Note that if you have defined acknowledgment by Monitor in the remote site GW\_PRV of the public Gateway settings, a <span style="font-style: italic;">positive</span> acknowledgment is sent automatically to the originator.

<!-- -->

-   Decision Rule <span style="font-style: italic;">short trace</span> results in the public Gateway:  
    The public Gateway log contains the following trace entries:  


        NOT442I  11.02.2005 
                                         12:07:21 
                                          Examining 
                                    rule table [DEFAULT].
        NOT421I  11.02.2005 
                                         12:07:21 
                                         [31138] 
                                    Decision rule [FROM_GTW_SRV] selected, execution type: "Model".
        NOT423I  11.02.2005 
                                         12:07:21 
                                         [31138] 
                                    Model TO_CLI_SRV will be applied.
        NOT434E  11.02.2005 
                                         12:07:21 
                                         [31138] 
                                    For General Model TO_CLI_SRV, dest_alias FOUNDRY1 is not defined.

      
       
    If you are also using Axway Sentinel to monitor transfer activities, in Sentinel you have the corresponding alert message:  




        2005.02.11 12:31:26 NOT434E

        [31141] For General Model TO_CLI_SRV, dest_alias FOUNDRY1 is not defined

        GTW-UNIX

        GW_PUB 3 EC 1

#### Case 2: The directory for the client does not exist on the public Gateway

-   Default tracing results on the public Gateway:  
    The route state is set to <span style="font-style: italic;">Failed.</span> Nothing is logged in the Log file.  
    If you have defined acknowledgment by Monitor in the GW\_PRV Remote Site object of the public Gateway, a<span style="font-style: italic;"> positive</span> acknowledgment is automatically sent to the originator.

<!-- -->

-   Decision Rule <span style="font-style: italic;">short trace</span> results in the public Gateway:  
    If you have defined acknowledgment by Monitor in the GW\_PRV Remote Site object of the public Gateway, a<span style="font-style: italic;"> positive</span> acknowledgment is automatically sent to the originator.  
    In the public Gateway log:  


        NOT421I  11.02.2005 
                                         12:52:47 
                                         [31149] 
                                    Decision rule [FROM_GTW] selected, execution type: "Model".
        NOT423I  11.02.2005 
                                         12:52:47 
                                         [31149] 
                                    Model TO_CLI will be applied.
        NOT409E  11.02.2005 
                                         12:52:47 
                                         [31149] 
                                    Routing failure: XferRequest error (ErrCod = VFD directory not found).

      
       
    If you are also using Axway Sentinel to monitor transfer activities, in Sentinel you have the corresponding alert message:  




        2005.02.11 12:53:38 NOT409E

        [31150] Routing failure: XferRequest error (ErrCod = VFD directory not found)

        GTW-UNIX

        GW_PUB 3 EC 1

Related topics

[Overview: DMZ deployment](../../../../gateway_userguide_(primary)/ov_gateway/ov_dmz_deployment)

[About Secure Relay](../secure_relay_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
