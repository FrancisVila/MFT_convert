{
    "title": "UCONF: IPv6  options",
    "linkTitle": "IPv6  options",
    "weight": "310"
}{{< TransferCFT/componentshortname  >}} provides support for both IPV4 and IPV6.

### Enable IPv6

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ipv6.disable_connect</p>         </td>
         <td><p><strong>No</strong> indicates that an address or a name used by {{< TransferCFT/componentshortname  >}} to connect to a host may be either an IPV4 or an IPV6 address. When using a name, this parameter can refer to a list of addresses, of any type.</p>         </td>
      </tr>
      <tr>
         <td>ipv6.disable_listen         </td>
         <td><p><strong>No</strong> indicates that an address or name used by {{< TransferCFT/componentshortname  >}} to listen for incoming connections may be either an IPV4 or an IPV6 address.</p>
<p>When using a name, this parameter can refer to a list of addresses, of any type.</p>         </td>
      </tr>
      <tr>
         <td><blockquote>
<p><strong>Note:</strong></p>
<p>It is recommended that you do not set ipv6.disable_listen to No, and ipv6.disable_connect to Yes.</p>
</blockquote>         </td>
      </tr>
   </tbody>
</table>

### Advanced IPv6

Refer to the [UCONF parameters](../uconf_directory) table `ipv6.set_ai_xxx`.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Default         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.ipv6.set_ai_numerichost</p>         </td>
         <td>Yes         </td>
         <td><ul>
<li><strong>Yes</strong>: Use when the host name is numeric to prevent the API system getaddrinfo from performing unnecessary DNS requests for numeric hostnames.</li>
<li><strong>No</strong>: Use DNS requests for all hostnames, including numeric.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cft.ipv6.set_ai_numericserv         </td>
         <td>Yes         </td>
         <td><ul>
<li><strong>Yes</strong>: Use when the service name is numeric (port number) to prevent the API system getaddrinfo from performing an unnecessary service name translation.</li>
<li><strong>No</strong>:</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cft.ipv6.use_ipv4_legacy_resolver         </td>
         <td>No         </td>
         <td><ul>
<li><strong>Yes</strong>: Use legacy IPv4 only host and
service names resolution API, namely gethostbyname() and getservbyname().
This detects if the performance issue involves new
IPv6 specific material as configuration items, new system API implementation,
etc.</li>
<li><strong>No</strong>: Use IPv6 functionality.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>
