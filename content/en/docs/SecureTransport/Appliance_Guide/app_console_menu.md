{
    "title": "Appliance console menu reference",
    "linkTitle": "Appliance console menu reference",
    "weight": "40"
}<span id="_Ref331672216"></span><span id="_Toc331683657"></span>To access the Appliance Console Menu, connect to the Console of your machine. Only connecting directly to the machine gives you complete control over the appliance. Console 1, the (blue) Appliance Console Menu, is the first screen you see when you power up the appliance.

The Appliance Console Menu consists of subpages, each with several options. The following table provides a quick reference for Appliance Console Menu options organized as they appear in the various subpages, and cross-references to other parts of this document where appropriate.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Console Menu Subpage         </th>
<th class="HeadD-Column1-Header1">Options         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Appliance Management</p>         </td>
         <td><p><strong>Reboot/Shut down System</strong> — Reboot or shutdown your appliance. See <a href="../appliancestartup_reboot_shutdown#_Toc331683654">Reboot or shut down the appliance</a> and <a href="../appliancestartup_reboot_shutdown#_Toc331683656">Shut down the appliance</a>.</p>
<p><strong>Clock/Timezone</strong> — Set the appliance clock and time zone. This is especially useful for clustered machines. See <a href="../manage_your_system#_Toc331683661">Set the clock and time zone</a> .</p>
<p><strong>Keyboard Layout</strong> — Select a language-based layout for your keyboard.</p>
<p><strong>System Log Files</strong> — Access your appliance's log files. See <a href="../manage_your_system#Work">Work with system log files</a>.</p>
<p><strong>Enable/Disable Independent Wallclock</strong> (<em>Amazon EC2 images only</em>) — Enable or disable time sync with the host server of the virtual appliance. When enabled, the virtual appliance will always perform time sync with the host server. The normal system time sync via NTP will have no effect. When disabled, the virtual appliance will not perform the time sync with the host server and will need another time sync method; for example, NTP.</p>         </td>
      </tr>
      <tr>
         <td><p>Hardening &amp; Security</p>         </td>
         <td><p><strong>Password Configuration</strong> — Specify rules for your appliance password. See <a href="../work_app_psswds#_Toc331683665">Manage the appliance password</a>.</p>
<p><strong>SuSEFirewall Management</strong> — Enable or disable firewall functionality and configure the firewall. See <a href="../config_network_access#_Toc331683662">Configure SuSEFirewall</a>.</p>
<p><strong>Linux Audit Framework</strong> — Enable or disable Linux audit framework functionality and configure the audit framework. See <a href="../configure_linux_audit">Configure Linux audit framework</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Network Settings</p>         </td>
         <td><p><strong>View Configuration</strong> — See the current network configuration on one screen.</p>
<p><strong>Set IP version</strong> — Choose between IPv4 and IPv6 and then specify options for that IP version. See <a href="../app_network_config#_Toc331683659">Configure network settings</a>.</p>
<ul>
<li><strong>Default Gateway</strong></li>
<li><strong>Network Interface</strong></li>
<li><strong>Static Routes</strong></li>
</ul>
<p><strong>Shared Folder Management</strong> — Choose from a list of options for viewing, exporting, and mounting shared folders. See <a href="../app_network_config/sharedfoldermanagement">Manage shared folders</a>.</p>
<p><strong>Hostname and Name Server</strong> — See <a href="../app_network_config#_Toc331683660">Configure network settings</a></p>
<p><strong>Edit Host Configuration</strong> — Choose from a list of hosts to configure, add a host or delete a host. See <a href="../app_network_config#Edit">Edit host configuration</a>.</p>
<strong>Proxy Configuration</strong> — Specify proxy information for HTTP, HTTPS, and FTP protocols. See <a href="../app_network_config#Configur">Configure proxies</a>.         </td>
      </tr>
      <tr>
         <td><p>Support Tools</p>         </td>
         <td><p><strong>Enable Remote Support</strong> — The appliance establishes a secure tunnel to Axway Global Support to be used to help troubleshoot complex issues. You must open port 22 outgoing in the firewall. This option requires a support code.</p>
<p><strong>Factory Network Reset</strong> — If you have incorrectly configured the network settings, this function resets them.</p>         </td>
      </tr>
   </tbody>
</table>
