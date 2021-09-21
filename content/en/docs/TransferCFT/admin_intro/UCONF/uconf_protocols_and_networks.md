{
    "title": "IPv6  options",
    "linkTitle": "IPv6  options",
    "weight": "330"
}# UCONF: IPv6 options

Transfer CFT provides support for both IPV4 and IPV6.

### Enable IPv6

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>ipv6.disable_connect</p>
         </td>
         <td>
            <p><b>No</b> indicates that an address or a name used by  <span>Transfer CFT</span> to connect to a host may be either an IPV4 or an IPV6 address. When using a name, this parameter can refer to a list of addresses, of any type.</p>
         </td>
      </tr>
      <tr>
         <td>ipv6.disable_listen         </td>
         <td>
            <p><b>No</b> indicates that an address or name used by  <span>Transfer CFT</span> to listen for incoming connections may be either an IPV4 or an IPV6 address. </p>
            <p>When using a name, this parameter can refer to a list of addresses, of any type.</p>
         </td>
      </tr>
      <tr>
         <td colspan="2">
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
   </tbody>
</table>

### Advanced IPv6

Refer to the [UCONF parameters](../uconf_directory) table ipv6.set\_ai\_xxx.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">It is recommended that you do <b>not</b> set<span> ipv6.disable_listen</span> to <span>No</span>, and <span>ipv6.disable_connect</span> to <span>Yes</span>.           </td>
      </tr>
</table>
