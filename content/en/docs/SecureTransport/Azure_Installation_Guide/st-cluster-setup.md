{
    "title": "Set up Enterprise Cluster with streaming",
    "linkTitle": "Set up Enterprise Cluster with streaming",
    "weight": "130"
}## Prerequisites

The following list outlines the prerequisites necessary for the described {{< SecureTransport/componentshortname  >}} Enterprise cluster setup.

1.  Two RHEL Instances for {{< SecureTransport/componentshortname >}} Servers.
2.  Two RHEL Instances for {{< SecureTransport/componentshortname >}} Edges.
3.  Two RHEL Instances with GlusterFS Servers installed.
4.  One Administration Host (optional).
5.  One Microsoft SQL Server.

For correct setup of all your instances, please refer to the *Prerequisites -> UNIX-based platforms* topic in the {{< SecureTransport/componentshortname  >}} {{< SecureTransport/componentversion  >}} *Installation Guide*.

> **Note:**
>
> Make sure to have the following prerequisite installation package added: ld-linux.so.2 library package

## Install SecureTransport

1.  Install {{< SecureTransport/componentshortname >}} Servers as described in the {{< SecureTransport/componentshortname >}} Installation Guide: *Install {{< SecureTransport/componentshortname >}} Server in an Enterprise Cluster or to use an external database*.
2.  Install {{< SecureTransport/componentshortname >}} Edges as described in the {{< SecureTransport/componentshortname >}} Installation Guide: *Install {{< SecureTransport/componentshortname >}} Server to use the embedded database* and in the {{< SecureTransport/componentshortname >}} Administrator's Guide: *{{< SecureTransport/componentshortname >}} Edge synchronization*
3.  Install GlusterFS client on both {{< SecureTransport/componentshortname >}} Servers and mount the GlusterFS volume on the client side.

For further reference, see [GlusterFS Documentation](https://gluster.readthedocs.io/en/latest/).
