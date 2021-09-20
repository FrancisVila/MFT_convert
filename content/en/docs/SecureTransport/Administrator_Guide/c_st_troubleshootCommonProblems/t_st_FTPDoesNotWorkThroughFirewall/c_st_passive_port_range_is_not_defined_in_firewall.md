{
    "title": "Passive port range is not defined in the firewall",
    "linkTitle": "Passive port range is not defined in the firewall",
    "weight": "290"
}Configure the passive mode port range in your firewall if you are planning on using passive FTP. The passive range is defined on the SecureTransport Server and must be made available on the firewall. To set the passive range on the SecureTransport Server, open the SecureTransport Administration Tool and select **Setup &gt; FTP Settings**. Configure the port range in the *FTP Passive Mode* pane of the page.

Firewalls with no stateful inspection must make this port range explicitly available. Firewalls that support stateful inspection can define the port range dynamically. To ensure proper operation, the FTP control channel must not be encrypted. If you are using a third-party secure FTP client, use Clear Command Channel (CCC).

If you are using Axway Secure Client, you can use firewall-friendly Tunnel mode.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Because the <span>Axway</span> Secure Client firewall-friendly Tunnel mode uses SSL v3, you cannot use it for FTPS in FIPS transfer mode.         </td>
      </tr>
</table>

**Related topics:**

-   [Firewall rules prevent the port from opening](../c_st_firewall_rules_prevent_port_from_opening)
-   [Check Point firewall is not configured for bidirectional transfers](../c_st_checkpoint_firewall_is_not_configured_for_bidirectional_transfers)
