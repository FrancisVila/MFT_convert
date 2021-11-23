{
    "title": "Deployment topology",
    "linkTitle": "Deployment topology",
    "weight": "60"
}This topic outlines the deployment of the containerized Enterprise Cluster. It supplies high-level diagrams and explanations about:

-   Specifics of containerized vs classic deployment
-   Streaming protocol deployment overview

<span id="High-lev"></span>

## High-level deployment diagram

The containerized SecureTransport high-level deployment is similar to the classic deployment on hardware/virtual machines in several ways:

-   The SecureTransport Enterprise Cluster (EC) server nodes are deployed in the Secure Internal network along with the shared external database and File storage
-   The SecureTransport Edges are deployed in the Perimeter (DMZ) network
-   The Streaming Protocol is used to establish the connection from the EC server nodes to the Edges

![](/Images/SecureTransport/contain-deployment-topology.png)

The main differences are highlighted below:

-   The containerized SecureTransport deployment requires a separate Kubernetes cluster in each network where SecureTransport Edges/Servers will be deployed in order to take advantage of the security benefits of the SecureTransport Streaming Protocol
-   The SecureTransport Edges require an external database

## SecureTransport Streaming Protocol

The main challenge in deploying SecureTransport in a containerized environment is the Streaming Protocol and the way connections are established between the Server and Edge containers. The following deployment diagram outlines the Streaming Protocol specifics.

In order to benefit from the native scalability of a containerized deployment (manual or automatic) SecureTransport is deployed as a Kubernetes StatefulSet.

However, this presents two challenges in the Streaming Protocol setup:

-   The SecureTransport EC nodes deployed in the Secure Network must automatically discover new SecureTransport Edge Pods deployed in a different Kubernetes cluster in the DMZ
-   The Streaming connections established from the SecureTransport EC nodes must be equally distributed across all currently deployed SecureTransport Edge Pods in a given StatefulSet.

A dedicated functionality in SecureTransport allows the SecureTransport Server and Edge to exchange information about the current number of running Edges in a given StatefulSet using the Streaming Protocol.

In order to ensure equal distribution of the Streaming connections, it is recommended to utilize an additional load balancer (HAProxy), that supports the "least connections" algorithm.

Note that there are other ways to configure the SecureTransport Streaming Protocol (for example [IPVS-Based In-Cluster load balancing](https://kubernetes.io/blog/2018/07/09/ipvs-based-in-cluster-load-balancing-deep-dive/ "IPVS-Based In-Cluster load balancing")).

![](/Images/SecureTransport/streaming-protocol.png)

*next topic:* [Deployment prerequisites](../deployment-prerequisites)
