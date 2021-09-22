{
    "title": "Containerized deployment specifics",
    "linkTitle": "Containerized deployment specifics",
    "weight": "50"
}The following section outlines some of the operational and functional specifics of the SecureTransport *containerized* deployments as compared to the *classic* deployments on hardware/virtual machines.

## Operations

This table provides explanations on operations differences in *containerized* deployment vs the *classic* deployment of SecureTransport.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <td>
            <p><strong>Feature</strong>
</p>
         </td>
         <td>
            <p><strong>Containerized SecureTransport</strong>
</p>
         </td>
         <td>
            <p><strong>Details</strong>
</p>
         </td>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Application Logs (ServerLog)</p>
         </td>
         <td>
            <p>The logs are stored in the external DB (Server) and are also written to stdout/stderr (Edge/Server).</p>
         </td>
         <td>
            <p>When the logs are written to <code>stdout/stderr</code>, the container runtime engine is responsible for storing and forwarding the logs. The Docker Engine has different log drivers that can send the logs to a number of different external systems for log aggregation. For more information, see section <a href="../../k8s-known-issues">Known limitations and deployment specifics</a>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Client Source IP preservation</p>
            <p>(Server Usage Tracking, File Tracking)</p>
         </td>
         <td>
            <p>Real Client IP addresses not visible by default</p>
         </td>
         <td>
            <p>The complex networking used by the container orchestration frameworks usually "hides" the real client source IP address by using Source NAT.</p>
            <p>Certain features in SecureTransport, like the Server Usage Tracking, rely on the real client IP address to function properly. For more information on possible solutions to this problem see the </p>
            <p>For more information  on possible solutions, see section <a href="../../k8s-known-issues">Known limitations and deployment specifics</a>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Graceful Services shutdown</p>
         </td>
         <td>
            <p><span>SecureTransport</span> Edge support only</p>
         </td>
         <td>
            <p>During scale down operations (manual/automatic) the enabled protocol services on the SecureTransport Edge are stopped gracefully. See <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/operations/graceful-shutdown.htm">Graceful shutdown</a> in the <i>SecureTransport </i><span>5.5</span><i> Administrator guide</i> for more information.</p>
            <p>Note that the configured graceful shutdown timeouts must be lower than the <code>"terminationGracePeriodSeconds"</code> specified in the Kubernetes StatefulSet manifest.</p>
            <p>The Protocol services and the Transaction manager are not stopped gracefully when scaling down the SecureTransport Server. This may cause client transfers to interrupt unexpectedly.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Update/Upgrade</p>
         </td>
         <td>
            <p>Update is performed by replacing the Docker Image</p>
         </td>
         <td>
            <p>Updates to the SecureTransport Containerized Delivery will be delivered as new Docker Images built by Axway whenever there is a new release/update.</p>
         </td>
      </tr>
   </tbody>
</table>

## Feature parity

This table provides explanations on functionality differences in containerized deployment vs classic deployment of SecureTransport.

<table cellspacing="0">
   <thead>
      <tr>
         <td>
            <p><strong>Feature</strong>
</p>
         </td>
         <td>
            <p><strong>Containerized SecureTransport</strong>
</p>
         </td>
         <td>
            <p><strong>Details</strong>
</p>
         </td>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Managing the TM Rules Packages ("TM Settings" page) </p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
         </td>
      </tr>
      <tr>
         <td>
            <p>FTP Passive Mode</p>
         </td>
         <td>
            <p>Supported, but requires more complex setup</p>
         </td>
         <td>
            <p>The setup involves using at least 2 load balancers. See <a href="../../using-st-cont-delivery/initial-config">FTP Passive Mode</a> for more info.</p>
         </td>
      </tr>
      <tr>
         <td>Real users         </td>
         <td>Not supported         </td>
         <td>Since SecureTransport is installed as non-root in the docker image, real users are not supported.         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>Clustering/Deployment</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Standard Cluster</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>The SecureTransport Server Docker image can be deployed using an external database in Enterprise Cluster mode only.         </td>
      </tr>
      <tr>
         <td>
            <p>Edge Deployment</p>
         </td>
         <td>
            <p>Requires external database</p>
         </td>
         <td>
            <p>The containerized deployment of SecureTransport Edges requires an external MariaDB Database. This is needed for the following reasons:</p>
            <ul>
               <li>Reduce the size of the SecureTransport Edge Docker Image               </li>
               <li>Persist the configuration outside of the container to survive container restarts               </li>
               <li>Allows multiple SecureTransport Edge pods to use the same configuration                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>
            <p>Edge Synchronization</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p>The SecureTransport Edges containerized deployment requires a shared external database. In this deployment the system configuration changes are stored in the external database and are visible by all Edges in the Kubernetes StatefulSet.</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">All system configuration changes require container restart.         </td>
      </tr>
</table></p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>System Configuration/Services</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Importing system configuration from non-containerized SecureTransport installation</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Multi-Port Protocol Listeners</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p>When running containerized SecureTransport Edge/Server you cannot add Protocol servers - only the default ones can be used. However, if there is a requirement to start multiple Protocol servers with different settings you can create additional SecureTransport Edge StatefulSets and configure separate network zones in the SecureTransport Enterprise Cluster. See <a href="../../using-st-cont-delivery/additional-network-zones">Multiple network zones</a>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Monitor Server</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p>The Monitor server checks that the SecureTransport servers are running and restarts them if they terminate. In a containerized deployment this function is performed using Kubernetes  Readiness and Liveliness Probes (see <a href="https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/" xrefformat="{paratext}">Kubernetes documentation</a>).</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>Database Specific</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Updating the External Database settings </p>
         </td>
         <td>
            <p>Supported only via the external <code>db.conf</code> file</p>
         </td>
         <td>
            <p>The external database configuration is specified in a file called <code>db.conf</code> which is supplied to the container as Kubernetes secret (see section <a href="../../using-st-cont-delivery/deployment-prerequisites">Deployment prerequisites</a>). This is the only supported way to configure the external database - making changes through the Administration Tool is not supported.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Direct log data to separate Oracle databases</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Use Custom JDBC URL for the external database</p>
         </td>
         <td>
            <p>Not supported</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Data pump database management system</p>
         </td>
         <td>
            <p>Always enabled</p>
         </td>
         <td>
            <p>Cannot be disabled.</p>
         </td>
      </tr>
   </tbody>
</table>

*next topic:* [Deploy SecureTransport on Kubernetes](../../using-st-cont-delivery)
