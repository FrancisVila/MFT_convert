{
    "title": "SecureTransport Edge synchronization",
    "linkTitle": "SecureTransport Edge synchronization",
    "weight": "90"
}You can deploy {{< SecureTransport/componentshortname  >}} Edge servers so that configuration changes are
dynamically synchronized from a primary {{< SecureTransport/componentshortname  >}} Edge to the other
(secondary) {{< SecureTransport/componentshortname  >}} Edge servers. This synchronization works like
configuration synchronization in a Standard Cluster (SC), but because {{< SecureTransport/componentshortname  >}} Edge
servers do not process events, they are not in a cluster.

You configure the secondary {{< SecureTransport/componentshortname  >}} Edge servers on the primary {{< SecureTransport/componentshortname  >}} Edge
server. Most configuration changes are dynamically synchronized across the {{< SecureTransport/componentshortname  >}} Edge servers immediately.

The following topics describe and provide how-to instructions to synchronize {{< SecureTransport/componentshortname  >}} Edge servers:

-   [Manual synchronization](r_st_manual_synchronization) - Describes manual synchronization of {{< SecureTransport/componentshortname >}} Edge servers.
-   [Requirements for synchronization](t_st_requirements_synchronization) - Lists the requirements for synchronizing {{< SecureTransport/componentshortname >}} Edge servers.
-   [What information is synchronized](t_st_what_information_is_synchronized) - Lists the information that is synchronized.
-   [Set up SecureTransport Edge servers for synchronization](t_st_setup_servers) - Provides the how-to instructions for setting up {{< SecureTransport/componentshortname >}} Edge servers for synchronization.
-   [Manually synchronize SecureTransport Edge servers](t_st_manually_synchronize_edge_servers) - Provides the how-to instructions for manually synchronizing {{< SecureTransport/componentshortname >}} Edge servers.
-   [Maintain synchronized SecureTransport Edge servers](t_st_maintain_synchronized_edge_servers) - Describes maintaining synchronized {{< SecureTransport/componentshortname >}} Edge servers and provides how-to instructions for maintaining synchronized {{< SecureTransport/componentshortname >}} Edge servers.
