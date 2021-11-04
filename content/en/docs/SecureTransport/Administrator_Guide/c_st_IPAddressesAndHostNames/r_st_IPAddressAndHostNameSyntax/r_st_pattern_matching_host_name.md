{
    "title": "Pattern matching a host name",
    "linkTitle": "Pattern matching a host name",
    "weight": "350"
}Use a host name pattern that uses asterisk (`*`) to represent one or more characters and question mark (`?`) to represent one character. The pattern specifies any host whose name matches. A host name pattern is valid for values that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses to match a host name, for example, in a user class definition.

Examples of valid values include the following:

-   `*.example.com`
-   `mail?.example.edu`
-   `int?*`

**Related topics:**

-   <a href="../r_st_exact_ipv4_ipv6_address" class="MCXref xref">Exact IPv4 or IPv6 address</a>
-   <a href="../r_st_classless_inter-domain_routing_notation" class="MCXref xref">Range of address using Classless Inter-Domain Routing notation</a>
-   <a href="../r_st_addresses_using_ipv4_address_subnet_mask" class="MCXref xref">Range of address using IPv4 address and subnet mask</a>
-   <a href="../r_st_patten_matching_ipv4_address" class="MCXref xref">Patten matching an IPv4 address</a>
-   <a href="../r_st_exact_host_name" class="MCXref xref">Exact host name</a>
