{
    "title": "IPv6 support",
    "linkTitle": "IPv6 support",
    "weight": "150"
}Gateway is able to communicate over TCP IPv6 with remote peers. Gateway objects involved in configuring the transport phase of a transfer now accept IPv6 addresses. Partner definition remains unchanged with the only modification being in the network address field: an operator can configure an IPv6 address or a hostname that resolves into an IPv6 address. Network profiles and cgates/sgates filtering rules allow operators to define rules using the IPv6 address format. The same pattern matching rules as with IPv4 addresses can be used, with an asterisk "\*" replacing an entire group and a question mark "?" replacing a single character. The GUI provides default matching rules for all addresses. (These default matching patterns also act as a guideline on how filters can be defined).

Configuration has been extended to accept IPv6 interfaces for Gateway services (protocol configuration) with or without Secure Relay. The operator can configure the interface on the Router agent side on which the listening ports are to be established. This means that when combined with Secure Relay, Gateway continues to function only on IPv4 addresses and uses IPv6 only when connecting to the outside world via Secure Relay (any combination is supported).

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
