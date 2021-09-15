{
    "title": "Set up SecureTransport Enterprise Cluster with streaming",
    "linkTitle": "Set up SecureTransport Enterprise Cluster with streaming",
    "weight": "110"
}## Prerequisites

The following list outlines the prerequisites necessary for the described SecureTransport Enterprise cluster setup.

1.  Two RHEL Instances for SecureTransport Servers.
2.  Two RHEL Instances for SecureTransport Edges.
3.  Two RHEL Instances with GlusterFS Servers installed.
4.  One Administration Host (optional).
5.  One Microsoft SQL Server.

For correct setup of all your instances, please refer to the *Prerequisites -> UNIX-based platforms* topic in the SecureTransport 5.5*Installation Guide*.

**Note:** Make sure to have the following prerequisite installation package added:

`ld-linux.so.2 library package`

## Install SecureTransport

1.  Install SecureTransportServers as described in the *SecureTransportInstallation Guide:* *Install SecureTransport Server in an Enterprise Cluster or to use an external database.*
2.  Install SecureTransportEdges as described in the SecureTransport *Installation Guide:* *Install SecureTransport Server to use the embedded database* and in the SecureTransport Administrator's Guide: *SecureTransport Edge synchronization*
3.  Install GlusterFS client on both SecureTransport Servers and mount the GlusterFS volume on the client side.

For more information, see the [GlusterFS Documentation](https://gluster.readthedocs.io/en/latest/).
