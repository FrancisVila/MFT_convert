{
    "title": "CFTNET  - Network resources",
    "linkTitle": "Network resources - CFTNET",
    "weight": "230"
}<span id="About_the_Generic_CFTNET_command"></span>You can use the CFTNET
command to define a network access resource. The available CFTNET network
is:

-   [TCI/IP](#Defining_TCP_IP__command_line_)

The example below is not an actual Transfer CFT command. It lists the
parameters which are common to all the network access methods.

The CFTNET TYPE = xxx commands are explained in the following Network
resources topics.

Related
topics

-   Command syntax
    [CFTNET](../../../command_summary#CFTNET)
-   Object concepts
    [Network resources
    concepts](../../../../admin_intro/admin_config_commands/network_resource_concepts)

#### Command parameters

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameters         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/call">CALL</a></p>         </td>
         <td><p>Call direction possible through this network resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/class">CLASS</a></p>         </td>
         <td><p>Logical class for the physical link.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a></p>         </td>
         <td><p>Network resource identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX </a></p>         </td>
         <td><p>Maximum number of simultaneous connections that Transfer
CFT will accept to establish on this network resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td><p>Defines the type of network resource.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_TCP_IP__command_line_"></span>

## Defining TCP/IP

This topic describes how to define the TCP/IP network resources object.
The CFTNET object for the TCP/IP type allows CFT to identify itself to
the TCP/IP access method Internet resource.

There can only be one resource for the TCP/IP type. However, you can
define a proxy type remote resource, linked to the local resource, that
allows access to another network.

Some parameters are common to all the CFTNET objects. These additional
parameters are not explained in this topic, but can be found in the generic
Defining network resources topic.

#### TYPE =  TCP

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">          </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><a href="../../../command_summary/parameter_intro/class">CLASS</a></p>         </td>
         <td><p>Class associated with this network resource.</p>
<p>This concept is used to group resources of the same type,
so that they can be used indifferently to establish connections with partners.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/host">HOST</a> </p>         </td>
         <td><p>IP address of the local resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX</a></p>         </td>
         <td><p>The maximum number of simultaneous connections
that Transfer CFT accepts to establish on a given network resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/call">CALL</a></p>         </td>
         <td><p>Call direction possible through this network
resource.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

Example



    CFTNET     MODE   =     
     CREATE,
         ID          =     
     TCP00,
         TYPE         =     
     TCP,
         HOST        =     
     localhost,
         MAXCNX     =     
     6,
         CALL       =     
     INOUT

Defines a resource on the "LOCALHOST" node, which corresponds
to the TCP/IP declaration of the local node. 6 simultaneous connections
may be opened. This resource accepts connections in both directions.

<span id="Defining_remote_TCP__command_line_"></span>

## Defining remote TCP

Access to a telecommunications network is defined by a CFTNET object.
Generally speaking, the resource used to access this network is local
to the system. A proxy is used to access a telecommunications network
via another network. It is considered to be a remote resource. This
section describes how to define the remote
TCP network resource.

Access to a telecommunications network via another network, remote access,
 is defined
by a:

-   CFTNET object describing
    access to the first network via a local resource
-   CFTNET object describing
    access to the second network via a remote resource - in this case, a proxy

The CFTNET object parameters vary, depending on whether the resource
is local or remote. For a local resource, the parameters remain unchanged.
For a remote resource, the parameters depend on the type of resource.

The HOST parameter is used only for incoming calls. For each CFTPROT
protocol definition on a CFTNET TCP/IP resource, only TCP connection requests
from interfaces matching the HOST parameter, and also matching the bound
port number, are accepted.

The keyword INADDR\_ANY that is assigned to the CFTNET card HOST parameter
has a specific meaning. TCP connection request from all
interfaces and matching the bound port number are accepted.

Use this command to access to a telecommunications network
via another network.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameters         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/class">CLASS</a></p>         </td>
         <td><p>Class associated with this network resource.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a></p>         </td>
         <td><p>Identifier of the network accessed via a proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> =
TCP</p>         </td>
         <td><p>The type of network accessed via a proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>INET</p>         </td>
         <td><p>Identifier of the CFTNET command defining access to the
first network.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/protocol">PROTOCOL</a> </p>         </td>
         <td><p>The proxy dialog protocol. Transfer CFT supports SOCKS4 and SOCKS5.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/host">HOST</a> </p>         </td>
         <td><p>Addresses of the proxies in the first network, with up to four
proxies in the same first network.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/port">PORT</a> </p>         </td>
         <td><p>Listening port of the proxy/proxies in the first network.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX</a></p>         </td>
         <td><p>Maximum number of concurrent connections that Transfer
CFT will establish with the proxy/proxies.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/user">USER</a></p>         </td>
         <td><p>User name transmitted in the connection request addressed
to the proxy.</p>
<p>This parameter is case-sensitive. By default, it is set
to the value of the user name in which Transfer CFT is being run.</p>         </td>
      </tr>
   </tbody>
</table>

For an example and proxy details, see [Transfers via
a Proxy and SOCKS protocol](../../../../protocols_start_here/ipv6/use_proxy_and_socks_protocol).
