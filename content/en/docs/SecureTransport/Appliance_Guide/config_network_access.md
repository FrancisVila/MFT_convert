{
    "title": "Configure your appliance firewall",
    "linkTitle": "Manage your appliance firewall",
    "weight": "80"
}Use the Appliance Console Menu to configure the firewall and proxy for the appliance.

<span id="_Toc331683662"></span>

## Configure SuSEFirewall

Use the following procedure to configure a firewall for your appliance.

1.  Connect to the console. See <a href="../appliancestartup_reboot_shutdown#_Ref331672216" class="MCXref xref">Reboot or shut down the appliance</a> for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **H**, Hardening & Security.
3.  On the Hardening & Security menu, type **S**, SuSEFirewall Management.
4.  On the SuSE Firewall Management menu, type **F**, SuSEFirewall Configuration.
5.  From the SuSE Firewall Configuration menu, use the arrow keys to move between sections in the menu on the left and the tab key to move between choices on the right. The SuSE Firewall Configuration menu is divided into the following sections:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Section         </th>
    <th class="HeadD-Column1-Header1">Details         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>Start-up</p>         </td>
             <td><p>Enable the Firewall to start as soon as the appliance powers up, or disable the Firewall so that it starts manually. In the box below the start-up box, you can also start or stop the Firewall manually.</p>         </td>
          </tr>
          <tr>
             <td><p>Interfaces</p>         </td>
             <td><p>Assign each network device attached to your appliance to the appropriate zone.</p>         </td>
          </tr>
          <tr>
             <td><p>Allowed Services</p>         </td>
             <td><p>Add servers and services to the list to allow the services to continue functioning. Listing them does create an exception in the Firewall protection. Unnecessary services should not be listed because this creates holes in the Firewall security.</p>
    <p>The Allowed Services menu item has an Advanced Option that allows you to enter port numbers to enable in the firewall zone.</p>         </td>
          </tr>
          <tr>
             <td><p>Masquerading</p>         </td>
             <td><p>Accept data from a source network and redirect it to another port by checking the Masquerade Networks box. Then, list both the source network and port in the Redirect Requests to the Masqueraded IP box.</p>         </td>
          </tr>
          <tr>
             <td><p>Broadcast</p>         </td>
             <td><p>Allow broadcasts from certain zones to reach your appliance. To accept broadcasts from a certain zone, uncheck the corresponding box.</p>         </td>
          </tr>
          <tr>
             <td><p>IPsec Support</p>         </td>
             <td><p>Activate IPsec to use virtual private networks or to specify security levels for employees who access the network remotely. Checking the box enables IPsec support.</p>         </td>
          </tr>
          <tr>
             <td><p>Logging Level</p>         </td>
             <td><p>Use the drop-down menus to select whether you want to log all, only the critical, or none of the accepted and non-accepted packets. Highlight the menu and press the down key to view the drop down menu, then select your desired logging style and press <strong>Enter</strong>.</p>         </td>
          </tr>
          <tr>
             <td><p>Custom Rules</p>         </td>
             <td><p>Add custom rules and protocol for a source network and its destination port.</p>         </td>
          </tr>
       </tbody>
    </table>

<!-- -->

1.  Once each section of the Firewall Configuration menu is set, a summary is displayed to confirm all changes. Type **Alt+F**, Finish, to complete the configuration.

For more information on configuration options, press **Alt+H** to open online Help.
