{
    "title": "Set up Enterprise Cluster with streaming",
    "linkTitle": "Set up SecureTransport Enterprise Cluster with streaming",
    "weight": "110"
}## Prerequisites

The following list outlines the prerequisites necessary for the described <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Enterprise cluster setup.

1.  Two RHEL Instances for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers.
2.  Two RHEL Instances for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges.
3.  Two RHEL Instances with GlusterFS Servers installed.
4.  One Administration Host (optional).
5.  One Microsoft SQL Server.

For correct setup of all your instances, please refer to the *Prerequisites -> UNIX-based platforms* topic in the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable" style="font-style: italic;">5.5</span>*Installation Guide*.

**Note:** Make sure to have the following prerequisite installation package added:

`ld-linux.so.2 library package`

## Install SecureTransport

1.  Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>Servers as described in the *<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>Installation Guide:* *Install SecureTransport Server in an Enterprise Cluster or to use an external database.*
2.  Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>Edges as described in the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> *Installation Guide:* *Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to use the embedded database* and in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide: *SecureTransport Edge synchronization*
3.  Install GlusterFS client on both <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers and mount the GlusterFS volume on the client side.

For more information, see the [GlusterFS Documentation](https://gluster.readthedocs.io/en/latest/).
