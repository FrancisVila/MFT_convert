{
    "title": "Introduction",
    "linkTitle": "Introduction",
    "weight": "30"
}Starting with the SecureTransport 5.5 GA release, the SecureTransport administrators have the option to deploy SecureTransport Servers or Edges as Linux (RHEL) containers using Docker Engine as the container runtime and Kubernetes as the container orchestrator. This guide outlines the specifics of containerized SecureTransport Enterprise Cluster (EC) deployment and provides the necessary steps to establish the streaming environment across cluster nodes.

The containerized delivery of SecureTransport includes two Docker images (one for Edge and one for Server) that can be downloaded from the [Axway Support Portal](https://login.axway.com/auth/realms/Broker/protocol/saml?SAMLRequest=fZFBb8IwDIXv%2FIoq9zYB2rJGpQjGYUhMQ9DtsMuUFgPR2qSLU8b%2B%2FVIYGieOtvyev2enk1NdeUcwKLUak37AyCTrpdPWHtQavlpA67kJhWPSGsW1QIlciRqQ25Jvps9LPggYb4y2utQV8RbzMflIdpFgsYiKMEzicMAeoA9lGIkoiYqkGO2KIomHSbzbbon3dt3tfJwcsYWFQiuUdS02YD6LfBbm%2FREfMh6F78SbOyiphD2rDtY2yCmt9F6qQJy%2BxU9Q6poKl4AaEFWNdGb0Jxh6haQoake6%2BitnUm2l2t8PWFyGkD%2Fl%2BcpfvWxy4k0RwXQUj1phW4PZgDnKEl7Xy38ubJtGG3tDBoqSLO0Y%2BDmtuRyYd537EOK6kGTYHMCAX1YSlPU7aUpvLLOU3r4w6%2F0C&SigAlg=http%3A%2F%2Fwww.w3.org%2F2001%2F04%2Fxmldsig-more%23rsa-sha256&Signature=hslfOjcccysAxCJfOHTk4UfnCsihZVl8k6C0y%2BQajOMA%2FeYdHBcbxK9HR3FxGexFYGRsUIXSOL1udqD%2F6L1LOSWyssWPfvIUwORFIacvo5Dh4pVePBvvot4lQkoC6OILQDjBb209Xw3Mgw%2Bmji%2F%2Fi4ZOqNjriZBKVlhhl%2FYhwvk6JZ8bBqJcsuXLy26UNWbfglEfnP8E4AaqYixQ%2B8kkeECz3MgPqTO4EiiTOm4WKjTzTqoCdoHiBdfwNaa4HjWyKGk5NLXXRBdMG2mh2xrhY9ydLwjwMjblNt9WU0eQZgbgyOh1qpUdHfU0rIKdvPPOXoTQfBYulcqSdxpRURuEzQ%3D%3D&redirect_uri=https%3A%2F%2Fsupport.axway.com%2Fen%2F "Axway Support").

The SecureTransport Containerized deployment offers the following advantages:

-   Simplified update: The steps required to update the deployment are as simple as changing the Docker Image with the new one (at the moment downtime is required)
-   Manual or automated scaling of Edges and Servers in your Enterprise Cluster: provides the ability to scale the Edge/Server deployments based on the current load without any additional steps (using Kubernetes as the container orchestrator)

## Deployment outline

The following steps outline the process required to deploy SecureTransport as a Linux Container on Kubernetes. In order to fully benefit from the security features of the SecureTransport Streaming Protocol, the deployment requires at least 2 Kubernetes clusters - one in the DMZ and another one in the Internal Network.

1.  Download the SecureTransport Edge and Server Docker Images from the [Axway Support Portal](https://login.axway.com/auth/realms/Broker/protocol/saml?SAMLRequest=fZFBb8IwDIXv%2FIoq9zYB2rJGpQjGYUhMQ9DtsMuUFgPR2qSLU8b%2B%2FVIYGieOtvyev2enk1NdeUcwKLUak37AyCTrpdPWHtQavlpA67kJhWPSGsW1QIlciRqQ25Jvps9LPggYb4y2utQV8RbzMflIdpFgsYiKMEzicMAeoA9lGIkoiYqkGO2KIomHSbzbbon3dt3tfJwcsYWFQiuUdS02YD6LfBbm%2FREfMh6F78SbOyiphD2rDtY2yCmt9F6qQJy%2BxU9Q6poKl4AaEFWNdGb0Jxh6haQoake6%2BitnUm2l2t8PWFyGkD%2Fl%2BcpfvWxy4k0RwXQUj1phW4PZgDnKEl7Xy38ubJtGG3tDBoqSLO0Y%2BDmtuRyYd537EOK6kGTYHMCAX1YSlPU7aUpvLLOU3r4w6%2F0C&SigAlg=http%3A%2F%2Fwww.w3.org%2F2001%2F04%2Fxmldsig-more%23rsa-sha256&Signature=hslfOjcccysAxCJfOHTk4UfnCsihZVl8k6C0y%2BQajOMA%2FeYdHBcbxK9HR3FxGexFYGRsUIXSOL1udqD%2F6L1LOSWyssWPfvIUwORFIacvo5Dh4pVePBvvot4lQkoC6OILQDjBb209Xw3Mgw%2Bmji%2F%2Fi4ZOqNjriZBKVlhhl%2FYhwvk6JZ8bBqJcsuXLy26UNWbfglEfnP8E4AaqYixQ%2B8kkeECz3MgPqTO4EiiTOm4WKjTzTqoCdoHiBdfwNaa4HjWyKGk5NLXXRBdMG2mh2xrhY9ydLwjwMjblNt9WU0eQZgbgyOh1qpUdHfU0rIKdvPPOXoTQfBYulcqSdxpRURuEzQ%3D%3D&redirect_uri=https%3A%2F%2Fsupport.axway.com%2Fen%2F "Axway Support") and load the images in Docker Engine on the Kubernetes Cluster Nodes.
2.  Prepare the external databases that will be used by the SecureTransport Edge/Servers.
3.  Prepare the external shared filesytem to be used by the SecureTransport Servers to store the user files.
4.  Create the needed configuration files and the respective Kubernetes secrets for each deployment (Edge/Server) in each Kubernetes Cluster.
5.  Create the Kubernetes manifest YML files using the provided examples.
6.  Deploy the Edges/Servers and perform the system configuration as required.

## Platform support

The Docker engine and Kubernetes orchestrator software must be installed on a Linux-based operating system. For more information, see the Docker/Kubernetes supported platforms documentation.

<table cellspacing="0">
   <tbody>
      <tr>
         <td>
            <p><strong>Container Runtime</strong>
</p>
         </td>
         <td>
            <p><strong>Release</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Docker Enterprise/Community Edition</p>
         </td>
         <td>
            <p>19.x+</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><strong>Container Orchestration</strong>
</p>
         </td>
         <td><strong>Release</strong>
         </td>
      </tr>
      <tr>
         <td>
            <p>Kubernetes</p>
         </td>
         <td>
            <p>1.9.x+</p>
         </td>
      </tr>
   </tbody>
</table>

## Supported external databases

The containerized version of SecureTransport Enterprise Cluster (EC) supports the same Oracle and MSSQL external databases as the classic deployment.

In order to address the requirement for manual/automatic scalability of the containerized SecureTransport Edge, an external MariaDB database is required as well.

For more information, see [Axway and third-party software support](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm#database) topic in the SecureTransport 5.5 *Administrator guide*.

*next topic:* [Containerized deployment specifics](classic-vs-containerized)
