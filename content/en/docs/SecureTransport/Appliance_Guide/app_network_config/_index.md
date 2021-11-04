{
    "title": "Configure network settings",
    "linkTitle": "Configure your appliance network settings",
    "weight": "70"
}This topic provides instructions for setting appliance network configuration parameters.

<span id="Configur2"></span>

## Configure the network

Use the following procedures to configure the IP version, network interface card, boot protocol, default gateway, and static routes.

1.  Connect to the console. See <a href="#" class="MCXref xref">Configure network settings</a> for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **N**, Network Settings. The Network Settings menu is displayed.
3.  Set the IP version by pressing **4** to select IPv4, or **6** to select IPv6.
4.  Specify a default gateway. Type **G**, Default Gateway, and enter the IP address of the gateway.
5.  Type **I**, Network Interface.  
    The Network Interface Configuration menu appears on display.

<!-- -->

1.  If available, select the interface boot protocol. Press **T** for Static or **H** for DHCP.
2.  If you choose Static, press **I** to enter an IP address and **N** to enter a netmask.
3.  (Optional) Type **E** to delete the configuration file for the NIC you selected above.
4.  Press **S** to save your settings or **C** to cancel the operation.

<span id="Configur3"></span>

## Configure the DNS server address, host name, and domain name

1.  Connect to the console. The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **N**, Network Settings. The Network Settings menu is displayed.
3.  Type **H**, Hostname and Name Server.
4.  Enter the correct values for your network in the fields. Use the tab keys to navigate among fields and the arrow keys to navigate within fields.
5.  Press **F10** to save your changes. The Network Settings menu is displayed.

<span id="Edit"></span>

## Edit host configuration

Use the Host Configuration screen to add, edit, or delete host configurations.

1.  Connect to the console. The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **N**, Network Settings. The Network Settings menu is displayed.
3.  Type **E**, Edit Host Configuration.  
    The Host Configuration screen is displayed with your cursor in the list of current hosts.  
    Use the arrow keys to navigate within the list of hosts. Use the Tab key to navigate among buttons and fields on the screen. Use the Enter key to invoke highlighted commands.
4.  Add, edit, or delete host configurations as needed.

> **Note:**
>
> When configuring SecureTransport in a cluster environment, verify that the hosts file configuration is correct across all nodes.

<span id="Configur"></span>

## Configure proxies

Use the following procedure to configure the proxy settings for the operating system.

1.  Connect to the console. The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **N**, Network Settings.
3.  On the Network Settings menu, type **P**, Proxy Configuration.
4.  The Proxy Configuration page displays. On this screen, you use **Alt+&lt;key>** combinations to choose highlighted options. For example, **Alt+E** selects Enable Proxy.
5.  On the Proxy Configuration page, type **Alt+E** and then press Enter to enable the proxy and make the remaining fields on the page available.
6.  Use the Tab key to cycle through the fields on the page. Specify values for each of the following fields as necessary:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>HTTP Proxy URL</p>         </td>
             <td><p>Name of the HTTP proxy server</p>         </td>
          </tr>
          <tr>
             <td><p>HTTPS Proxy URL</p>         </td>
             <td><p>Name of the HTTPS proxy server</p>         </td>
          </tr>
          <tr>
             <td><p>FTP Proxy URL</p>         </td>
             <td><p>Name of the FTP proxy server</p>         </td>
          </tr>
       </tbody>
    </table>

<!-- -->

1.  *(optional)* Use the same proxy for all protocols. Type **Alt+a** to use the value you specified in the HTTP Proxy URL field for all protocols.
2.  *(optional)* Specify domains for which no proxies should be used. Type **Alt+D** to move the cursor to the No Proxy Domains field, and then enter the names or addresses for which there should be no proxies used.
3.  *(optional)* Specify a user name and password for proxy authentication. Type **Alt+U** and then enter a user name. Type **Alt+P** and then enter a password.
4.  *(optional)* Type **Alt+O** to test the proxy settings.
