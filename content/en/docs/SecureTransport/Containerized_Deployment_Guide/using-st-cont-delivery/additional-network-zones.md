{
    "title": "Multiple network zones",
    "linkTitle": "Multiple network zones",
    "weight": "110"
}Using multiple network zones in your SecureTransport deployment is necessary for adding multiple listeners per protocol service.

The recommended deployment of the protocol listeners is to configure them on the Edges. You can have only one listener per protocol service. This model brings a limitation when you want to take advantage of the "Multi Port Protocol Listeners" feature in the classic deployment.

The solution to this is to create a separate StatefulSet/Network Zone which allows deploying the same protocol service (HTTP for example) with a different configuration.

You can follow the processes as described in the [Communication across Transaction Manager, protocol, and proxy servers](https://docs.axway.com//bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/c_st_networkZones.htm) topic, part of the *SecureTransport* 5.5 *Administrator guide*.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The load balancer which is in front of the Kubernetes cluster must be added as endpoint (IP address).         </td>
      </tr>
</table>

*next topic:* [Update the deployment](../update-st)