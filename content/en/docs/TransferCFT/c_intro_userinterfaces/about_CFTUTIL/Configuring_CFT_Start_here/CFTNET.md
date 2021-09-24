{
    "title": "CFTNET - Network resources",
    "linkTitle": "CFTNET - Network resources",
    "weight": "400"
}# <span id="kanchor73"></span><span id="Defining_network_resources__command_line___Start_here"></span>CFTNET - Network resources

<span id="About_the_Generic_CFTNET_command"></span>You can use the CFTNET
command to define a network access resource. The available CFTNET network
is:

-   [TCI/IP](#defining_tcp_ip__command_line_)

The example below is not an actual Transfer CFT command. It lists the
parameters which are common to all the network access methods.

The CFTNET TYPE = xxx commands are explained in the following Network
resources topics.

Related
topics

-   Command syntax
    [CFTNET](../../../command_summary)
-   Object concepts
    [Network resources
    concepts](../../../../admin_intro/admin_config_commands/network_resource_concepts)

#### Command parameters

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/call">CALL</a>
</p>
         </td>
         <td>
            <p>Call direction possible through this network resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/class">CLASS</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Logical class for the physical link. </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network resource identifier.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX </a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of simultaneous connections that Transfer 
 CFT will accept to establish on this network resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Defines the type of network resource.</p>
         </td>
      </tr>
</table>

## <span id="Defining_TCP_IP__command_line_"></span>Defining TCP/IP

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

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th> </th>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="4">
            <p>Parameters</p>
         </td>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/class">CLASS</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Class associated with this network resource.</p>
            <p>This concept is used to group resources of the same type, 
 so that they can be used indifferently to establish connections with partners. 
 </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/host">HOST</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>IP address of the local resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The maximum number of simultaneous connections 
 that Transfer CFT accepts to establish on a given network resource. </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/call">CALL</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Call direction possible through this network 
 resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3" rowspan="1">
            <p> </p>
         </td>
      </tr>
   </tbody>
</table>

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTNET     MODE   =     
 CREATE,</p>
            <p>     ID          =     
 TCP00,</p>
            <p>     TYPE         =     
 TCP,</p>
            <p>     HOST        =     
 localhost,</p>
            <p>     MAXCNX     =     
 6,</p>
            <p>     CALL       =     
 INOUT</p>
         </td>
      </tr>
   </tbody>
</table>

Defines a resource on the "LOCALHOST" node, which corresponds
to the TCP/IP declaration of the local node. 6 simultaneous connections
may be opened. This resource accepts connections in both directions.

## <span id="Defining_remote_TCP__command_line_"></span>Defining remote TCP

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

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/class">CLASS</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Class associated with this network resource.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/id">ID</a>
</p>
         </td>
         <td>
            <p>Identifier of the network accessed via a proxy.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a> = 
 TCP</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The type of network accessed via a proxy.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="inet.htm">INET</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier of the CFTNET command defining access to the 
 first network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/protocol">PROTOCOL</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The proxy dialog protocol. Transfer CFT supports SOCKS4 and SOCKS5.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/host">HOST</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Addresses of the proxies in the first network, with up to four 
 proxies in the same first network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/port">PORT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Listening port of the proxy/proxies in the first network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/maxcnx">MAXCNX</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of concurrent connections that Transfer 
 CFT will establish with the proxy/proxies.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/user">USER</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User name transmitted in the connection request addressed 
 to the proxy.</p>
            <p>This parameter is case-sensitive. By default, it is set 
 to the value of the user name in which Transfer CFT is being run.</p>
         </td>
      </tr>
   </tbody>
</table>

For an example and proxy details, see [Transfers via
a Proxy and SOCKS protocol](../../../../protocols_start_here/ipv6/use_proxy_and_socks_protocol).
