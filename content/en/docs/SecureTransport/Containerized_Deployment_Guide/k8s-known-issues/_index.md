{
    "title": "Known limitations and deployment specifics",
    "linkTitle": "Known limitations and deployment specifics",
    "weight": "50"
}The following topic contains some tips and information on containerized deployment limitations and specifics.

## Container logs limitations

The SecureTransport Docker images allow starting multiple services inside one container and when you start/stop a service in the SecureTransport Administration Tool, the service logs will not be available on `stdout/stderr`. See section <a href="../using-st-cont-delivery/initial-deployment" class="MCXref xref">Initial deployment</a> for more information on how to properly deploy the SecureTransport Server or Edge pods to ensure that the logs are not lost.

## Client Source IP is not preserved in Kubernetes

In Kubernetes on-premise deployment, the services are exposed to the outside world using K8S NodePort Service.

Packets sent to Services with Type <u>NodePort</u> are source NATd by default, so the client Source IP is lost. See the [Kubernetes Services documentation](https://kubernetes.io/docs/tutorials/services/source-ip/ "Kubernetes Services documentation") for more information.

To disable the Source NAT, the end-user K8S NodePort services must be deployed with `externalTrafficPolicy: Local`. This requires having an Edge Pod on each K8S node, otherwise end-user connections will fail.

In some cases, when using WeaveNet CNI, the weave DaemonSet must be edited to add the setting: `NO_MASQ_LOCAL=1`. See the [Weave Net documentation](https://www.weave.works/docs/net/latest/kubernetes/kube-addon/#configuration-options) for more info.

## Kubernetes DNS TTL maximum allowed values

If there is need for a bigger DNS TTL value, a dedicated configuration option is introduced on SecureTransport Edges: `Docker.EdgeCount.DelayInterval`. It modifies the delay prior to establishing new streaming connections when new edge pod is discovered and its value must be the same or higher than the DNS TTL, but not more than 20 seconds as this may present unexpected results.

> **Note:**
>
> Docker.EdgeCount.DelayInterval is a Server configuration option present only on SecureTransport Edges and cannot be set via environment variable.

## Service restart specifics

If you need to restart any service (admin, protocol, etc.), it is recommended to restart the respective container.

## Multiple Edge specifics

-   It is recommended to have only one Server StatefulSet in the internal Kubernetes cluster, with multiple Edge StatefulSets (if needed) in the DMZ Kubernetes cluster.
-   Multiple Edges in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> configuration are supported only when a separate zone is configured for each Edge. See section <a href="../using-st-cont-delivery/additional-network-zones" class="MCXref xref">Multiple network zones</a> for more info.
-   Changes in configuration which is dynamically reloaded is not replicated if there is more than one Edge. See section <a href="../using-st-cont-delivery/initial-deployment" class="MCXref xref">Initial deployment</a> for more info.
-   In multiple (more than one) Edge deployments, HTTP, FTP and SSH sessions established on the Edge side cannot be killed via the Server Usage monitor on the SecureTransport Server. The administrator can manipulate via the Server Usage monitor only the local sessions of each SecureTransport Edge.

 