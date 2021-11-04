{
    "title": "Multiple network zones",
    "linkTitle": "Multiple network zones",
    "weight": "110"
}Using multiple network zones in your SecureTransport deployment is necessary for adding multiple listeners per protocol service.

The recommended deployment of the protocol listeners is to configure them on the Edges. You can have only one listener per protocol service. This model brings a limitation when you want to take advantage of the "Multi Port Protocol Listeners" feature in the classic deployment.

The solution to this is to create a separate StatefulSet/Network Zone which allows deploying the same protocol service (HTTP for example) with a different configuration.

You can follow the processes as described in the <a href="https://docs.axway.com//bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/c_st_networkZones.htm" class="MCXref xref">Communication across Transaction Manager, protocol, and proxy servers</a> topic, part of the *SecureTransport* <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> *Administrator guide*.

> **Note:**
>
> The load balancer which is in front of the Kubernetes cluster must be added as endpoint (IP address).

*next topic:* <a href="../update-st" class="MCXref xref">Update the deployment</a>
