{
    "title": "Appliance console menu reference",
    "linkTitle": "Appliance console menu reference",
    "weight": "40"
}<span id="_Ref331672216"></span><span id="_Toc331683657"></span>To access the Appliance Console Menu, connect to the Console of your machine. Only connecting directly to the machine gives you complete control over the appliance. Console 1, the (blue) Appliance Console Menu, is the first screen you see when you power up the appliance.

The Appliance Console Menu consists of subpages, each with several options. The following table provides a quick reference for Appliance Console Menu options organized as they appear in the various subpages, and cross-references to other parts of this document where appropriate.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Console Menu Subpage</th>
         <th>Options</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>Appliance Management</p>
         </td>
         <td>
            <p><b>Reboot/Shut down System</b> — Reboot or shutdown your appliance. See <a href="../appliancestartup_reboot_shutdown">Reboot or shut down the appliance</a> and <a href="../appliancestartup_reboot_shutdown">Shut down the appliance</a>. </p>
            <p><b>Clock/Timezone</b> — Set the appliance clock and time zone. This is especially useful for clustered machines. See <a href="../manage_your_system">Set the clock and time zone </a>.</p>
            <p><b>Keyboard Layout</b> — Select a language-based layout for your keyboard.</p>
            <p><b>System Log Files</b> — Access your appliance's log files. See <a href="../manage_your_system">Work with system log files</a>.</p>
            <p><b>Enable/Disable Independent Wallclock</b> (<i>Amazon EC2 images only</i>) — Enable or disable time sync with the host server of the virtual appliance. When enabled, the virtual appliance will always perform time sync with the host server. The normal system time sync via NTP will have no effect. When disabled, the virtual appliance will not perform the time sync with the host server and will need another time sync method; for example, NTP.
                        </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Hardening &amp; Security</p>
         </td>
         <td>
            <p><b>Password Configuration</b> — Specify rules for your appliance password. See <a href="../work_app_psswds">Manage the appliance password</a>.</p>
            <p><b>SuSEFirewall Management</b> — Enable or disable firewall functionality and configure the firewall. See <a href="../config_network_access">Configure SuSEFirewall</a>.</p>
            <p><b>Linux Audit Framework</b> — Enable or disable Linux audit framework functionality and configure the audit framework. See <a href="../configure_linux_audit">Configure Linux audit framework</a>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Network Settings</p>
         </td>
         <td>
            <p><b>View Configuration</b> — See the current network configuration on one screen.</p>
            <p><b>Set IP version</b> — Choose between IPv4 and IPv6 and then specify options for that IP version. See <a href="../app_network_config">Configure network settings</a>.</p>
            <ul>
               <li><strong>Default Gateway</strong>
               </li>
               <li><strong>Network Interface</strong>
               </li>
               <li><strong>Static Routes</strong>
               </li>
            </ul>
            <p><b>Shared Folder Management</b> — Choose from a list of options for viewing, exporting, and mounting shared folders. See <a href="../app_network_config/sharedfoldermanagement">Manage shared folders</a>.</p>
            <p><b>Hostname and Name Server</b> — See <a href="../app_network_config">Configure network settings</a></p>
            <p><b>Edit Host Configuration</b> — Choose from a list of hosts to configure, add a host or delete a host. See <a href="../app_network_config">Edit host configuration</a>. </p><b>Proxy Configuration</b> — Specify proxy information for HTTP, HTTPS, and FTP protocols. See <a href="../app_network_config">Configure proxies</a>.
                             </td>
      </tr>
      <tr>
         <td>
            <p>Support Tools</p>
         </td>
         <td>
            <p><b>Enable Remote Support</b> — The appliance establishes a secure tunnel to Axway Global Support to be used to help troubleshoot complex issues. You must open port 22 outgoing in the firewall. This option requires  a support code.</p>
            <p><b>Factory Network Reset</b> — If you have incorrectly configured the network settings, this function resets them.</p>
         </td>
      </tr>
   </tbody>
</table>
