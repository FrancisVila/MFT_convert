{
    "title": "Setup N-th node in a cluster using multicast",
    "linkTitle": "Setup N-th node in a cluster using multicast",
    "weight": "200"
}To setup the N-th node in a cluster using multicast:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">Make sure you fulfill the following <a href="..//securetransport/appliance_guide/axway_appliance_san_card/setting_up_suse_linux_enterprise_ha_ocfs2">prerequisites</a>.         </td>
      </tr>
</table>

1.  Run `sleha-join`.
2.  Enter the alias for the first node. Be sure this alias is present in `/root/.ssh/config`.
3.  Enter the root password for the first node when prompted.
4.  Run `mount | grep ocfs2` to check if OCFS2 mount is present.

 

 

 
