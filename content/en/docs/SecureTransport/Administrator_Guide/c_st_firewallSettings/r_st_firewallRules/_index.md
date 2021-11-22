{
    "title": "Firewall rules",
    "linkTitle": "Firewall rules",
    "weight": "280"
}You can use the firewall rules in the following tables for active/active (load-balanced) or active/passive (failover) Standard Clusters and Enterprise Clusters.

> **Note:**
>
> For a non-streaming deployment with active/active or active/passive systems, skip the rules for port 1080. For a non-streaming setup with only a single machine, also skip the Standard Clustering rules. The Destination Port values listed are the default values or ranges used by SecureTransport.

The following topics list the firewall rules:

-   <a href="r_st_protocol_rules" class="MCXref xref">Protocol rules</a> - Lists the firewall protocol rules.
-   <a href="r_st_authentication_rules" class="MCXref xref">Authentication rules</a> - Lists the firewall authentication rules.
-   <a href="r_st_administration_rules" class="MCXref xref">Administration rules</a> - Lists the firewall administration rules.
-   <a href="r_st_tm_server_communication_rules" class="MCXref xref">TM server communication rules</a> - Lists the firewall Transaction Manager server communication rules.
-   <a href="r_st_server_transfer_rules" class="MCXref xref">Server transfer rules</a> - Lists the firewall server transfer rules.
-   <a href="r_st_standard_clustering_rules" class="MCXref xref">Standard Cluster rules</a> - Lists the firewall Standard cluster rules.
-   <a href="r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a> - Lists the firewall Enterprise Cluster rules.
-   <a href="r_st_protocol_rules_outbound" class="MCXref xref">Protocol rules - outbound from SecureTransport Edge</a> - Lists the firewall protocol rules for outbound communication from the {{< SecureTransport/componentshortname >}} Edge.
