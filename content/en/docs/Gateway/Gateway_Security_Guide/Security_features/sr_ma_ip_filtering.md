{
    "title": "IP filtering",
    "linkTitle": "IP filtering",
    "weight": "160"
}This section describes the IP filtering feature.

## About IP filtering

It is possible to filter incoming connections in the DMZ with the help of an IP address list, which can either be a:

-   Blacklist – allows everyone access, except for the partners contained in the list
-   Whitelist – authorize access only to the members in the list

The address that will be checked against the IP list is the remote socket address as seen on the Router Agent side. If an intermediary system which will change the partner's address (for example, a proxy) is present, IP filtering in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> should not be used.

The IP list consists of a semi-colon separated group of IP addresses (for example, 10.133.56.14; 10.\*.57.1?; support.axway.com; \*.axway.net; fe80::8923:fec5:91ae:2b3e). The allowed IP address types are:

-   IPv4 address in the well-known decimal dotted representation (RFC 820) with the possibility to specify wildcards. Two characters are allowed for wildcards: the star character ('\*') will replace an entire group (for example, 10.15.1.\* is equivalent to the range 10.15.1.1-10.15.1.255), whilst the question mark character ('?') will replace a single character (for example, 10.15.1.1?2 stands for the set 10.15.1.102, 10.15.1.112 to 10.15.1.192)
-   IPv6 address in the known hexadecimal long and short notations (RFC 5952) with the possibility of using wildcards as above. Ranges are accepted for both IPv4 and IPv6.
-   Hostnames (for example, machine-a2432)
-   Fully qualified domain names, in short FQDNs, (for example, support.axway.com), with the possibility to specify the star character ('\*') to replace one group (for example, \*.axway.com)

## Dynamic whitelist

Gateway can instruct <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Router Agent to create a list of IP addresses from accepted connections to listen points with Security Termination and Protocol Login. This feature is called the *dynamic whitelist*, in contrast to the *static whitelist* which requires user interaction.

-   the dynamic whitelist can only be built in blacklist operation mode. IP addresses are added as soon as the TLS/SSH handshake is performed and authentication is successful. As such, they are added to the list of valid partners.
-   Filtering using this list will work only in whitelist mode, in parallel with the existing static list for all listen points that have IP filtering switched on.
-   Not all SAPs (Service Access Points) can contribute to the creation of dynamic whitelist, but they can benefit from its filtering capabilities by simply having IP filtering enabled.

Currently, the only method to remove IP addresses from the dynamic whitelist is to restart the Router Agent.

## Lists and agents

By default, any IP address list (either whitelist or blacklist or even dynamic whitelist) is dedicated to each Master Agent, therefore:

-   if multiple Gateways are connected to the same Router Agent, each Master will have its own list on that Router Agent.
-   if one Gateway is connected to multiple Router Agents, then:
    -   the *whitelist* or *blacklist* will be *identical* on each Router
    -   the *dynamic whitelist*, will *differ* depending on what valid connections each Router Agent receives. This is because it depends on what valid connections each Router Agent receives.

## Performance considerations

The recommended IP address types are IPv4 or IPv6, ranges included, because they have the best filtering performance. Hostnames and FQDNs without wildcards are almost as fast, because the name resolution is performed once, at initialization.

On the other hand, wildcards for IPv4 and IPv6 and FQDNs are checked with Java regular expressions with lesser performance. Performance is even less for FQDNs because a reverse name resolution is required for each connection.

Related topics

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
