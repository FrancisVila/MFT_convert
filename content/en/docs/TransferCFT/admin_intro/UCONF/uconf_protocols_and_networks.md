{
    "title": "UCONF: IPv6  options",
    "linkTitle": "IPv6  options",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> provides support for both IPV4 and IPV6.

### Enable IPv6

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ipv6.disable_connect</p>         </td>
         <td><p><strong>No</strong> indicates that an address or a name used by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to connect to a host may be either an IPV4 or an IPV6 address. When using a name, this parameter can refer to a list of addresses, of any type.</p>         </td>
      </tr>
      <tr>
         <td>ipv6.disable_listen         </td>
         <td><p><strong>No</strong> indicates that an address or name used by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to listen for incoming connections may be either an IPV4 or an IPV6 address.</p>
<p>When using a name, this parameter can refer to a list of addresses, of any type.</p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>It is recommended that you do <strong>not</strong> set<span class="code"> ipv6.disable_listen</span> to <span class="code">No</span>, and <span class="code">ipv6.disable_connect</span> to <span class="code">Yes</span>.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
   </tbody>
</table>

### Advanced IPv6

Refer to the [UCONF parameters](../uconf_directory) table <span class="code">ipv6.set\_ai\_xxx</span>.

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Default         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.ipv6.set_ai_numerichost</p>         </td>
         <td>Yes         </td>
         <td><ul>
<li><span class="bold_in_para">Yes</span>: Use when the host name is numeric to prevent the API system getaddrinfo from performing unnecessary DNS requests for numeric hostnames.</li>
<li><span class="bold_in_para">No</span>: Use DNS requests for all hostnames, including numeric.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cft.ipv6.set_ai_numericserv         </td>
         <td>Yes         </td>
         <td><ul>
<li><span class="bold_in_para">Yes</span>: Use when the service name is numeric (port number) to prevent the API system getaddrinfo from performing an unnecessary service name translation.</li>
<li><span class="bold_in_para">No</span>:</li>
</ul>         </td>
      </tr>
      <tr>
         <td>cft.ipv6.use_ipv4_legacy_resolver         </td>
         <td>No         </td>
         <td><ul>
<li><span class="bold_in_para">Yes</span>: Use legacy IPv4 only host and
service names resolution API, namely gethostbyname() and getservbyname().
This detects if the performance issue involves new
IPv6 specific material as configuration items, new system API implementation,
etc.</li>
<li><span class="bold_in_para">No</span>: Use IPv6 functionality.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>
