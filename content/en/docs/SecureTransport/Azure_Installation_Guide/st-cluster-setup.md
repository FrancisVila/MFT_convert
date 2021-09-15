{
    "title": "Set up Enterprise Cluster with streaming",
    "linkTitle": "Set up Enterprise Cluster with streaming",
    "weight": "130"
}## Prerequisites

The following list outlines the prerequisites necessary for the described SecureTransport Enterprise cluster setup.

1.  Two RHEL Instances for SecureTransport Servers.
2.  Two RHEL Instances for SecureTransport Edges.
3.  Two RHEL Instances with GlusterFS Servers installed.
4.  One Administration Host (optional).
5.  One Microsoft SQL Server.

For correct setup of all your instances, please refer to the *Prerequisites -> UNIX-based platforms* topic in the SecureTransport 5.5 *Installation Guide*.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Make sure to have the following prerequisite installation package added: <br/><em>ld-linux.so.2 library package</em>         </td>
      </tr>
</table>

## Install SecureTransport

1.  Install SecureTransport Servers as described in the SecureTransport Installation Guide: *Install SecureTransport Server in an Enterprise Cluster or to use an external database*.
2.  Install SecureTransport Edges as described in the SecureTransport Installation Guide: *Install SecureTransport Server to use the embedded database* and in the SecureTransport Administrator's Guide: *SecureTransport Edge synchronization*
3.  Install GlusterFS client on both SecureTransport Servers and mount the GlusterFS volume on the client side.

For further reference, see [GlusterFS Documentation](https://gluster.readthedocs.io/en/latest/).
