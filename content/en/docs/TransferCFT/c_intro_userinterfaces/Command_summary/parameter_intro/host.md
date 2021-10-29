{
    "title": "host",
    "linkTitle": "host",
    "weight": "1490"
}### <span id="host"></span>host

#### CFTNET, TYPE = TCP

\[HOST = string64\]

Networking IP address of the local resource. If you are defining a proxy, you may only enter one proxy host/port per CFTNET object.

You can enter up to 512 alphanumeric characters an address, which
can be either:

-   A real IP address in dot notation, for example 192.9.200.10, or
-   A logical name HOSTNAME associated with the real IP address and configured
    in the corresponding database file (HOST), supplied with the TCP/IP package

An address may either be expressed as an IP address (*nnn.nnn.nnn.nnn*
numerical format) or a host name.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The host field can specify IPv4 or IPv6:         </td>
      </tr>
   </tbody>
</table>

> CFTNET TYPE = TCP

> HOST = { string | INADDR\_ANY | IN6ADDR\_ANY | IN4ADDR\_ANY }

#### CFTCOM, TYPE = TCPIP

\[HOST = string64\]

Networking IP address of the local resource.

#### CFTTCP, TYPE = TCP

\[HOST = string512\]

Networking IP address for the local resource.

 

[Return to Command index](../)
