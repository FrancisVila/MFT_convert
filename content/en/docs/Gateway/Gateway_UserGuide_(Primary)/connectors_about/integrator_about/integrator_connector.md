{
    "title": "Axway Integrator connector",
    "linkTitle": "Integrator connector",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Connectors

[{{< Gateway/componentlongname  >}} and Axway Integrator / AMTrix](#gateway_and_integrator)

[Required versions](#versions)

[Deployment](#deployment)

[Configuration](#config)

[Purging for transfers routed from Gateway to Integrator](#Purging)

<span id="gateway_and_integrator"></span>

## {{< Gateway/componentlongname  >}} and Axway Integrator / AMTrix

The Axway Integrator connector in Gateway enables you to:

-   Route files received on Gateway to Integrator (or AMTrix)
-   Send files from Integrator (or AMTrix) using any of the Gateway supported protocols

### Routing files received on Gateway to Integrator

After configuring the connector, Gateway handles file routing to Integrator (or AMTrix) as illustrated in the following figure.

<img src="/Images/Gateway/Integrator_routing.png" class="mediumWidth" />

1.  On reception of a file from a Gateway client, Gateway sends a notification to the destination Integrator server indicating that a file is available for retrieval by Integrator.  
    If Sentinel monitoring is activated on Gateway, the notification includes information that enables Gateway and Integrator to share a CycleID link on the transfer.
2.  Integrator retrieves the file identified in the Gateway notification.
3.  Integrator deletes the copy of the retrieved file in the Gateway directory.

### Sending files from Integrator to remote servers using any Gateway supported protocol

Once you have configured your connector, Integrator (or AMTrix) sends files to remote servers via Gateway, as illustrated in the following figure.

<img src="/Images/Gateway/Integrator_remote_server.png" class="mediumWidth" />

1.  Integrator initiates a request to Gateway for a Transfer Request of a file to a remote server. This request from Integrator is handled by a Gateway API. The initiation request includes information that enables Gateway to access the file on the Axway Integrator platform.
2.  Gateway uses information contained in the initial Integrator request to create a Transfer Request sending a copy of the indicated file from Integrator to the target remote server. Gateway derives the `file_component` attribute of the Transfer Request (indicating the location of the file to be transferred from the Axway Integrator machine) from information provided by Integrator.
3.  Gateway notifies Integrator of each change of transfer state (ToBegin, Processing, Ended, Acked...).  
    If Sentinel monitoring is activated, Gateway generates Sentinel state change messages and CycleID for the transfer.

<span id="versions"></span>

## Required versions

You can connect Gateway to:

-   Axway Integrator 2.0.1 (or later)
-   Axway AMTrix 4.4.0 (or later)

<span id="deployment"></span>

## Deployment

Two types of configuration are possible:

-   Gateway and Integrator (or AMTrix) on the same machine
-   Gateway and Integrator (or AMTrix) on two different machines running the same operating system

If you deploy Gateway and Integrator (or AMTrix) on different machines, you must create a folder on each machine to which the other machine has access.

<span id="config"></span>

## Configuration

To configure Gateway for use with Integrator (or AMTrix), set up the Integrator connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

1.  In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select **Configure**.
2.  Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > Integrator</span>.
3.  Complete the [Integrator parameters](../../../configuration_start_here/config_connectors#olh_connectivity_xib).
4.  Click <span style="font-weight: bold;">Activate</span> to enable the connector.
5.  Click <span style="font-weight: bold;">OK</span>.

### From Gateway to Integrator

Integrator (or AMTrix) listens to the port that you define for it in the Gateway configuration menu. Gateway connects via this port, and sends the transfer parameters to Integrator. By default, the Gateway routing file is located in <span class="code">run\_time\\tmp</span>.

If there is a problem with the connection, Gateway creates a new file that lists the transfer parameters. This file is placed in the <span style="font-style: italic;">shared directory</span> which is accessible to both Gateway and Integrator. When Integrator is reconnected, it can recover this file. Therefore, the shared directory is used only to record off-line functioning.

### From Integrator to Gateway

Integrator (or AMTrix) uses the API-C standards for Gateway to create a transfer. By default, the file coming from the source Integrator is placed in the <span class="code">xib/data/tmp</span> directory.

### Configuration limitations

-   You must never configure Gateway to have more than one action (<span class="code">route-to-XIB</span>) for a transfer. This means the only decision rule for a transfer routed to Integrator should be in the transfer's final state: <span class="code">ENDED</span>, <span class="code">ENDED-TO-ACK</span> (for business ack only), <span class="code">ACKED</span>.
-   Routing <span class="code">ENDED\_TO\_ACK</span> transfers to Integrator (FileAct RealTime) generates a business ACK from Integrator. If the receipt option is set to Monitor (Automatic), Gateway automatically sends its own ACK message which results in error for the second ack send. The recommendation is to update the decision rule by adding the value <span class="code">MANUAL</span> for <span class="bold_in_para">receipt send mode</span>. In such cases there will be no ACK duplication by assuring that only transfers which have set the manual ACK (<span class="code">ACK\_BY\_USER</span>) are routed to Integrator. An alternative would be to set the receipt option to <span class="code">ACK\_BY\_USER</span>.
-   For SWIFTNet FileAct RealTime, the final state should be <span class="code">ENDED</span> or <span class="code">ENDED\_TO\_ACK</span> and Integrator must send the business ACK (receipt option: ACK By User).
-   For SWIFTNet Store-and-Forward flows, the final state should be ACKED, and Gateway must send the protocol ACK (receipt option: ACK By Monitor).

<span id="Purging"></span>

## Purging for transfers routed from Gateway to Integrator

To prevent Gateway's purge from deleting the payload file after a transfer is routed (via a decision rule) from Gateway to Integrator, even if Integrator was offline or was not fast enough to process the payload:

-   The transfers routed to Integrator are marked by a <span class="code">routed\_to\_XIB</span> flag. This is done automatically after the routing and can be seen using <span class="code">peldsp display\_trans</span> command line.

<!-- -->

-   The purge operation, when <span class="bold_in_para">Purge the file sent or received</span> is selected, will not delete the files associated with the <span class="code">routed\_to\_XIB</span> transfers (including also the temporary files). The following protocols do not obey this rule and will have their temporary files (only) removed during purge:
    -   AS1 (SMTP and POP3)
    -   RosettaNet (SMTP, POP3 and HTTP)
    -   AS2
    -   Odette

### Limitations

Note that this approach has certain limitations:

-   You must ensure that a purge operation is not launched when routing to XIB is in progress. The transfer will have to be marked during the routing action itself so purge would later know to delete the transfer from the mailbox but not its payload.
-   You must never configure Gateway to have more than one action (route-to-XIB) for a transfer. This means the only decision rule for a transfer routed to Integrator should be in the transfer's final state: ENDED, ENDED-TO-ACK (for business ack only), ACKED.
-   Multiple post-processing must never be performed on the same transfer or it may cause undesirable results like in the following case:
    -   If a script, for example, is launched by a decision rule prior to the decision rule routing the transfer to XIB, a race condition occurs: if the user script modifies the data, Integrator may read the file in an inconsistent state. If a script is then launched by a decision rule after routing the transfer to XIB, the script can access the payload file while it is still being modified by Integrator.

<span class="bold_in_para">Note</span>: Gateway does not modify or delete the payload file after a transfer has been routed to XIB.

Related topics

[About Axway Integrator / AMTrix](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
