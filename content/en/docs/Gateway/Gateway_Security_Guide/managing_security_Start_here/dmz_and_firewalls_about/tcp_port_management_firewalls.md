{
    "title": "TCP port management with Firewalls",
    "linkTitle": "TCP port management with Firewalls",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Managing Security

[About TCP port management](#About)

[Support for multiple addresses](#Support_for_multiple_addresses)

[Assigning TCP origin port](#Assigning_TCP_origin_ports)

<span id="About"></span>

## About TCP port management

Gateway provides advanced port management features that ensure its compatibility with firewalls.

To use the TCP/IP network with a transfer protocol, you define the TCP/IP listener ports. You can declare or define single or multiple listening ports.

Define multiple listening ports as follows:

-   Assign different routing rules to a single user
-   Define access to specific clients on a specific port

<span id="Support_for_multiple_addresses"></span>

## Support for multiple addresses

If the Gateway host machine is connected to multiple TCP/IP networks, and is assigned more than one IP address, it may need to listen on multiple TCP/IP addresses (that correspond to a list of port numbers).

Gateway enables you to define the list of ports to use for a given TCP/IP address. When you define a Remote Site, you can attribute a main address and three alternative addresses in the **[Network address](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_network_address_tab)** tab.

<span id="Assigning_TCP_origin_ports"></span>

## Assigning TCP origin port

To force the use of specific origin ports for outgoing TCP connections, you define those ports in the file <span class="code">tcpoport.ini</span>. This file is located in<span class="code"> &lt;Gateway installation directory> \\runtime\\etc</span>.

Gateway bases its selection of the origin port on the destination address for the connection. If a connection request matches a pattern defined in<span class="code"> tcpoport.ini</span>, Gateway assigns the corresponding origin port to the connection. If Gateway does not find a match, the operating system assigns the origin port.

Each line of<span class="code"> tcpoport.ini</span> has the form:

dest\_ip dest\_ports: org\_ports

or:

! dest\_ip dest\_ports: org\_ports

where:

<span class="code">dest\_ip</span> = IP address (10.1.1.1), IP pattern (10.\*.\*.\*) or DNS name (machine.domain)

<span class="code">dest\_ports</span> = port number (21), port range (2200-2300) or any port (\*)

<span class="code">org\_ports</span> = port number (65001) or port range (65000-65100). Special port 0 is used to let the system choose the origin port.

The destination address is matched based on the parameters <span class="code">dest\_ip</span> and <span class="code">dest\_ports</span>. If both parameters match, the corresponding origin port is used. If one of them does not match, the rule is ignored.

If a line begins with an exclamation mark ( ! ), the rule matches any outgoing TCP connection that does not match the destination address or destination port. If you use a destination port of "\*" that is not preceded by the "!" character, the result could be unexpected behavior.

### Examples

The following examples use the local IP network  10.\*.\*.\* .

<span style="font-weight: bold;">Example 1:</span> If you only want to use origin ports between 42000 and 43000 for connections going out of your network, add the following line to the <span class="code">tcpoport.ini</span> file:

! 10.\*.\*.\*  \*:  42000-43000

<span style="font-weight: bold;">Example 2:</span> If you want to use origin ports between 64000 and 64100 for connection toward your local network (like in a DMZ), add the following line to the <span class="code">tcpoport.ini</span>:

10.\*.\*.\*  \*:  64000-64100

DNS names are resolved when needed and only if they have not been resolved in the previous five minutes.

Origin port assignment does not override FTP protocol specifications. Data connections triggered by the server (active mode) use origin port L-1 (with L the listening port).

Related topics

[Working with Remote Sites](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites)

[Working with Remote Sites (command line)](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
