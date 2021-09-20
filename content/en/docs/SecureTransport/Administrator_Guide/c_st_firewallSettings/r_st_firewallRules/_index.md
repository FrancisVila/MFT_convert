{
    "title": "Firewall rules",
    "linkTitle": "Firewall rules",
    "weight": "290"
}You can use the firewall rules in the following tables for active/active (load-balanced) or active/passive (failover) Standard Clusters and Enterprise Clusters.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For a non-streaming deployment with active/active or active/passive systems, skip the rules for port  1080. For a non-streaming setup with only a single machine, also skip the Standard Clustering rules. The Destination Port values listed are the default values or ranges used by <span>SecureTransport</span>.         </td>
      </tr>
</table>

The following topics list the firewall rules:

-   [Protocol rules](r_st_protocol_rules) - Lists the firewall protocol rules.
-   [Authentication rules](r_st_authentication_rules) - Lists the firewall authentication rules.
-   [Administration rules](r_st_administration_rules) - Lists the firewall administration rules.
-   [TM server communication rules](r_st_tm_server_communication_rules) - Lists the firewall Transaction Manager server communication rules.
-   [Server transfer rules](r_st_server_transfer_rules) - Lists the firewall server transfer rules.
-   [Standard Cluster rules](r_st_standard_clustering_rules) - Lists the firewall Standard cluster rules.
-   [Enterprise Cluster rules](r_st_large_enterprise_clustering_rules) - Lists the firewall Enterprise Cluster rules.
-   [Protocol rules - outbound from SecureTransport Edge](r_st_protocol_rules_outbound) - Lists the firewall protocol rules for outbound communication from the SecureTransport Edge.
